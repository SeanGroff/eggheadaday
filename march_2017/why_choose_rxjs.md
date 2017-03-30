## [Reactive Programming - Why choose RxJS?](https://egghead.io/lessons/rxjs-reactive-programming-why-choose-rxjs)

### Example
```javascript
/* Why choose RxJS? */
console.clear();

/********
** Rx allows you to specify the dynamic behavior of a value completely, only once, at the time of the declaration.
*********
*/

// Opposite static example of this ^
console.log('Static examples');

let a = 3;
let b = 10 * a;
console.log(b); // -> 30

a = 4;
console.log(b); // -> 30

b = 11 * a;
console.log(b); // -> 44
// b doesn't accumlate over time like an event stream, it's value is whatever it is when it's assigned a value

/* ********************************************************************************************************* */

/* Observable */
console.log('Observable examples');

// Specify the behavior of streamA and streamB ONLY at the time of declaration!
const streamA = Rx.Observable.of(3, 4);
const streamB = streamA.map(a => a * 10);

//streamA.set(4); // NOPE! Add 4 to the declaration

/**
 * Reminder
 * subscribe can accept 3 callbacks in the following order
 * onNext(), onError, onCompleted
 */
streamB.subscribe(b => console.log(b)); // -> 30, 40
```


### Tweet
<blockquote class="twitter-tweet" data-lang="en"><p lang="en" dir="ltr">Reactive Programming - Why choose RxJS? - rx Video Tutorial <a href="https://twitter.com/hashtag/pro?src=hash">#pro</a> <a href="https://twitter.com/eggheadio">@eggheadio</a>: <a href="https://t.co/zOe1fxS1yE">https://t.co/zOe1fxS1yE</a><br>By: <a href="https://twitter.com/andrestaltz">@andrestaltz</a> <a href="https://twitter.com/hashtag/eggheadADay?src=hash">#eggheadADay</a> <a href="https://twitter.com/hashtag/RxJS?src=hash">#RxJS</a> <a href="https://twitter.com/hashtag/js?src=hash">#js</a></p>&mdash; Sean Groff (@_SeanGroff) <a href="https://twitter.com/_SeanGroff/status/847469103879077889">March 30, 2017</a></blockquote>

### Github Contributor
[@SeanGroff](https://github.com/SeanGroff) :koala:

##### Date - 03/30/2017
___
