## [Using the map method with Observable](https://egghead.io/lessons/javascript-using-the-map-method-with-observable)

### Example
```javascript
/* Observable Map Example */

const obsButton = document.getElementById('obsBtn');

// Creates an Observable from a click event
// Maps over each click event projecting an object
const clicks = Rx.Observable.fromEvent(obsButton, 'click')
  .map(e => ({ x: e.clientX, y: e.clientY }));

// Subscription to the clicks Observable
// pass the onNext callback to the subscribe method
const subscription = clicks.subscribe((point) => {
    console.log('clicked! ', JSON.stringify(point))
    subscription.unsubscribe();
  });

/**
 * Just like Arrays we can .map, filter, concat, etc on Observables to project new Observables!
 **/
```

### Tweet
<blockquote class="twitter-tweet" data-lang="en"><p lang="en" dir="ltr">Using the map method with Observable - js Video Tutorial <a href="https://twitter.com/hashtag/free?src=hash">#free</a> <a href="https://twitter.com/eggheadio">@eggheadio</a>: <a href="https://t.co/9BVcF4J7Te">https://t.co/9BVcF4J7Te</a><br>By: <a href="https://twitter.com/jhusain">@jhusain</a> <a href="https://twitter.com/hashtag/eggheadADay?src=hash">#eggheadADay</a> 🗺️</p>&mdash; Sean Groff (@_SeanGroff) <a href="https://twitter.com/_SeanGroff/status/847106884582719488">March 29, 2017</a></blockquote>

### Github Contributor
[@SeanGroff](https://github.com/SeanGroff) :koala:

##### Date - 03/29/2017
___
