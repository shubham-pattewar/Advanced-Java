Database:
mysql 8.0 command line client

Java Connector jar file => in lib
https://dev.mysql.com/downloads/connector/j/

<img width="366" height="484" alt="image" src="https://github.com/user-attachments/assets/a8d7de06-ce2b-4be3-b4b6-d350d092be41" />


```
CREATE DATABASE studentdb;

USE studentdb;

CREATE TABLE users(
    id INT AUTO_INCREMENT PRIMARY KEY,
    name VARCHAR(100),
    email VARCHAR(100)
);

SELECT * FROM users;
```


```
// DBServlet.java
package com.servlets;

import jakarta.servlet.annotation.WebServlet;
import jakarta.servlet.http.*;
import java.io.IOException;
import java.io.PrintWriter;
import java.sql.*;

@WebServlet("/DBServlet")
public class DBServlet extends HttpServlet {

    protected void doPost(HttpServletRequest req, HttpServletResponse resp) throws IOException {

        resp.setContentType("text/html");
        PrintWriter out = resp.getWriter();

        String name = req.getParameter("name");
        String email = req.getParameter("email");

        try {
            Class.forName("com.mysql.cj.jdbc.Driver");
            Connection con = DriverManager.getConnection(
                "jdbc:mysql://localhost:3306/studentdb", "root", "root"
            );

            PreparedStatement ps = con.prepareStatement(
                "INSERT INTO users(name, email) VALUES(?, ?)"
            );

            ps.setString(1, name);
            ps.setString(2, email);

            ps.executeUpdate();

            out.println("<h3>Data Inserted Successfully!</h3>");

            con.close();

        } catch (Exception e) {
            out.println("<h3>Error: " + e.getMessage() + "</h3>");
        }
    }
}
```


```
//index.jsp

<%@ page contentType="text/html;charset=UTF-8" %>
<!DOCTYPE html>
<html>
<body>

<h2>Database Demo (JSP + Servlet)</h2>

<form action="DBServlet" method="post">
    Name: <input type="text" name="name"><br><br>
    Email: <input type="text" name="email"><br><br>
    <input type="submit" value="Save to DB">
</form>

</body>
</html>
```








