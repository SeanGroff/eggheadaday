# #eggheadADay

## How do I #eggheadADay?
- Watch one [egghead.io](egghead.io) lesson a day
- Tweet about it for personal accountability
- Reinforce your knowledge of what you learned by creating a pull request adding to this readme.

##### Note: Click the tweet share button from the [egghead.io](egghead.io) lesson to easily tweet about the lesson.

##### Note: Use the templates in the templates directory to save time. Embed your tweet into the template. Click the tweet options menu, select embed tweet, copy the provided code. Paste it into your post and strip out the script tag. DONT FORGET TO ADD #eggheadADay to the tweet.

### Contributions are encouraged to better this project!

# Daily Lessons

## [ES6 Rest Parameters](https://egghead.io/lessons/javascript-es6-rest-parameters?course=learn-es6-ecmascript-2015)

### Example
```javascript
/* ES6 Rest parameters vs ES5 arguments keyword */

(function () {
  /* ES5 arguments keyword example */
  var personalInfo = function (name, cellNumber, address, twitterHandle) {
    // The arguments keyword provides access to the functions parameters using array like syntax
    // Note: Not all array methods are available to arguments as arguments is "array like"
    console.log(arguments); // Output:
    // { '0': 'Bob Dole', '1': '555-555-5555', '2': '123 Main St. Chicago, IL 87654', '3': '@bobdole' }

    console.log(arguments[0]); // Bob Dole
    console.log(arguments[3]); // @bobdole
    console.log(arguments.length); // 4
  }

  personalInfo('Bob Dole', '555-555-1234', '123 Main St. Chicago, IL 87654', '@bobdole');

  /* ES6 Rest parameters example */
  const personalInfo2 = (name, ...theRestOfPersonalInfo) => {
    // Arrow functions cannot use the arguments keyword.
    console.log(arguments); // { }

    // Rest parameters are litterally "The rest of the parameters"
    console.log(name, theRestOfPersonalInfo); // Output:
    // 'Bob Dole', ['555-555-1234', '123 Main St. Chicago, IL 87654','@bobdole']
    console.log(name, theRestOfPersonalInfo[1]); // 'Bob Dole' '123 Main St. Chicago, IL 87654'
  }

  // Notice in the function declartion I have one named parameter 
  // then a Rest Parameter to grab the rest of values passed to this function.  
  personalInfo2('Bob Dole', '555-555-1234', '123 Main St. Chicago, IL 87654','@bobdole');
})();
```


### Tweet
<blockquote class="twitter-tweet" data-lang="en"><p lang="es" dir="ltr">ES6 Rest Parameters - js Video Tutorial <a href="https://twitter.com/hashtag/pro?src=hash">#pro</a> <a href="https://twitter.com/eggheadio">@eggheadio</a>: <a href="https://t.co/OyVWzYccBp">https://t.co/OyVWzYccBp</a> <a href="https://twitter.com/hashtag/eggheadaday?src=hash">#eggheadaday</a> <a href="https://twitter.com/hashtag/js?src=hash">#js</a></p>&mdash; Sean Groff (@SeanG816) <a href="https://twitter.com/SeanG816/status/842435671621042177">March 16, 2017</a></blockquote>

### Github Contributor
[@sgroff04](https://github.com/sgroff04) :koala:

##### Date - 03/16/2017
