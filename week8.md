# CS50 WEEK 8

## HTML, CSS AND JavaScript

The internet is a network of computers. Packets of infomation are sent over the internet. 
All devices speak a protocol language called TCP/IP. IP gives every device a unique ip address to identify it on the internet. The identifier is known as an ip address. Ip v4 addresses have 32 bits. IP v6 addresses have 128 bits. 
TCP allows devices to uniquely identify services being offered. This helps the computer know if they are recieving an email, webpage, etc. this comes in the form of port numbers on the packet.
TCP allows devices handle multiple types of services and send and recieve information efficiently.
DNS is a type of server that translates domain names into their corresponding ip addresses.
DHCP is a server that answer questions of the form, what is my ip address? the ip address of my DNS server, etc.
HTTP is a web protocol. something.something is a domain name. .com is a top level domain name. There are a lot of them in the world though. 
Hostname (www.) refers to the name of the server you are requesting.
scheme or protocol being used (https)
https://www.example.com

## HTML

An element includes a start or open tag and an end or close tag.
An attribute has an element name and a value separated by an equal to. The end or close tag have / after the angle bracket before the tag name. Eg:`</html>`
We use `<p></p>` for paragraphs in html, `<h1></h1>` for headings. For headings, we have from h1 to h6 from the boldest to the least bold heading.

### List
We have `<ul></ul>` for unordered list for the bolded list and in that we have `<li></li>` for the list items.
`<ol></ol>` is used for ordered list with the `<li></li>` for the list of items.

### table
We have `<table></table>` and in that, we input `<tr></tr>` for each table row and `<td></td>` each table data.

### Images
To add an image to an html file we add `<img alt="harvard university" scr='image link'>`. The alt adds a text discription to the image that is displayed when the image is slow to load. 
`<img>` is an empty tag and hence does not require a close tag.

### Video
`<video controls muted>`
`    <source src="video.mp4" type="video/mp4">`
`</video>`
the controls attribute does not need a value. Adding a muted attribute can start the video muted.

### Link
`<a href="https://www.harvard.edu/"> Harvard </a>`. This can be easily used to mislead people to the wrong website and can be used for phising attacks.

### Regular expressions
Regexes for short are syntaxes that exist in a lot of programing languages. They ate short hand notations.
`.`      any single character
`*`      zero or more times
`+`      one or more times
`?`      o or 1 time
`{n}`    n occurences
`{n,m}`  at least n occurences, at most m occurences
`[012]`  any one of the enclosed characters
`[0-9]`  any one of the range of characters
`\d`     any digit
`\D`     any character that is not a digit

Validator.w3.org is a website used to validate or make sure our html is correct or has no syntax errors.

## CSS
Cascading Styles Sheet is used to style a website or design a website and add styles and design to the plain html website.

### Properties
They are key value pairs in css.
`&#169;` is used to denote the copywrite symbol in the html website.

## JavaScript
JavaScript is usually put at the end of the body right before the closing tag so that whatever part of the html the JavaScript will be modifying already exists.
 

## Shorts and Sections

The DOM (Document Object Model) represents an HTML page as a tree of elements, which allows JavaScript to access and modify the content of a webpage.

CSS selectors can be used to target specific HTML elements, classes, or IDs so that different parts of a webpage can have different styles.

JavaScript can respond to events such as button clicks and use the DOM to change elements on the page. This is what allows webpages to become interactive rather than just displaying static content.We’ll add the specific new points from the Shorts and Sections here, while leaving out anything that is already in the lecture notes.