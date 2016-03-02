Among the various CSS lengths are lengths relative to the
[viewport](https://developer.mozilla.org/en-US/docs/Web/CSS/length#Viewport-percentage_lengths).
[Flexbox](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_Flexible_Box_Layout/Using_CSS_flexible_boxes)
is the go to rule for layouts these days, but viewport lengths have their use cases. Below is an
example using all of the viewport and placing content in the center of the viewport.


```html
<html>
    <head>
        <style>
            body {
                display: table-cell;
                height: 100vh;
                margin: 0;
                text-align: center;
                vertical-align: middle;
                width: 100vw;
            }
        </style>
    </head>
    <body>
        Content
    </body>
</html>
```
