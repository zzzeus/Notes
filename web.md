# This is a note about HTML, CSS, and JavaScript

## Contents

### Usage of HTML

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

### USage of JavaScript


