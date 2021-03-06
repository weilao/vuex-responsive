# vuex-responsive
A vuex responsive solution.

## Install
```
npm i vuex-responsive -S
```

## Usage
Setup:
```js
import vuexResponsive from 'vuex-responsive';

const store = new Vuex.Store({
  plugins: [vuexResponsive],
  getters: {
    responsive: state => state.responsive
  }
});
```

Use it in your component:
```html
<template>
    <div>
    <div v-show="responsive.xs">xs</div>
    <div v-show="responsive.sm">sm</div>
    <div v-show="responsive.md">md</div>
    <div v-show="responsive.lg">lg</div>
    <div v-show="responsive.xl">xl</div>
    <div v-show="responsive.only.xs">xs only</div>
    <div v-show="responsive.only.sm">sm only</div>
    <div v-show="responsive.only.md">md only</div>
    <div v-show="responsive.only.lg">lg only</div>
    <div v-show="responsive.only.xl">xl only</div>
    </div>
</template>
<script>
    import {mapGetters} from 'vuex';

    export default {
        name: 'demo',
        computed: {...mapGetters(['responsive'])}
    }
</script>
```

## Customize
```js
import {createResponsivePlugin} from 'vuex-responsive';

const store = new Vuex.Store({
  plugins: [createResponsivePlugin({
    breakPoints: [768, 992, 1200, 1920],
    throttle: 100,
    updateOnResize: true
  })]
});
```