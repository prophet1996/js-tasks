## Promise API JS

The Promise object represents the eventual completion (or failure) of an asynchronous operation, and its resulting value.

> Imagine you have dispatched a async callback that you expect to happen in sometime future(A slow API call), promise API provides a nice wrapped implementation to graciously handle such task.

It helps preventing [callback hell](http://callbackhell.com/)

Networks are unreliable and slow and cumbersome to deal with, there is no guarantee that what your code expects to happen, will happen, in given time. Most network connections are unrelaible.

For a deeper understanding of [asyncronicity](https://eloquentjavascript.net/11_async.html).

A promise either **_Resolve_** or **_Reject_**

```
/*Create a promise object to consume, in real life it would be a network call that creates this.
Pass a callback function that takes care of two state of a promise
Here this example always resolve, we could also reject
*/
var promise1 = new Promise(function(resolve, reject) {
setTimeout(function() {
resolve('foo');
}, 300);
});

/*now we subscribe to the promise by - calling 'then' function and passing a callback that handles a value */

promise1.then(function(value) {
    //whatever value is given to resolve, the same thing is give to our callback which we can use
console.log(value);
// expected output: "foo"
});
//as we can see we can't just use promise, we have to login
console.log(promise1);
// expected output: [object Promise]
```

Task - Use and demonstrate fetch API by creating a js file that calls https://google.com/ and console.log() the output

Bonus - write the output to a file
