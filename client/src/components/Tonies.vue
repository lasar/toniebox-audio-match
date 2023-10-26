<template>
  <ul>
    <li v-for="tonie in tonies" @click="tonieSelected" :key="tonie.id">
      <img :src="tonie.image" />
      <span>{{ tonie.name }}</span>
    </li>
  </ul>
</template>

<script>
export default {
  props: {
    tonies: String,
    audiobookID: String,
  },
  methods: {
    tonieSelected(event) {
      // eslint-disable-next-line
      alert('Starting upload. Your tonie will be ready in a few minutes! :)');
      this.$emit('onchange', event.target.value, this.audiobookID);
    },
  },
};
</script>

<style>
ul {
  list-style: none;
  padding: 0 10px;
}

li {
  display: inline-block;
  max-width: 33%;
  text-align: left;
}

img {
  display: block;
  max-width: 100%;
}

span {
  font-size: small;
}</style>
