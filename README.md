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

## Смена формата
```vue
<template>
    <tir-datepicker v-model="value1" is-use-timepicker time-format="HH:MM" date-format="YYYY.MM.DD"/>
    <tir-timepicker v-model="value2" time-format="HH:MM"/>
    <tir-timepicker-range v-model="value3" time-format="HH:MM"/>
    <tir-datepicker-range v-model="value4" date-format="YYYY.MM.DD"/>
</template>
```

## Использование опций быстрого выбора (в Datepicker)
```vue
<template>
 <tir-datepicker v-model="value1" enable-quick-options/>
 <tir-datepicker-range v-model="value2" enable-quick-options/>
</template>
```
### Добавление кастомынх опций быстрого выбора
```vue
<template>
 <tir-datepicker v-model="value1" enable-quick-options :custom-quick-options="customQuickOptions"/>
 <tir-datepicker-range v-model="value2" enable-quick-options :custom-quick-options="customQuickOptionsRange"/>
</template>
<script lang="ts" setup>
import {DatepickerDate, QuickOptionModel } from "vue3-tir-datepicker";
const customQuickOptions = [
  new QuickOptionModel({
    /** Подпись */
    title: "Тестовая опция",
    /** Значение */
    data: new DatepickerDate().addDays(2),
    /** Иконка слева (optional) */
    iconLeft: "mdi mdi-clock-time-eight-outline",
    /** Иконка спарва (optional) */
    iconRigth: "mdi mdi-clock-time-eight-outline",
  }),
];

const customQuickOptionsRange = [
  new QuickOptionModel<[DatepickerDate, DatepickerDate]>({
    /** Подпись */
    title: "Тестовая опция",
    /** Значение */
    data: [new DatepickerDate(), new DatepickerDate().addDays(2)],
    /** Иконка слева (optional) */
    iconLeft: "mdi mdi-clock-time-eight-outline",
    /** Иконка спарва (optional) */
    iconRigth: "mdi mdi-clock-time-eight-outline",
  }),
];
</script>
```
