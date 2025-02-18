# jQuery Cheat Sheet

## Basic Syntax
```javascript
$(selector).action();
```

## Document Ready
```javascript
$(document).ready(function() {
    // code here
});
```

## Selectors
```javascript
// Select by ID
$("#id");

// Select by class
$(".class");

// Select by element
$("element");

// Select all elements
$("*");

// Select multiple elements
$("element1, element2, element3");

// Select the first matched element
$("selector:first");

// Select the last matched element
$("selector:last");

// Select even elements
$("selector:even");

// Select odd elements
$("selector:odd");
```

## Events
```javascript
// Click event
$("selector").click(function() {
    // code here
});

// Double-click event
$("selector").dblclick(function() {
    // code here
});

// Mouse enter event
$("selector").mouseenter(function() {
    // code here
});

// Mouse leave event
$("selector").mouseleave(function() {
    // code here
});

// Hover event
$("selector").hover(
    function() {
        // mouse enter
    },
    function() {
        // mouse leave
    }
);

// Focus event
$("selector").focus(function() {
    // code here
});

// Blur event
$("selector").blur(function() {
    // code here
});
```

## Effects
```javascript
// Hide element
$("selector").hide();

// Show element
$("selector").show();

// Toggle visibility
$("selector").toggle();

// Fade in
$("selector").fadeIn();

// Fade out
$("selector").fadeOut();

// Slide up
$("selector").slideUp();

// Slide down
$("selector").slideDown();

// Slide toggle
$("selector").slideToggle();
```

## CSS Manipulation
```javascript
// Get CSS property
$("selector").css("property");

// Set CSS property
$("selector").css("property", "value");

// Add class
$("selector").addClass("class");

// Remove class
$("selector").removeClass("class");

// Toggle class
$("selector").toggleClass("class");
```

## HTML Manipulation
```javascript
// Get HTML content
$("selector").html();

// Set HTML content
$("selector").html("new content");

// Get text content
$("selector").text();

// Set text content
$("selector").text("new content");

// Append content
$("selector").append("content");

// Prepend content
$("selector").prepend("content");

// Remove element
$("selector").remove();

// Empty element
$("selector").empty();
```

## Attributes
```javascript
// Get attribute value
$("selector").attr("attribute");

// Set attribute value
$("selector").attr("attribute", "value");

// Remove attribute
$("selector").removeAttr("attribute");
```

## Traversing
```javascript
// Parent element
$("selector").parent();

// All ancestor elements
$("selector").parents();

// Direct child elements
$("selector").children();

// Find elements
$("selector").find("childSelector");

// Next sibling element
$("selector").next();

// Previous sibling element
$("selector").prev();
```

## AJAX
```javascript
// Load data from server and place into matched element
$("selector").load("url");

// Perform an AJAX GET request
$.get("url", function(data) {
    // code here
});

// Perform an AJAX POST request
$.post("url", { key: "value" }, function(data) {
    // code here
});

// Perform a custom AJAX request
$.ajax({
    url: "url",
    type: "GET/POST",
    data: { key: "value" },
    success: function(data) {
        // code here
    }
});
```

## Utilities
```javascript
// Each function
$.each(array, function(index, value) {
    // code here
});

// Trim whitespace
$.trim(" string ");

// Parse JSON
$.parseJSON('{"key":"value"}');
```