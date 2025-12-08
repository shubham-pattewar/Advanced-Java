This repository contains 10 complete Java Web Technology experiments using Servlets, JSP, Filters, Sessions, Cookies, JDBC, MVC, and WebSockets.
Each experiment includes code, explanation, and execution steps.

✅ Experiment 1 — Basic Java Servlet: Request Handling

Uses HttpServlet to read request parameters and display output.

Files

RequestHandler.java 

01JavaServlet

index.html

Summary

A form sends name and email using GET. Servlet fetches parameters and prints them.

Learning Outcome

✔ Handling GET requests
✔ Using HttpServletRequest & HttpServletResponse

✅ Experiment 2 — Cookies in Servlets

Demonstrates setting and reading cookies.

Files

SetCookieServlet.java

GetCookieServlet.java

index.html


02Cookies

Summary

The user submits a username → servlet stores cookie → another servlet reads cookie.

Learning Outcome

✔ Cookie creation
✔ Cookie retrieval
✔ Persistent user state

✅ Experiment 3 — URL Rewriting

Shows how to pass data in URL when cookies are disabled.

Files

URLRewrite1.java

URLRewrite2.java

index.html


03URLRewriting

Summary

Servlet 1 stores data and forwards via URL query string → Servlet 2 prints value.

Learning Outcome

✔ Session tracking without cookies
✔ Encoding data in URLs

✅ Experiment 4 — HttpSession API

Uses HttpSession for server-side session tracking.

Files

SessionSetServlet.java

SessionGetServlet.java

index.html


04HttpSessionAPI

Summary

User enters name → stored in session → second servlet retrieves session value.

Learning Outcome

✔ Creating sessions
✔ Reading attributes
✔ Session ID

✅ Experiment 5 — Servlet Collaboration (RequestDispatcher)

Servlet-to-Servlet communication using forward().

Files

FirstServlet.java

SecondServlet.java

index.html


05ServletCollaboration

Summary

Form → First servlet (stores attribute) → forwards to second servlet → display result.

Learning Outcome

✔ Inter-servlet communication
✔ Using RequestDispatcher

✅ Experiment 6 — Servlet Filters

Demonstrates filters for logging or pre-processing.

Files

LoggingFilter.java

WelcomeServlet.java

index.html


06ServletFilters

Summary

Filter logs request before servlet execution and logs response afterward.

Learning Outcome

✔ Filter chain
✔ Pre/post servlet processing

✅ Experiment 7 — JSP Form Handling

Handles form submission inside a JSP page.

Files

index.jsp


07JSPFormHandling

Summary

JSP reads submitted name & email directly via scriptlets.

Learning Outcome

✔ JSP request parameter handling
✔ Mixing HTML + Java (scriptlets)

✅ Experiment 8 — JDBC + Servlet + JSP Database Insertion

Stores form data into MySQL database.

Files

DBServlet.java

index.jsp

SQL Schema


08DBServlet

Summary

Form → Servlet → JDBC → Inserts into studentdb.users.

Learning Outcome

✔ JDBC connection
✔ PreparedStatement usage
✔ Integration of JSP + Servlet + Database

✅ Experiment 9 — MVC Architecture (Model–View–Controller)

Implements proper MVC using Servlet (Controller), POJO (Model), and JSP (View).

Files

UserController.java

User.java

index.jsp

result.jsp


09MVCArchitecture

Summary

Form → Controller → Model object → Stored in request → View (JSP) displays data.

Learning Outcome

✔ Separation of concerns
✔ Model creation
✔ RequestDispatcher → JSP

✅ Experiment 10 — Real-Time Chat Using WebSockets

Implements a WebSocket-based multi-user chat room.

Files

index.jsp

chat.jsp

ChatServer.java


10ChatApplication

Summary

WebSocket endpoint broadcasts messages to all connected clients.

Learning Outcome

✔ WebSocket API
✔ Real-time communication
✔ Broadcasting messages

How to Run the Projects

Install Apache Tomcat 10.1+

Install JDK 17+

Import each experiment folder into Eclipse/IntelliJ

Add jakarta.servlet-api.jar (if not using Tomcat runtime)

For Experiment 8, install MySQL and run the SQL script

Deploy to Tomcat & run in browser

Technologies Used

Jakarta Servlets 5+

JSP

JDBC (MySQL)

WebSockets

HTML, CSS

Tomcat 10.1
