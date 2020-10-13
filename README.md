# SlidePanel

Javascript plugin to use a sliding panel that you can place wherever you need.

## Parameters and Functions

### place

*Default value* : right

Indicates where you want to display the panel. This value can be one of [top|left|right|bottom].

### body_slide

*Default value* : true

Indicates whether the body content will moved accordingly to the space used by the panel you open (unless the panel is full sized).

## **How to use it ?**

First of all, you must place a HTML element in the root layout inside of the body element.
This element can be one of these types :

* section
* article
* div
* nav

### Usage of HTML element

```html
<body>
<section id="*your id*" class="navigation-slide">
    <div class="ns-header-title">TITLE</div>
        <button class="ns-exit">
            <img src="/Images/Close.png" />
        </button>
    </div>
</section>
...
</body>
```

This example shows you how to create your HTML element. This element is the panel that will be displayed in the place you select in the JavaScript call.

### CSS

The example filled out below is an example and is not intended to be used as it in your code.

### JavaScript

