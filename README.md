# router-test

## Gör såhär

1. Installera vue router
```
npm install vue-router
```

2. Aktivera vue-routes i main.js-filen
```
Vue.use(VueRouter);
```

3. Deklarera dina routes
```
const router = new VueRouter({
  routes: [
    { path: '/', component: Home },
    { path: '/products/', component: Products },
    { path: '/products/:favlist', component: Products }
  ],
  mode: 'history'
});

new Vue({
  router,
  render: h => h(App),
}).$mount('#app');
```

4. Med `:favlist` kan du nu kolla ifall url:en innehåller något

5. Ta url:en och gör ett API-anrop med id-nummer