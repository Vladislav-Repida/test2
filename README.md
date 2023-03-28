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

## Использование Timepicker в Datepicker
```vue
<template>
    <tir-datepicker v-model="value1" is-use-timepicker :time-input-position="EnumInputPosition.Bottom"/>
    <tir-datepicker-range v-model="value4"/ is-use-timepicker>
</template>
<script lang="ts" setup>
import {DatepickerDate, EnumInputPosition} from "./vue3-tir-datepicker";
const value1 = ref(new DatepickerDate(2023, 3, 28, 10, 30, 20));
const value2 = ref<DatepickerDate>();
</script>
```

## Использование минимального и максимального ограничений
```vue
<template>
    <tir-datepicker v-model="value1" :min-value="min" :max-value="max"/>
    <tir-timepicker v-model="value2" :min-value="min" :max-value="max"/>
    <tir-timepicker-range v-model="value3" :min-values="minRange" :max-values="maxRange" />
    <tir-datepicker-range v-model="value4" :min-values="minRange" :max-values="maxRange"/>
</template>
<script lang="ts" setup>
import {DatepickerDate} from "vue3-tir-datepicker";
/** Минимальное значение */
const min = new DatepickerDate(2023, 2, 10);
/** Максимальное значение */
const max = new DatepickerDate(2023, 3, 30);
/** Минимальное значение для range пикера */
const minRange = [new DatepickerDate(2023, 2, 10), new DatepickerDate(2023, 2, 12)];
/** Максимально значение для range пикера */
const maxRange = [new DatepickerDate(2023, 3, 30), new DatepickerDate(2023, 3, 20)]
</script>
```

## Использование подписей
```vue
<template>
    <tir-datepicker v-model="value1" :date-labels="dateLabels"/>
    <tir-timepicker v-model="value2" :time-labels="timeLabels"/>
    <tir-timepicker-range v-model="value3" :time-labels="timeLabels"/>
    <tir-datepicker-range v-model="value4" :date-labels="dateLabels"/>
</template>
<script lang="ts" setup>
import { DateLabels, TimeLabels } from "./vue3-tir-datepicker";
/** Подписи для даты (20 д. 02 м. 2023г.) */
const dateLabels = new DateLabels({
  year: "г.",
  month: " м. ",
  days: " д. ",
});

/** Подписи для времени (13 ч. 15 мин. 30 сек.) */
const timeLabels = new TimeLabels({
  hours: " ч. ",
  min: " мин. ",
  sec: " сек.",
});
</script>
```
