# FlexBox

## Getting Started with FlexBox

1. Place the following HTML in a file:

    ``` .html
    <div id="container">
    	<div class="box box1">1</div>
    	<div class="box box2">2</div>
    	<div class="box box3">3</div>
    	<div class="box box4">4</div>
    	<div class="box box5">5</div>
    	<div class="box box6">6</div>
    	<div class="box box7">7</div>
    </div>
    ```

2. Add these styles:

    ``` .css
    #container {
    	border: 1px solid darkred;
    	height: 100%;
    }
    .box {
    	font: 18pt sans-serif;
    	text-align: center;
    }
    .box1 { background-color: red; }
    .box2 { background-color: orange; }
    .box3 { background-color: yellow; }
    .box4 { background-color: forestgreen; }
    .box5 { background-color: dodgerblue; }
    .box6 { background-color: purple; }
    .box7 { background-color: violet; }
    ```

3. Now add `display: flex;` to the _container_ div. What happens?
   (Take a copy of your HTML file here - call it `justify.html`.
   We'll use it later.)
4. To have the items displayed proportionately, add `flex: 1;`
   to each _item_ (use the `box` class). What happens now?
   Resize your browser and notice how items grow and shrink automatically.

## Item Sizing

The `flex` property says “give each box 1 proportion of the whole space”.
Let's give Box 4 _two_ proportions:

1. Create a new rule for class `box4`, and give it a property `flex: 4;`.
   See how this affects the items in the browser.

## Recap

1. We laid the container out using _flex layout_:

	``` .css
	#container {
       display: flex;
   }
	```

2. We gave each item a proportion of the whole:

	``` .css
	.box {
       flex: 1;
   }
	```

3. We gave Box 4 two proportions:

	``` .css
	.box4 {
		flex: 2;
	}
	```
