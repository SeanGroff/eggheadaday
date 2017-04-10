## [Starting a Stream with SwitchMap](https://egghead.io/lessons/rxjs-starting-a-stream-with-switchmap?course=step-by-step-async-javascript-with-rxjs)

### Example
```javascript
/* Starting a Stream with SwitchMap */

const timerButton = document.getElementById('#btnTimer');

// Create click event stream
const clickEvent$ = Rx.Observable.fromEvent(timerButton, 'click');

// Create an Interval that fires every 1 second
const intervalTick$ = Rx.Observable.interval(1000);

// Map over EACH click event and run the intervalTick stream
const startInterval$ = clickEvent$
// switchMapTo is the same as switchMap(() => cb)
  .switchMapTo(intervalTick$);

// subscribe to the Stream logging out each event (interval)
startInterval$
  .subscribe(event => console.log(event));
```


### Tweet
<blockquote class="twitter-tweet" data-lang="en"><p lang="en" dir="ltr">Starting a Stream with SwitchMap - rx Video Tutorial <a href="https://twitter.com/hashtag/free?src=hash">#free</a> <a href="https://twitter.com/eggheadio">@eggheadio</a>: <a href="https://t.co/433x2fIAMU">https://t.co/433x2fIAMU</a><br>By: <a href="https://twitter.com/johnlindquist">@johnlindquist</a> <a href="https://twitter.com/hashtag/eggheadADay?src=hash">#eggheadADay</a> <a href="https://twitter.com/hashtag/RxJS?src=hash">#RxJS</a> 👌</p>&mdash; Sean Groff (@_SeanGroff) <a href="https://twitter.com/_SeanGroff/status/851475440313262082">April 10, 2017</a></blockquote>

### Github Contributor
[@SeanGroff](https://github.com/SeanGroff) :koala:

##### Date - 04/10/2017
___
