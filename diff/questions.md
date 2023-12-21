**JSON vs XML**
| JSON | XML |
| :------------: |:---------------:|
| Text based format (Not a Language) | Markup Language |
| Free to define anything | Has some rules |
| Smaller Size | Big in size due to markups |
| JSON is similar to JavaScript | Browser need parsers to handle XML |
| Objects literals. Browser read faster. | Slow processing |
| No support on namespaces and comments | Both are supported |

**What is Progressive Rendering?**

- Progressive rendering refers to the techniques that are used to improve web page performance, such as displaying content as quickly as possible. Web developers should always learn such methods to build web pages that are more user-friendly and compatible with slow internet connections.
- For example:
  - Lazy loading of images using JavaScript can be used to load images when the user scrolls down to the page.
  - Using only minimum CSS scripts for the number of pages that would be rendered to the user's browser as fast as possible.

**How to optimize website assets loading?**

- To optimize website load time we need to optimize its asset loading and for that:
  - CDN hosting — A CDN or content delivery network is geographically distributed servers to help reduce latency.
  - File compression — This is a method that helps to reduce the size of an asset to reduce the data transfer
  - File concatenation — This reduces the number of HTTP calls
  - Minify scripts — This reduces the overall file size of js and CSS files
  - Parallel downloads — Hosting assets in multiple subdomains can help to bypass the download limit of 6 assets per domain of all modern browsers. This can be configured but most general users never modify these settings.
  - Lazy Loading — Instead of loading all the assets at once, the non-critical assets can be loaded on a need basis.

**What is Webpack?**

- Webpack is a powerful module bundler for JavaScript applications. It takes modules with dependencies and generates static assets that can be served to a browser. It simplifies the process of managing and bundling various assets like JavaScript, CSS, and images, enabling efficient resource utilization and enhancing application performance.

**What are the key features of Webpack?**

- Webpack offers several key features that make it a popular choice among developers:

  - Module bundling: Webpack allows you to bundle all the dependencies, including JavaScript, CSS, and other assets, into a single file or a few optimized files.
  - Code splitting: It supports code splitting, which allows you to split your code into smaller chunks and load them asynchronously when needed, reducing initial loading times.
  - Loaders: Webpack provides loaders to preprocess and transform different types of files, such as CSS, SCSS, TypeScript, and more, allowing you to incorporate them into your project seamlessly.
  - Plugins: Plugins enhance the functionality of Webpack by providing additional optimization, code generation, and asset management capabilities.

**How does Webpack handle dependencies?**

- Webpack uses a dependency graph to manage dependencies. It starts with an entry point and recursively follows the dependencies of the modules to build a complete graph. Each module is treated as a separate entity and can have its own dependencies. Webpack analyzes the graph and bundles all the dependencies into one or more output files.

**What is a loader in Webpack?**

- Loaders in Webpack are transformations applied to source files as they are added to the dependency graph. They allow you to preprocess files before they are bundled. For example, you can use loaders to transpile TypeScript to JavaScript, convert SCSS to CSS, or optimize and compress images. Loaders are configured in the Webpack configuration file and specified using rules.

**Explain the concept of code splitting in Webpack**

- Code splitting is a technique used in Webpack to split the code into smaller chunks that can be loaded on-demand. It helps reduce the initial loading time of an application by loading only the essential code required for the initial view and loading additional code as needed. Webpack achieves code splitting through dynamic imports or by configuring entry points for specific chunks.

**How can you optimize the size of Webpack bundles?**

- To optimize the size of Webpack bundles, you can employ several strategies: - Minification: Webpack offers plugins like UglifyJSPlugin or TerserPlugin to minify and compress the bundled code, reducing its size. - Tree shaking: Tree shaking is a process in which Webpack eliminates dead code that is not used in the application, resulting in smaller bundle sizes. - Code splitting: By splitting code into smaller chunks and loading them on-demand, you can reduce the initial bundle size and improve performance. - Using dynamic imports: Utilizing dynamic imports allows you to load modules asynchronously when needed, reducing the initial loading time.
  **What is the purpose of the Webpack Dev Server?**
- The Webpack Dev Server is a development server that provides an easy way to test and debug applications during development. It offers features like hot module replacement (HMR), which allows you to see changes instantly without refreshing the entire page. The dev server also provides an optimized build process for faster development iterations.

**How can you configure Webpack?**

- Webpack can be configured using a JavaScript configuration file (webpack.config.js). In this file, you define various settings such as entry points, output paths, loaders, plugins, and optimization options. Webpack provides a flexible configuration system that allows you to customize the bundling process according to your project's specific requirements.

**What are the differences between Webpack 4 and Webpack 5?**

- Webpack 5 introduced several notable features and improvements over Webpack 4, including:
  - Improved build speed: Webpack 5 offers enhanced build performance with faster compilation times and improved caching mechanisms.
  - Module federation: Webpack 5 introduced module federation, allowing you to share modules across multiple applications without the need for a monolithic bundle.
  - Asset modules: Asset modules simplify the handling of various assets like images, fonts, and media files, making it easier to manage and optimize them.

**How can you handle CSS in Webpack?**

- Webpack offers multiple ways to handle CSS, including:
  - CSS loaders: You can use CSS loaders like style-loader and css-loader to import CSS files and apply styles to your application.
  - CSS preprocessors: Webpack supports loaders for CSS preprocessors such as Sass, Less, and PostCSS, enabling you to write CSS with advanced features and compile them into regular CSS.
  - Extracting CSS: Webpack allows you to extract CSS into separate files using plugins like `mini-css-extract-plugin`, which is useful for production builds.
