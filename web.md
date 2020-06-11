# This is a note about HTML, CSS, and JavaScript

## Contents

### Usage of HTML
* Open a link in a new tab
```html
<a href="JavaScript.md" target="_blank">A JavaScript Note</a>
```
* Open a link in a new tab
```html
<a href="#C4">Go to chapter 4</a>

<h2><a id="C4">Chapter 4</a></h2>
```
### Usage of CSS
* overflow and float

```css
/* To clear the float */
.div_parent{
    overflow:hidden;
}

.div_parent .div_child{
    float:left;
}
```

* Flex layout
![Flex](images/flex.gif)
```css
.row {
    display: -ms-flexbox; /* IE10 */
    display: flex;
    -ms-flex-wrap: wrap; /* IE10 */
    flex-wrap: wrap;
}

.side {
    -ms-flex: 30%; /* IE10 */
    flex: 30%;
    background-color: #f1f1f1;
    padding: 20px;
}

.main {   
    -ms-flex: 70%; /* IE10 */
    flex: 70%;
    background-color: white;
    padding: 20px;
}
```

### Usage of JavaScript

* DateTime
```js
var today=new Date();
var h=today.getHours();
var m=today.getMinutes();
var s=today.getSeconds()
```

* Strings
```js
// reverse string
'abcd'.split('').reverse().join('') //"dcba"
```

* 

