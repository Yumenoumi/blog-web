---
title: go-noss
date: 2024-01-07T12:16:03+08:00
draft: False
featuredImage: https://images.unsplash.com/photo-1701743804452-24fd24844bd4?ixid=M3w0NjAwMjJ8MHwxfHJhbmRvbXx8fHx8fHx8fDE3MDQ2MDA5NDF8&ixlib=rb-4.0.3
featuredImagePreview: https://images.unsplash.com/photo-1701743804452-24fd24844bd4?ixid=M3w0NjAwMjJ8MHwxfHJhbmRvbXx8fHx8fHx8fDE3MDQ2MDA5NDF8&ixlib=rb-4.0.3
---

# [ubuygold/go-noss](https://github.com/ubuygold/go-noss)

1. 将.env.example改为.env
2. 在.env里配置公私钥。NPUB/NSEC的获取可以使用OKX钱包的nostr链获取地址/导出私钥获取，暂时不知道如何从TP钱包获取NPUB/NSEC。注意npub... nsec..开头的需要转换一下才能使用，可以去https://nostrcheck.me/converter/ 转换
3. 使用golang编译脚本，或者使用release中编译好的版本
4. 运行
5. 再加一句话：判断你是否成功运行脚本：1. 成功运行没闪退 2. 在蹦字 3. 返回值Response显示是200 4. Publish to后面有id，并且id前5位为0

## FAQ
1. 我运行时闪退了：ARB节点没配置好，或者节点被冲烂了，换一个。
2. 返回值一直是429：算力过剩，项目方的服务器嫌你烦了，临时封禁了你的IP，等一会儿。
3. 打出来的ID为空或者前5位不是0：公私钥配置错误，仔细阅读上面的第2条。

## 2024.1.5更新
修改了由于项目方不认识美化后Json导致的问题，本人已经使用工具出块，效率不明，自己尝试，不保证能出块;
另外，由于Noss难度为21，因此大家的算力都是过剩的，频繁提交POST请求会导致服务器返回429（Too Many Requests/太多请求）错误，与本程序无关；
内存问题持续优化中。