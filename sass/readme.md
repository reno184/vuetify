# sass

````  npm install -D sass-loader sass ````

The vuetify modification variable purpose concerns only element structure

I order to change color, rather use Vuetify theme

vuetify/plugins/vuetify.ts

````js
// Styles
import '@mdi/font/css/materialdesignicons.css'
import 'vuetify/styles'

// Composables
import { createVuetify } from 'vuetify'

// https://vuetifyjs.com/en/introduction/why-vuetify/#feature-guides
export default createVuetify({
  theme: {
    defaultTheme: 'dark',
  },
})

````

vuetify/styles/settings.scss
````css
@use 'vuetify/settings' with (
    $button-height: 80px,
);
````


