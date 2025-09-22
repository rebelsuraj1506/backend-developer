# HTML

## Overview

HTML stands for Hypertext Markup Language.
But what does that mean exactly?
Hypertext is text which contains links to other text.
Markup refers to tags and elements used within a document.
For now, let's just focus on some of the basics of HTML.
HTML is simply a text file with a specific structure that consists of elements and tags.
Also take note that HTML files usually have a dot HTML suffix.

For instance, when you visit a website, the first page that is returned to the browser is often called index.html.
Now, let's explore what HTML tags and elements are.
Each HTML element consists of an opening tag enclosed in angle brackets.
For example to create a paragraph, you type a left angle bracket, the letter p for paragraph, and then a right angle bracket.
Most elements are paired with a closing tag, which has a forward slash off to the left angle bracket.
For example you close the paragraph element with a left angle bracket, a forward slash the letter p and a right angle bracket.
HTML elements usually have some content inside them.

For example between the opening and closing tags of a paragraph, you add the text of the paragraph you want to write.
HTML elements can also contain other elements, for example you can add an italics element inside a paragraph element to make texts appear in italics.
Elements can also be empty or self-closing, meaning they do not have a closing HTML tag.
One example of a self-closing element is the line break tag.
You can add a line break tag in a paragraph tag to move content to the following line by typing left angle bracket, the letters br, then right angle bracket.
At the end of a self-closing tag, you simply add a right angle bracket.
You can also close the right angle bracket by typing a forward slash right before it.

Now that you know what elements and tags are, you will explore what HTML standards are.
The rules and structure for elements and tags are known as the HTML specification.
The HTML specification is maintained by the World Wide Web Consortium, or W3C, as it is commonly known.
Whenever the HTML specification changes, a new version of HTML is standardized, the current version is HTML 5.
To summarize, HTML elements with their opening and closing tags, and angle brackets build up an HTML document.
These elements form the structure of a web page and describe to the web browser what to display.
For example the browser reads an HTML page that has an image tags display an image file called icon.png.

Next, it reads a p tag to display a paragraph under that image.
But the browser reads the HTML document and displays the web page to the user in a very basic format.
Now, if you want to tell the browser how to display the web page, you should use CSS.
You will learn more about CSS in this course.
By now, you have learned how HTML tags are used to create elements that build the structure of a web page.
You'll have an opportunity to explore HTML in action in this course.

## HTML Basics at a glance

| Element | Tag(s) | Purpose | Example |
| --- | --- | --- | --- |
| Heading | `h1`–`h6` | Titles and section headings | `<h2>Section</h2>` |
| Paragraph | `p` | Blocks of text | `<p>Hello world</p>` |
| Line break | `br` | Force a new line inside text | `Line 1<br>Line 2` |
| Emphasis | `em` | Semantic emphasis | `Do it <em>now</em>` |
| Strong | `strong` | Strong importance | `<strong>Warning</strong>` |
| Italic | `i` | Alternative voice/term | `<i>HTML</i>` |
| Bold | `b` | Visual bold without semantics | `<b>Bold</b>` |
| Lists | `ul`, `ol`, `li` | Unordered/ordered lists | `<ul><li>Item</li></ul>` |
| Division | `div` | Generic container | `<div>...</div>` |

## Summary of HTTP Examples

### Understanding HTTP Requests and Responses

HTTP Request: An HTTP request is initiated by a client (like a web browser) to a server. It includes a request line, headers, and an optional body.

Request Line: Contains the HTTP method (e.g., GET, POST), the requested resource (e.g., /home.html), and the HTTP version (e.g., HTTP/1.1).
Headers: Provide additional information about the request, such as the host, user agent, and accepted content types.
Body: Used mainly with methods like POST and PUT to send data to the server.
HTTP Response: After processing the request, the server sends back an HTTP response, which includes a status line, headers, and a body.
Status Line: Indicates the HTTP version, status code (e.g., 200 for success), and a reason phrase.
Headers: Provide metadata about the response, such as content type and length.
Body: Contains the actual content returned by the server, such as HTML, images, or JSON data.

HTTP Request vs Response (at a glance)

| Part | Request | Response | Example |
| --- | --- | --- | --- |
| Start line | Method + path + version | Version + status + reason | `GET /index.html HTTP/1.1` ↔ `HTTP/1.1 200 OK` |
| Headers | Client preferences, metadata | Resource metadata | `Accept: */*` ↔ `Content-Type: text/html` |
| Body | Optional payload (POST/PUT) | Resource content | JSON payload ↔ HTML document |
Common HTTP Methods

| Method | Purpose |
| --- | --- |
| GET | Retrieve data from the server |
| POST | Submit data to the server |
| PUT | Update existing data on the server |
| DELETE | Remove data from the server |

Request Headers (Example)

| Header | Example | Meaning |
| --- | --- | --- |
| Host | example.com | Specifies server host for the requested resource |
| User-Agent | Mozilla/5.0 (Macintosh; Intel Mac OS X 10.9; rv:50.0) Gecko/20100101 Firefox/50.0 | Identifies the client application making the request |
| Accept | */* | Content types the client can accept in the response |
| Accept-Language | en | Preferred language/locale |
| Content-Type | text/json | Media type of the request body |



```http
POST /users HTTP/1.1
Host: example.com

{
 "key1":"value1",
 "key2":"value2",
 "array1":["value3","value4"]
}

PUT /users/1 HTTP/1.1
Host: example.com
Content-type: text/json

{"key1":"value1"}
```

HTTP Status Codes

- 1XX: Informational responses (e.g., 100 Continue)
- 2XX: Successful responses (e.g., 200 OK, 201 Created)
- 3XX: Redirection responses (e.g., 301 Moved Permanently)
- 4XX: Client error responses (e.g., 404 Not Found)
- 5XX: Server error responses (e.g., 500 Internal Server Error)

1XX Informational

| Status Code | Reason Phrase | Description |
| --- | --- | --- |
| 100 | Continue | The server received the request headers and should continue to send the request body |
| 101 | Switching Protocols | The client requested a protocol switch and the server agreed |

2XX Successful

| Status Code | Reason Phrase | Description |
| --- | --- | --- |
| 200 | OK | Standard response indicating the request was successfully processed |
| 201 | Created | The request succeeded and a resource was created |
| 202 | Accepted | The request was accepted for processing, but processing is not complete |
| 204 | No Content | The server successfully processed the request but is not returning content |

3XX Redirection

| Status Code | Reason Phrase | Description |
| --- | --- | --- |
| 301 | Moved Permanently | This and future requests should be sent to the returned location |
| 302 | Found | Temporarily points to a different resource location |

4XX Client Error

| Status Code | Reason Phrase | Description |
| --- | --- | --- |
| 400 | Bad Request | The server cannot process the request due to a client error |
| 401 | Unauthorized | Authentication is required and has failed or not been provided |
| 403 | Forbidden | The server understood the request but refuses to authorize it |
| 404 | Not Found | The server did not find the requested resource |
| 405 | Method Not Allowed | The method is not supported for the targeted resource |

5XX Server Error

| Status Code | Reason Phrase | Description |
| --- | --- | --- |
| 500 | Internal Server Error | A generic error occurred on the server |
| 502 | Bad Gateway | The server received an invalid response from an upstream server |
| 503 | Service Unavailable | The server is currently unable to handle the request |

Date: Fri, 11 Feb 2022 15:00:00 GMT+2
Server: Apache/2.2.14 (Linux)
Content-Length: 84
Content-Type: text/html

The Date header specifies the date and time the HTTP response was generated.

The Server header describes the web server software used to generate the response.

The Content-Length header describes the length of the response.

The Content-Type header describes the media type of the resource returned (e.g. HTML document, image, video).

```http
HTTP/1.1 200 OK
Date: Fri, 11 Feb 2022 15:00:00 GMT+2
Server: Apache/2.2.14 (Linux)
Content-Length: 84
Content-Type: text/html

<html>
  <head><title>Test</title></head>
  <body>Test HTML page.</body>
</html>
```

### Other Internet Protocols
Hypertext Transfer Protocols (HTTP) are used on top of Transmission Control Protocol (TCP) to transfer webpages and other content from websites.
This reading explores other protocols commonly used on the Internet.

Summary

| Protocol | Purpose | Transport | Notes |
| --- | --- | --- | --- |
| DHCP | Assign IP addresses dynamically | UDP | Client requests from a DHCP server |
| DNS | Resolve domain names to IP addresses | UDP/TCP | UDP for queries; TCP for large responses/zone transfers |
| IMAP | Access and manage email on the server | TCP | Keeps mail on server; syncs state across devices |
| SMTP | Send and relay email | TCP | Used for submission and server-to-server delivery |
| POP | Download email to client | TCP | Typically removes emails from server after download |
| FTP | Transfer files | TCP | Unencrypted; separate control and data channels |
| SSH | Secure remote login and commands | TCP | Encrypted interactive shell and tunneling |
| SFTP | Secure file transfer over SSH | TCP (via SSH) | Uses SSH for secure file operations |

#### Dynamic Host Configuration Protocol (DHCP)
You've learned that computers need IP addresses to communicate with each other. When your computer connects to a network, the Dynamic Host Configuration Protocol or DHCP as it is commonly known, is used to assign your computer an IP address.
Your computer communicates over User Datagram Protocol (UDP) using the protocol with a type of server called a DHCP server. The server keeps track of computers on the network and their IP addresses. It will assign your computer an IP address and respond over the protocol to let it know which IP address to use. Once your computer has an IP address, it can communicate with other computers on the network.

#### Domain Name System Protocol (DNS)
Your computer needs a way to know with which IP address to communicate when you visit a website in your web browser, for example, meta.com. The Domain Name System Protocol, commonly known as DNS, provides this function. Your computer then checks with the DNS server associated with the domain name and then returns the correct IP address.

#### Internet Message Access Protocol (IMAP)
Do you check your emails on your mobile or tablet device? Or maybe you use an email application on your computer?
Your device needs a way to download emails and manage your mailbox on the server storing your emails. This is the purpose of the Internet Message Access Protocol or IMAP.

#### Simple Mail Transfer Protocol (SMTP)
Now that your emails are on your device, you need a way to send emails. The Simple Mail Transfer Protocol, or SMTP, is used. It allows email clients to submit emails for sending via an SMTP server. You can also use it to receive emails from an email client, but IMAP is more commonly used.

#### Post Office Protocol (POP)
The Post Office Protocol (POP) is an older protocol used to download emails to an email client. The main difference in using POP instead of IMAP is that POP will delete the emails on the server once they have been downloaded to your local device. Although it is no longer commonly used in email clients, developers often use it to implement email automation as it is a more straightforward protocol than IMAP.

#### File Transfer Protocol (FTP)
When running your websites and web applications on the Internet, you'll need a way to transfer the files from your local computer to the server they'll run on. The standard protocol used for this is the File Transfer Protocol or FTP. FTP allows you to list, send, receive and delete files on a server. Your server must run an FTP Server and you will need an FTP Client on your local machine. You'll learn more about these in a later course.

#### Secure Shell Protocol (SSH)
When you start working with servers, you'll also need a way to log in and interact with the computer remotely. The most common method of doing this is using the Secure Shell Protocol, commonly referred to as SSH. Using an SSH client allows you to connect to an SSH server running on a server to perform commands on the remote computer.
All data sent over SSH is encrypted. This means that third parties cannot understand the data transmitted. Only the sending and receiving computers can understand the data.

#### Secure File Transfer Protocol (SFTP)
The data is transmitted insecurely when using the File Transfer Protocol. This means that third parties may understand the data that you are sending. This is not right if you transmit company files such as software and databases. To solve this, the SSH File Transfer Protocol, alternatively called the Secure File Transfer Protocol, can be used to transfer files over the SSH protocol. This ensures that the data is transmitted securely. Most FTP clients also support the SFTP protocol.

### Simple HTML Tags

Summary

| Topic | Primary tags | Purpose |
| --- | --- | --- |
| Headings | `h1`–`h6` | Page titles and section headings |
| Paragraphs | `p` | Blocks of text |
| Line breaks | `br` | Force a line break inside text |
| Strong/Bold | `strong`, `b` | Emphasis (semantic) vs visual bold |
| Emphasis/Italics | `em`, `i` | Emphasis (semantic) vs visual italics |
| Lists | `ul`, `ol`, `li` | Unordered/ordered lists and items |
| Div | `div` | Generic container for grouping and styling |
| Comments | `<!-- -->` | Notes not rendered in the browser |

#### Headings

Headings are used to define titles and subtitles on a webpage. Tags range from `h1` (most important) to `h6` (least important).

```html
<body>
  <h1>Heading 1</h1>
  <h2>Heading 2</h2>
  <h3>Heading 3</h3>
  <h4>Heading 4</h4>
  <h5>Heading 5</h5>
  <h6>Heading 6</h6>
</body>
```

#### Paragraphs

The `p` tag is used to create paragraphs of text.

```html
<p>
  This paragraph
  contains a lot of lines
  but they are ignored.
</p>
```

#### Line Breaks

Line breaks within paragraphs are ignored unless specified with the `br` tag.

```html
<p>
  This paragraph<br>
  contains a lot of lines<br>
  and they are displayed.
</p>
```

#### Strong and Bold Text

The `strong` tag indicates important text semantically, while the `b` tag is used for visual emphasis without implying importance.

```html
<p>
  No matter how much the dog barks: <strong>don't feed him chocolate</strong>.
</p>
<p>
  The primary colors are <b>red</b>, <b>yellow</b> and <b>blue</b>.
</p>
<p>
  In case of emergency, <b>push the red button</b>.
</p>
```

#### Emphasis and Italics

The `em` tag adds emphasis to text, while the `i` tag is used for italicized text, often for technical terms or titles. Both have similar visual effects but differ semantically.

```html
<p>
  Wake up <em>now</em>!
</p>
<p>
  The term <i>HTML</i> stands for HyperText Markup Language.
</p>
```

#### Lists

HTML supports two types of lists: unordered (`ul`) and ordered (`ol`). List items are defined using the `li` tag.

```html
<ul>
  <li>Tea</li>
  <li>Sugar</li>
  <li>Milk</li>
  </ul>

<ol>
  <li>Rocky</li>
  <li>Rocky II</li>
  <li>Rocky III</li>
</ol>
```

#### Div Tags

The `div` tag is a generic container for grouping content and can be styled with CSS. It has no inherent effect on content unless styled.

```html
<div>
  <p>This is a paragraph inside a div</p>
</div>

<div>
  <div>
    <p>This is a paragraph inside a div that’s inside another div</p>
  </div>
</div>

<style>
  div {
    border: 1px solid black;
    padding: 2px;
  }
</style>
<div>
  <div>
    <p>This is a paragraph inside stylized divs</p>
  </div>
</div>
```

#### Comments

Comments can be added in the code using `<!-- Comment -->` and are not displayed in the browser.

```html
<!-- This is a comment and will not be shown in the page -->
```

### CSS Selectors

Summary

| Selector | Syntax | Selects | Example |
| --- | --- | --- | --- |
| Element | `tag` | All elements of a type | `p { color: blue; }` |
| ID | `#id` | One element with a unique id | `#latest { background: purple; }` |
| Class | `.class` | All elements with a class | `.navigation { margin: 2px; }` |
| Element + Class | `tag.class` | Elements of a type with a class | `p.introduction { margin: 2px; }` |
| Descendant | `A B` | `B` inside `A` at any depth | `#blog h1 { color: blue; }` |
| Child | `A > B` | `B` that is a direct child of `A` | `#blog > h1 { color: blue; }` |
| Pseudo-class | `A:state` | Elements in a state | `a:hover { color: orange; }` |

#### 1) Element Selectors

Selects HTML elements based on their tag name.

```html
<p>Once upon a time...</p>
<p>In a hidden land...</p>
```

```css
p {
  color: blue;
}
```

#### 2) ID Selectors

Targets a specific element with a unique `id` attribute. Prefixed with `#`.

```html
<span id="latest">New!</span>
```

```css
#latest {
  background-color: purple;
}
```

#### 3) Class Selectors

Selects elements based on their `class` attribute. Prefixed with `.` and applies to all elements with that class.

```html
<a class="navigation">Go Back</a>
<p class="navigation">Go Forward</p>
```

```css
.navigation {
  margin: 2px;
}
```

#### 4) Element with Class Selector

Combines an element selector with a class selector for more specificity.

```html
<p class="introduction">Hello</p>
```

```css
p.introduction {
  margin: 2px;
}
```

#### 5) Descendant Selectors

Selects elements that are nested within another element (at any depth).

```html
<div id="blog">
  <h1>Latest News</h1>
  <div>
    <h1>Today's Weather</h1>
    <p>The weather will be sunny</p>
  </div>
  <p>Subscribe for more news</p>
</div>
<div>
  <h1>Archives</h1>
</div>
```

```css
#blog h1 {
  color: blue;
}
```

#### 6) Child Selectors

Targets only the immediate children of a specified element.

```html
<div id="blog">
  <h1>Latest News</h1>
  <div>
    <h1>Today's Weather</h1>
    <p>The weather will be sunny</p>
  </div>
  <p>Subscribe for more news</p>
</div>
```

```css
#blog > h1 {
  color: blue;
}
```

#### 7) Pseudo-Classes

Allows selection based on the state of an element (e.g., hover, focus).

```css
a:hover {
  color: orange;
}
```

These selectors provide flexibility and precision in applying styles to HTML elements, enabling developers to create well-structured and visually appealing web pages.

### Text and Colors

Summary

| Concept | Property | Example |
| --- | --- | --- |
| Text color | `color` | `p { color: blue; }` |
| Font family | `font-family` | `p { font-family: "Arial", sans-serif; }` |
| Font size | `font-size` | `p { font-size: 16px; }` |
| Transform case | `text-transform` | `p { text-transform: uppercase; }` |
| Text decoration | `text-decoration` | `p { text-decoration: underline; }` |

#### 1) Colors in CSS

Common ways to define colors:

```css
/* RGB */
p { color: rgb(255, 0, 0); }

/* RGBA (with opacity) */
p { color: rgba(255, 0, 0, 0.8); }

/* HSL */
p { color: hsl(0, 100%, 50%); }

/* Hexadecimal */
p { color: #FF0000; }

/* Named color */
p { color: red; }
```

#### 2) Text Color

The `color` property sets the text color of elements.

```css
p { color: blue; }
```

#### 3) Font and Size

Control typeface and size with `font-family` and `font-size`.

```css
p {
  font-family: "Arial", sans-serif;
  font-size: 16px; /* also supports em, rem, %, etc. */
}
```

#### 4) Text Transformation

Change capitalization with `text-transform`.

```css
p { text-transform: uppercase; }
/* lowercase | capitalize are other common values */
```

#### 5) Text Decoration

Add underlines, line-through, and more. Use shorthand or longhand properties.

```css
/* Shorthand */
p { text-decoration: underline; }

/* Longhand */
p {
  text-decoration-line: underline;
  text-decoration-color: #555;
  text-decoration-style: dotted; /* solid | double | wavy */
  text-decoration-thickness: 2px;
}
```

### Alignment

Summary

| Topic | Property/Technique | Common values / notes |
| --- | --- | --- |
| Text alignment | `text-align` | `left`, `right`, `center`, `justify` |
| Center block element | `width` + `margin: auto` | Requires defined width |
| Float alignment | `float` | `left`, `right` (text wraps around) |
| Positioning | `position` | `static`, `relative`, `absolute`, `fixed`, `sticky` |

#### 1) Text Alignment

Set horizontal alignment of text within an element.

```css
.text-left { text-align: left; }
.text-right { text-align: right; }
.text-center { text-align: center; }
.text-justify { text-align: justify; }
```

#### 2) HTML Element Alignment (centering blocks)

Center a block-level element by setting a width and using auto margins.

```css
.child {
  width: 50%;
  margin: auto;
}
```

For inline elements (e.g., `img`), make them block-level first.

```css
img {
  display: block;
  margin: auto;
}
```

#### 3) Left and Right Alignment (float)

```css
img { float: right; }
```

#### 4) Position Property (advanced alignment)

```css
.parent { position: relative; }
.child {
  position: absolute;
  top: 0;
  right: 0;
}
```

### Bootstrap Overview

Bootstrap is a popular front-end framework with a responsive grid and a rich set of components, enabling fast, mobile-first development.

Key areas to explore

- Layout: Grid system, offsets, alignment, auto-layout
- Content: Typography, images, tables
- Forms: Form controls and validation utilities
- Components: Buttons, modals, navbars, alerts, cards

Bootstrap sections (cheat sheet)

| Section | What it covers | Where to start in docs |
| --- | --- | --- |
| Layout | Grid, breakpoints, containers, utilities | Layout → Grid |
| Content | Typography, images, tables, helpers | Content → Typography |
| Forms | Inputs, validation, layout | Forms → Overview |
| Components | Buttons, modal, navbar, cards, alerts | Components → Buttons |
| Utilities | Spacing, display, flex, colors | Utilities → API |

Example: include Bootstrap via CDN

```html
<link
  href="https://cdn.jsdelivr.net/npm/bootstrap@5.3.3/dist/css/bootstrap.min.css"
  rel="stylesheet"
>
<script
  src="https://cdn.jsdelivr.net/npm/bootstrap@5.3.3/dist/js/bootstrap.bundle.min.js"
></script>
```

Example: grid layout

```html
<div class="container">
  <div class="row">
    <div class="col-12 col-md-8">Main</div>
    <div class="col-12 col-md-4">Sidebar</div>
  </div>
  <div class="row align-items-center mt-3">
    <div class="col-6">Left</div>
    <div class="col-6 text-end">Right</div>
  </div>
  <button class="btn btn-primary mt-3">Click me</button>
  </div>
```

### Other CSS Frameworks and Libraries

Summary

| Framework | Style | Highlights | Ideal for |
| --- | --- | --- | --- |
| Foundation | Component + grid | Robust, enterprise-ready; email styling tools | Complex, scalable sites |
| Pure.css | Minimal utility set | Very small size, fast load | Performance-critical UIs |
| Tailwind CSS | Utility-first | Fine-grained control; design system friendly | Rapid prototyping; custom designs |
| UIKit | Lightweight components | Simple, easily customizable | Small-to-medium projects |
| MVP.css | Classless CSS | Auto-styles native HTML elements | Quick prototypes, simple sites |