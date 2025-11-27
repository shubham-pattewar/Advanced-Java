<img width="372" height="433" alt="image" src="https://github.com/user-attachments/assets/ed4ad0f6-9dd8-43f4-99f8-4ca9ccbba8e1" />


```
//SessionGetServlet.java
package com.servlets;

import jakarta.servlet.annotation.WebServlet;
import jakarta.servlet.http.*;
import java.io.IOException;

@WebServlet("/SessionGetServlet")
public class SessionGetServlet extends HttpServlet {

    protected void doGet(HttpServletRequest req, HttpServletResponse resp) throws IOException {

        resp.setContentType("text/html");

        HttpSession session = req.getSession(false);

        String name = "No Session Found";

        if (session != null)
            name = (String) session.getAttribute("username");

        resp.getWriter().println("<h2>Welcome: " + name + "</h2>");
    }
}

```


```
//SessionSetServlet.java
package com.servlets;

import jakarta.servlet.annotation.WebServlet;
import jakarta.servlet.http.*;
import java.io.IOException;

@WebServlet("/SessionSetServlet")
public class SessionSetServlet extends HttpServlet {

    protected void doPost(HttpServletRequest req, HttpServletResponse resp) throws IOException {

        resp.setContentType("text/html");

        String name = req.getParameter("username");

        HttpSession session = req.getSession();
        session.setAttribute("username", name);
        
        String id = session.getId();

        resp.getWriter().println("Session saved!<br>");
        resp.getWriter().println("Session ID: " + id + "<br><br>");
        resp.getWriter().println("<a href='SessionGetServlet'>Next</a>");
    }
}
```


```
//index.html
<!DOCTYPE html>
<html>
<body>

<h2>HttpSession Demo</h2>

<form action="SessionSetServlet" method="post">
    Username: <input type="text" name="username">
    <input type="submit" value="Start Session">
</form>

</body>
</html>
```


