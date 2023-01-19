<template>
  <div class="hello">
    <h1>{{ msg }}</h1>
    
    <h3>Installed CLI Plugins</h3>
    <div v-if="showGreet">
    <teleport to=".modals">
      <Modal @close="toggleGreet" :greet='greet'>
        <p>this is it the slot</p>
        <template v-slot:namedSlot>this is in the named slot</template>
      </Modal>
    </teleport>
    </div>
    <button @click="toggleGreet">toggle greet</button>
    <input type="text" ref="dog" />
    <button @click="handleClick">call dog</button>
    <br>
    <button @click="multiplyBy2">multiply by 2</button>
    <h1>{{num}}</h1>
  </div>
</template>

<script setup>
import {ref, watch} from 'vue'
import Modal from '@/components/Modal.vue'

const msg = ref('ciao io sono il nuovo bellissimo messaggio, pronto ad essere inutilmente letto da te');
const showGreet = ref(true);
const greet = ref('Hello world')
const multiplyBy2 = () => num.value = num.value * 2
const num = ref(2);

const toggleGreet = newValue => {
  showGreet.value = !showGreet.value;
  num.value = newValue
}
 watch(num, (newV, oldV) => console.log('the old value of num: ',oldV, 'the new value of num: ', newV))
  // import Modal from './Modal.vue';

  // export default {
  //   data() {
  //     return {
  //       msg: 'ciao',
  //       greet: 'Hello there!',
  //       showGreet: true,
  //     };
  //   },
  //   components: {
  //     Modal,
  //   },
  //   // $refs!: {
  //   //   input: HTMLFormElement
  //   // },
  //   methods: {
  //     handleClick() {
  //       this.$refs.dog.focus();
  //     },
  //     toggleGreet() {
  //       this.showGreet = !this.showGreet;
  //     },
  //   },
  // };
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped lang="scss">
  h3 {
    margin: 40px 0 0;
    &:first-of-type {
      color: red;
    }
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
