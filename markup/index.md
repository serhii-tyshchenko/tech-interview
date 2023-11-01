**What is Critical Rendering Path (CRP)?**

- The Critical Rendering Path is the sequence of steps that a web browser takes to convert HTML, CSS, and JavaScript into a rendered webpage. It includes HTML parsing, loading external resources (stylesheets, scripts, images), building DOM, and rendering pixels on the screen.

**How can I get indexed better by search engines?**

- Prioritize user experience.
- Create high-quality, unique content.
- Use descriptive, semantic and relevant meta tags.
- Build high-quality backlinks from reputable websites.
- Submit a sitemap to search engines.
- Ensure that website is mobile-friendly and loads quickly.

**What is desktop-first and mobile-first design approach?**

- Desktop-first design starts by creating a website layout for larger screens and then adapting it for smaller screens. Mobile-first design, on the other hand, begins with designing for mobile devices and progressively enhances the layout for larger screens.

**How to make a page responsive?**

- Use media queries in CSS to adjust styles for different screen sizes.
- use flexible layouts with relative units (rems, vws, percents etc).
- use scalable images.
- use CSS frameworks like Bootstrap.

**What are the building blocks of HTML5?**

- Semantic HTML tags.
- customized appearance of HTML tags
- client-side data storage.
- support for video and audio files.
- 2D/3D graphics and effects.

**When should you use `section`, `div`, or `article`?**

- We are using `<section>` for grouping related content.
- `<div>` for generic containers or layout purposes.
- `<article>` for self-contained, independent content that can stand alone.

**What are the semantic tags available in HTML5?**

They are `<header>`, `<nav>`, `<main>`, `<article>`, `<section>`, `<aside>`, `<footer>`, `<figure>`.

**Why would you like to use semantic tags?**

- Semantic tags improve the structure and accessibility of web content. They provide meaning to elements, making it easier for search engines and assistive technologies to understand and navigate a webpage.

**What is accessibility? What does ARIA role mean in a web application?**

- Accessibility is a designing web content and applications in a way that can be used by people with disabilities. ARIA roles are attributes used to enhance the accessibility of web elements. They provide extra information to assistive technologies, such as screen readers, about the roles and states of elements on a webpage.

**What is the purpose of the `alt` attribute on images?**

- The `alt` attribute provides alternative text for an image. It serves two main purposes: to describe the image to users who cannot see it and to provide context for search engines.

**Define semantic markup. What are the semantic meanings for and when/how should each be used in structuring HTML markup?**

- Semantic markup is the use of HTML elements with additional meaning. Examples include using `<header>` for page headers, `<nav>` for navigation menus, `<article>` for self-contained content, `<section>` for thematic grouping, and `<footer>` for page footers. Semantic elements should be used according to their intended meaning to improve accessibility and SEO.

**Describe the difference between a `cookie`, `sessionStorage`, and `localStorage`.**

- Cookies are small pieces of data stored on the user's device and sent to the server with each HTTP request. They have an expiration date and can be used for various purposes, including user authentication and tracking.
- `sessionStorage` and `localStorage` are web storage options in the browser. `sessionStorage` stores data only for a single session, while `localStorage` stores data persistently until cleared by the user or the application.

**What are the possible ways to apply CSS styles to a web page?**

- Inline styles (within HTML tags).
- Internal stylesheets (using `<style>` tags within the HTML document).
- External stylesheets (linked via `<link>` tags to separate CSS files).
- Using CSS frameworks and libraries.

**What does the cascading portion of CSS mean?**

- Cascading in CSS refers to the process of determining which styles should be applied when multiple conflicting styles are defined. It follows a hierarchy, including specificity, importance, and source order.

**What is a CSS preprocessor?**

- A CSS preprocessor is a scripting language that extends CSS, allowing developers to write more maintainable and efficient stylesheets. Popular CSS preprocessors include Sass, Less, and Stylus.

**What are media queries?**

- Media queries are CSS rules that apply styles based on the characteristics of the device or viewport, such as screen width, height, and orientation. They are commonly used for responsive web design.

**What does `box-sizing` do?**

- The `box-sizing` property in CSS controls how the sizing of an element's box is calculated. It can be set to `content-box` (default) or `border-box`. When set to `border-box`, padding and borders are included in the element's width, making it easier to create predictable layouts.

**Explain some pros and cons for CSS animations versus JavaScript animations.**

- CSS Animations:

  - Pros: Easier to implement for simple animations, hardware-accelerated, smoother performance.
  - Cons: Limited control over animations, less support for complex interactions.

- JavaScript Animations:

  - Pros: Full control over animations, support for complex interactions.
  - Cons: Requires more code and can be less performant for simple animations.

**What is theming? How to respond to the system theme change?**

- Theming refers to customizing the visual appearance. To respond to the system theme change (e.g., light to dark mode), we can use CSS Media Queries to detect the user's preference and apply corresponding styles.

**How to make images responsive?**

- To make images responsive, we should apply following CSS properties:

  - `max-width: 100%;` to ensure images don't exceed their container's width.
  - `height: auto;` or `aspect-ratio: 1` to maintain the aspect ratio.

**Explain CSS grid layout with an example.**

- CSS Grid Layout is a two-dimensional grid system for creating complex layouts. Here's an example:

```css
.grid-container {
  display: grid;
  grid-template-columns: repeat(3, 1fr); /* Three equal columns */
  grid-gap: 1rem; /* Gap between grid items */
}

.grid-item {
  background-color: #ccc;
  padding: 1.5rem;
}
```

```html
<div class="grid-container">
  <div class="grid-item">Item 1</div>
  <div class="grid-item">Item 2</div>
  <div class="grid-item">Item 3</div>
</div>
```

- This code creates a grid container with three equally sized columns and 1rem gaps between items. The grid items will automatically flow into the grid, adapting to different screen sizes.
