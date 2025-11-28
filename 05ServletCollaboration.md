<img width="386" height="429" alt="image" src="https://github.com/user-attachments/assets/cc6c3967-8e37-42c9-85d6-cb3f22b8461e" />

```
//FirstServlet.java
package com.servlets;

import jakarta.servlet.annotation.WebServlet;
import jakarta.servlet.http.*;
import jakarta.servlet.RequestDispatcher;
import jakarta.servlet.ServletException;

import java.io.IOException;

@WebServlet("/FirstServlet")
public class FirstServlet extends HttpServlet {

    protected void doPost(HttpServletRequest req, HttpServletResponse resp) throws IOException, ServletException {

        resp.setContentType("text/html");

        String name = req.getParameter("username");
        req.setAttribute("myname", name);   // store value

        RequestDispatcher rd = req.getRequestDispatcher("SecondServlet");
        rd.forward(req, resp);  // servlet collaboration
    }
}

```


```
//SecondServlet.java
package com.servlets;

import jakarta.servlet.annotation.WebServlet;
import jakarta.servlet.http.*;
import java.io.IOException;

@WebServlet("/SecondServlet")
public class SecondServlet extends HttpServlet {
	// No URL Rewriting

    protected void doGet(HttpServletRequest req, HttpServletResponse resp) throws IOException {

        resp.setContentType("text/html");

        String name = (String) req.getAttribute("myname");

        resp.getWriter().println("<h2>Welcome: " + name + "</h2>");
    }

    protected void doPost(HttpServletRequest req, HttpServletResponse resp) throws IOException {
        doGet(req, resp);   // handle both
    }
}
```


```
//index.html
<!DOCTYPE html>
<html>
<body>

<h2>Servlet Collaboration Demo</h2>

<form action="FirstServlet" method="post">
    Name: <input type="text" name="username">
    <input type="submit" value="Submit">
</form>

</body>
</html>
```
