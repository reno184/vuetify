# v-btn

#### 1.loading attribute

---

![](VBtnLoading.png)

```html
 <v-row class="mt-5">
            <v-col cols="12" md="3" >
                <v-text-field type="date" variant="outlined" density="compact" label="start date" class="mx-5" ></v-text-field>
            </v-col>
            <v-col cols="12" md="3" >
                <v-text-field type="date" variant="outlined" density="compact" label="end date"  class="mx-5"></v-text-field>  
            </v-col>
            <v-col cols="12" md="3" >
                <v-select variant="outlined" density="compact" label="Code"  class="mx-5"></v-select>
            </v-col>
            <v-col cols="12"  md="3" >
                <v-btn color="primary" :loading="true" >Submit</v-btn>
            </v-col>
        </v-row>
```

``variant="text"`` remove shadow
prefer to use ``slim`` than `` size="'small"``...better style
