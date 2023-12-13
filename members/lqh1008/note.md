[什么是web3？](https://aws.amazon.com/cn/what-is/web3/)
### 概念
web3 简单来说是区块链技术的总称，这些技术可以分散互联网上数据的所有权及控制权。
### 核心理念（也具有透明性，不可篡改性）

1. 去中心化

这个概念大家经常能听到，所谓去中心化就是数据不由某个权威的机构所有以及控制，而是每位用户都可以控制数据存放的位置。去中心化的互联网用户可以根据需要出售自己的数据。

2. 去信任

web2 中，数据是由一些权威机构控制的，如果数据存在安全风险，或者管理不善，会导致用户信息丢失或者滥用。而 web3 则是去信任，用户可以在无需信任任何特定方的情况下进行交易和交互。

3. 语义网

借助语义网，应用程序能够通过理解 Web 数据的内容和上下文来执行复杂的任务。语义网使用元数据和人工智能为用户生成的数据提供含义（语义）。
Web 3.0 旨在更全面地转向目前存在于现有 Web 技术某些方面中的语义网技术。例如，搜索引擎可提供更准确且与上下文相关的搜索结果，而智能代理则可帮助用户更高效地执行任务。

4. 互操作性

Web 3.0 的目标是在不同技术之间建立更多的互连，从而数据无需中介即可在不同平台之间流动。互操作性使数据具有可移植性，因此用户可以在服务之间无缝切换，同时保持自己的首选项、配置文件和设置。
与此同时，集成各种物联网（IoT）设备的协议将 Web 的覆盖范围扩展到传统边界之外。例如，支持无边界交易的加密货币技术允许跨地域和政治边界进行价值交换。

**后面两个也不是太清楚是什么意思，希望有大佬可以解释下~**

[比特币跟区块链原理？](https://youtu.be/g_fSistU3MQ?si=4YrWZqI926lB0Nz0)
![image.png](https://cdn.nlark.com/yuque/0/2023/png/25628421/1701957746405-cc092109-6c47-4518-82a1-c1c97db0bad8.png#averageHue=%2342735d&clientId=u31180b18-6beb-4&from=paste&height=809&id=u959be399&originHeight=1011&originWidth=1902&originalType=binary&ratio=1.25&rotation=0&showTitle=false&size=2558408&status=done&style=none&taskId=udebd132e-7c0f-421e-9cca-6b873662e4f&title=&width=1521.6)
以上视频内容总结如下：
### 比特币概念
他是一个去中心化的电子记账系统。
场景：比如 A，B，C，D四个小朋友，每个人给其他人比特币都会广播一下，让每个人都知道这笔交易，链上的每个人都会记录这笔交易，交易记录 4000 条左右就会打包成一个块放到链上去。
在这种情况下就会出现几个问题？
1.为什么需要记账？ 2.以谁为准？  3.如何防伪？
reply1：因为记账的人会有奖励，奖励来源于，手续费（类似于银行转账的手续费）+ 打包奖励。
reply2：以谁为准的衡量是用工作量证明，也就是我们常说的挖矿。
extend：挖矿的原理就是通过 hash 函数 sha256 来生成加密，这个算法的特点就是正向算容易，反向及其困难，只能通过计算机的算力一个个试出来。
![](https://cdn.nlark.com/yuque/0/2023/jpeg/25628421/1701958848114-4fa3fe4a-ec1a-45bf-a98c-6a2048f3b917.jpeg)
在区块链中，每一个区块含有的信息是一个字符串 = 前块的头部 + 账单 + 时间戳 + 随机数，然后对这个值进行两次 sha256 的计算，计算后的结果要求前 64 为都是 0。这种情况下谁的算力强，谁算出来的概率就越大。
[比特币如何防伪？](https://youtu.be/pbAVauYsqP0?si=MO6E3FJLoUSAk-RI)
![image.png](https://cdn.nlark.com/yuque/0/2023/png/25628421/1701959620698-1b763d07-6a10-4b2e-a03d-32219dbc7df6.png#averageHue=%234c6f58&clientId=u31180b18-6beb-4&from=paste&height=555&id=u17fa70b5&originHeight=694&originWidth=1297&originalType=binary&ratio=1.25&rotation=0&showTitle=false&size=1478476&status=done&style=none&taskId=ubf0238ef-2527-455c-949b-c89742e0443&title=&width=1037.6)
reply3：

- 身份认证

采用非对称加密对交易信息来实现。
先使用 hash 算法生成一个摘要，然后用私钥加密生成一个密码，然后将公钥、交易信息以及密码广播到链上。这时候链上的人拿到这个交易信息会用 hash 进行运算获得摘要1，然后用公钥去解密这个密码生成摘要2，对比两个摘要，如果相等，那么就证明这个信息不是伪造的。

- 双重支付的问题

余额检查
通过追溯之前的块，来判断当前所剩的余额，避免出现余额不足的情况下还可以进行交易。
双重支付
两个交易同时发出后，因为每个人接受到的消息可能会不一样，接受到后就会把区块进行打包，等某个幸运儿数学题解出来后（也就是挖矿成功后），这个交易才会被确认，那么就会把这个区块链接到区块链上去，那另一个块就会作废，这样就避免了双重支付。

- 防止篡改

根据最长链原则，如果一个人想篡改数据，那么需要有比全世界所有人更强的算力才能解决，但是如果这个人真有这个实力，也没必要篡改了。
### [合约是什么？](https://youtu.be/UlDmA2buwGU?si=VzPwHfscIOs0ehoi)
### [MetaMask使用说明](https://youtu.be/cxkXzTA9YIc?si=sKsB0z0XnMcxGbHq)
### [gas是什么？](https://youtu.be/E932myMejGY?si=R1ETQrBs8GaL6sE1)
### [什么是以太坊？](https://youtu.be/26kR2vUbbJo?si=ny9xhqf5yDBL_1tJ)
他是一个开源的平台，可以让任何人都使用基于区块链技术的去中心化应用程序，它上面运行的程序叫做 dapps。不依靠传统中心化金融中介机构的金融应用简称DeFi，致力于让金融系统变得更加透明，更加可信。
什么是以太币？
区别于比特币
 	1.比特币随着金融危机应运而生的，它具有一般流通货币的属性，被称为黄金2.0。以太币更像石油2.0。为了激励人们在以太坊上维护数据，任何人想要在以太坊开发程序，都需要支付以太币来支撑 dapp s的运营。
  	2.比特币数量有限，以太坊无限。
以太币无论交易是否成功，都需要支付gas。
