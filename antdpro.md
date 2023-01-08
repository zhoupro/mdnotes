
# and pro admin

## umijs

[umijs](https://v3.umijs.org/zh-CN/docs/getting-started)
### 快速启动
```bash
mkdir myapp && cd myapp
# create app
yarn create @umijs/umi-app
# install
yarn

# start 
yarn start
```

### 验证antd
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




