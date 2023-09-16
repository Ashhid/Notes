s<h1 style="text-align: center">JavaScript-DOM</h1>
<hr>
<marquee style="font-size: 20px">Accessing the tags in HTML</marquee>
<hr>

```markdown
Document
└── Element <html>
    ├── Element <head>
    │   ├── Element <title>
    │   └── Class Attribute "className"
    └── Element <body>
        ├── Element <h1>
        └── Element <p>

```
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
---

2. GetElementByTagName(): 
	- This query allows you to select and retrieve HTML elements with the specified tag name as an HTML Collection object.
	- Returns `HTMLCollection`.
```js
	const listItems = document.getElementsByTagName('li');
	//returns HTMLCollection.
```
---
3. querySelector():
	- What is does is that it selects the tags with the first item which that matches
```js
const container = document.querySelector('div');
//returns only the first item that matches
```
---
4. querySelectorAll():
	- This is exactly the same as `querySelectorAll()` but we did notice that the above query only selects top most one.
	- But this one instead selects everything, which matches
	- Returns a `NodeList`.
```js 
const container = document.querySelectorAll('div');
//returns all the div's that matches in th html file.
```
---
#### Styling an Element
---
- This is used for making the making a single `CSS` query inside of `Js`.
- note that `CSS` property uses `snake-case` but in `Js` we use  `camel-case`
- This will not work with `querySelectorAll`. It'll throw a `cannot set properties of undefined` error. Since the return type of `querySelectorAll` is a `HTMLCollection`.
```js
const grab = document.querySelector('h1')
grab.style.fontSize = '10px';
```
Incase if you want to do we can. use a for loop for it.
```js
for (i = 0; i < grab.length; i++){
	grab[i].style.fontSize = '10px';
}
```
---
#### Creating a Elements
---
- To add a new element into a container we use the `append` function.
- The format is `<container>.append(<newElement>)`.
```js
//here this "grab" is for the container we want to include the new element.
const grab = document.querySelector('div.lol');

//now we create a new element variable.
const addNewH1 = document.createElement('h1');

//append to the container.
grab.append(addNewH1);
```
---
#### Modifying The Text
---
- Consider this HTML File:
```html
<ul>
	<li>
		<span> Neo </span>
		The Matrix
	</li>
</ul>
```
--- 
1. innerText:
	- This is used for returning the whole content inside of the container
```js
const grab = document.querySelector('.list');
console.log(grab.innerText);

//output 
Neo The matrix
```
---
2. innerHTML:
	- As the name says, it returns a content with the original HTML. 
```js
const grab = document.querySelector('.list');
console.log(grab.innerHTML);

//output
<span>Neo</span>
The matrix
```
---

3. textContent:
	- It returns all the text within an element, including that may be hidden or styled to or not.
```js
const grab = document.querySelector('.list');
console.log(grab.textContent);

//output
Neo
The Matrix
```
---
