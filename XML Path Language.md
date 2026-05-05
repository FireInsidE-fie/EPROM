---
tags:
  - language
abbreviation: XPATH
---
XML Path Language or XPATH is a **language for querying and/or modifying [[eXtensible Markup Language]] documents**.
It does this by representing XML documents as a tree that you can then walk through with specific expressions.
# Cheat Sheet
XPath expressions are **relative by default**, which means they start from the node the expression is being evaluated from.
## General Selection
```xpath
# Selects all nodes that are direct children of bookstore nodes under the current node
bookstore/book
# Selects from the root node, any direct book children of bookstore nodes
/bookstore/book
# Selects all nodes that are direct children of bookstore nodes throughout the document
//bookstore/book
# Selects book descendants of bookstore, wherever they are under bookstore
bookstore//book
# Selects the current node
.
# Selects the parent node of the current node
..
# Selects all attributes that are named lang
//@lang
```
## Predicates
Predicates are **great at isolating a specific node, often with a specific value**.
```xpath
# Selects all title nodes that have a lang attribute
//title[@lang]
# Selects all title nodes that have their lang attribute set to "en"
//title[@lang='en']
# Selects all title elements under a book that has a price higher than 35, under bookstore, starting from the root of the document
/bookstore/book[price>35.00]/title
```

# Resources
- [MDN Snippets Guide](https://developer.mozilla.org/en-US/docs/Web/XML/XPath/Guides/Snippets)
- [XPath Tester](https://extendsclass.com/xpath-tester.html)
- [XPath Syntax](https://www.w3schools.com/xml/xpath_syntax.asp)