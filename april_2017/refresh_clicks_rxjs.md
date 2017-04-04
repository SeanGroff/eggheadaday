## [Reactive Programming - New requests from refresh clicks](https://egghead.io/lessons/rxjs-reactive-programming-new-requests-from-refresh-clicks)

### Example
```html
<!DOCTYPE html>
<html>
<head>
  <meta charset="utf-8">
  <meta name="viewport" content="width=device-width">
  <title>JS Bin</title>
  <style>
    img {
      width: 50px;
      height: 50px;
      border-radius: 50%;
      margin-right: 10px;
    }

    li {
      display: flex;
      align-items: center;
      margin-bottom: 15px;
    }

    a {
      padding-left: 10px;
    }
  </style>
</head>
<body>
  <div>
    <h1 style="display: inline;">Who to follow</h1>
    <a class="refresh" href="#">Refresh</a>
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

// refresh button element selector
const refreshButton = document.querySelector('.refresh');

// Creates an Observable click event stream on the refresh button
const refreshClickStream$ = Rx.Observable.fromEvent(refreshButton, 'click');


// Create an Observable of just the URL string
const startupRequestStream$ = Rx.Observable.of('https://api.github.com/users')

// Create an Observable of just the URL string
const requestOnRefreshStream$ = refreshClickStream$
  .map((event) => {
    const randomOffset = Math.floor(Math.random() * 500);
    return 'https://api.github.com/users?since=' + randomOffset;
  });


// think of .switchMap as .then() from a Promise
// .merge takes both streams and merges them to one stream
// ----a------b--c--->
// s----------------->
// Merge()
// s---a------b--c--->
const responseStream$ = requestOnRefreshStream$
  .merge(startupRequestStream$)
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
  const imgEl = element.querySelector('img');
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
<blockquote class="twitter-tweet" data-lang="en"><p lang="en" dir="ltr">New requests from refresh clicks - rx Video Tutorial <a href="https://twitter.com/hashtag/pro?src=hash">#pro</a> <a href="https://twitter.com/eggheadio">@eggheadio</a>: <a href="https://t.co/ta5eBav81c">https://t.co/ta5eBav81c</a><br>By: <a href="https://twitter.com/andrestaltz">@andrestaltz</a> <a href="https://twitter.com/hashtag/eggheadADay?src=hash">#eggheadADay</a> <a href="https://twitter.com/hashtag/js?src=hash">#js</a> <a href="https://twitter.com/hashtag/RxJS?src=hash">#RxJS</a></p>&mdash; Sean Groff (@_SeanGroff) <a href="https://twitter.com/_SeanGroff/status/849280434345299970">April 4, 2017</a></blockquote>

### Github Contributor
[@SeanGroff](https://github.com/SeanGroff) :koala:

##### Date - 04/04/2017
___
