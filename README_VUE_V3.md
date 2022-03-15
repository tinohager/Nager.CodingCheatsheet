# Vue.js V2

Good editor for examples
https://codesandbox.io/s/

## 1. `v-if`
```html
// Correct
<div v-if="hostName">{{hostName}}</data>

// Avoid
<div v-if="hostName !== null">{{hostName}}</data>
```
## 2. Use filters to format values
```html
filters: {
  moment: function (date) {
    return moment(date).fromNow();
  }
}

<span>{{ date | moment }}</span>
```
## 3. Use eslint

with plugin:vue/recommended

## 4. axios inegration

Use ES6 "arrow functions", to keep the reference to the instance with the `this` keyword

```js
// Correct
this.axios.get('/Data')
  .then(response => {
    this.myData = response.data;
  })
  .catch(error => {
    console.log(error);
  });

// Avoid
let self = this;
this.axios.get('/Data')
  .then(function (response) {
    self.myData = response.data;
  })
  .catch(function (error) {
    console.log(error);
  });
```
