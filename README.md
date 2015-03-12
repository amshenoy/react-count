react-count
===========
Real-time counter button [React](http://facebook.github.io/react/) component baked by [Firebase](https://www.firebase.com/).



## Installation

If you use webpack just install react-count module

```
  npm install react-count
```

and require it anywhere in your react app:

```
  var Count = require('react-count');
```

## Firebase security rules

Add following firebase security rules if you want to prevent users from arbitrary changing vote results.
We allow incremental vote submissions:


```
{
    "rules": {
        ".read": true,
        "$counter": {
          ".write": "!root.child($counter).exists() || ((newData.val() - data.val()) === 1)"
        }
    }
}
```

