# WEEK 9

## FLASK

It is a microframework that is used to make it easier for us to write code. It allows us to only implement the conventions that we care about and the application does the rest.

### app.py

```python
from flask import Flask, render_template, request

app = Flask(__name__)

@app.route("/")
def index():
    return "hello, world"
```

We can return a full string of HTML.

We can use `render_template` to create and add an HTML file to the `app.py` file so that it returns exactly what is in the HTML file. First create a `templates` folder and create the HTML file in it.

```python
@app.route("/")
def index():
    return render_template("index.html")
```

To have a more interactive program where we can have a program that takes a person's name and returns `"hello <plus the name>"`:

```python
from flask import Flask, render_template, request

app = Flask(__name__)

@app.route("/")
def index():
    name = request.args["name"]
    return render_template("index.html", placeholder=name)
```

In `index.html`, `"hello, world"` will be changed to:

```html
hello, {{ placeholder }}
```

Jinja is a templating library used with Flask.

So that the name does not only have to be passed in the URL, the code is modified to:

```python
@app.route("/")
def index():
    if "name" in request.args:
        name = request.args["name"]
    else:
        name = "world"

    return render_template("index.html", placeholder=name)
```

I can also do:

```python
name = request.args.get("name", "world")
```

We get the name and if there is no name, we get the default value of `"world"`.

We can also add a form to the HTML file that we will use to get the name.

The GET method puts the input and everything in the URL an  using POST removes the key-value pair from the URL.

When using POST, we move from `request.args` to `request.form`.

### Templates

Flask looks for HTML files inside the `templates` folder.

We can pass Python variables into an HTML template using Jinja:

```python
return render_template("index.html", name=name)
```

Then in the HTML:

```html
<h1>Hello, {{ name }}</h1>
```

Jinja allows us to put Python-like logic inside HTML.

For example, we can use an `if` statement:

```html
{% if name %}
    <h1>Hello, {{ name }}</h1>
{% else %}
    <h1>Hello, world</h1>
{% endif %}
```

We can also use loops in a template:

```html
{% for name in names %}
    <p>{{ name }}</p>
{% endfor %}
```

### Static files

HTML files are not the only files a Flask application can use.

CSS, JavaScript and images are called static files.

These are normally placed inside a `static` folder.

```text
project/
├── app.py
├── templates/
│   └── index.html
└── static/
    ├── styles.css
    └── script.js
```

We can link to a static file using `url_for`:

```html
<link href="{{ url_for('static', filename='styles.css') }}" rel="stylesheet">
```

### Layouts

If multiple HTML pages have the same navigation bar or other parts of the page, we do not need to repeat the same HTML in every file.

We can create a base template and let other templates inherit from it.

The base template can have:

```html
{% block body %}{% endblock %}
```

Then another page can use:

```html
{% extends "layout.html" %}

{% block body %}
    <h1>Hello!</h1>
{% endblock %}
```

This allows us to reuse the same HTML structure across different pages.

### Forms

A form can send information to the Flask application.

For example:

```html
<form action="/" method="post">
    <input name="name">
    <button type="submit">Submit</button>
</form>
```

The Flask route can then get the submitted value:

```python
name = request.form.get("name")
```

Using `.get()` is useful because it allows us to provide a default value instead of getting an error when the value is missing.

### Redirects

Instead of returning a page directly after something happens, Flask can redirect the user to another route.

```python
from flask import redirect, url_for
```

Then:

```python
return redirect("/")
```

`url_for` can also be used to refer to a Flask route instead of manually writing the URL.

### Sessions

A session allows Flask to remember information about a user between requests.

This can be useful for things like:

- remembering that a user is logged in
- storing a username
- keeping track of information while the user moves between pages

We can use:

```python
from flask import session
```

and store a value:

```python
session["name"] = name
```

Then we can access it later with:

```python
session["name"]
```

### Databases

Flask applications can also work with databases.

We can use SQL to store and retrieve information instead of keeping everything in Python variables.

This allows an application to keep data even after the program stops running.

For example, a database could store:

- users
- passwords
- products
- transactions
- application data

The Flask application can receive information from a form, use SQL to work with the database, and then return the result through an HTML template.
