
# and pro admin

## 1.1 umi 快速启动

### 1.1.1 快速启动

[umijs](https://v3.umijs.org/zh-CN/docs/getting-started)

```bash
mkdir myapp && cd myapp
# create app
yarn create @umijs/umi-app
# install
yarn

# start 
yarn start
```

### 1.1.2 验证antd
修改/opt/myapp/src/pages/index.tsx
```tsx
import styles from './index.less';
// add
import {DatePicker} from 'antd'


export default function IndexPage() {
  return (
    <div>
      <h1 className={styles.title}>Page index</h1>
      <!--add--/>
      <DatePicker />
    </div>
  );
}

```
### 1.1.3 发布
```bash 
yarn build
# confirm
yarn global add serve
~/.yarn/bin/serve ./dist/
```

## 1.2 umi 路由

```tsx
 routes: [
    { path: '/', component: '@/pages/index' },
    { path: '/user', 
        component: '@/layouts/index',
        wrappers: ['@/wrappers/auth'],
        routes:[
            { path: '/user/one', component: '@/pages/index' },
            { path: '/user/two/:id', component: '@/pages/two' },
            { component:'@/pages/404' }
        ]
    },
    { component:'@/pages/404' }
  ]
```
### 1.2.1 组件
path: /opt/myapp/src/layouts/index.tsx
```tsx
export default function index(props:any) {
  return (
  <div>
    <h2>header</h2>
    {props.children}
    <h2>footer</h2>
  </div>
   )
}
```
### 1.2.2 wrappers
path: src/wrappers/auth.tsx
```tsx 
import {Redirect} from 'umi'

export default function auth(props: any) {
    
    const isLogin = true
    if (isLogin){
         return <div>{props.children}</div>
    }else{
        return <Redirect to="/" />
    }
}
```

### 1.2.3 参数

{ path: '/user/two/:id', component: '@/pages/two' },

```tsx 
export default function two(props:any) {
  console.log(props)
  return (
    <div>two</div>
  )
}
```

### 1.2.3 404 页面

{ component:'@/pages/404' }

## 1.3 mock

### 1.3.1 mock
path:/opt/myapp/mock/index.ts
```ts 
export default {
    '/api/index':{
        id:1,
        name:'Tom',
        age:12
    },
    'GET /api/person':{
        id:2,
        name:'lili',
        age:22
    }
}
```

### 1.3.2 request
```tsx
import styles from './index.less';
import {request} from 'umi'
//add
import {DatePicker,Button} from 'antd'


export default function IndexPage() {
    const getData = async ()=>{
        //请求数据
        const res = await request('/api/index')
        console.log(res)

    }
  return (
    <div>
      
      <h1 className={styles.title}>Page index</h1>
      <DatePicker />
      <Button onClick={getData}>click</Button>
    </div>
  );
}
```


