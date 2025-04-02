# Theme

### Init

---

````js
import {myCustomDarkTheme} from '@/plugins/themeDark.mjs'
import {myCustomLightTheme} from '@/plugins/themeLight.mjs'

const vuetify = createVuetify({
    theme: {
        defaultTheme: 'myCustomLightTheme',
        themes: {
            myCustomLightTheme,
            myCustomDarkTheme
        }
    },
````

### layout/components match variable 

---

Note: theme variables are specifically for color theming

- **primary:** This is the main color used across your application, often for key interactive elements.
- **secondary:** A complementary color to the primary, used for secondary elements.
- **accent:** Used for highlighting elements.
- **error:** Represents error states.
- **warning:** Represents warning states.
- **info:** Represents informational states.
- **success:** Represents successful states.
- **background:** The overall background color of the application.
- **surface:** The color of cards, dialogs, and other surface-like components.
  + v-card
  + v-dialog
  + v-menu
  + v-sheet
  + v-text-field background
  + v-list-item background
  + v-btn (if no color set)

- **on-surface:** The color of text and icons that appear on top of surface colors.
- **on-background:** The color of text and icons that appear on top of background colors.

### Example dark/light theme

---

*source: Opsealog Bourbon Datas Managment*

````js
export const themeDark = {
    dark: true,
    colors: {
        'primary' : '#c9c909',
        'surface': '#333',
        'surface-variant': '#444',
        'on-surface-variant': '#fefefe'
    },
    variables: {
        'disabled-opacity': 0.2,
    }
}
````
````js
export const themeLight = {
    dark: false,
    colors: {
        'surface': '#fefefe',
        'surface-variant': '#eee',
        'on-surface-variant': '#333',
        'on-field-focused' : 'red'
    },
    variables: {
        'disabled-opacity': 0.6,
        'btn-size': '.9rem'
    },
}
````
### Use case
Apply yellow outline over input only in dark mode but nothing on light mode.

*source: Opsealog Bourbon Datas Managment*
````html
 <v-text-field  :color="theme.global.current.value.dark ? 'primary' : '' " ></v-text-field>
````
````js
   setup(){
        const theme = useTheme()
        return {   theme }
    }
````

### Vuetify util colors
````js
import colors from 'vuetify/util/colors'

export const myCustomDarkTheme = {
    dark: true,
    colors: {
        primary: colors.amber.base,
````


### Color variable injection tips

---

into html
````html
<v-pagination color="var(--v-primary-darken1)" ... />
````
into css
```css
.myClass {
    background:var(--v-grey-lighten1);
  }
```
Carefull : sometime variable return rgb
```css
.myClass {
    background: rgb(var(--v-theme-background));
  }
```

### sass variables vs theme variables 
**Key Differences:**

 + Granularity: SASS variables allow for more detailed customization, while theme variables are more suited for broad, consistent theming.
 + Application: SASS variables are applied globally and can be used in any component's styles, whereas theme variables are specifically for color theming.

### sass implementation

---

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

### switch dark/light mode

*Source: PNLApp*

