Prefer Tomcat 10.1

<img width="380" height="428" alt="image" src="https://github.com/user-attachments/assets/b2c926d4-8414-43c1-9472-defc27003930" />

```
//LoggingFilter.java
package com.servlets;

import jakarta.servlet.*;
import jakarta.servlet.annotation.WebFilter;
import java.io.IOException;
import java.time.LocalDateTime;

@WebFilter("/WelcomeServlet")
public class LoggingFilter implements Filter {

    public void doFilter(ServletRequest req, ServletResponse res, FilterChain chain)
            throws IOException, ServletException {

        System.out.println("Request at: " + LocalDateTime.now());
        System.out.println("User: " + req.getParameter("user"));

        chain.doFilter(req, res); // pass to WelcomeServlet

        System.out.println("Response at: " + LocalDateTime.now());
    }
}
```


```
///WelcomeServlet.java
package com.servlets;

import jakarta.servlet.annotation.WebServlet;
import jakarta.servlet.http.*;
import java.io.IOException;
import java.io.PrintWriter;

@WebServlet("/WelcomeServlet")
public class WelcomeServlet extends HttpServlet {

    protected void doGet(HttpServletRequest req, HttpServletResponse res) throws IOException {

        res.setContentType("text/html");
        PrintWriter out = res.getWriter();

        String name = req.getParameter("user");
        if (name == null || name.trim().isEmpty())
            name = "Guest";

        out.println("<h3>Welcome, " + name + "!</h3>");
        out.println("<p>You passed through the LoggingFilter.</p>");
    }
}
```


```
//index.html
<!DOCTYPE html>
<html>
<body>

<h2>Filter Demo</h2>

<form action="WelcomeServlet">
    Enter Name: <input type="text" name="user">
    <button>Go</button>
</form>

</body>
</html>
```
