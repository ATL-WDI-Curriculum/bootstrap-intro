# Bootstrap

Screencasts:

- [Part 1](http://youtu.be/Nerq19rQFrc)
- [Part 2](http://youtu.be/iTeqXPIvgys)
- [Part 3](http://youtu.be/O-sh4Hb3FUw)

## Learning Objectives

- Explain the benefits (and shortcomings) of using a design framework.
- Describe the use cases for Bootstrap as a library versus as a framework.
- List 10 useful classes from the Bootstrap library.
- Compare and contrast Bootstrap with other design frameworks (e.g., Foundation and Material Design).

---

## Hook (5m)
Raise your hand if you have ever seen a bad website.  

What would you consider a 'bad site'?

Let's take a look at some bad website examples: http://www.topdesignmag.com/20-examples-of-bad-web-design/.  

In comparison, let's look at examples of sites that are built with bootstrap: https://bootstrapbay.com/blog/built-with-bootstrap/


Spend the next 3 minutes, reading through these two pages on why you should consider bootstrap:
https://css-tricks.com/bootstrap/
<br />
https://bootstrapbay.com/blog/reasons-to-use-bootstrap/

---

## Intro (5m)

> "Bootstrap is the most popular HTML, CSS, and JS framework for developing responsive, mobile first projects on the web."

Bootstrap provides visual themes for which a lot of the modern web is based. For example, the styling of Github's readmes and markdown files are based heavily on Bootstrap.

Bootstrap was born in 2011 as Twitter Blueprint. The fact that it is ubiquitious now speaks to how much it was needed: prior to Bootstrap, there were lots of mini-frameworks that you could use, but trying to run 35 stylesheets at the same time will induce a migraine.

As previously discussed, you can make the most amazing back-end functionality ever, but if the front-end doesn't look presentable you will have a difficult time selling it.

Unless you're specifically trying to show off your CSS skills, it is often better to spend 15 minutes making your app look great with Bootstrap than it is to spend 3 days writing your own CSS. Why?

The obvious reason is that one takes you 15 minutes, the other takes 3 days, and time is money. And of course, there are those clients who are non-tech-savvy and think you will have written all the CSS yourself no matter what you do.

Also, Bootstrap is written with responsive and/or mobile-first design approach, replacing hand-rolled media queries with more intuitive and semantic class names. Clients and employers of all levels of tech-savviness will appreciate that you've prioritized these qualities.

AND, unlike your hand-rolled CSS, Bootstrap is [well-documented](http://getbootstrap.com/) and therefore easily replicable and shareable throughout the development community.

---

## Getting Started

### Download Options

- You can grab it from a [CDN](http://getbootstrap.com/getting-started/#download-cdn).
  - Does anyone know what CDN stands for?

  A **Content Delivery Network** is a system of distributed servers that deliver content based on the user's geographic location.  A CDN can also provide protection from traffic serges.  Because these servers exist around the world, they can help speed up the process of getting the content to your end user.  **Speed** is the most important word in that sentence.  

``` html
<link rel="stylesheet" href="https://maxcdn.bootstrapcdn.com/bootstrap/3.3.6/css/bootstrap.min.css" integrity="sha384-1q8mTJOASx8j1Au+a5WDVnPi2lkFfwwEAa8hDDdjZlpLegxhjVME1fgjWPGmkzs7" crossorigin="anonymous">
```

``` html
<script src="https://maxcdn.bootstrapcdn.com/bootstrap/3.3.6/js/bootstrap.min.js" integrity="sha384-0mSbJDEHialfmuBBQP6A4Qrprq5OVfW37PRR3j5ELqxss1yVqOtnepnHVP9aJ7xS" crossorigin="anonymous"></script>
```

- You can [download the complied and minified CSS, JS, and fonts](http://getbootstrap.com/getting-started/#download) and include them manually in link and script tags.

- You can [download the uncompiled source code as SASS or LESS](http://getbootstrap.com/getting-started/#download) (which we'll touch on later), pick the components that you want, and compile the subset that you need.

### You Are Also Going to Need jQuery...

`<script src="https://cdnjs.cloudflare.com/ajax/libs/jquery/3.1.1/jquery.min.js"></script>`

…if you want to use any of Bootstrap's JS components.

- Does anything stand out from that url?

### Document Setup

Since Bootstrap is written with mobile in mind, they recommend configuring the viewport with this meta tag in the head of your html document:

``` html
<meta name="viewport" content="width=device-width, initial-scale=1.0">
```

This ensures "proper rendering and touch zooming". 

- **viewport**- gives the browser instructions on how to control the page's dimensions and scaling
- **width=device-width**- sets the width of the page to follow the screen-width of the device
  - this will vary by device
- **initial-scale=1.0**- sets the inital zoom level when the page is first loaded.

If you want to disable zooming on mobile devices, you can add:

``` html
<meta name="viewport" content="width=device-width, initial-scale=1.0, maximum-scale=1, user-scalable=no">
```

### Containers

Bootstrap requires that you organize site contents using one of two `"container"` classes:

- `<div class="container">` gives you a responsive, fixed-width container, with side margins.
- `<div class ="container-fluid">` creates a full width container that spans 100% of your viewport.

[This Bootply snippet](http://www.bootply.com/render/CK6xB6cRuE) demonstrates the difference between container and container-fluid.

Both types of containers are responsive, and both allow you to implement Bootstrap's grid system inside of them.

### Grid System Basics

The [Bootstrap grid](http://getbootstrap.com/css/#grid) is built on 12 columns, of `.col-[device size]-[number]` divs inside of `.row` divs, e.g.:

``` html
<div class="container">
  <div class="row">
    <div class="col-md-3"></div>
  	<div class="col-md-9"></div>
  </div>
</div>
```

The device sizes are:

- `xs` (phones, less than 768px)
- `sm`  (tablets, 768px and up)
- `md`(desktops, 992 px and up)
- `lg`(big desktops, 1200px and up)

The numbers indicate how many 1/12ths of the viewport width you would like that column to occupy, so `class="col-md-9 col-sm-12"` would be 9/12ths the width of a desktop screen, and 12/12ths the width of a tablet screen.

<br />

---

## We Never Go Out of Style...

### Out-of-the-box, Bootstrap styles some elements

For starters, Bootstrap implements baseline styles for links and typography, as well as using the styles from `normalize.css` to improve cross-browser performance. For instance, you'll notice changes with `<button>`, `<mark>`, `<code>`, `<samp>`, `<kbd>`, `<pre>`, `<abbr>`...

These are all standard HTML elements, and browsers have default styling for all of them. For instance, on pretty much every browser anything inside `<code>`, `<kbd>`, and `<pre>` will be in a monospace font.

### Out-of-the-box, Bootstrap *doesn't* style most elements

For instance, `<button>` with Bootstrap doesn't change too many properties, compared to your browser's default styling: it has square corners and a slightly different gradient, which goes a long way toward making it look "cleaner" and more "modern",  that's pretty much it.

The bulk of Bootstrap's customizing power lies in its dozens of components, which are implemented through a combination of CSS classes and jQuery plugins.

---

### YOU DO: Bootstravenger Hunt (20m)

As a class, we're going to compile an appendix to the Bootstrap documentation, providing tips and tricks on the implementation of some of Bootstrap's Greatest Hits.

**Group One**

- Popover
- Scrollspy
- Affix

**Group Two**

- Jumbotron
- Well
- Glyphicon

**Group Three**

- Badge
- Progress bar
- List groups

**Group Four**

- Navbar
- Dropdowns
- Panels

**Group Five**

- Carousel
- Modal
- Tooltip

Each group should create Codepen demo of their three components and write up the answers to the following questions for each:

- What is it?
- What's it good for?
- Where can I read more about it?
- Any tips/tricks for implementation? _(Think: What value can I add to the existing docs?")_

Be prepared to share! It may be helpful to split into subgroups so you can divide and conquer...

---

## Making it Your Own (15m)

### Customization

Some use "Bootstrap-y" as a perjorative — a shorthand for "generic and uninspired". I wonder what those people would say to [these](https://bootstrapbay.com/blog/built-with-bootstrap/) which we have seen, or [these](http://builtwithbootstrap.com/).

You can assemble a custom download or modify an existing configuration at http://getbootstrap.com/customize/

### Bootstrap-SASS

As many of you might have noticed when preparing your demos, implementing customized Bootstrap elements can easily get repetitive, lengthy and difficult to read. Straight Bootstrap also verges on violating separation of concerns, with all of those visually-oriented classnames muddying up your HTML.

For instance, if I wanted to make a small "delete" button, I'd write something like this:

``` html
<button class="btn btn-danger btn-xs">Delete</button>
```

That's a lot of `btn`'s...

#### ...so why does Bootstrap have such repetitive class names?

This is one place where you sort-of see Bootstrap trying to straddle the line between being a framework and being a library.

**You insert a library into your code; you insert your code into a framework.**

To explain the difference between a framework and a library a bit further, we are going to watch this short 3 minute video: https://www.youtube.com/watch?v=D_MO9vIRBcA

To reiterate, the differences between a library and framework can be summarized by The Hollywood Principle: "don't call us, we'll call you."

A framework encapsulates common application functionality, allowing the developer to focus on the parts that are unique to their application. Usually that means the developer writes pieces of code that get called by the framework when various things happen.  With a framework, we change the structure of our code according to the rules given by them, and use the functionality provided by them.

Libraries are packages of code that typically get called by your application to perform a task, like DOM manipulation or HTTP requests; jQuery, for example.  With a library, we can use the functionality directly without changing our code.

It is not unlikely that a developer using Bootstrap, will want to make their own CSS class called `.danger` that is completely unrelated to Bootstrap. It's extremely unlikely, however, that anyone is going to create their own class called `.btn-danger`.

Bootstrap works to be as unobtrusive as possible and not conflict with any classes users might be defining, so it engages in this sort of **classnamespacing**.

![Inversion of Control](https://qph.ec.quoracdn.net/main-qimg-590e2cd0dfea3a4466296e48167029ac-p)

The key difference between a library and a framework is **“Inversion of Control”**. When you call a method from a library, you are in control. But with a framework, the control is inverted: the framework calls you.

#### We can use SASS to DRY up our Bootstrap!

Bootstrap is written in LESS, which is like SASS, but it is written in Javascript ( there is also an [official SASS port!](http://getbootstrap.com/css/#sass)). [SASS](http://sass-lang.com/) stands for Syntactically Awesome Style Sheets. SASS is an extension of CSS.  SASS allows you to use variables for colors, nested rules, and even different variants of colors.  However, in order to use SASS, you need to have Ruby installed.  If you have a mac, Ruby comes pre-installed.  On a Linux or Windows computer, you will also need to install Ruby before using SASS.

The [Github README for bootstrap-sass](https://github.com/twbs/bootstrap-sass) details a number of ways to incorporate this "Sass-powered version of Bootstrap 3" into your applications.

Today, we're going to use [Bower](https://github.com/twbs/bootstrap-sass#c-bower):

- `npm install -g bower`

  - bower is used for managing front end components like html, css and js
  - `-g` means install this gem globally

<!-- - `gem install sass`
  
  - will install sass globally

- `gem list` -->

  - will list all of the local gems we have installed

- `mkdir case-study`
- `cd case-study`
<!-- - `bower install bootstrap-sass` -->

#### We Do: An InFORMED Case Study

First, touch an `index.html` that contains this form:

``` html
<form class="grumbleForm">
  <div class="form-horizontal">
    <fieldset class="form-group">
      <label class="control-label col-sm-2">Title:</label>
      <div class="col-sm-8"><input class="form-control" type="text" name="title" value="Harry Potter and the Sorcerer's Stone"></div>
    </fieldset>
    <fieldset class="form-group">
      <label class="control-label col-sm-2">By:</label>
      <div class="col-sm-8"><input class="form-control" type="text" name="authorName" value="J.K. Rowling"></div>
    </fieldset>
    <fieldset class="form-group">
      <label class="control-label col-sm-2">Content:</label>
      <div class="col-sm-8"><textarea class="form-control" name="content">Harry Potter's life is miserable. His parents are dead and he's stuck with his heartless relatives, who force him to live in a tiny closet under the stairs. But his fortune changes when he receives a letter that tells him the truth about himself: he's a wizard. A mysterious visitor rescues him from his relatives and takes him to his new home, Hogwarts School of Witchcraft and Wizardry.</textarea></div>
    </fieldset>
    <fieldset class="form-group">
      <label class="control-label col-sm-2">Photo URL:</label>
      <div class="col-sm-8"><input class="form-control" type="text" name="photoUrl" value="https://www.google.com/url?sa=i&rct=j&q=&esrc=s&source=images&cd=&ved=0ahUKEwj_vL3OianSAhVMKyYKHdZNAPcQjBwIBA&url=http%3A%2F%2Fd.ibtimes.co.uk%2Fen%2Ffull%2F237990%2Fjk-rowling.jpg&psig=AFQjCNEtVFa3Jdr687s4vwNxhxjJVsuywA&ust=1488037417080235"></div>
    </fieldset>
    <fieldset class="form-group">
      <label class="control-label col-sm-2">&nbsp;</label>
      <div class="col-sm-8">
        <button class="btn submit btn-primary">Submit</button>
        <button class="btn cancel">Cancel</button>
      </div>
    </fieldset>
  </div>
</form>
```

Then, touch a stylesheet called `form-styles.scss`  that contains this:

``` scss
@import "bower_components/bootstrap-sass/assets/stylesheets/_bootstrap.scss";

h1 {
    text-align: center;
    margin: 50px 0px; 
}

input,
textarea {
  @extend .form-control;
}
label {
  @extend .control-label;
}
fieldset {
  @extend .form-group;
}
.form-horizontal{
  label{
    @extend .col-sm-2;
  }
  div{
    @extend .col-sm-8;
  }
}
```

Also, touch `form-styles.css` and leave it blank.

Next, **and this is a big one**, in your terminal, run`sass form-styles.scss form-styles.css`. This command converts your sass to css, and add the converted cofe to your form-styles.css file.  Now I only need to `<link rel="stylesheet" href="form-styles.css" />` to load **all** of Bootstrap **plus** the changes you just made! Let's take a look at your CSS file...

Finally, remove all of the classes on your `div` elements, except for `"form-horizontal"` on the first one.

``` html
<form class="grumbleForm">
  <div class="form-horizontal">
    <fieldset>
      <label>Title:</label>
      <div><input type="text" name="title" value="Harry Potter and the Sorcerer's Stone"></div>
    </fieldset>
    <fieldset>
      <label>By:</label>
      <div><input type="text" name="authorName" value="J.K. Rowling"></div>
    </fieldset>
    <fieldset>
      <label>Content:</label>
      <div><textarea name="content">Harry Potter's life is miserable. His parents are dead and he's stuck with his heartless relatives, who force him to live in a tiny closet under the stairs. But his fortune changes when he receives a letter that tells him the truth about himself: he's a wizard. A mysterious visitor rescues him from his relatives and takes him to his new home, Hogwarts School of Witchcraft and Wizardry.</textarea></div>
    </fieldset>
    <fieldset>
      <label>Photo URL:</label>
      <div><input type="text" name="photoUrl" value="https://www.google.com/url?sa=i&rct=j&q=&esrc=s&source=images&cd=&ved=0ahUKEwj_vL3OianSAhVMKyYKHdZNAPcQjBwIBA&url=http%3A%2F%2Fd.ibtimes.co.uk%2Fen%2Ffull%2F237990%2Fjk-rowling.jpg&psig=AFQjCNEtVFa3Jdr687s4vwNxhxjJVsuywA&ust=1488037417080235"></div>
    </fieldset>
    <fieldset>
      <label>&nbsp;</label>
      <div>
        <button class="btn submit btn-primary">Submit</button>
        <button class="btn cancel">Cancel</button>
      </div>
    </fieldset>
  </div>
</form>
```

#### You Do: BootSassify the `btn` situation

--- 

## Questions to work on with your buddy (5m)

- What's the difference between a framework and a library?

- Name two Bootstrap classes and explain what they do.

- What's the difference between a glyphicon, a jumbotron and a Megatron?

- Give an example of a situation in which you might want to use Bootstrap, versus one in which you might not.

---

## Homework

Bootstrapify (or [Foundation](http://foundation.zurb.com)-ify or [Materialize](http://materializecss.com)-ify or [Picnic](http://picniccss.com)-ify or [Pure](http://purecss.io/)-ify or…) something that you built earlier in the course. If you don't want to overwrite your previous styling, you're welcome to work on an branch. Open an issue with a link to your re-styled homework/project/lab [here](https://github.com/ga-dc/bootstrap-ify).

---

## Helpful References

http://getbootstrap.com/components/

http://getbootstrap.com/css/

http://getbootstrap.com/customize/

https://github.com/twbs/bootstrap-sass

http://www.tutorialspoint.com/bootstrap/

http://bootsnipp.com/

http://tutorialzine.com/2015/06/12-time-saving-bootstrap-examples/

http://builtwithbootstrap.com/

https://bootstrapbay.com/blog/built-with-bootstrap/

https://scotch.io/bar-talk/bootstrap-3-tips-and-tricks-you-might-not-know

https://scotch.io/tutorials/understanding-the-bootstrap-3-grid-system

## CSS Style Guides

https://www.sitepoint.com/top-ten-css-tricks/

https://css-tricks.com/css-style-guides/

## Other libraries

http://tutorialzine.com/2014/07/20-impressive-css3-techniques-libraries-and-examples/
