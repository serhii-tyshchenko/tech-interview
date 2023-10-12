**What is the difference between a block level element and an inline element. Can you provide examples of each type of element?**
- Block-level elements are elements that take up the full width available to them and create a new line after the element. They are typically used for larger structures such as page sections, headings, and paragraphs. Examples of block-level elements include `<div>`, `<h1>`-`<h6>`, `<p>`, `<ul>`, `<ol>`, and `<li>`.
- Inline elements, on the other hand, only take up as much width as necessary and do not create a new line after the element. They are typically used for smaller structures such as text and images. Examples of inline elements include `<span>`, `<a>`, `<img>`, `<strong>`, `<em>`, and `<br>`.

**What do you know about CSS image sprites?**
- CSS image sprite is a collection of images put into a single image. A web page with many images can take a long time to load and generates multiple server requests. It is much more memory- and bandwidth-friendly to send images as a single image. Using background position as a way to distinguish between individual images in the same image file, so the number of HTTP requests is reduced.

**Can you give an example of a pseudo class? Can you provide an example use case for a pseudo class?**
- A pseudo class is a keyword added to a selector that specifies a special state of the selected element(s). One example of a pseudo class is `:hover`, which is used to select and style an element when the user hovers over it with their mouse.

- A common use case for the `:hover` pseudo class is to provide visual feedback to the user when they interact with a webpage. For example, you might use `:hover` to change the background color of a button when the user hovers over it, or to underline a hyperlink when the user hovers over it. This can help make your website feel more interactive and engaging for users.

**How is `clearfix` css property useful?**
- The `clearfix` CSS property is useful for clearing floated elements within a container. When you float an element, it is taken out of the normal flow of the document, which can cause issues with the layout of other elements on the page. The `clearfix` property is used to fix this issue by adding an invisible pseudo-element to the container that clears the floats.

**How does CSS selector specificity work?**
- The specificity using the four comma-separated values a, b, c, d is calculated based on the following:
    - a is wherever inline styles are being used & if the property declaration is an inline style on the element a is 1, else 0.
    - b is the number of ID Selectors.
    - c is the number of pseudo classes, attributes & classes.
    - d is the number of tags and pesudo-element selectors.
- Specificity in CSS work on a basis of matrix values which are later compared column by column. In order to look for the highest specificity, look from left to right and compare the highest value in each column.

- *Note:* The value in column b will override the values in column c and d, no matter what value we have. For example, the speciity of 0,1,0,0 will be greater than 0,0,10,10.

**Describe what you like and dislike about the CSS preprocessors you have used.**
- CSS preprocessors are tools that extend the functionality of CSS by adding features such as variables, mixins, and functions. Some popular CSS preprocessors include Sass, Less, and Stylus.

- One advantage of using a CSS preprocessor is that it can help you write more efficient and maintainable CSS code. For example, you can use variables to store commonly used values such as colors or font sizes, which can make it easier to update your styles later on. You can also use mixins to reuse blocks of CSS code across your project, which can help reduce duplication and make your code more modular.

- However, one potential disadvantage of using a CSS preprocessor is that it can add complexity to your workflow. You may need to learn a new syntax and tooling in order to use a preprocessor effectively, which can take time and effort. Additionally, using a preprocessor can add an extra step to your build process, which can slow down your development workflow.

- Overall, whether or not to use a CSS preprocessor depends on your specific needs and preferences. Some developers find that using a preprocessor helps them write better CSS code more efficiently, while others prefer to stick with plain CSS.

**Can you explain the difference between `px`, `em` and `rem` as they relate to font sizing?**
- `px` (pixels) is an absolute unit of measurement that is based on the physical size of the screen. When you specify font size in pixels, it will always be the same size regardless of the size of the parent element or the user's device.

- `em` is a relative unit of measurement that is based on the font size of the parent element. When you specify font size in ems, it will be relative to the font size of the parent element. For example, if the parent element has a font size of 16px and you set the font size of a child element to 1em, it will be 16px. If you set the font size of the child element to 2em, it will be 32px.

- `rem` (root em) is a relative unit of measurement that is based on the font size of the root element (usually the <html> element). When you specify font size in rems, it will be relative to the font size of the root element. For example, if the root element has a font size of 16px and you set the font size of an element to 1rem, it will be 16px. If you set the font size of the element to 2rem, it will be 32px.

- The main difference between `em` and `rem` is that `em` is relative to the font size of the parent element, while `rem` is relative to the font size of the root element. This means that rem can be more predictable and easier to manage, especially when dealing with nested elements.

- In general, it's a good practice to use relative units like `em` and `rem` for font sizing, as it can help make your website more responsive and accessible across different devices and screen sizes.

**What’s the difference between a relative, fixed, absolute and statically positioned element?**
- A static positioned element is positioned according to the normal flow of the document. This is the default position value for all elements. You cannot use the `top`, `bottom`, `left`, or `right` properties with a static positioned element.

- A relative positioned element is positioned relative to its normal position. You can use the `top`, `bottom`, `left`, or `right` properties to move the element away from its normal position. Other elements on the page will not be affected by a relative positioned element.

- An absolute positioned element is positioned relative to the nearest positioned ancestor (an ancestor element that is not static positioned). If there is no positioned ancestor, it is positioned relative to the initial containing block (usually the `<html>` element). You can use the `top`, `bottom`, `left`, or `right` properties to position the element. An absolute positioned element is removed from the normal flow of the document, so other elements on the page may be affected by it.

- A fixed positioned element is positioned relative to the viewport (the browser window). You can use the `top`, `bottom`, `left`, or `right` properties to position the element. A fixed positioned element is removed from the normal flow of the document, so other elements on the page may be affected by it. A fixed positioned element will stay in the same position even if the page is scrolled.

- In general, you should use relative positioning when you want to move an element away from its normal position, but you don't want to affect other elements on the page. You should use absolute positioning when you want to position an element relative to a specific ancestor element. You should use fixed positioning when you want an element to stay in the same position even if the page is scrolled.

**How many ways can you make the text disappear?**
- Set `display: none` or `visibility: hidden`. This is the most basic answer. Follow up question is what is the difference between the two? What happens to the “space” occupied by the element? Do they proactively tell me the difference between an inline vs. block element? Can you convert an inline element to block and vice versa?
- Remove the element from DOM. There are multiple possibilities here as well. You can remove the element itself, or any of its parents, or use a parent’s innerHTML.
- Remove the innerText, or textContent, i.e. setting it to an empty string. textContent is rarely used, so bonus if you know that.
- Position the element off the page using a negative top or left value. Follow up question could be to explain difference between absolute and relative positioning.
- Hide it behind another element using `z-index`.
- Camouflage it by setting the text color the same as the background. This is one of the oldest tricks on the internet where you have to “highlight” to reveal the answer.
- Make the text transparent using opacity. Set opacity to zero. Bonus points if you can explain the difference between opacity and RGBA alpha. Opacity affects both the background and text, while RGBA only affects transparency of the background image.
- 3D transform the text to disappear by `transform: rotateX(90deg)` or `rotateY`. This is extra extra points. I don’t expect anyone to know this.

**What is margins collapsing?**

**What’s the difference between “resetting” and “normalizing” CSS? Which would you choose, and why?**

**Describe Floats and how they work**

**Describe z-index and how stacking context is formed**

**What are the various clearing techniques and which is appropriate for what context?**

**Can you give an example of an @media property other than screen?**

**Explain how a browser determines what elements match a CSS selector**

**Explain your understanding of the box model and how you would tell the browser in CSS to render your layout in different box models**

**What is the CSS `display` property and can you give a few examples of its use?**

**What’s the difference between inline and inline-block?**

**What’s the difference between the `nth-of-type()` and `nth-child()` selectors?**

**Have you ever worked with retina graphics? If so, when and what techniques did you use?**

**Is there any reason you’d want to use translate() instead of absolute positioning, or vice-versa? And why?**



















