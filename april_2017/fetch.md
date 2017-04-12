## [React Native: fetch API introduction](https://egghead.io/lessons/react-react-native-fetch-api-introduction)

### Example
```javascript
const URL = 'https://api.github.com/users/seangroff';

// global method fetch to make XHR requests
fetch(URL)
  // fetch returns a Promise
  // the returned Promise is a Response Object, not the data
  // .json() takes the Response Object returning a Promise with an
  // object literal containing the json data.
  .then(responseObject => {
    console.log('res: ', responseObject);
    return responseObject.json()
  })
  // this logs out the json data!
  .then(data => console.log(data))
  // Output any errors that occur
  // NOTE: HTTP errors such as 404 or 503 do NOT count as an error
  // they can be acted upon from the responseObject.status property
  .catch(err => console.log('Error ', err));
```


### Tweet
<blockquote class="twitter-tweet" data-lang="en"><p lang="en" dir="ltr">React Native: fetch API introduction - react Video Tutorial <a href="https://twitter.com/hashtag/pro?src=hash">#pro</a> <a href="https://twitter.com/eggheadio">@eggheadio</a>: <a href="https://t.co/tincg3j8L6">https://t.co/tincg3j8L6</a><br>By: <a href="https://twitter.com/tylermcginnis33">@tylermcginnis33</a> <a href="https://twitter.com/hashtag/eggheadADay?src=hash">#eggheadADay</a> 🍖🐕</p>&mdash; Sean Groff (@_SeanGroff) <a href="https://twitter.com/_SeanGroff/status/852021633539637249">April 12, 2017</a></blockquote>

### Github Contributor
[@SeanGroff](https://github.com/SeanGroff) :koala:

##### Date - 04/11/2017
___
