---
title: N-Queens Problem
author: Andreas Hernández Hauser
---

A simple implementation of the N-Queens Problem using Genetic Algorithms to find a solution.

An example of a standard sized (8x8) chess board with 8 queens placed on it without conflicts with each other:

~~~text
╔════╤════╤════╤════╤════╤════╤════╤════╗
║    │    │    │    │    │ 00 │    │    ║
╟────┼────┼────┼────┼────┼────┼────┼────╢
║ 00 │    │    │    │    │    │    │    ║
╟────┼────┼────┼────┼────┼────┼────┼────╢
║    │    │    │    │ 00 │    │    │    ║
╟────┼────┼────┼────┼────┼────┼────┼────╢
║    │ 00 │    │    │    │    │    │    ║
╟────┼────┼────┼────┼────┼────┼────┼────╢
║    │    │    │    │    │    │    │ 00 ║
╟────┼────┼────┼────┼────┼────┼────┼────╢
║    │    │ 00 │    │    │    │    │    ║
╟────┼────┼────┼────┼────┼────┼────┼────╢
║    │    │    │    │    │    │ 00 │    ║
╟────┼────┼────┼────┼────┼────┼────┼────╢
║    │    │    │ 00 │    │    │    │    ║
╚════╧════╧════╧════╧════╧════╧════╧════╝
~~~

An example of a 16x16 sized chess board with 16 queens placed on it without conflicts with each other:

~~~text
╔════╤════╤════╤════╤════╤════╤════╤════╤════╤════╤════╤════╤════╤════╤════╤════╗
║    │    │    │    │    │    │    │    │    │    │    │    │    │    │    │ 00 ║
╟────┼────┼────┼────┼────┼────┼────┼────┼────┼────┼────┼────┼────┼────┼────┼────╢
║    │    │    │    │    │    │    │    │ 00 │    │    │    │    │    │    │    ║
╟────┼────┼────┼────┼────┼────┼────┼────┼────┼────┼────┼────┼────┼────┼────┼────╢
║    │    │    │    │    │    │    │    │    │    │ 00 │    │    │    │    │    ║
╟────┼────┼────┼────┼────┼────┼────┼────┼────┼────┼────┼────┼────┼────┼────┼────╢
║    │    │    │ 00 │    │    │    │    │    │    │    │    │    │    │    │    ║
╟────┼────┼────┼────┼────┼────┼────┼────┼────┼────┼────┼────┼────┼────┼────┼────╢
║    │ 00 │    │    │    │    │    │    │    │    │    │    │    │    │    │    ║
╟────┼────┼────┼────┼────┼────┼────┼────┼────┼────┼────┼────┼────┼────┼────┼────╢
║    │    │    │    │    │    │    │    │    │    │    │ 00 │    │    │    │    ║
╟────┼────┼────┼────┼────┼────┼────┼────┼────┼────┼────┼────┼────┼────┼────┼────╢
║    │    │    │    │ 00 │    │    │    │    │    │    │    │    │    │    │    ║
╟────┼────┼────┼────┼────┼────┼────┼────┼────┼────┼────┼────┼────┼────┼────┼────╢
║    │    │    │    │    │    │ 00 │    │    │    │    │    │    │    │    │    ║
╟────┼────┼────┼────┼────┼────┼────┼────┼────┼────┼────┼────┼────┼────┼────┼────╢
║    │    │    │    │    │    │    │    │    │    │    │    │    │ 00 │    │    ║
╟────┼────┼────┼────┼────┼────┼────┼────┼────┼────┼────┼────┼────┼────┼────┼────╢
║    │    │ 00 │    │    │    │    │    │    │    │    │    │    │    │    │    ║
╟────┼────┼────┼────┼────┼────┼────┼────┼────┼────┼────┼────┼────┼────┼────┼────╢
║    │    │    │    │    │    │    │    │    │    │    │    │ 00 │    │    │    ║
╟────┼────┼────┼────┼────┼────┼────┼────┼────┼────┼────┼────┼────┼────┼────┼────╢
║    │    │    │    │    │    │    │    │    │    │    │    │    │    │ 00 │    ║
╟────┼────┼────┼────┼────┼────┼────┼────┼────┼────┼────┼────┼────┼────┼────┼────╢
║    │    │    │    │    │    │    │ 00 │    │    │    │    │    │    │    │    ║
╟────┼────┼────┼────┼────┼────┼────┼────┼────┼────┼────┼────┼────┼────┼────┼────╢
║    │    │    │    │    │ 00 │    │    │    │    │    │    │    │    │    │    ║
╟────┼────┼────┼────┼────┼────┼────┼────┼────┼────┼────┼────┼────┼────┼────┼────╢
║ 00 │    │    │    │    │    │    │    │    │    │    │    │    │    │    │    ║
╟────┼────┼────┼────┼────┼────┼────┼────┼────┼────┼────┼────┼────┼────┼────┼────╢
║    │    │    │    │    │    │    │    │    │ 00 │    │    │    │    │    │    ║
╚════╧════╧════╧════╧════╧════╧════╧════╧════╧════╧════╧════╧════╧════╧════╧════╝
~~~
