<img width="358" height="437" alt="image" src="https://github.com/user-attachments/assets/10b68ac9-34fb-4a5d-a969-441e4ba95a70" />

```
//URLRewrite1.java
package com.servlets;

import jakarta.servlet.annotation.WebServlet;
import jakarta.servlet.http.*;
import java.io.IOException;

@WebServlet("/URLRewrite1")
public class URLRewrite1 extends HttpServlet {

    protected void doGet(HttpServletRequest req, HttpServletResponse resp) throws IOException {

        resp.setContentType("text/html");

        String name = req.getParameter("uname");

        resp.getWriter().println("Data saved! <a href=\"URLRewrite2?uname=" + name + "\">Next</a>");
    }
}
```


```
//URLRewrite2.java
package com.servlets;

import jakarta.servlet.annotation.WebServlet;
import jakarta.servlet.http.*;
import java.io.IOException;

@WebServlet("/URLRewrite2")
public class URLRewrite2 extends HttpServlet {

    protected void doGet(HttpServletRequest req, HttpServletResponse resp) throws IOException {

        resp.setContentType("text/html");

        String name = req.getParameter("uname");

        resp.getWriter().println("<h2>Welcome: " + name + "</h2>");
    }
}
```


```
//index.html
<!DOCTYPE html>
<html>
<body>

<h2>URL Rewriting Demo</h2>

<form action="URLRewrite1">
    Name: <input type="text" name="uname">
    <input type="submit" value="Submit">
</form>

</body>
</html>
```
