# Node / React Applications

I have a similar structure that works for node and react as well.

[http://jaysoo.ca/2016/02/28/organizing-redux-application/](http://jaysoo.ca/2016/02/28/organizing-redux-application/)

> Leverage webpack's `resolve.modules` to give you npm like imports in your own code.
>
> [https://webpack.js.org/configuration/resolve/\#resolve-modules](https://webpack.js.org/configuration/resolve/#resolve-modules)

I still need to polish it up a bit more for redux.

```text
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
      selectors.js    // redux helpers
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

```text
~/
  features/
    feature-a/
      components/
        <component>/
          index.js // reexports things
          <widgetName>.js
      actionTypes.js
      actions.js
      constants.js
      reducer.js
      selectors.js
      index.js
      <feature>.js
```

### Components

This is where the various React components are stored.

### Redux Support Files

`actionType.js` contains `CONST` of names like `FEATURE/UPDATE` a

`actions.js` contains the functions to make new action objects

`constants.js` contains any module level constants such as the root for redux

`reducer.js` is where the redux reducer lives

 &gt; As of 3/2019 should use `immer.js` 

`selectors.js` allow users to consume the "root" state object outside of the feature.

&gt; As of 3/2019 should use `reselect.js` 

### Root Files

This is where the actual feature logic lives

### Type Script Notes

## 3/2019 Libs I like

* reselect
* immer
* node-uuid
* react-redux 
* react-router
* react-saga
* redux
* create-react-app

