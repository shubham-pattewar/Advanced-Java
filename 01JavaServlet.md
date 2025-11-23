<img width="380" height="405" alt="image" src="https://github.com/user-attachments/assets/99123234-abeb-496e-8472-210fe4640e39" />


```
// RequestHandler.java


package com.servlets;
import jakarta.servlet.ServletException;
import jakarta.servlet.annotation.WebServlet;
import jakarta.servlet.http.HttpServlet;
import jakarta.servlet.http.HttpServletRequest;
import jakarta.servlet.http.HttpServletResponse;
import java.io.IOException;
import java.io.PrintWriter;

@WebServlet("/RequestHandler")
public class RequestHandler extends HttpServlet {

	protected void doGet(HttpServletRequest request, HttpServletResponse response) throws ServletException, IOException {
		response.setContentType("text/html");
		
		String name = request.getParameter("uname");
		String email = request.getParameter("uemail");
		
		PrintWriter out = response.getWriter();
		out.println("<h2>Details Received </h2>");
		out.println("Name: " + name + "<br>");
		out.println("Email: " + email);
	}
}
```

```

// index.html
<!DOCTYPE html>
<html>
<head>
<meta charset="UTF-8">
<title>Insert title here</title>
</head>
<body>
	<h2>Enter Details</h2>
	<form action="RequestHandler" method = "get">
		Name: <input type = "text" name = "uname">
		Email: <input type = "email" name = "uemail">
		<input type = "submit" value = "Submit">
	</form>
</body>
</html>

```
