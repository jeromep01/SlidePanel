# SlidePanel

Javascript plugin to use a sliding panel that you can place wherever you need.

Current version : 1.0.

## Parameters and Functions

### Parameters

This chapter shows you all parameters that can be applied with this plugin.

#### place

*Default value* : right

Indicates where you want to display the panel. This value can be one of these values :

* *top*
* *left*
* *bottom*
* *right*

#### body_slide

*Default value* : true

Indicates whether the body content will moved accordingly to the space used by the panel you open (unless the panel is full sized).

#### no_scroll

*Default value* : false

Indicates whether you want to disable the scrolling effects when the panel is opened.

#### close_selector

*Default value* : Empty.

Set the type of the HTML element that gets the role of the close action. You can use a button type for example.

This value change the default comportment of the `<a></a>` element.

#### auto_close

*Default value* : false

Indicates whether you want to close automatically the panel if the user clicks in the HTML content.

By default, the element must be an element of type `<a ...></a>`.

To use another element type, please indicate it by setting the close_selector setting.

For example, the code below should be correct :

```html
<a href="#" class="btn-close-sliding">
    <img src="close.png" />
</a>
```

#### animation_duration

*Default value* : 0.5s

Defines the duration of the animation. You can change the unit ('s') to a time unit valid.

#### animation_curve

*Default value* : cubic-bezier(0.54, 0.01, 0.57, 1.03)

Defines the animation as a mathematic operation. Change this to whatever you need.

#### toggle

*Default value* : '#sliderpanel-toggle'

Sets the id or class of the element that is used to open the panel by sliding.

#### title_selector

*Default value* : Empty.

Sets the text to display as the title of the panel. You can ignore this parameter if your panel does not manage any title.

#### exit_selector

*Default value* : '.slider-exit'

Sets the id or class of the element that is used to close the panel if the auto close is not activated.

### Functions

This chapter shows you the list of all functions and events that can be used to make the plugin more efficient.

#### onSlideOpening

This is a callback that you can use to make some additional operations while the panel is being displayed.

#### onSlideClosing

This is a callback that you can use to make some additional operations while the panel is being hidden.

#### onSlideOpened

This is a callback that you can use to make some additional operations while the panel is displayed.

#### onSlideClosed

This is a callback that you can use to make some additional operations while the panel is hidden.

#### reset

This function resets the panel automatically to its defaults.

#### activate

This function displays the panel automatically by using the settings previously set.

#### deactivate

This function hides the panel automatically by using the settings previously set.

#### setTitle

This function sets the title using the content used in the parameter of the function.

This function takes one parameter containing the text to display.

```javascript
sliderPanel.setTitle("Product ref. P000001/001");
```

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

```css
/* ================================== NAVIGATION ================================== */
.navigation-slide {
    width: 400px;
    background-color: #fff;
    overflow: hidden !important;
    z-index: 150000;
    box-shadow: 8px 0 8px -10px #000000,-8px 0 8px -10px #000000;
    position: fixed;
    top: 0;
    right: 0;
    bottom: 0;
    z-index: 1999999999;
    text-align: left;
    background: #fff;
    pointer-events: auto;
    max-height: 100vh;
    display: flex;
    flex-direction: column;
    padding-top: 1rem;
}

    .navigation-slide .ns-header {
        padding: 0 2rem .75rem;
        display: flex;
        align-items: center;
    }

        .navigation-slide .ns-header .ns-header-title {
            font-size: .875rem;
            line-height: 1.2857143;
            color: #6f676c;
            width: 100%;
        }

    .navigation-slide .ns-header .ns-exit {
        border: none;
        background: none;
    }

.navigation-overlay {
    position: fixed;
    top: 0;
    right: 0;
    bottom: 0;
    left: 0;
    height: 100vh;
    background-color: rgba(34,32,32,.7);
    z-index: 298;
    cursor: pointer;
}

    .is-visible {
        visibility: visible;
    }

    .is-hidden {
        display: none;
    }
```

### JavaScript

```javascript
        var menu = $('.navigation-slide').SlidePanel({
            place: 'right',
            exit_selector: '.ns-exit',
            toggle: '#ns-product-toggle',
            no_scroll: true,
            body_slide: false,
            auto_close: true,
            onSlideOpening: function () {
                // Displays the overlay for UI stuffs.
                $(".navigation-overlay").removeClass("is-hiding").addClass("is-showing");
            }, onSlideClosing: function () {
                // Hides the overlay for UI stuffs.
                $(".navigation-overlay").removeClass("is-showing").addClass("is-hiding");
            }
        });

        menu.activate();
```

This example shows how to open a panel that can be slided manually.

In theory this code is not intended to be called directly, but this way you see how to map a button to open this panel if you need it.
