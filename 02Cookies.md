<img width="369" height="428" alt="image" src="https://github.com/user-attachments/assets/f8df0daa-8c1a-4e44-9817-605b49276198" />

```
//GetCookieServlet.java
package com.servlets;

import jakarta.servlet.annotation.WebServlet;
import jakarta.servlet.http.*;
import java.io.IOException;

@WebServlet("/GetCookieServlet")
public class GetCookieServlet extends HttpServlet {

    protected void doGet(HttpServletRequest req, HttpServletResponse resp) throws IOException {
    	resp.setContentType("text/html");
        Cookie[] c = req.getCookies();
        String name = "No Cookie Found";

        if(c != null)
            for(Cookie x : c)
                if(x.getName().equals("username"))
                    name = x.getValue();

        resp.getWriter().println("<p>Welcome: " + name + "</p>");
    }
}
```


```
//SetCookieServlet.java
package com.servlets;

import jakarta.servlet.annotation.WebServlet;
import jakarta.servlet.http.*;
import java.io.IOException;

@WebServlet("/SetCookieServlet")
public class SetCookieServlet extends HttpServlet {

    protected void doPost(HttpServletRequest req, HttpServletResponse resp) throws IOException {
    	resp.setContentType("text/html");
        String name = req.getParameter("username");
        resp.addCookie(new Cookie("username", name));

        resp.getWriter().println("Cookie saved!");
    }
}
```


```
//index.html
<!doctype html>
<html>
<body>
  <h2>Cookie Demo</h2>

  <form action="SetCookieServlet" method="post">
    Username: <input type="text" name="username">
    <input type="submit" value="Set Cookie">
  </form>

  <p><a href="GetCookieServlet">Read Cookie</a></p>
</body>
</html>
```
