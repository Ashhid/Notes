*`This is based on the video from` [Slaying the Dragon](https://www.youtube.com/watch?v=EiNiSFIPIQE&list=PPSV)* 


---
##### Let's consider a container with the classes of div.'s of gird


```html
<div class="container">
	<div class="grid-1"></div>
	<div class="grid-2"></div>
	<div class="grid-3"></div>
</div>
```
---
- To Toggle the grid mode to a div (here Container). We add a CSS Rule `display: grid` to it.
- To assign how many columns and rows we need. we use `grid-template-columns.` and `grid-template-rows.`
	- As we if `100px` twice is added it means that there are 2 `100px` columns. the same with the rows too.
```css
.container {
  display: grid;
  grid-template-columns: 100px 100px 100px 100px 100px 100px;
  grid-template-rows: 100px 100px 100px 100px 100px 100px;
}
```
- If I want to position an item, we apply these rules
	- The rules are very straight forward as you can see `grid-column-start` & `grid-row-start` means it's the location of the column or rows starting and `grid-column-end` & `grid-row-end` means that's it's the location of the ending columns or rows.
```css
.grid-1{
	grid-column-start: ;
	grid-column-end: ;
	grid-row-start: ;
	grid-row-end: ;
}
```
- Writing this much ain't efficient so there is a short-hand method which is more convenient.
- This method involves using the rule `grid-row` and `grid-column`. 
- The start value and the end value is separated by a `/` 
```css
.grid-1{
	grid-row: 1/3;
	grid-column: 2/4; 
}
/**/
```
> *Here as we can see that the start value of `grid-row` is `1` and the end value is `3`*
> *Similarly for the `grid-column` the start value is `2` and the end value is `4`*

