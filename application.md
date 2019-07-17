# Cro Metrics Front-End Engineering Application

Thanks for your interest in working with us! To apply:

- Create a "new _private_ gist" (link in github header once you're logged in) with the Raw Text of this .md file (**do not fork this gist**). Please name your gist `application.md` so that it's formatted correctly (not a .txt file)
- We're considering only US based applicants. We're also an all remote company who operates on thin margins to drive down the cost of testing for our clients. As such, we play to our strengths and hire outside more competitive markets like New York, San Francisco, and Washington State. We ask that you submit desired minimum rates so that we can move forward accordingly based on application quality. This will not lock you into those rates from a negotiation standpoint, but are rather used to help us all move forward knowing we're not outside what we can fit into our business model.
- Answer the following questions in the spaces provided respond to the email that linked you here with a link to your gist.
- Once we receive your submission and all looks well, we’ll reach out for next steps. If you have any questions / concerns about the process please reach out to brian.norman@crometrics.com. We're happy to address anything before you apply.

---

## Handling Clicks

Consider the following HTML:

```
<!DOCTYPE html>
<html lang="en">
<head>
  <!-- Custom click handler -->
  <script>
    window.myHandler = function() {
      console.log('Click!');
    };
  </script>
  <!-- jQuery -->
  <script src="https://ajax.googleapis.com/ajax/libs/jquery/3.1.0/jquery.min.js"></script>
  <script>
    /* YOUR CODE HERE */
  </script>
</head>
<body>
  <script src="https://slow.com/takes-2-seconds-to-load.js"></script>
  <div id="myDiv">OMG Click me!</div>
  <script>
    $('#myDiv').click(myHandler);
  </script>
</body>
</html>

```

**Question 1:**

What would you write in the `YOUR CODE HERE` section to add a click handler to the `#myDiv` element?

The handler should use `console.log()` to tell us something interesting about your development background, for example:

`console.log('I know FORTRAN lol long story');`.

Your response:

```
/* Question 1 Response Here */

$(document).ready(() => {
        $('#myDiv').click(() => {
          console.log('I prefer watching vidoe tutorilas to reading books ): ');
        });
      });
```

---

**Question 2:**

Rewrite your solution to Question 1. Make sure your `console.log()` executes every time a visitor clicks `#myDiv`, but _do not add another handler_ and retain the original behavior.

Your response:

```
/* Question 2 Response Here */

let formal = window.myHandler.bind(window.myHandler);
    window.myHandler = ()=> {
      formal();
       console.log('I prefer watching vidoe tutorilas to reading books ): ');
    };
```

---

## Modifying an element

**Question 3:**

Write code in `YOUR CODE HERE` that replaces 'OMG Click me!' with another string of your choosing. Use `requestAnimationFrame` and do not rely on DOM ready or load.

Your response:

```
/* Question 3 Response Here */

 let content = () => {
        document.body && document.querySelector('#myDiv')
          ? $('#myDiv').text('Coding marathon !!!')
          : window.requestAnimationFrame(content);
      };
      window.requestAnimationFrame(content);
```

---

## Regex fu

**Question 4:**

Our client, bacondelivery.com, is launching a test on all product pages -- for example:

- www.bacondelivery.com/weekly-bacon-delivery/
- www.bacondelivery.com/daily-bacon-delivery/
- www.bacondelivery.com/bacon-of-the-month-club/

Write a regular expression that will match the above URLs _and any similar pages_, but which _does not match_ the following:

- www.bacondelivery.com/ (the home page)
- www.bacondelivery.com/about/
- www.bacondelivery.com/contact-us/

Be sure that home page traffic containing query parameters is also excluded.

Your response:

```
/* Question 4 Regex Here */

/(bacondelivery\.com)\/(([\w]+\?[\w]+\=[\w]+\/?)?)(?!about\/?|contact-us\/?)([\w]+)((-[\w]+){1,})?$/
```

---

## Stylin'

**Question 5:**

Share a link to an original CodePen/JSFiddle that implements this:

![Boxes with hover animation](http://uploads.crometrics.com/7P8x/4F9VmEDq.gif)

Don't worry about pixel perfection; just eyeball it.

Your response:

```
/* Question 5 Link Here */

https://codepen.io/isaacelesia/pen/WqVyzW?editors=0110

```

---

## jQueryin'

**Question 6:**

How could you improve the following code?

```
$(document).ready(function() {
  $('.foo #bar').css('color', 'red');
  $('.foo #bar').css('border', '1px solid blue');
  $('.foo #bar').text('new text!');
  $('.foo #bar').click(function() {
    $(this).attr('title', 'new title');
    $(this).width('100px');
  });

  $('.foo #bar').click();
});
```

Your response:

```
/* Question 6 Code/Comments Here */

$(document).ready(() => {
        $('.foo #bar')
          .css({
            color: 'red',
            border: '1px solid blue'
          })
          .text('new text!');

        $('.foo #bar').click(() => {
          $('#bar')
            .css('width', '100px')
            .attr('title', 'new title');
        });
      });
```

---

## Behaviors

**Question 7:**

What code could run before the following statement that would make it evaluate to true?

```
'bc'.prefix('a') === 'abc';
```

Your response:

```
/* Question 7 Code/Comments Here */

String.prototype.prefix = function(str) {
          return str.concat(this);
        };
```
