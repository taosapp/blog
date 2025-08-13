查看npm镜像源地址

```bash
npm config get registry
npm config set registry https://registry.npmjs.org/
npm login
```

控制台会返回下一个小版本号 如v1.0.2（**不要手动修改package.json里的版本号**）

```bash
npm version patch
npm publish
```

设置回cnpm镜像源
```bash
npm config set registry https://registry.npmmirror.com
```
