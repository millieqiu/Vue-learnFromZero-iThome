<template>

  <!-- 引用元件成功 -->
  <myHeader :date="date" greetings="Nice to meet you :D"/> 

  <br />

  {{ message }}
  <br />
  {{ count }}
  <br />
  My name is {{ name }}
  <button @click="myFunction(10), changeName()">Click me!</button>

  <hr />

  {{ userName }}
  <br />
  <input type="text" v-model.lazy="formData.userName">
  <!-- v-model.lazy 可以在輸入完畢才會將內容儲存起來，換句話說就是將游標跳出，input 輸入框才會將值寫入到變數內 -->

  <hr>

  <h3>Day9 - 表單常用欄位</h3>
  {{ selectValue }} <br />
  <select v-model="formData.selectValue">
    <option value="">select</option>
    <option value="1">1</option>
    <option value="2">2</option>
    <option value="3">3</option>
  </select>

  <br />

  <input type="checkbox" v-model="formData.isCheck" /> {{ isCheck }}

    <br />

    {{ checkbox }} <br />
  <input type="checkbox" value="0" v-model="formData.checkbox" /> 0
  <input type="checkbox" value="1" v-model="formData.checkbox" /> 1
  <input type="checkbox" value="2" v-model="formData.checkbox" /> 2
  <input type="checkbox" value="3" v-model="formData.checkbox" /> 3

  <button @click="submit">送出</button>

  <br />

  <myView @viewText="getViewText" />

  {{ text }}

  <br>

  {{ emitText }}
  <myInput v-model="emitText" />

  <br>

  <Card>
    <h2>Content</h2>
  </Card>
  <Card>
    <a href="">Link</a>
  </Card>

</template>

<script>
import myHeader from './components/Header.vue'; // 引用元件，將程式碼模組化
import myView from './components/View.vue';
import myInput from './components/Input.vue';
import myCard from './components/Card.vue';

// 程式邏輯放置的地方

export default { // 所有程式邏輯都要寫在 export default 裡
  name: 'App', // 宣告這個 Vue
  components: {
    myHeader,
    myView,
    myInput,
    myCard,
  },
  data() {
    return {
      date: '2023/9/21',
      message: 'Hello World',
      count: 0,
      formData: {
        name: 'Alan',
        userName: '',
        selectValue: '',
        isCheck: false,
        checkbox: [],
      },
      text: '',
      emitText: '',
    }
  },
  methods: {
    myFunction(temp) {
      this.count += temp;
    },
    changeName() {
      this.name = 'Jacky';
    },
    submit() {
      console.log(this.formData);
    },
    getViewText(text) {
      this.text = text;
    },
  },
}
</script>

<style>
/* 相關 css 標籤語法放置的地方 */
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
