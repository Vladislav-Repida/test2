# test2
### Datepicker
```vue
<template>
    <tir-datepicker v-model="value"/>
</template>
<script lang="ts" setup>
import {DatepickerDate} from "vue3-tir-datepicker";
const value = ref<DatepickerDate>();
</script>
```

### Datetimepicker
```vue
<template>
    <tir-timepicker v-model="value"/>
</template>
<script lang="ts" setup>
import {DatepickerDate} from "vue3-tir-datepicker";
const value = ref<DatepickerDate>();
</script>
```

### DatepickerRange
```vue
<template>
    <tir-datepicker-range v-model="value"/>
</template>
<script lang="ts" setup>
import {DatepickerDate} from "vue3-tir-datepicker";
const value = ref<[DatepickerDate, DatepickerDate]>();
</script>
```

### TimepickerRange
```vue
<template>
    <tir-timepicker-range v-model="value"/>
</template>
<script lang="ts" setup>
import {DatepickerDate} from "vue3-tir-datepicker";
const value = ref<[DatepickerDate, DatepickerDate]>();
</script>
```
----

