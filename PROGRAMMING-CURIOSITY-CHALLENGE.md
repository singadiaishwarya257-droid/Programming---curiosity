# Programming Curiosity Challenge

The purpose of this challenge is to get you asking:

> “But how does this actually work?”

Don't search for answers immediately. Pick questions, discuss them with your team, make your own assumptions, and then find the real answer. The goal is not to memorize answers; it is to get comfortable investigating how software works.

The questions below are grouped to match this repository's folders and topic pages. Original question numbers are preserved so you can still refer to the original list. Some questions connect to more than one topic; they are listed with the closest starting point.

## 01 — Programming basics

### [Why programming?](01-programming-basics/why-programming.md)

1. What exactly is programming?
2. Why was programming invented?

### [Programming languages](01-programming-basics/programming-languages.md)

3. Why can't humans directly communicate with a computer?
4. How does a computer understand `if`, `for`, `while`, and `function`?
5. Who decides what a programming language can do?
6. Why are there hundreds of programming languages?
7. Why do we need Python, Java, JavaScript, C, C++, Go, Rust, and others?
8. What makes one programming language different from another?

## 02 — Variables and memory

### [Variables](02-variables-and-memory/variables.md)

11. What happens internally when you write `x = 10`?
13. Where is `x` stored?
14. Is `x` actually the value `10`?
15. What happens when you write:

    ```python
    x = 10
    x = 20
    ```

16. What happens to `10`?
17. What happens when you write `a = b = c = 100`?
18. Are `a`, `b`, and `c` three copies of `100`?
23. Where does a Python variable live?
24. What is a memory address?
25. Why can't we normally see memory addresses in Python?

### [Memory](02-variables-and-memory/memory.md)

12. Where is `10` stored?
21. What is RAM actually doing while your program runs?
22. What is the difference between RAM and storage?
30. What happens when your program consumes too much memory?

### [Stack and heap](02-variables-and-memory/stack-and-heap.md)

19. What happens to variables when a function finishes?
26. What is a stack?
27. What is a heap?

### [Garbage collection](02-variables-and-memory/garbage-collection.md)

20. Who cleans unused memory?
28. What is garbage collection?
29. Why doesn't unused memory remain forever?

## 03 — How programs run

### [Compilers](03-how-programs-run/compiler.md) and [interpreters](03-how-programs-run/interpreter.md)

9. Why does a programming language need a compiler or interpreter?
35. Where does the Python interpreter run?
36. How does Python read your `.py` file?
37. Does Python directly understand your source code?
38. What is bytecode?
39. What is the Python Virtual Machine?

### [Processes](03-how-programs-run/process.md)

31. Who receives the `python app.py` command?
32. How does the operating system know where Python is?
33. What is a process?
40. What happens when the program crashes?

### [Threads](03-how-programs-run/threads.md)

34. What is a thread?

## 04 — Internet

### [DNS](04-internet/dns.md)

41. What happens when you type `google.com` into a browser?
42. How does your computer find Google's server?
43. What is DNS?

### [IP addresses](04-internet/ip.md)

44. What is an IP address?
45. Why do we need ports?
49. How does your request travel thousands of kilometres?

### [HTTP](04-internet/http.md) and [HTTPS](04-internet/https.md)

46. What is HTTP?
47. Why was HTTPS created?
48. What happens when you click a button on a website?
50. How does the server know where to send the response?

## 05 — APIs

### [What is an API?](05-apis/what-is-api.md)

51. What exactly is an API?
52. Why can't two applications simply access each other's variables?

### [Request and response](05-apis/request-response.md)

53. What happens when a React application calls a Node.js or Python API?
54. What is a request?
55. What is a response?
56. Why do APIs commonly use JSON?
59. What happens if an API takes 10 seconds to respond?
60. What happens if the API server is completely down?
90. Can different programming languages communicate with each other?

### [REST APIs](05-apis/rest-api.md)

57. What are HTTP methods?
58. Why do we have `GET`, `POST`, `PUT`, `PATCH`, and `DELETE`?

## 06 — Databases

### [SQL databases](06-databases/sql.md)

61. Why can't we simply store everything in Python variables?
62. Why do applications need databases?
63. What happens when you click “Save”?
64. Where does the data physically go?
65. What is a table?
66. What is a row?
67. What is a column?
68. Why do we need primary keys?

### [Indexes](06-databases/indexes.md)

69. Why do we need indexes?

### [NoSQL databases](06-databases/nosql.md)

70. What is the difference between SQL and NoSQL?

### [Transactions](06-databases/transactions.md)

Rabbit-hole question 7: What happens if two users try to modify the same database record at exactly the same time?

## 07 — Security

### [Authentication](07-security/authentication.md)

71. How does a website know who you are after login?
72. Where is your password stored?
73. Why shouldn't passwords be stored as plain text?
79. What is a token?

### [Authorization](07-security/authorization.md)

78. How does a server know whether you are authorized?

### [Hashing](07-security/hashing.md)

75. What is hashing?

### [Encryption](07-security/encryption.md)

74. What is encryption?

### Related security questions without a dedicated page

These topics are part of security, but do not yet have their own pages. Start with the closest related guide:

76. What happens if someone changes an API request? See [request and response](05-apis/request-response.md) and [authorization](07-security/authorization.md).
77. What is CORS? See [request and response](05-apis/request-response.md); CORS is a browser security policy, not encryption.
80. How can one careless line of code expose millions of users? Start with [authorization](07-security/authorization.md) and [authentication](07-security/authentication.md).

## 08 — Cloud and deployment

### [Servers](08-cloud-and-deployment/server.md)

91. Where does your application actually run after deployment?
95. What is a server?
98. What happens when a server crashes?
100. If you had to build WhatsApp from scratch, what would you need?

### [Cloud computing](08-cloud-and-deployment/cloud.md)

96. What is cloud computing?
97. What is AWS or Azure actually providing?
Rabbit-hole question 5: When I upload a photo to Instagram, where does that photo actually go?
Rabbit-hole question 10: If the Internet disappeared tomorrow, which parts of your application would still work?

### [Scaling](08-cloud-and-deployment/scaling.md)

92. What happens when 1 user uses your application?
93. What changes when 1 million users use it?
94. Why can't we simply buy one huge computer?
99. How do Netflix, YouTube, or Instagram handle millions of users?
Rabbit-hole question 6: How can millions of people use the same application at the same time?

## 09 — Language comparisons

### [Python](09-language-comparisons/python.md)

81. Why is Python popular for AI?
89. Can Python call code written in C?

### [JavaScript](09-language-comparisons/javascript.md)

82. Why is JavaScript used in browsers?
83. Why is Node.js able to run JavaScript on servers?

### [Java](09-language-comparisons/java.md)

84. Why is Java still heavily used in enterprise applications?

### [Python vs JavaScript vs Java](09-language-comparisons/python-vs-javascript-vs-java.md)

85. Why is C still important?
86. Why is Rust becoming popular?
87. Is Python actually slower than Java?
88. Does “faster language” always mean “better language”?

## 10 — Rabbit holes

### [What happens when you run code?](10-rabbit-holes/what-happens-when-you-run-code.md)

10. What actually happens when you run a program?
Rabbit-hole question 2: When I type `python app.py`, what happens between pressing Enter and seeing the output?
Rabbit-hole question 8: How does a program know that another program has crashed?

### [What happens when you open Google?](10-rabbit-holes/what-happens-when-you-open-google.md)

Rabbit-hole question 3: When I enter `google.com`, how does my computer find another computer somewhere in the world?

### [How a login works](10-rabbit-holes/how-a-login-works.md)

Rabbit-hole question 4: When I click Login, how does my password travel from my phone to the server and come back as “Login successful”?

### Cross-topic rabbit holes

These questions span several chapters, so start with the linked pages and follow the connections:

1. When I type `x = 10`, where exactly does `10` go? Follow [variables](02-variables-and-memory/variables.md) → [memory](02-variables-and-memory/memory.md) → [processes](03-how-programs-run/process.md).
2. When I type `python app.py`, what happens between pressing Enter and seeing the output? Start with [what happens when you run code](10-rabbit-holes/what-happens-when-you-run-code.md).
3. When I enter `google.com`, how does my computer find another computer somewhere in the world? Start with [what happens when you open Google](10-rabbit-holes/what-happens-when-you-open-google.md).
4. When I click Login, how does my password travel from my phone to the server and come back as “Login successful”? Start with [how a login works](10-rabbit-holes/how-a-login-works.md).
5. When I upload a photo to Instagram, where does that photo actually go? Start with [cloud computing](08-cloud-and-deployment/cloud.md) and [servers](08-cloud-and-deployment/server.md).
6. How can millions of people use the same application at the same time? Start with [scaling](08-cloud-and-deployment/scaling.md).
7. What happens if two users try to modify the same database record at exactly the same time? Start with [transactions](06-databases/transactions.md).
8. How does a program know that another program has crashed? Start with [processes](03-how-programs-run/process.md).
9. If Python, JavaScript, and Java are completely different languages, how can they communicate with each other? Start with [request and response](05-apis/request-response.md) and [language comparisons](09-language-comparisons/python-vs-javascript-vs-java.md).
10. If the Internet disappeared tomorrow, which parts of your application would still work? Start with [cloud computing](08-cloud-and-deployment/cloud.md) and [servers](08-cloud-and-deployment/server.md).

## Ask seven questions whenever you learn something

Use this framework to investigate any new concept:

**WHY? → WHAT? → HOW? → WHERE? → WHEN? → WHO? → WHAT IF?**

For example, if you learn about MongoDB, don't stop at its name:

- **What** is MongoDB?
- **Why** do we use it?
- **How** does it store data?
- **Where** is the data physically stored?
- **When** should I choose MongoDB?
- **Who** uses it in the industry?
- **What if** MongoDB goes down?

A good programmer doesn't just learn answers. A good programmer develops better questions.
