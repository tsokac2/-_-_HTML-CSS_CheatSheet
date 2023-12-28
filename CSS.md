<h1 align="center">CSS</h1>

### Overview of the Section
* **[CSS Selectors](#CSS-Selectors)**
* **[Order of specificity in CSS](#Order-of-specificity-in-CSS)**
* **[CSS box-model](#CSS-box-model)**
* **[CSS viewport](#CSS-viewport)**
* **[CSS Measurement Units](#CSS-viewport)**
* **[CSS Positions properties](#CSS-Positions-properties)**

* **[CSS display vs visibility](#CSS-display-vs-visibility)**

#
### CSS Selectors
Here are some common types of CSS selectors:

1. **Element Selector:** Selects all instances of a specified HTML element. For example, ``p`` selects all paragraph elements.

		```
		p {
			color: blue;
		}
		```

2. **ID Selector:** Selects a single element with a specified ID attribute. It is denoted by a hash symbol ``(#)``. For example, #header selects the element with the ID ``"header"``.

		#header {
			background-color: gray;
		}


3. **Class Selector:** Selects all elements with a specified class attribute. It is denoted by a period ``(.)``. For example, .button selects all elements with the class ``"button"``.

		.button {
			font-size: 16px;
		}


4. **Descendant Selector:** Selects an element that is a descendant of another specified element. It is denoted by whitespace. For example, div p selects all paragraph elements that are descendants of a ``div``.

		div p {
			margin: 10px;
		}


5. **Child Selector:** Selects an element that is a direct child of another element. It is denoted by the greater-than symbol ``(>)``. For example, ``ul > li`` selects all list items that are direct children of a list.

		ul > li {
			list-style-type: square;
		}

6. **Attribute Selector:** Selects elements based on the presence or value of their attributes. For example, ``input[type="text"]`` selects all text input elements.

		input[type="text"] {
			border: 1px solid #ccc;
		}

7. **Pseudo-class Selector:** Selects elements based on their state or position. For example, ``:hover`` selects an element when the user hovers over it.

		a:hover {
			text-decoration: underline;
		}

**[Back To The Top](#Overview-of-the-Section)**
#

### Order of specificity in CSS
Here's the ascending order of specificity:

1. **Universal selectors** (*) **and combinators** (+, >, ~, ): These have the lowest specificity.
2. **Type selectors (e.g., h1, p, div): These are the basic CSS selectors that select elements based on their type.

3. **Class selectors** ```(.className)```, **attributes selectors** ``([type="checkbox"])``, **and pseudo-classes** ``(:hover, :focus)``: These have higher specificity than type selectors.

4. **ID selectors** ``(#idName)``: These are more specific than class, attribute, and pseudo-class selectors.

5. **Inline styles** ``(style="")``: Inline styles added to HTML elements directly have a higher specificity than any selectors in your external or internal stylesheet.

6. **``!important``**: This rule overrides all other styles and should only be used as a last resort.

Remember that if two rules have the same level of specificity, the one that **comes last in the CSS document** will be the one that gets applied.

**[Back To The Top](#Overview-of-the-Section)**
#

### CSS box-model

Here's a brief explanation of the box model components:

	Margin <br/>
		Border <br/>
			Padding <br/>
				Content

1. **Margin:** Clears an area outside the border. It is transparent and contributes to spacing between elements.

2. **Border:** A border surrounding the padding (if any) and content. It can have properties like width, style, and color.

3. **Padding:** Clears an area around the content inside the box. It is transparent and usually has a background color.

4. **Content:** The actual content of the box, where text and images appear. It has width and height properties.
```
   .example-box {
      width: 200px;
      height: 100px;
      padding: 20px;
      border: 2px solid #3498db;
      margin: 30px;
    }
```
**[Back To The Top](#Overview-of-the-Section)**
#

### CSS viewport

Viewport units are a set of CSS units that relate to the dimensions of the viewport, the browser window or the area in which the web content is displayed. 

There are four primary viewport units:

- ``vw`` (viewport width): This unit is equal to 1% of the viewport's width. For example, if you set an element's width to 50vw, it will take up half of the viewport's width.

- ``vh`` (viewport height): Similar to vw, but it is based on the height of the viewport. 1vh is 1% of the viewport's height.

- ``vmin`` This unit is relative to the smaller of the viewport's width or height. It takes the smaller dimension and is 1% of that.

- ``vmax`` Like vmin, but it's relative to the larger of the viewport's width or height. It is 1% of the larger dimension

Using viewport units is particularly useful for creating responsive layouts that adapt to different screen sizes.

**[Back To The Top](#Overview-of-the-Section)**
#
### CSS Measurement Units

CSS provides various measurement units for specifying sizes, distances, and other dimensions. The commonly used measurement units include:

**[Back To The Top](#Overview-of-the-Section)**
#
### CSS Positions properties

- **Pixels** ``(px)``: A pixel is a single point on a screen. 
It's a fixed-size unit and is commonly used for specifying sizes in a way that is consistent across different devices.

- **Percentage** ``(%)``: Percentages are often used in relation to the size of the parent element. For example, setting a width to 50% means the element will take up half the width of its containing element.

- **Em** The ``em`` unit is relative to the font-size of the closest parent or the element itself. It is particularly useful for creating scalable and accessible designs.

- ``Rem`` Similar to em, but it is relative to the root element (html) rather than the closest parent. This makes rem units particularly handy for maintaining consistent spacing and sizing across the entire document.

- Inches (in), Centimeters (cm), Millimeters (mm): These units allow you to specify sizes in physical units, which can be useful for print stylesheets.

**[Back To The Top](#Overview-of-the-Section)**
#
### CSS Positions properties

#### ```position: static;``` 
**Static** by default - always positioned according to the normal flow of the page.

#### ```position: relative;``` 
**Relative** to its normal position top, right, bottom, and left will be adjusted away from their normal position - other content will not be adjusted.

#### ```position: fixed;```
**Relative** to the viewport NO - top, right, bottom, and left - is always stays in the same place if the page is scrolled.

#### ```position: absolute;```
**Absolute** positioned to the nearest positioned ancestor or parent if no parent element then to the body - outside of the normal flow.

#### ```position: sticky;```
**Sticky** is positioned based on the user's scroll position.

**[Back To The Top](#Overview-of-the-Section)**
#

### CSS display vs visibility

Let's delve into the distinctions between display: none; and visibility: hidden; in CSS.

#### ``display: none;:``
- **Effect:** This property completely removes the element from the layout, meaning it's as if the element doesn't exist in the document flow.
- **Space:** The space that the element would have occupied is also removed, causing other elements to adjust accordingly.
- **Interactivity:** The element and its child elements are not interactive, as they are essentially not rendered on the page.

#### ``visibility: hidden;``
- **Effect:** This property hides the element, but the space it occupies is still reserved in the layout.
- **Space:** The element is still present in the document flow, maintaining the space it would occupy if it were visible.
- **Interactivity:** The element is not visible, but it is still interactive, and its child elements are also rendered.


### CSS pseudo-element?
A keyword is added to a selector that lets you style a specific part of the selected element(s).

Syntax - ```selector:: pseudo-element { property: value; }```

```
p:: first-line {
	color: #fff;
	font-variant: small-caps; 
	}
```
The first line in a paragraph will be red and in small caps.

### Media types in CSS?
- all		- suitable for all devices
- print 	- for print preview mode
- screen	- intended primarily for screens

### CSS3 features?
- Advance animations
- Multiple Backgrounds and Gradient
- Multiple Column layouts
- Opacity
- Rounded Corner
- Shadows
- Flexbox

### Hov remove the margin in the inline-block element when kept under a div?
Assign the font size of a parent if the inline-block element to **0px** - apply font size to the inline element.

### Difference between container and container-fluid?
*Container* - provides a responsive fixed-width container<br/>
*Container-fluid* - provides a full-width container, spanning the entire width of the viewport.

### When to use !important?
Avoid using it as much as possible.
Use specificity to avoid it.
Don't use it.

### Break points in Bootstrap?
| Breakpoint |		Class infix |	Dimensions |
| ---------- | ---------------- | -------------|
| x-small		 |	xs 				| < 576px   |
| small		     |	sm  			| >= 576px |
| medium			 | md  			| >= 768px |
| large			 | lg  				| >= 992px |
| Extra large		 | xl 			| >= 1200px|
| Extra extra 	 | xxl				| >= 1400px|

### 1 REM = ? PX
REM - (root-em) - unit dictate elements' font-size relative to the size of the root element
**Font-size = 16px => 1 REM = 16 px** - in most cases

### CSS animation properties?
- animation-delay
- animation-direction
- animation-duration
- animation-fill-mode
- animation-iteration-count
- animation-name
- animation-play-state
- animation-timing-function

### CSS Preprocessors?
Sass
Less
Stylus
PostCSS

### What advantages of using SCSS over CSS?
Helps you write CSS codes easily by letting you use loops, functions, import, variables, and math operations, thus making CSS writing more powerful.

### CSS Resource(s)?
- StackOverflow
- Mozilla MDM DevDocs
- YouTube

### Flexbox properties?
- flex-direction
- flex-wrap
- flex-flow
- justify-content
- align-items
- align-content