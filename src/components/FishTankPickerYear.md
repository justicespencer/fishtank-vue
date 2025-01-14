FishTankPickerYear Example
```js
<template>
  <div>
    <div>Hovered Example</div>
    <div style="position: relative">
      <FishTankPickerYear :value="value1" v-show="!hide1" @selectYear="selectYear" />
      <button @click="hide1=!hide1">toggle</button>
      <div>{{value1}}</div>
    </div>
    <hr />
    <div>Inline Example</div>
    <FishTankPickerYear :value="value2" inline :disabled-dates="disabled" @selectYear="selectYear" />
    <div>{{value2}}</div>
    <hr />
    <div>events:</div>
    <div v-for="(e, index) in events">{{e}}</div>
  </div>
</template>

<script>

export default {
  components: {FishTankPickerYear},
  data () {
    return {
      disabled: {
        from: new Date(2022, 5, 14),
        to: new Date(2002, 3, 14)
      },
      events: [],
      hide1: true,
      value1: new Date(),
      value2: new Date()
    }
  },
  methods: {
    selectYear(year) {
      this.events.push(`selectYear-${year.label}`)
      this.hide1 = true
    }
  }
}
</script>
```
