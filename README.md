# SlidePanel

Javascript plugin to use a sliding panel that you can place wherever you need.

## Parameters and Functions

### place

*Default value* : right

Indicates where you want to display the panel. This value can be one of [top|left|right|bottom].

### body_slide

*Default value* : true

Indicates whether the body content will moved accordingly to the space used by the panel you open (unless the panel is full sized).

### no_scroll

*Default value* : false

Indicates whether you want to disable the scrolling effects when the panel is opened.

### auto_close

*Default value* : false

Indicates whether you want to close automatically the panel if the user clicks in the HTML content.

### animation_duration

*Default value* : 0.5s

Defines the duration of the animation. You can change the unit ('s') to a time unit valid.

### animation_curve

*Default value* : cubic-bezier(0.54, 0.01, 0.57, 1.03)

Defines the animation as a mathematic operation. Change this to whatever you need.

### toggle

*Default value* : '#sliderpanel-toggle'

Sets the id or class of the element that is used to open the panel by sliding.

### exit_selector

*Default value* : '.slider-exit'

Sets the id or class of the element that is used to close the panel if the auto close is not activated.

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

