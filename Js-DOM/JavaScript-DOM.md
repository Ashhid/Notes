<h1 style="text-align: center">JavaScript-DOM</h1>
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
- These can be used to make changes to the elements. let's suppose `textText`.
```js
const grabContainer = document.querySelector('.container');
const newh1 = document.createElement('h1');
newH1.innerText = "test";
grab.append(newH1);
```
- What this does it makes a new element `h1` and then creates a text with the content `test`.
- same with the other methods like `innerHTML` and `textContent`
---
#### Attribute Manipulation
---
attribute can be manipulated by adding, removing etc.

1. setAttribute():
	- this function, which is self-explanatory. it adds a attribute to a element.
	- `<name>.setAttribute(<attribute>,<value>)`
	- You can add  `class`, `id`, `style`.
```js
const grab = document.querySelector('ul');
const newLi = document.createElement('li');
const.append(newLi);
newLi.innerText = 'hello';
newLi.setAttribute('id','list-items');
console.log(newLi)
```
- this gives the output in the console as:
```html
<li class= "list-items"> hello </li>
```
- which makes complete sense.
---
2. .removeAttribute():
	- Again pretty self-explanatory. removes a attribute-name from existing element
	- `<name>.removeAttribute('<attribute-name>')`
```js
newElement.setAttribute('id', 'list-item');
newElement.removeAttribute('id')
```
---
3. .getAttribute():
	- This is not basically not an manipulation function
	- But this is useful for getting the value of the given attribute
```js
const grab = document.querySelector('list');
console.log(grab.getAttribute('id'));
```
- this will return the attribute value.
---
#### Class Manipulation
1. .classList.add():
	- This function is used for adding the new class to the element.
	- Yes a class name can be added with the `setAttribut` function too.
```js
const grab = document.querySelector('ul');
const newLi = document.createElement('li');
newLi.classList.add("list-items");
```
- This will add a new class name with `"list-items"`
---
2. .classList.remove():
	- This is of-course what it says. it's used for removing the class name.
	- This function can be achieved by the `.removeAttribute` too.
```js
newLi.classList.remove('list-items');
console.log(newLi.getAttribute('class'));
```
- We will get no output for this. Which means that there is no class name.
---
3. .classList.contains():
	- This is used for checking weather the class name is present or not.
	- This can be even achieved by the `.getAttribute` too.
```js
newLi.classList.add('list-items');
console.log(newLi.classList.contains('list-items'));
```
-  The output will be `true`. since it's a class for the `Newli`
---
- .remove(): 
	- This is used to remove a element from the document.
```js
const grab = document.querySelector('ul');
grab.remove();
console.log(grab);
```
- The output will be still
```html
<ul class = "list">
	<li>---</li>
	<li>---</li>
	<li>---</li>
</ul>
```
- The reason you're still getting an output after removing the `ul` element from the DOM is because the `console.log(grab)` statement is executed after the removal. When you call `console.log(grab)`, it logs the current state of the `grab` variable, which still contains a reference to the removed `ul` element. However, the element is no longer a part of the DOM.
- ---
#### Traversing The DOM
---
1. .parentNode:
	- This is used to find the father of the element.
	- Consider this html 
```html
<body>
	<div class="container">
		<ul>
			<li>Roxxane</li>
			<li>Baby</li>
		</ul>
	</div>
</body>
```
```js
let grab = document.querySelector("ul");
console.log(grab.parentNode);
```
- What this gives is a `father` element which is the `<div class="container"> ... </div>`
- Now let's suppose we want to access the `grandfather` element.
- So, what we now do it use the `parentNode` two times.
```js
console.log(grab.parentNode.parentNode);
```
- which will give the output of the `grandfather` element that is `<body>...</body>`
---
- We can use `parentElement`. for this same thing too.
```js
let grab = doument.querySelector('ul');
console.log(grab.parentElement);
//also
console.log(grab.parentElement.parentElement);
```
---
- We can see the difference of these both two is by running this piece of code
```js
const html = document.documentElement;
console.log(html.parentNode);
console.log(html.parentElement);
```
- output
```bash
#document
null
```
- What means here is that the `parentElement` returns the element. since there is no element here so, it returns `null` 
- the `parentNode` returns the `#document` is because the name `parentNode` is more self-explanatory, this returns a `node`.
---
#### Child Node Traversal
---
1. .childNodes:
	- This is used to return the child elements as a `nodeList`.
``` js
let grab = document.querySelector('ul')
console.log(grab.childNodes);
```
- So, the output will be like this.
```shell
NodeList(7) [text, li.list-items, text, li.list-items, text, li.list-items, text]
```
- The `text` here means that it's the indentation between the `<li>` elements.
---
2. .firstChild:
	- As the name say's it's used for selecting the first child element.
	- Here's how to do this.
```js
let grab = document.querySelector('ul');
console.log(grab.firstChild);
```
- output
```bash
#text
```
- This implies that the first element is going to be a `text` since there's a indentation in the HTML file.
- So, formatting / modifying this element, will mostly fail because as we discussed above that the `text` element is basically due to the indentation.
- To avoid this we can use the indexing method.
```js
let grab = document.querySelector('ul');
console.log(grab.childNodes[1]);
```
- Now this can be used for later modification.
---
- To, prevent this we can use one more thing which will only select the elements. 
---
3. .children
	- This is will only select the `valid elements`, instead of the all `nodes`.
```js
const grab = document.querySelector('ul');
console.log(grab.children)
```
- Output
```bash
HTMLCollection(3) [li.list-items, li.list-items, li.list-items]
```
- As we can see it just gave as the `HTMLCollection` of only the valid elements instead of giving the `NodeList` of all the components like `text`. which is annoying for later modification.
---
4. .firstElementChild :
	- For selecting the first child element. we can use this function.
	- This can be seen that the first element will be selected of `text`. This is because this function selects the first element.
```js
const grab = document.querySelector('ul');
console.log(grab.firstElementChild);
```
---
5. .lastElementChild:
	- Same as the above one but with the last element.
```js
const grab = document.querySelector('ul');
console.log(grab.lastElementChild);
```
---
6. .nextSiblings:
	- This function is used for finding the next element after the targeted element.
```js
const grab = document.querySelector('ul');
console.log(grab.nextSiblings);
```
- Output
```bash
#text
```
- The output is `#text` because of the indentation.
---
7. .previousSiblings:
	- This is the exactly the similar one as the top one but the difference is that, this selects the previous one instead of the next one.
```js
const grab = document.querySelector('ul');
console.log(grab.previousSiblings);
```
-  The output will be again `#text` due to the same reason.
---
8. .nextElementSiblings: 
	- This is exactly what we learned earlier. This is used for selecting the elements instead of the node.
```js
const grab = document.querySelector('ul');
console.log(grab.nextElementSiblings);
```
- Now this will not log a `text`. instead it will show the output of the previous element.
---
9. .previousElementSiblings:
	- This is used for selecting the previous element.
```js
const grab = documnet.querySelector('ul');
console.log(grab.previousElementSiblings);
```
--- 
