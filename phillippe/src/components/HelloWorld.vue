<template>
  <div class="hello">
    <h1>{{ msg }}</h1>

    <button @click="onClick">Click!</button>
    <input v-model="message" placeholder="edit me">

  <input type="checkbox" id="jack" value="Jack" v-model="checkedNames">
  <label for="jack">Jack</label>
  <input type="checkbox" id="john" value="John" v-model="checkedNames">
  <label for="john">John</label>
  <input type="checkbox" id="mike" value="Mike" v-model="checkedNames">
  <label for="mike">Mike</label>
  <br>
  <span>Checked names: {{ checkedNames }}</span>
  <div id="example-4">
  <input type="radio" id="one" value="One" v-model="picked">
  <label for="one">One</label>
  <br>
  <input type="radio" id="two" value="Two" v-model="picked">
  <label for="two">Two</label>
  <br>
  <span>Picked: {{ picked }}</span>
  <div id="example-5">
  <select v-model="selected" multiple style="50px;" >
    <option disabled value="">请选择</option>
    <option disabled>A</option>
    <option>B</option>
    <option>C</option>
    <option>A</option>
    <option>B</option>
    <option>C</option>
    <option>A</option>
    <option>B</option>
    <option>C</option>
    <option>A</option>
    <option>B</option>
    <option>C</option>
  </select>
  <span>Selected: {{ selected }}</span>
  <br>
  <div>
  </div>
  <div>
    <input type="checkbox" @click="change($event)"  v-model="toggle" true-value="yes" false-value="no">
    <span>toggle: {{ toggle }}</span>
    <button v-on:click="doSomething()"> </button>
  </div>
  <div>
    <ul><li id='name'>{{name}}</li><li>{{age}}</li><li>{{city}}</li></ul>
  </div>
</div>
</div>
</div>
</template>

<script lang="ts">
import { Component, Prop, Vue, Watch } from 'vue-property-decorator'

@Component
export default class HelloWorld extends Vue {
  @Prop() private msg!: string;
  @Prop() private msgalter!:string;

  message: string = 'Hello1111111!'
  checkedNames: Array<string> = []
  picked: Array<string> = []
  selected: Array<string> = []
  toggle: Array<string> = []
  name: string = ''
  age : string = ''
  city: string = ''

  options = [
    { text: 'One', value: 'A' },
    { text: 'Two', value: 'B' },
    { text: 'Three', value: 'C' }
  ]

  // mounted (): void {
  //   console.log('created')
  // }
  onClick (): void {
    window.alert(this.message)
    this.message = this.message.split('').reverse().join('')
  };
  created (): void {
    // `this` 指向 vm 实例
    var y = document.getElementById('name')
    console.log(y)
  }
  mounted () {
    console.log('created')
    this.name = 'paula'
    this.age = '12'
    this.city = '上海'
    var x = document.getElementById('name')
    console.log(x)
  }
  change (e:any) {
    console.log(e)
    console.log(e.target.checked)
  };
  computed () {
    console.log(this.message)
  };
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped lang="less">
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
