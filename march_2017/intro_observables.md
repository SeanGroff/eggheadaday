## [Introducing the Observable](https://egghead.io/lessons/javascript-introducing-the-observable)

### Example
```javascript
/* Introducing the Observable */

/**
 * An Observable is like an Array.
 * With an Array all data is stored in memory and has the data ready to pop-out synchronously.
 * An Observable is a collection of data where no data is stored in memory and the items arrive over time asynchronously.
 */

/* DOM Event Example */

// DOM events are very similiar to Observables.
const button = document.getElementById('btn');

// Event handler
const handler = (e) => {
  console.log('clicked');
  // removes or "Unsubscribes"
  button.removeEventListener('click', handler);
}

/**
 * @param Name of event
 * @param callback function
 */
button.addEventListener('click', handler);

/* Observable Example */

const obsButton = document.getElementById('obsBtn');

// An Observable is more powerful because it gives us an object to represent that Event Stream!
const clicks = Rx.Observable.fromEvent(obsButton, 'click');

// Since Observables are asynchronous unlike Arrays the native Array forEach method will not work. Subscribe accepts 3 callbacks.
const subscription = clicks.subscribe(
  // 1) onNext
  (e) => {
    console.log('click!');
    // We don't care about anymore onNext method or any callbacks
    subscription.unsubscribe();
  },
  // 2) onError
  (err) => console.log('ERROR! ', err),
  // 3) onCompleted
  () => console.log('Done!')
);
```

### Tweet
<blockquote class="twitter-tweet" data-lang="en"><p lang="en" dir="ltr">Introducing the Observable - js Video Tutorial <a href="https://twitter.com/hashtag/free?src=hash">#free</a> <a href="https://twitter.com/eggheadio">@eggheadio</a>: <a href="https://t.co/OxxBAKtdCv">https://t.co/OxxBAKtdCv</a><br>By: <a href="https://twitter.com/jhusain">@jhusain</a> <a href="https://twitter.com/hashtag/eggheadADay?src=hash">#eggheadADay</a> <a href="https://twitter.com/hashtag/RxJs?src=hash">#RxJs</a><br>Observables are 🔥‼️</p>&mdash; Sean Groff (@SeanG816) <a href="https://twitter.com/SeanG816/status/846751030138327040">March 28, 2017</a></blockquote>

### Github Contributor
[@sgroff04](https://github.com/sgroff04) :koala:

##### Date - 03/28/2017
___
