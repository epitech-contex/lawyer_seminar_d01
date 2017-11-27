---
module:			DLA Piper
title:			Day 1
subtitle:		Simple page
background:		'./png/EpitechCapBackground.png'

repository: 	dla\_piper
repoRights:		gecko
language:		HTML, CSS, JS
groupSize:		1

noErrorMess:	true
noFormalities:  true
author:			Raphael Fourdrilis
version:		1.1
---

# Introduction

Welcome!

Today, we will show you an example of a very simple web page. The given wireframe only contains HTML (HyperText Markup Language), the key language in web development. We'll let you improve upon this simple page thanks to two other language, CSS (Cascading StyleSheet), which allows to customize you page style (colors, formatting ...), and JS (JavaScript), which allows a website to become dynamic ("responsive").


For any question, please first visit [this site](https://www.w3schools.com/html/), very well made. If, after your research, you still have doubts, we're at your disposal.


#hint(Crafting your request like this: '_ill understood topic_ W3Schools' will save you significant amounts of time.)

#hint(Given sources will show commentaries or FIXMEs to guide you.)

# Step 1 - Simple HTLM

For this step, we ask you to complete the existing page by adding __inside a text tag__ the following message:

	Hello World! The date is:

Still inside this tag, add an empty __span__, with the `clock` id:

```html
<span id="clock"></span>
```

Of course, we'll add the code printing the current date in following steps.

Right beneath this text, add two __button tags__:

- The firs tone will show 'Turn on the red light!'
- The second one will show 'Paint it black!'

In the same manner, we will link the buttons to their actions later.

#newpage

# Step 2 - HTML - Form and Table

## Form

Most websites will, at some point, need to ask some information to the user. This is called a __form__, allowing the user to enter text, images, documents... directly into the webpage. This information will, _in fine_, be gathered by a __server__ to bo stored and saved.
Today, we will simply store this information __locally__, or temporarily.

Add a __form containing three forms__:

- A text field to enter a name. This field is called `nameInput`
- A numeric field to enter an age. This field is called `ageInput`
- A numeric field to enter a participation amount. This field is called `participationInput`

Remember to associate each field with a __label__, as well as a __submit button__ at the end of the form.

## Table

Now that the user can enter some information, we can print them! We will see how to print them dynamically later. For now, add an __HTML table__:

- The first line is the __table header__, composed of three columns (one per field, in the same order)
- The following lines will be added dynamically later.

#newpage

# Step 3 - Javascript and simple CSS

## CSS

CSS is a very simple but flexible language, allowing to format a web page easily. For instance, the website we have here is nowhere near responsive: it doesn't adapt to screen size, nor does it adapt to different devices (iPhone, tablet, pc ...).
To fix this, the world wide web gives some simple and efficient __CSS directives__:

- Add a tag defining the __viewport__ of your webpage.
- In the given CSS file, add a selector for the whole __body__ of your page.
- Add those directives in the previous selector:

```html
	display: flex;
    flex-direction: column;
    align-content: center;
    align-items: center;
```

We won't spend too much time explaining each of them; just be aware we are using [flexbox](https://css-tricks.com/snippets/css/a-guide-to-flexbox/), and that it allows to layout a webpage really easily and in a flexible manner. Usually, they are explicit enough so that you understand what they do. But feel free to browse the given link for more explanation. Mastering this technology can become really time-consumming though.

## JavaScript

#warn(For this step\, it is primordial that you __correctly identify your HTML tags__.)

#hint(The `id` attribute is your friend.)

Now that we have the static wireframe of our page, let's make it dynamic. We'll start bu adding actions to our buttons. For this tutorial purposes, we give you the code for the 'Paint it Black!' button.

```js
document.getElementById('toBlackButton').onclick = function dateToBlack() {
    document.getElementById('clock').classList.add("black");
    document.getElementById('clock').classList.remove("red");
};
```

JavaScript is a dynamic and flexible (sometimes too flexible...) allowing to manipulate you page elements __in real time__; HTML being a simple markup language, interpreted only once on page load, it doesn't allow dynamic actions by itself. It is just an ingredient list. JavaScript is the 'recipe' part, how you chain actions, what are their effects, etc...#br

`document` reprensents our page. We call the `getElementById` function, which does exactly as advertised: it gets the element with the id passed as parameter.
`on-click` is an __event__: in most cases, it represents some user action. Generally, an event is an action that comes 'from the outside', from another part of the program, from a different source ... We assign (fill) this event with a function, called `dateToBlack`, which also gets another element in our page, in order to manipulate its `classes`. Understand __CSS class__ here, a way to identify our elements to style them more easily from CSS. Refer to W3Schools and the given source code to understand the link between __CSS classes__ and __HTML Attributes__.

#hint(Traditionally\, we wouldn't put JavaScript directly inside the HTML page\, but in its own files instead\, referenced via specific tags. Today\, for clarity reasons\, we'll make everything fit in one HTML and CSS file.)

Following the same pattern than the given function, bind a function to the `on-click` envent of our other button, which will color the date in red.

#hint(Don't forget to remove the 'black' class!)

#newpage

# Step 4 - JavaScript form

Our form doesn't do anything yet. Check the code in step4: the `validateForm` function checks that the user didn't leave any field blank before submitting the form. If everything went fine, it returns a list of what the user typed in, or an empty list otherwise.

Then, check the `addToTable` function. This one is called when the user clicks on the form's submit button, checks the form's content thanks to the previous function, then fills the table with the newly formed data.

Following the given example, fix the end of the function so that the two other fields (age and participation) get their value added to a new line in the table.

# Step 5 - CSS Framework

This step is just what you could see when using a __CSS framework__, a (huge) list of prebuilt CSS selectors allowing you to style your elements just by adding a class to them.
The one we use here is called [MDL](https://getmdl.io/started/), and implements Google's Material Design. Take time to see how the elements have been modified compared to the previous step: some simple modifications to the `class` attribute and your page suddenly is material!

Other CSS frameworks exist, especially [Bootstrap](https://getbootstrap.com/) or [Foundation](https://foundation.zurb.com/).
