# Java Web Technology Experiments — Servlets, JSP, JDBC, MVC, WebSockets

This repository contains **10 complete Java Web Technology experiments** using **Servlets, JSP, Filters, Sessions, Cookies, JDBC, MVC, and WebSockets**.
Each experiment includes **source code, explanation, and execution steps**.

---

## 📂 Experiment List

---

## ✅ **Experiment 1 — Basic Java Servlet: Request Handling**

**Folder:** `01JavaServlet`
**Files:**

* `RequestHandler.java`
* `index.html`

**Summary:**
A simple HTML form sends *name* and *email* via GET. The servlet reads parameters and prints them.

**Learning Outcomes:**
✔ Handling GET requests
✔ Using `HttpServletRequest` & `HttpServletResponse`

---

## ✅ **Experiment 2 — Cookies in Servlets**

**Folder:** `02Cookies`
**Files:**

* `SetCookieServlet.java`
* `GetCookieServlet.java`
* `index.html`

**Summary:**
User submits a username → servlet stores it as a cookie → another servlet reads and displays it.

**Learning Outcomes:**
✔ Cookie creation
✔ Cookie retrieval
✔ Persistent user state

---

## ✅ **Experiment 3 — URL Rewriting**

**Folder:** `03URLRewriting`
**Files:**

* `URLRewrite1.java`
* `URLRewrite2.java`
* `index.html`

**Summary:**
Servlet 1 stores data and forwards it via URL query string → Servlet 2 reads and displays it.

**Learning Outcomes:**
✔ Session tracking without cookies
✔ Encoding data in URLs

---

## ✅ **Experiment 4 — HttpSession API**

**Folder:** `04HttpSessionAPI`
**Files:**

* `SessionSetServlet.java`
* `SessionGetServlet.java`
* `index.html`

**Summary:**
User enters name → stored in session → retrieved by second servlet.

**Learning Outcomes:**
✔ Creating sessions
✔ Setting & getting attributes
✔ Understanding Session ID

---

## ✅ **Experiment 5 — Servlet Collaboration (RequestDispatcher)**

**Folder:** `05ServletCollaboration`
**Files:**

* `FirstServlet.java`
* `SecondServlet.java`
* `index.html`

**Summary:**
Form → First servlet stores attribute → forwards to second servlet → displays final output.

**Learning Outcomes:**
✔ Servlet-to-servlet communication
✔ Using `RequestDispatcher.forward()`

---

## ✅ **Experiment 6 — Servlet Filters**

**Folder:** `06ServletFilters`
**Files:**

* `LoggingFilter.java`
* `WelcomeServlet.java`
* `index.html`

**Summary:**
Filter logs request before servlet runs, and logs response after servlet execution.

**Learning Outcomes:**
✔ Filter chain
✔ Pre-processing & post-processing

---

## ✅ **Experiment 7 — JSP Form Handling**

**Folder:** `07JSPFormHandling`
**Files:**

* `index.jsp`

**Summary:**
JSP page reads form inputs using scriptlets and displays them.

**Learning Outcomes:**
✔ Accessing request parameters in JSP
✔ Mixing Java + HTML (scriptlets)

---

## ✅ **Experiment 8 — JDBC + Servlet + JSP Database Insertion**

**Folder:** `08DBServlet`
**Files:**

* `DBServlet.java`
* `index.jsp`
* `SQL Schema`

**Summary:**
Form → Servlet → JDBC → inserts data into `studentdb.users` table.

**Learning Outcomes:**
✔ JDBC connection setup
✔ Using `PreparedStatement`
✔ Integration of JSP + Servlet + Database

---

## ✅ **Experiment 9 — MVC Architecture (Model–View–Controller)**

**Folder:** `09MVCArchitecture`
**Files:**

* `UserController.java`
* `User.java` (Model)
* `index.jsp`
* `result.jsp`

**Summary: **
Form → Controller → Model → forwarded to JSP View.

**Learning Outcomes:**
✔ Separation of concerns
✔ Passing model objects
✔ Using `RequestDispatcher` with JSP Views

---

## ✅ **Experiment 10 — Real-Time Chat Application Using WebSockets**

**Folder:** `10ChatApplication`
**Files:**

* `ChatServer.java`
* `index.jsp`
* `chat.jsp`

**Summary:**
A multi-user chat room using WebSocket API. Messages broadcast to all connected clients.

**Learning Outcomes:**
✔ WebSocket endpoint
✔ Real-time communication
✔ Broadcasting to all sessions

---

# 🚀 How to Run All Experiments

1. Install **Apache Tomcat 10.1+**
2. Install **JDK 17+**
3. Import each experiment folder into **Eclipse** or **IntelliJ**
4. Add dependency (if required):

   ```
   jakarta.servlet-api.jar
   ```
5. For Experiment 8:

   * Install **MySQL**
   * Run the provided SQL script
6. Deploy project to Tomcat
7. Open browser and run the experiment URLs

---

# 🛠 Technologies Used

* **Jakarta Servlets 5+**
* **JSP**
* **JDBC (MySQL)**
* **MVC architecture**
* **WebSockets**
* **HTML & CSS**
* **Apache Tomcat 10.1**

---

