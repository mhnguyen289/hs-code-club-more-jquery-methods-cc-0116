# Traffic Light

<img src="https://s3.amazonaws.com/after-school-assets/traffic_light.gif" hspace="10" align="right" width="300px">

There are so many jQuery methods that we couldn't possibly cover them all in just one lesson. You are going to use even more to build a fully functioning traffic light. 

## Let's Get Started

### Step 1:

Click `Open` at the top of this page to bring this lesson down so you can edit files in Nitrous.

<img src="https://s3.amazonaws.com/after-school-assets/new-open-in-nitrous.png">

### Step 2:

Open `index.html` in the browser by running in terminal `python -m SimpleHTTPServer 3000`. 

Once you have the server running, select `preview` and then `port 3000`.

<img src="https://s3.amazonaws.com/after-school-assets/nitrous-preview.png" alt="nitrous preview">


### Step 3:

You're going to code your solution in `js/script.js`. Go ahead and open that file in the Nitrous text editor, as well as `index.html`. You shouldn't need to make any changes to `index.html` in order to code your solution. Don't worry about the code in `css/styles.css`. All the styling has be written for you, and will work perfectly if you don't change the HTML.

In `js/script.js`, we've set up the code for the first two traffic light buttons, but your job is to fill in the rest.

### Step 4:

Take a look at `index.html` in the browser. You should see something like this:

<img src="https://s3.amazonaws.com/after-school-assets/traffic-light-lab.png">

Try clicking the `Turn Red` and `Say Stop` buttons. You should see the red light turn on and the words "STOP" appear. Try the rest of the buttons. They shouldn't work. Your job is to code the solution to make the rest of the buttons work.


### Step 5:

Let's start with the `Turn Yellow` button. You know you need a click event that will be triggered when the user clicks the button. If you look at the HTML, you can see the button has an ID of `button3` which you can use as our jQuery selector.

```html
 <button id="button3">Turn Yellow</button>
```

So basically you need to write jQuery that has a click event on that ID. Copy the jQuery below and paste it in `js/script.js` below the comment `/* code for button 3 -- Turn the light Yellow */`:

```js
$('#button3').click(function() {
  //code for yellow light goes here
});
```

Now, you need to write the code that will be trigged when the user does click the button - which is to fill in the background of the middle light with the color yellow.

If you look at the HTML, you see the following:
```html
<span id="middle-light"></span>

```

The middle light is a span with the ID `middle-light` which you can use as our jQuery selector to change the light color.

You can use the jQuery method `css` to change the CSS. This method needs to know what CSS to add to the HTML, and in this case you want to use the CSS `background` property with the value `yellow`. Copy the jQuery below and paste it below the comment `//code for yellow light goes here`:

```js
  $("#middle-light").css("background", "yellow")
```

Save your changes to `js/script.js` and refresh in the browser. Try clicking the `Turn Yellow` button. You should see the yellow light come on!


### Step 6:

Now let's tackle the `Turn Green` button. You're going to follow the exact same pattern as the yellow light to achieve this.

If you look at the HTML for the button, you see:

```html
<button id="button4">Turn Green</button>
```

You'll notice this button has an ID `button4` which you can use as your jQuery selector to trigger the click event.

Copy the jQuery below and paste it under the comment `/* code for button 4 -- Turn the light Green */`:

```js
 $('#button4').click(function() {
  //code for green light goes here
 });
```

Now take a look at the HTML for the yellow light:

```html
<span id="bottom-light"></span>
```

This time you'll notice a span with the ID `bottom-light`. Again, this ID will be our jQuery selector to change the light to green. Also again, we can use the jQuery `css` method and give it the property (`background`) and value (`green`). 

Copy the jQuery below and paste it in `js/script.js` underneath the comment `//code for green light goes here`:

```js
$("#bottom-light").css("background", "green")
```

Save your changes to `js/script.js` and refresh the page in the browser. Click the `Turn Green` button and watch it light up!


### Step 7:

Now it's time to make the word "GO" appear on the green light.

First, you need to set up a click event on the button `Say Go`. The HTML for this button has the ID `button5` which will be our jQuery selector for the click event.

Copy the jQuery below and paste it in `js/script.js` where you see the comment `/* code for button 5 -- Say GO! */`:

```js
$('#button5').click(function() {
//code for GO goes here
});
```

Now that you've got the click event, it's time to write the code to make the words appear. Just in like the `Say Stop` button, you're going to use the jQuery `html` method. This method will add HTML to any part of the page you call the method on, it just needs to know what HTML you want to add. In this case we want to add `<p> GO </p>`.

In this case, we want to add the HTML to the `span` with the ID `bottom-light` to make the text appear in the light.

```js
$("#bottom-light").html("<p> GO </p>")
```

Save your changes to `js/script.js` and refresh in the browser. Test the `Say Go` button and watch the text appear in the light!

### Step 8:

Now It's time to make the light blink red. You first need to set up a click event on the very last button `Blink Red`. This button has the ID  `button6` which you can use as your jQuery selector.

Copy the jQuery below and paste it in `js/script.js` where you see the comment `/* code for button 6 -- Make Green Light Blink -- Extension!! */`:

```js
$('#button6').click(function() {
  //code for blink red goes here
});
```

Next, you need to write the code that will make the light blink. First, the background needs to appear red. Go ahead and copy the code from the very first button to make the light appear red and paste it below the comment `  //code for blink red goes here`
 

```js
$('#top-light').css("background", "red");
```
Next, in order to make the light blink you'll be using the `fadeIn` and `fadeOut` jQuery methods. The `fadeOut` method makes a visible element hidden, and the `fadeIn` method makes a hidden element visible. Copy the jQuery below and paste it in `js/script.js` directly below the code to make the red light appear:

```js
$("#top-light").fadeOut();
$("#top-light").fadeIn(); 
```

We want to have the light `fadeOut` before the light `fadeIn` so that the background color will first appear, then disappear, and then appear again.

Your final code for the `Blink Red` button should look like this:

```js
$('#button6').click(function() {
  //code for blink red goes here       
  $('#top-light').css("background", "red");
  $("#top-light").fadeOut();
  $("#top-light").fadeIn();     
});
```

Save your changes to `js/script.js` and refresh in the browser. All six buttons should work now!

## Done and Done

Lastly, you need to enter in terminal in Nitrous `learn submit`. This command will push your work to GitHub and mark this lesson as complete in Learn!

## Share Share Share!
Show of your work by taking a screenshot of your filled treasure box or code and share with **\#flatironcodeclub** and **\#jQueryTrafficLight**

## Reminder 

Don't forget to shut down your server by hitting `control` and `c` before you move on to other material!










<a href='https://learn.co/lessons/hs-code-club-more-jquery-methods' data-visibility='hidden'>View this lesson on Learn.co</a>
