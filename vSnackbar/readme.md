# v-snackbar

---

```html
<v-snackbar    v-model="snackbar"  color="red" >{{error}}</v-snackbar>
```

```js 
data(){
    return {  error:'' }
},
computed : {
    snackbar() {
      return this.error !==""
    }
}
```
