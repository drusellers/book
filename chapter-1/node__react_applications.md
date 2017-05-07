# Node / React Applications

I have a similar structure that works for node and react as well.

[http://jaysoo.ca/2016/02/28/organizing-redux-application/](http://jaysoo.ca/2016/02/28/organizing-redux-application/)

> Leverage webpack's `resolve.modules` to give you npm like imports in your own code. 
>
> https://webpack.js.org/configuration/resolve/\#resolve-modules

I still need to polish it up a bit more for redux.

```
src/
  features/
    feature-a/
      components/     // react ui components
        widget-a.js
        widget-b.js
      index.js        // mounts and exposes sub modules
      actionTypes.js  // redux noise
      actions.js      // redux noise
      constants.js    // redux noise
      reducer.js      // redux logic
  infrastructure/
    redux/
      index.js        // configures redux (configure store)
    localStorage/
      index.js        // exposes common local storage access (immutable.js <-> json)
    serviceWorkers/
      index.js        // spin up service workers
  index.js            // public static void main
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



## 5/2017 Libs I like

* immutable.js
* node-uuid
* react-redux 
* react-router
* react-saga
* redux
* create-react-app



