<img width="375" height="479" alt="image" src="https://github.com/user-attachments/assets/b0dcd102-3c14-4033-9e74-511e9c956337" />

```
//UserController.java
package com.controller;

import com.model.User;
import jakarta.servlet.*;
import jakarta.servlet.annotation.WebServlet;
import jakarta.servlet.http.*;
import java.io.IOException;

@WebServlet("/UserController")
public class UserController extends HttpServlet {

    protected void doPost(HttpServletRequest req, HttpServletResponse resp)
            throws ServletException, IOException {

        String name = req.getParameter("name");
        String email = req.getParameter("email");

        // Create Model object
        User user = new User(name, email);

        // Store model in request scope
        req.setAttribute("userdata", user);

        // Forward to View
        RequestDispatcher rd = req.getRequestDispatcher("result.jsp");
        rd.forward(req, resp);
    }
}
```


```
//User.java
package com.model;

public class User {
    private String name;
    private String email;

    public User() {}

    public User(String name, String email) {
        this.name = name;
        this.email = email;
    }

    public String getName() { return name; }
    public String getEmail() { return email; }

    public void setName(String name) { this.name = name; }
    public void setEmail(String email) { this.email = email; }
}
```



```
//index.jsp
<!DOCTYPE html>
<html>
<body>

<h2>MVC Demo - Input Form</h2>

<form action="UserController" method="post">
    Name: <input type="text" name="name"><br><br>
    Email: <input type="text" name="email"><br><br>
    <input type="submit" value="Submit">
</form>

</body>
</html>
```


```
//result.jsp
<%@ page language="java" contentType="text/html; charset=UTF-8"
    pageEncoding="UTF-8" import="com.model.User" %>
<!DOCTYPE html>
<html>
<head>
<meta charset="UTF-8">
<title>Insert title here</title>
</head>
<body>
	<h2>MVC Demo - Result Page</h2>

<%
    User u = (User) request.getAttribute("userdata");
%>

<p>Name: <%= u.getName() %></p>
<p>Email: <%= u.getEmail() %></p>
</body>
</html>
```
