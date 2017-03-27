## [Observables are almost like Functions](https://egghead.io/lessons/rxjs-observables-are-almost-like-functions?series=rxjs-beyond-the-basics-creating-observables-from-scratch)

### Example
```javascript
// Observables are almost like functions
const plainFunc = () => {
  console.log('Hello!');
  return 7;
};

console.log(plainFunc());

// RxJS Observable
const foo = Rx.Observable.create((observer) => {
  console.log('Observable!');
  // .next() returns a value
  observer.next(5);
  // .next() can be called more than once to return multiple values!
  observer.next('Whoa, more values returned!');
  // async works just fine too
  setTimeout(() => observer.next(`I'm asynchronous!`), 1000);
  observer.next('Functions can only return a single value, I can return all the things!');
});

// Observables are like functions in that if you don't express interest 
// by calling a function or subscribing to an observable nothing will happen.

// subscribing to an Observable is like calling a function
// A function returns a single value immediately
// Subscribing to an observable says give me values, maybe just one value, immediately, or asynchronously.
foo.subscribe((x) => {
  // x will always be the value passed through .next() in the Observable
  console.log(x);
});
```


### Tweet
<blockquote class="twitter-tweet" data-lang="en"><p lang="en" dir="ltr">GREAT EXPLANATION!<br>Observables are almost like Functions: rx Tutorial <a href="https://twitter.com/hashtag/pro?src=hash">#pro</a> <a href="https://twitter.com/eggheadio">@eggheadio</a>: <a href="https://t.co/vhNyLhtoRU">https://t.co/vhNyLhtoRU</a><br>By: <a href="https://twitter.com/andrestaltz">@andrestaltz</a> <a href="https://twitter.com/hashtag/eggheadADay?src=hash">#eggheadADay</a></p>&mdash; Sean Groff (@SeanG816) <a href="https://twitter.com/SeanG816/status/846375330415869954">March 27, 2017</a></blockquote>

### Github Contributor
[@sgroff04](https://github.com/sgroff04) :koala:

##### Date - 03/27/2017
___
