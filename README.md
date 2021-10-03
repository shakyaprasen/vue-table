# vue-table

An unopinionated, barebones and highly customizable table library for vuejs

### vue-table works with Vue 2.x, no current support for Vue 3.x

### Tutorial

use slot and scoped slots to customize the table to your liking. Slot for table header corresponds to the column id i.e. `th-1`, `th-2`, slot for 
table item also corresponds to the column id i.e. `1`, `2`.

e.g.

```js
const COLUMNS = [
  {
    id: 'name',
    label: 'Full Name,
  },
  {
    id: 'address',
    label: 'Add'
  }
];

const ITEMS = [
  {
    name: 'Agent Smith',
    address: '123 Timbuktu'
  },
  {
    name: 'Neo',
    address: '331b Baker Street'
  }
];
```


```html
<Vue-table
  :columns="$options.COLUMNS"
  :items="$options.ITEMS"
/>
```
