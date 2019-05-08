# 前端学习中遇到的小问题
## 小问题
1. Store中不可使用指向vue的this，this是指向store的  
将vue实例添加到window.vue,用window.vue.$XXX代替this.$XXX  
2. 执行顺序，vue-router的beforeEnter在vue的beforeCreated之前执行，无法访问vue组件实例，需要在next(vm =>{})回调中访问
3. router中beforeEnter next(to)无限跳转导致电脑死机
4. 在store中action发起异步http请求获取数据修改state，导致action后面代码获取到的state是修改之前的state  
临时解决方案，后面的操作全放到action中执行
5. mongoose的find()返回的是document对象，无法修改属性，delete XX时返回值是true但实际上并不会删除该属性  
把对象的属性拷贝到另一个对象自己改  
`var targetObj = JSON.parse(JSON.stringify(copyObj))`  
通过JSON完成拷贝不会拷贝对象中的函数，以及原型上的属性和函数，单纯的拷贝数据:)
6. vue中的__ob__是什么  
7. element-ui el-input回车刷新页面，在el-form中加@submit.native.prevent阻止原始事件
8. element-ui el-table中使用v-if不会重新渲染表格  
用this.$set(obj,key,value)代替直接修改某个数据的的值，以后遇到不能动态渲染的用$set就完事了噢
9. 多维数组合并成一维数组
## 大问题
1. 是否考虑用户信息持久化保存在cookie里还是localstorage里还是sessionstorage以及安全问题
2. 前端权限管理根据角色动态添加路由  
  使用vue-router addRoutes()动态挂载路由  
3. 跨域session改变的问题  
  axios请求拦截器每一次请求前加一个token  
