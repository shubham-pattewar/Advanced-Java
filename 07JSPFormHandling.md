


```
//index.jsp

<%@ page contentType="text/html;charset=UTF-8" %>
<!DOCTYPE html>
<html>
<body>

<h2>JSP Form Handling</h2>

<form method="post">
    Name: <input type="text" name="name"><br><br>
    Email: <input type="text" name="email"><br><br>
    <input type="submit" value="Submit">
</form>

<%
    String name = request.getParameter("name");
    String email = request.getParameter("email");
%>

<h3>Submitted Details</h3>
<p>Name: <%= name %></p>
<p>Email: <%= email %></p>
</body>
</html>

```
