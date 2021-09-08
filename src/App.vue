<template>
  <div id="app">
   
   <input v-model="message" placeholder="edit me" />
   <br>
   <textarea v-model="message" placeholder="复选框"></textarea>
   <p>Message is: {{ message }}</p>
   <p><button @click="message='李雪芹'">set message to lixueqin</button></p>
  <hr>
  复选框 (Checkbox)<br>
  你去哪儿旅游?{{x}}
  <br>
  <label> 
   <input type="checkbox" v-model="x" :value="1"/>
   <span>北京环球影城</span>
  </label>
  <label> 
   <input type="checkbox" v-model="x" :value="2"/>
   <span>大海</span>
  </label>
  <label> 
   <input type="checkbox" v-model="x"  :value="3"/>
   <span>上海迪士尼</span>
  </label>
  <hr/>
  单选框 (Radio)<br>
  你想去哪儿?{{y}}
  <br>
  <label> 
   <input type="radio" nane="want" v-model="y" :value="1"/>
   <span>北京环球影城</span>
  </label>
  <label> 
   <input type="radio" nane="want" v-model="y" :value="2"/>
   <span>大海</span>
  </label>
  <label> 
   <input type="radio" nane="want" v-model="y"  :value="3"/>
   <span>上海迪士尼</span>
  </label>
  <hr/>
  选择框 (Select)<br>
  你想去哪儿?{{z}}<br>
   <select  v-model="z">
    <option :value="1">环球影城</option>
    <option :value="2">大海</option>
    <option :value="3">迪士尼</option>
  </select>
  <hr/>
  多选multiple<br>
  用 v-for 渲染的动态选项<br>
  你想去哪儿?{{w}}<br>
   <select multiple v-model="w">
    <option v-for="item in array" :value="item.value" :key="item.value">
    {{item.text}}
    </option>
  </select>
  <hr/>
  from<br>
  登陆
   {{user}}<br>
  <form @submit.prevent="onSubmit">
   <label>
     <span>用户名：</span>
     <input type="text" v-model.lazy="user.username" />
   </label>
   <label>
     <span>密码：</span>
     <input type="password" v-model.trim="user.password" />
   </label>
   <button type="submit">提交</button>
  </form>
</div>
</template>

<script>
export default {
  name: 'App',
  data(){
    return {
     message:'hello',
     array:[
     {text:"环球影城",value:1},
     {text:"大海",   value:2},
     {text:"迪士尼",  value:3}
     ],
     x:[],
     y:'',
     z:'',
     w:[],
     user:{
       username:'',
       password:''
     }
    }
  },
  methods:{
    onSubmit(){
      console.log(this.user)
    }
  }
  ,
  components: {}
};
</script>