<template>
  <div>
    <span v-bind:title="message">
      鼠标悬停几秒钟查看此处动态绑定的提示信息！
    </span> 
    <div id="app-3">
      <p v-if="seen">现在你看到我了</p>
    </div>
    <ol id="app-4">
      <li v-for="todo in todos" :key="todo.text">
        {{ todo.text }}
      </li>
    </ol>
    <p>{{ message }}</p>
    <input v-model="message">
    <button v-on:click="reverseMessage">反转消息</button>
    <pp post-title="ss"></pp>
  </div>
</template>

<script>
import pp from './prop.vue'
export default {
  components:{pp},
  data:()=> ( {
    message: '页面加载于 ' + new Date().toLocaleString(),
    seen: false,
    todos: [
      { text: '学习 JavaScript' },
      { text: '学习 Vue' },
      { text: '整个牛项目' }
    ],

  }),
  methods: {
    reverseMessage: function () {
      this.message = this.message.split('').reverse().join('')
    }
  }
}
</script>
