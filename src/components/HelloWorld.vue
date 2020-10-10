<template>
  <div class="hello">
    <h1>{{ msg }}</h1>
    <span>msg.length: {{ state.msgLength }}</span>
  </div>
</template>

<script>
import { toRefs, onMounted, reactive, computed } from 'vue';

export default {
  name: 'HelloWorld',
  props: {
    msg: String
  },
  setup(props) {
    const { msg } = toRefs(props);
    console.log(msg.value);

    onMounted(() => {
      console.log('Component is mounted!')
    });

    const state = reactive({
      msgLength: computed(() => msg.value.length),
    });

    return { state };
  },
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
h3 {
  margin: 40px 0 0;
}
ul {
  list-style-type: none;
  padding: 0;
}
li {
  display: inline-block;
  margin: 0 10px;
}
a {
  color: #42b983;
}
</style>
