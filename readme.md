# Emoji-Picker

An elegant emoji picker built with Vue.

![emoji-picker](https://github.com/zaichaopan/emoji-picker/blob/master/emoji-picker.png?raw=true "emoji picker image")

Play it on [code sandbox]()

## Installation

```bash
npm install --save @zaichaopan/emoji-picker
```

## Usage

* Register the plugin

```js
import Vue from 'vue';
import EmojiPicker from '@zaichaopan/emoji-picker';

Vue.use(EmojiPicker);
```

Now you have the component __emoji-picker__ in your application.

* Import emoji json file

To reduce bundle size, this plugin __does not include emojis by default__. So when using this plugin, you need to __import__ a Json file which contains all the emojis and pass it as a property named __data__ to the __emoji-picker__ component.

```html
<!-- MyComponent.vue -->
<template>
    <div>
        <emoji-picker :data="data" />
    </div>
</template>

<script>
import data from '@zaichaopan/emoji-picker/data/emojis.json';

export default {
   data () {
    return {
      data: data
    };
  },
  // ...
}
</script>
```

* Add styling

```html
<!-- MyComponent.vue -->
<template>
    <div>
        <emoji-picker :data="data" />
    </div>
</template>

<script>
import data from '@zaichaopan/emoji-picker/data/emojis.json';

export default {
   data () {
    return {
      data: data
    };
  },
  // ...
}
</script>

<style lang="scss">
@import "@zaichaopan/emoji-picker/dist/emoji-picker.css";

</style>
```

* Listen for emoji picked event

When a emoji gets picked, the component will emit event __emoji:picked__. You can listen to it and get the picked emoji to update your form

```html
<template>
    <div>
        <emoji-picker @emoji:picked="handleEmojiPicked"
                      :data="data" />
        </div>
   </div>
</template>

<script>
import data from '@zaichaopan/emoji-picker/data/emojis.json';

export default {
  data () {
    return {
      data: data,
    };
  },
  methods: {
    handleEmojiPicked (emoji) {
        // ...
    }
  }
};
</script>

<style lang="scss">
@import "@zaichaopan/emoji-picker/dist/emoji-picker.css";
</style>
```

__That is all you need to do to add emoji picker to your application__. A complete example can be found in [code sandbox]().