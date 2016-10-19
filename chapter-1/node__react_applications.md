# Node / React Applications

I have a similar structure that works for node and react as well.

http://jaysoo.ca/2016/02/28/organizing-redux-application/

I still need to polish it up a bit more for redux.

```
src/
  features/
    feature-a/
      components/     // react ui components
      index.js
      actionTypes.js  // redux noise
      actions.js
      constants.js
      reducer.js
  infrastructure/
    redux/
      index.js        // configures redux
    localStorage/
    serviceWorkers/
  index.js            // public statac void main
webpack.config.js
package.json
```

## The anatomy of a feature folder

```
~/
  features/
    feature-a/
      components/
        <component>/
          index.js // reexports things
          <widgetName>.js
      redux/
        actionTypes.js
        actions.js
        constants.js
        reducer.js
        index.js
      <feature>.js
```

### Components

This is where the various React components are stored.

### Redux

Still not sure if there is value in grouping these together

### Root Files

This is where the actual feature logic lives