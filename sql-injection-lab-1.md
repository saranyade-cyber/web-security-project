# writeup: SQL Injection Vulnerability in WHERE Clause

### the goal
The objective of this lab was to exploit a SQL injection vulnerability in the product 
category filter of a shopping website to make the application display hidden and 
unreleased products that are normally restricted from public view.

### Where the input was (Parameter)
The vulnerable input was located in the `category` GET parameter within the URL path 
(`/filter?category=Gifts`).

### What Payload worked
The payload that successfully exploited the vulnerability was:
`Gifts' OR 1=1--`

### Why did it work
The input parameter was directly concatenated into a backend SQL query string without 
sanitization. Adding the single quote (`'`) closed the category string literal early, 
`OR 1=1` and then added an always true condition that bypassed the category check entirely 
and the double dash (`--`) commented out the remainder of the query, removing the 
`AND released = 1` constraint.

### How to fix
To prevent this vulnerability, the application must avoid dynamic string concatenation 
and implement parameterized queries (prepared statements). Using prepared statements 
ensures the database treats user input strictly as data rather than executable code and
hence, neutralizing any malicious logic.

<img width="1122" height="631" alt="image" src="https://github.com/user-attachments/assets/2d12ac60-e547-469f-93a9-1be560ddb499" />
