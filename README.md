# 前端学习中遇到的小问题
## 小问题
1. Store中不可使用指向vue的this，this是指向store的  
将vue实例添加到window.vue,用window.vue.$XXX代替this.$XXX  

## 大问题
1. 是否考虑用户信息持久化保存在cookie里还是localstorage里还是sessionstorage以及安全问题
2. 前端权限管理根据角色动态添加路由  
  使用vue-router addRoutes()动态挂载路由  
3. 跨域session改变的问题  
  axios请求拦截器每一次请求前加一个token  

