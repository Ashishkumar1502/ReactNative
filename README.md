Returns the element of an array when the callback returns true.

Purpose
---

This module provides a similar function as `Array.prototype.filter`, but
it returns the element, not an array. And it stops looping as soon as it
finds a result.

Usage
---

```javascript
var arr = ['item', 'other', 'finally'];

var item = or(arr, function(item) {
    return item === 'other';
});

console.log(item); // "other"

// Real world example
var matchesSelector = or(['matchesSelector', 'mozMatchesSelector',
    'webkitMatchesSelector', 'oMatchesSelector',
    'msMatchesSelector'], function(shim) {
    return shim in document.documentElement;
});

document.getElementById('some')[matchesSelector]('#some'); // true
```

API
---

The module returns a function accepting the following arguments:

- `array`: the array on which to iterate
- `callback`: the function being called
- `context`: the context on which to call the callback

Contributors
---

- [Florian Margaine](http://margaine.com)

License
---

MIT License.
[![React-Native](https://img.shields.io/badge/React%20Native-333.svg?style=for-the-badge&logo=react&labelColor=4630eb&logoWidth=30&logoColor=fff)](https://reactnative.dev/) [![supports iOS and Android](https://img.shields.io/badge/Getting%20Started-4630EB.svg?style=for-the-badge&labelColor=000)](https://reactnative.dev/docs/getting-started) [![Subscribe To The Channel](https://img.shields.io/badge/Subscribe-red.svg?style=for-the-badge&logo=youtube&labelColor=red&logoWidth=20&logoColor=fff)](https://www.youtube.com/channel/UCC6L3eilEVJhhqiAdepWcng)

# Firebase

### Demo
<p>
<picture>
  <source width="240" media="(prefers-color-scheme: dark)" srcset="https://github.com/vishalpwr/firebase/blob/master/imgs/auth1.png">
  <img src="hhttps://github.com/vishalpwr/firebase/blob/master/imgs/auth1.png">
</picture>
<picture>
  <source width="240" media="(prefers-color-scheme: dark)" srcset="https://github.com/vishalpwr/firebase/blob/master/imgs/auth2.png">
  <img src="hhttps://github.com/vishalpwr/firebase/blob/master/imgs/auth2.png">
</picture>
</p>

clone then repo and then go into root dir of the app and run
```
npm install or yarn
npm start or react-native start
npm run android or yarn android
```
ios
```
pod install
npm run ios or yarn ios
```
1. **create new firebase project from firebase console**
2. **add google-services.json file in android/app folder**
3. **add sha keys in firebase project settings**


____________________________________________________________________
### Generate keystore
**Move to RootProject-Directory/android/app then run this command to generate new keystore**
```
keytool -genkeypair -v -storetype PKCS12 -keystore firebase.keystore -alias fbalias -keyalg RSA -keysize 2048 -validity 10000
```

### Get Debug signing certificate SHA-1 key:
**first move to your keystore file dir. then run this command**
```
keytool -list -v -keystore firebase.keystore -alias fbalias -storepass android -keypass android
```