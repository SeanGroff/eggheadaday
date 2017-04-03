## [Reactive Programming - Rendering on the DOM with RxJS](https://egghead.io/lessons/rxjs-05-reactive-programming-rendering-on-the-dom-with-rxjs)

### Example
```html
<!DOCTYPE html>
<html>
<head>
  <meta charset="utf-8">
  <meta name="viewport" content="width=device-width">
  <title>JS Bin</title>
</head>
<body>
  <div>
    <ul class="suggestions">
      <li class="suggestion1">
        <img />
        <a href="#" target="_blank" class="username">username</a>
        <a href="#" class="close close1">x</a>
      </li>
      <li class="suggestion2">
        <img />
        <a href="#" target="_blank" class="username">username</a>
        <a href="#" class="close close2">x</a>
      </li>
      <li class="suggestion3">
        <img />
        <a href="#" target="_blank" class="username">username</a>
        <a href="#" class="close close3">x</a></li>
    </ul>
  </div>
  <script src="https://unpkg.com/@reactivex/rxjs@5.0.3/dist/global/Rx.js"></script>
</body>
</html>
```
```javascript
// fetch() github users api endpoint
const fetchEndpoint = url => fetch(url)
    .then(response => response.json());

// Create an Observable of just the URL string
const requestStream$ = Rx.Observable.of('https://api.github.com/users');

// think of .switchMap as .then() from a Promise
const responseStream$ = requestStream$
  .switchMap(url =>
    Rx.Observable.fromPromise(fetchEndpoint(url))
  );

// Takes the responseStreaam Observable which is a list of users
// and returns a random user from the Observable list.
const randomUserStream$ = (responseStream) =>
  responseStream.map(user =>
    user[Math.floor(Math.random() * user.length)]
);

// Stores the random user Observable to a variable.
const suggestion1Stream$ = randomUserStream$(responseStream$);

const suggestion2Stream$ = randomUserStream$(responseStream$);

const suggestion3Stream$ = randomUserStream$(responseStream$);

// helper function to grab a selector on the dom and add data from the api to it.
const renderSuggestion = (userData, selector) => {
  const element = document.querySelector(selector);
  const usernameEl = element.querySelector('.username');
  usernameEl.href = userData.html_url;
  usernameEl.textContent = userData.login;
  const imgEl = element.querySelection('img');
  imgEl.src = userData.avatar_url;
};

// Subscribes to the Observable calling renderSuggestion() for each user
suggestion1Stream$.subscribe(user =>
  renderSuggestion(user, '.suggestion1'));

suggestion2Stream$.subscribe(user =>
  renderSuggestion(user, '.suggestion2'));

suggestion3Stream$.subscribe(user =>
  renderSuggestion(user, '.suggestion3'));
```


### Tweet
<blockquote class="twitter-tweet" data-lang="en"><p lang="en" dir="ltr">Rendering on the DOM with RxJS - rx Video Tutorial <a href="https://twitter.com/hashtag/pro?src=hash">#pro</a> <a href="https://twitter.com/eggheadio">@eggheadio</a>: <a href="https://t.co/LHStPtKyZl">https://t.co/LHStPtKyZl</a><br>By: <a href="https://twitter.com/andrestaltz">@andrestaltz</a> <a href="https://twitter.com/hashtag/eggheadADay?src=hash">#eggheadADay</a> <a href="https://twitter.com/hashtag/js?src=hash">#js</a> <a href="https://twitter.com/hashtag/RxJS?src=hash">#RxJS</a></p>&mdash; Sean Groff (@_SeanGroff) <a href="https://twitter.com/_SeanGroff/status/848927988515295233">April 3, 2017</a></blockquote>

### Github Contributor
[@SeanGroff](https://github.com/SeanGroff) :koala:

##### Date - 04/03/2017
___
