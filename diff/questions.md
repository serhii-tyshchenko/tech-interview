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
