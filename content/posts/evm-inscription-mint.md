---
title: evm-inscription-mint
date: 2023-12-16T12:18:20+08:00
draft: False
featuredImage: https://images.unsplash.com/photo-1701979396507-4f4f8db40269?ixid=M3w0NjAwMjJ8MHwxfHJhbmRvbXx8fHx8fHx8fDE3MDI3MDAxMjR8&ixlib=rb-4.0.3
featuredImagePreview: https://images.unsplash.com/photo-1701979396507-4f4f8db40269?ixid=M3w0NjAwMjJ8MHwxfHJhbmRvbXx8fHx8fHx8fDE3MDI3MDAxMjR8&ixlib=rb-4.0.3
---

# [sfter/evm-inscription-mint](https://github.com/sfter/evm-inscription-mint)

# 兼容EVM链的铭文自动化Mint脚本

## 🛠 使用说明

### Step 1: 首先安装 nodejs

先去 Nodejs 官网下载安装自己电脑操作系统对应的版本

```bash
https://nodejs.org/en
```

然后看一下安装的版本，是否安装成功

```bash
node -v
npm -v
```

如果你更喜欢使用 yarn 则安装 yarn
```bash
npm i -g yarn
```

### Step 2: 下载脚本源代码
先用 git clone 源代码到本地
```bash
git clone https://github.com/sfter/evm-inscription-mint.git

cd evm-inscription-mint
```
如果是 Windows 电脑没有安装 git，先去下面网站下载安装 git 软件
```bash
https://gitforwindows.org
```

### Step 3: 重命名当前目录下的 config.js.example 为 config.js 文件
```bash
cp config.js.example config.js
```

### Step 4: 修改当前目录下的 config.js 配置文件
```javascript
const config = {
    // 你想要打多少张，这里就设置多少，建议单次别超过 50，不然容易不上链
    repeatCount: 1,

    // 在当前的 gas 基础上增加多少倍
    increaseGas: 1.2,

    // 你钱包的私钥
    privateKey: "",

    // 铭文json数据（替换成你想打的铭文json格式数据）
    tokenJson: 'data:,{"p":"fair-20","op":"mint","tick":"fair","amt":"1000"}',

    // RPC结点（兼容 evm 链都行）打哪条链就用哪条链的节点地址
    // eth =>  https://mainnet.infura.io/v3
    // arb => https://arb1.arbitrum.io/rpc
    // polygon => https://polygon-rpc.com
    // op => https://mainnet.optimism.io
    // linea => https://mainnet.infura.io/v3
    // scroll => https://rpc.scroll.io
    // zks => https://mainnet.era.zksync.io
    rpcUrl: "https://arb1.arbitrum.io/rpc"
}
```

### Step 5: 安装依赖包
```bash
npm i
```
or
```bash
yarn install
```

### Step 6: 运行 Mint 脚本程序
```shell
node index.js
```
or
```shell
yarn start
```
or
```shell
npm run start
```