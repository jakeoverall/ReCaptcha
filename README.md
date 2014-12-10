Google's New Recaptcha
=======================


###Using Angular and Node

I was curious as to how googles new recaptcha service worked so I created a simple form to test it out. Using angular and node with express it is pretty easy to put it together. A few things I learned Google will only verify the response code once if you try to submit the form multiple times it will not be allowed more than once. Also you can hack the form submission by doing something simple like this in your console.

`````javascript
  grecaptcha.getResponse = function(){
    return "banana"
  };
`````
This is why it is important that you have your server or backend make the get request with the response string because google will send back JSON with a success key either set to true or false depending on this string. Don't rely on the captcha response only for form submission.

###Test it out

Fork or clone this repo then

  $ npm install

  $ node server.js

go to localhost:8881 in your favorite browser