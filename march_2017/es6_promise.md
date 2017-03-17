## [Promises with ES6](https://egghead.io/lessons/ecmascript-6-promises-with-es6)

### Example
```javascript
/**
 * Promises with ES2015
 * Promises allow you to perform async behaviors in a sync manner.
 */

//Promise accepts a callback function, the callback has 2 parameters, resolve & reject.
const p = new Promise((resolve, reject) => {
  // switch true to false to test Promise reject()
  if (true) {
    resolve('Success');
  } else {
    reject('Rejected');
  }
});

// When a Promise is resolved the .then() will fire.
// then() accepts a callback method (I know....just use .then() and .catch() though :P)
p.then((data) => {
  // data is the argument passed into the resolve() method.
  console.log(data);
});

// When a Promise is rejected the .catch() will fire.
// if an Error occurs ANYWHERE in the Promise the .catch() will fire.
p.catch((error) => {
  // error is the argument passed into the catch() method.
  console.log(error);
});

/**
 * Let's chain the Promise methods
 */
const d = new Promise((resolve, reject) => {
  // switch true to false to test reject and the catch method.
  if (true) {
    resolve('Promise was resolved!');
  } else {
    reject('Promise was rejected :(');
  }
})
  .then((data) => {
    console.log(`Success : ${data}`);
    return 'foo bar';
  })
  .then((data) => {
    // What will data be here? What if there was no return statement in the previous .then() ?
    console.log(`I wonder what data will be? : ${data}`);
  })
  .catch(error => console.log(`Error : ${error}`));
```


### Tweet
<blockquote class="twitter-tweet" data-lang="en"><p lang="en" dir="ltr">Promises with ES6 - js Video Tutorial <a href="https://twitter.com/hashtag/free?src=hash">#free</a> <a href="https://twitter.com/eggheadio">@eggheadio</a>: <a href="https://t.co/SpIvnk4UAq">https://t.co/SpIvnk4UAq</a><a href="https://twitter.com/hashtag/eggheadADay?src=hash">#eggheadADay</a> <a href="https://twitter.com/hashtag/js?src=hash">#js</a></p>&mdash; Sean Groff (@SeanG816) <a href="https://twitter.com/SeanG816/status/842757415695278080">March 17, 2017</a></blockquote>

### Github Contributor
[@sgroff04](https://github.com/sgroff04) :koala:

##### Date - 03/17/2017
___
