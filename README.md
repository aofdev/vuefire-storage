# vuefire-storage demo

## Config
 > firebase storage rules  
 ``` bash
   allow read, write: if request.auth != null; change to allow read, write: if true;
 ```

At -> src/components/Hello.vue     [firebase console](https://console.firebase.google.com/)
``` bash
let config = {
//firebase console
		apiKey: '',
        authDomain: "",
        databaseURL: "",
        storageBucket: "",
        messagingSenderId: ""
}
```

## Build Setup

``` bash
# install dependencies
npm install

# serve with hot reload at localhost:8080
npm run dev

# build for production with minification
npm run build

# build for production and view the bundle analyzer report
npm run build --report
```
