# Selectors


## Reading and Understanding Selectors and Rules

What would these rules do?

1.

``` css
nav header {
  background-color: beige;
}
```


2.  

``` css
ul + p {
  color: red;
}
```


3.

``` css
#submission-panel > div {
  margin-left: 12em;
}
```

4.

``` css
form ~ p {
   font-size: smaller;
}
```

5.

``` css
a[title] {
   text-decoration: none;
}
```

6.

``` css
img:not([alt]) {
   border: 2px solid red;
}
```

7.

``` css
a[href^="http"] {
   background: url(images/external_link_font_awesome.svg) no-repeat;
   padding-left: 10px;
}
```


## Choosing Selectors

How would you target the following?

1. All `<div>`s that are direct children of a `<section>`.

2. Any `<h2>` that is preceded by an `<h1>` (any other elements can intervene).

3. Any `<h2>` that is _immediately_ preceded by an `<h1>`.

4. All anchors (`<a>`) that link to a `file://` URL.

5. All `<script>` elements that are inline (they don't refer to an external file).

6. Any user interface element (eg checkbox or radio button) that has been checked.

7. Any `<li>` that the mouse cursor is hovering over.

8. The fourth item in an unordered list.


## Extra Challenge

Think you know CSS? Challenge yourself at the [CSS Diner](http://flukeout.github.io/)
