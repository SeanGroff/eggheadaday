## [Reactive Programming - Async requests and responses in RxJS](https://egghead.io/lessons/rxjs-04-reactive-programming-async-requests-and-responses-in-rxjs)

### Example
```javascript
/* Async requests and responses in RxJS */

// checkout the fetch docs on MDN for more information
const fetchEndpoint = url => fetch(url)
    .then(response => response.json());

// Create an Observable of just the URL string
const request$ = Rx.Observable.of('https://api.github.com/users');
// think of .switchMap as .then() from a Promise
const response$ = request$.switchMap(url => Rx.Observable.fromPromise(fetchEndpoint(url)));

// subscribe to the response Observable and console log the response object for each response
response$.subscribe(response => console.log(response));
```

### Tweet
<blockquote class="twitter-tweet" data-lang="en"><p lang="en" dir="ltr">Try fetch()<br><br>Async requests and responses in RxJS - rx Video Tutorial <a href="https://twitter.com/hashtag/pro?src=hash">#pro</a> <a href="https://twitter.com/eggheadio">@eggheadio</a>: <a href="https://t.co/a7pktH6nUJ">https://t.co/a7pktH6nUJ</a><br>By: <a href="https://twitter.com/andrestaltz">@andrestaltz</a> <a href="https://twitter.com/hashtag/eggheadADay?src=hash">#eggheadADay</a></p>&mdash; Sean Groff (@_SeanGroff) <a href="https://twitter.com/_SeanGroff/status/847878631699468289">March 31, 2017</a></blockquote>

### Github Contributor
[@SeanGroff](https://github.com/SeanGroff) :koala:

##### Date - 03/31/2017
___
