## [Manage Angular 2 Elements with Events and Refs](https://egghead.io/lessons/angular-2-using-events-and-refs?series=angular-2-fundamentals)

### Example
```javascript
/**
 * Angular 2 Elements with Events and Refs
 */

import { Component, OnInit } from '@angular/core';

@Component({
  // The DOM element type
  selector: 'app-simple-form',
  /* The View */
  /* The #myInput is how you place a reference on a DOM element */
  /* To place an event on an element you surround the Angular event with parenthesis */
  /* You then assign it a method and call the method */
  /* ex. (click)="onClick(myInput.value) */
  /* This calls the onClick Class method and passes the <input>'s value */
  template: `<div>
    <input #myInput type="text">
    <button (click)="onClick(myInput.value)">Click me!</button>
  </div>`,
  styles: []
})
export class SimpleFormComponent implements OnInit {

  constructor() { }

  ngOnInit() {
  }

  onClick(value) {
    console.log(`Input value is - ${value}`); // -> Whatever you type in #myInput text input.
  }
}
```


### Tweet
<blockquote class="twitter-tweet" data-lang="en"><p lang="en" dir="ltr">Manage Angular 2 Elements with Events and Refs - Video Tutorial <a href="https://twitter.com/hashtag/free?src=hash">#free</a> <a href="https://twitter.com/eggheadio">@eggheadio</a>: <a href="https://t.co/xDWGJLdWc9">https://t.co/xDWGJLdWc9</a><br>By: <a href="https://twitter.com/johnlindquist">@johnlindquist</a> <a href="https://twitter.com/hashtag/eggheadADay?src=hash">#eggheadADay</a></p>&mdash; Sean Groff (@SeanG816) <a href="https://twitter.com/SeanG816/status/844935679012474880">March 23, 2017</a></blockquote>

### Github Contributor
[@sgroff04](https://github.com/sgroff04) :koala:

##### Date - 03/23/2017
___
