# v-date-picker

---

Vuetify offers a composable called useDate, that allows to format date with local, but also make manipulation on date, like dateDiff...

example

````js
this.date.getDiff(this.filter.toDate, this.filter.fromDate, 'days' )>20
````


Setup config local

````js
    const vuetify = createVuetify({
        locale: {
            locale: 'fr',
        },
        date: {
            locale: {
                fr: 'fr-FR',
            },
        }
    })
````
or
````html
<v-locale-provider locale="fr">
              <v-date-input label="start date" variant="outlined" placeholder="dd/mm/yyyy" v-model="item.startDate"  hint="Champs obligatoire" :rules="[required]" required  density="compact" prepend-icon="" prepend-inner-icon="$calendar" ></v-date-input>
</v-locale-provider>
````
