![[DOM Tree.png]]
- This is a diagram of a document tree.
- The diagram is in a tree format with the root node begin "Document".
- The tree has three levels
- The first level ahs one node "Element `<head>`" & "Element `<body>`"
---
##### DOM Manipulation

```Javascript
GetElementById();
GetElementByClassName();
GetElementByTagName();
querySelector();
querySelectorAll();
```
---
1. GetElementById():
	- This is used for selecting a ID from the `HTML` tag
	- like `<div id="hello">` to select this we can use the query
```Js
const title = document.getElementById('hello');
```
---

2. GetElementByClassName():
	- This is used for selecting a class from the `html` tag
	- like `<div class="hello"` to select this we can use the query.
```Js
const title = document.getElementByClassName('hello');
```
1. GetElementByTagName(): 
	- This query allows you to select and retrieve HTML elements with the specified tag name as an HTML Collection object.
```js
	const
```