<template>
  <img class="logo" alt="Krishna Apps logo" src="./assets/logo.png" />
  <br />
  <h2>Presents</h2>
  <h1>Vue Tag Input</h1>
  <hr />
  <div class="main">
    <h1>Default options</h1>
    <tag-input v-model="tags" />
    <br>
    <span>Use <code>enter</code> key or <code>tab</code> key to create a new tag.</span>
    <h1>With custom delimiter and colors</h1>
    <tag-input tagBgColor="lightgreen" @focus-event="handleFocusEvent" tagTextColor="darkgreen" :customDelimiter="customDelimiter" v-model="tags" />
    <br>
    <span>Use <code>enter</code> key or <code>tab</code> key or any of the custom delimeters to create a new tag.</span>
    <p>Custom delimiters: <code v-for="delim in customDelimiter" :key="delim"> "{{delim}}"</code></p>
    <br>
    <h1>Do not allow custom tags</h1>
    <tag-input :options="options" :allowCustom="false" tagBgColor="blue" tagTextColor="lightblue" :customDelimiter="customDelimiter" v-model="tags" />
    <br>
    Try entering tag that is not in options and hit <code>enter</code>
    <br>
    <span>Use <code>enter</code> key or <code>tab</code> key or any of the custom delimeters to create a new tag.</span>
    <p>Allowed Tags: <code v-for="tag in options" :key="tag"> "{{tag}}"</code></p>
    <p>Custom delimiters: <code v-for="delim in customDelimiter" :key="delim"> "{{delim}}"</code></p>
    <br>
    <h1>Provide options for autofill but also allow custom tags</h1>
    <tag-input :options="options" tagBgColor="blue" tagTextColor="lightblue" :customDelimiter="customDelimiter" v-model="tags" />
    <br>
    <span>Use <code>enter</code> key or <code>tab</code> key or any of the custom delimeters to create a new tag.</span>
    <p>Allowed Tags: <code v-for="tag in options" :key="tag"> "{{tag}}"</code></p>
    <p>Custom delimiters: <code v-for="delim in customDelimiter" :key="delim"> "{{delim}}"</code></p>
    <br>
  </div>
</template>

<script>
// import TagInput from '@mayank1513/tag-input'
// import '@mayank1513/tag-input/dist/TagInput.css'
import TagInput from './components/TagInput.vue'

export default {
  name: 'App',
  data() {
    return {
      tags: [],
      customDelimiter: [',', ' '],
      options: ['vue', 'composition', 'js', 'mytag1', 'mayank1513']
    };
  },
  components: {
    TagInput
  },
  methods: {
    handleFocusEvent(test) {
      console.log('focus');
    },
  }
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
  max-width: 1400px;
  margin: auto;
}
.main {
  text-align: start;
}
.logo {
  width: 70%;
  max-width: 250px;
}
.tag1 {
  background: green;
  color: red;
  padding: 5px;
  border-radius: 4px;
  white-space: nowrap;
  transition: 0.1s ease background;
}
</style>
