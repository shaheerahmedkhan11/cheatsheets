# HTML Cheatsheet

## Basic Structure
```html
<!DOCTYPE html>
<html>
<head>
    <title>Page Title</title>
</head>
<body>

<h1>This is a Heading</h1>
<p>This is a paragraph.</p>

</body>
</html>
```

## Text Formatting
```html
<b>Bold</b>
<strong>Strong</strong>
<i>Italic</i>
<em>Emphasized</em>
<small>Small</small>
<mark>Marked</mark>
<del>Deleted</del>
<ins>Inserted</ins>
<sub>Subscript</sub>
<sup>Superscript</sup>
```

## Links
```html
<a href="https://www.example.com">This is a link</a>
<a href="https://www.example.com" target="_blank">Open in new tab</a>
<a href="#section1">Jump to Section 1</a>
```

## Images
```html
<img src="image.jpg" alt="Description of image">
<img src="image.jpg" alt="Description of image" width="300" height="200">
```

## Lists
### Unordered List
```html
<ul>
  <li>Item 1</li>
  <li>Item 2</li>
  <li>Item 3</li>
</ul>
```

### Ordered List
```html
<ol>
  <li>First item</li>
  <li>Second item</li>
  <li>Third item</li>
</ol>
```

### Description List
```html
<dl>
  <dt>Term 1</dt>
  <dd>Description 1</dd>
  <dt>Term 2</dt>
  <dd>Description 2</dd>
</dl>
```

## Tables
```html
<table>
  <tr>
    <th>Header 1</th>
    <th>Header 2</th>
  </tr>
  <tr>
    <td>Data 1</td>
    <td>Data 2</td>
  </tr>
  <tr>
    <td>Data 3</td>
    <td>Data 4</td>
  </tr>
</table>
```

## Forms
```html
<form action="/submit-form" method="post">
  <label for="fname">First name:</label><br>
  <input type="text" id="fname" name="fname"><br>
  <label for="lname">Last name:</label><br>
  <input type="text" id="lname" name="lname"><br>
  <input type="submit" value="Submit">
</form>
```

## Input Types
```html
<input type="text" placeholder="Text Input">
<input type="password" placeholder="Password">
<input type="email" placeholder="Email">
<input type="number" placeholder="Number">
<input type="date">
<input type="checkbox"> Checkbox
<input type="radio"> Radio
<input type="submit" value="Submit">
```

## Media
### Audio
```html
<audio controls>
  <source src="audio.mp3" type="audio/mpeg">
  Your browser does not support the audio element.
</audio>
```

### Video
```html
<video width="320" height="240" controls>
  <source src="movie.mp4" type="video/mp4">
  Your browser does not support the video tag.
</video>
```

## Semantic Elements
```html
<header>
  <h1>Header</h1>
</header>

<nav>
  <ul>
    <li><a href="#home">Home</a></li>
    <li><a href="#about">About</a></li>
  </ul>
</nav>

<main>
  <h2>Main Content</h2>
</main>

<footer>
  <p>Footer</p>
</footer>
```

## Comments
```html
<!-- This is a comment -->
```