# 加密技术与商业创新

区块链高级技术专家群内部讲座系列活动。

群内由区块链相关团队或组织的技术专家、学者和负责人等组成，目前仅限邀请加入。

分享内容会在 `TechFirst` 微信公众号进行首发，欢迎关注。

## 嘉宾介绍

![Zhi Liu](_images/lz.jpg)

刘智，a security  and crypto zealot。电子科技大学信息安全博士、纽约州立大学石溪分校安全研究员。多年安全系统研发经验，精通安全攻防和加密技术。
专注安全和加密技术及商业创新，擅长构建安全产品、设计安全架构。

他的 Email 是 [cowliucd@gmail.com](cowliucd@gmail.com)，他的个人微信公众号为

![wechat](_images/lz_wechat.jpg)

## 讲座内容

## Part 1. Opening
### 1. 开始
非常感谢有这样一个机会，能和大家分享交流我对加密的理解和思考。

#### 为什么要做这次分享？
大家都了解加密并且可能深入研究过算法，但往往忽略了 **如何在产品中正确和高效的使用加密算法**。常见问题包括：

- 错误使用加密算法，无法提供安全性保护(甚至减弱安全性)
- 自己造轮子设计安全通信协议
- 未能平衡安全性和性能开销


**内容简介**
第一部分是常用加密算法实践指南；第二部分是我对该领域商业创新的思考。

<i class="icon-pencil"></i> 本文内容属于 “crypto engineering”，不涉及数学原理。


### 2. 关于我
- a security and crypto zealot
- 电子科技大学信息安全博士(2009-2013)
- 纽约州立大学石溪分校安全研究员(2010-2012)
- 多年安全架构和产品研发经验，精通安全攻防和加密技术
- 专注安全和加密技术及商业创新
- 擅长构建安全产品、设计安全架构

大部分朋友对我还不熟悉，先介绍下自己。我一直从事安全领域，了解区块链来源于对加密的兴趣，同时也感受到区块链社区的开放性。我现在成都 **作为产品经理和架构师负责大数据安全产品，即用大数据技术分析和解决安全问题**。

本文最后有联系方式，欢迎随时交流，ping me!

### 3. 我们需要加密吗？
![03.png-116.5kB][1]
加密要解决的核心问题是 **数据安全和隐私保护**。“the armor in digital age” 是非常贴切的比喻。

<i class="icon-pencil"></i> 有多少人了解 **Safe Harbor(安全港)** 和 **HIPAA**？

中国《网络安全法》即将立法，对公民隐私的保护已提上日程。

### 4. 加密的应用
![04.png-87.8kB][2]

加密技术古老而崭新，有非常多的机会和其它场景结合；新型行业如物联网、区块链、人工智能都迫切需要数据和隐私保护。这些结合属于跨界创新，是发挥想象力和“奇迹”诞生的方向。

### 5. 加密的现实意义(1)

![6.png-51.2kB][3]
最近几年，加密遭遇到了前所未有的挑战(和机会)，**它是技术、商业和社会的交叉点**。区块链也是这三者的结合。要在一个垂直领域做出原创创新比较难，而跨界创新更有可能，如史蒂夫 乔布斯所言：
> It is in Apple's DNA that technology alone is not enough, it's technology married with liberal arts, married with the humanities.”

大部分国际 IT 巨头对加密持积极意见，如 Google，Apple 等公司都在大力提倡 HTTPS。Google 将使用 HTTPS 的网站优先展示；2017 年 1 月起，**AppStore 强制要求所有 app 使用 https**。加密同时也产生了负面影响，如恐怖分子采用加密技术通讯。

### 6. 加密的现实意义(2)
![07.png-259.9kB][4]
邮件门事件很大程度影响了美国大选结果；朴槿惠也受到邮件泄露影响。

* 为什么他们不用加密邮件？
* 有多少人用过 OpenPGP，Outlook 加密数据和邮件？

[McAfee 开始用区块链提升邮件安全][5]，**我觉得区块链并不能解决邮件安全的核心问题**。事实上我们并不迫切需要分布式账本保护邮件内容和发送记录，相反，邮件信息不应该放在公开账本。

## Part2. 常见加密算法与陷阱

### 7. 加密算法的问题

David Brumley 是卡耐基梅隆大学教授，网络安全顶级专家，美国国防部安全顾问。他对人工智能在安全的发展趋势有非常深刻的洞见，见我的个人公众号分享。下面是他关于加密的看法：

> In crypto, I think the biggest weakness right now is not the algorithms, but the implementation. That gets far too little attention. Most people don't even know what authenticated encryption is, and end up implementing something poorly themselves.

这段话来自我和他去年交流。这引申出一个重要话题：**如何看待加密技术的发展和应用**？

尽管加密算法不断发展，例如同态和量子加密，但一个新型加密算法从诞生到成熟、最后成为标准少则数年多则十多年。例如 RSA, AES, Diffie-Hellman 仍是二三十年前发明的算法，而区块链也没有使用新型加密算法。所以，**我们不能对正在发展的加密算法过于乐观，一些复杂场景仍可通过现有技术解决**。尽管国内在安全和密码学理论不输欧美，但工业界创新成果差距非常大。

*评价一个加密算法的优劣不仅是安全性，还包括性能和兼容性。国密、同态加密的应用都需考虑这些因素。*

### 8. 跨界创新
Ross Anderson 是剑桥大学网络安全教授，这段话非常有趣，再次说明跨界创新的重要性。
> Unfortunately, the computer security and cryptology communities have drifted apart over the last 25 years. Security people don't always understand the available crypto tools, and crypto people don't always understand the real-world problems.


### 9. 安全核心要素
![10.png-45.6kB][6]
最重要的是保密性、完整性和身份可认证性，它们都可通过单个或组合加密算法解决。

* 能说出每类问题由哪些加密算法解决吗？
* 能否和你们在产品中需要解决的问题对应？

### 10. 加密算法分类
加密算法的分类(按照个人理解的分类)。深刻理解这些算法的优缺点，才可能创造性解决问题。例如不了解 Hash 的使用场景，就很难把它联想运用于 POW 的设计中。 

* 能否说出各分类的常见算法、使用场景和 **局限性**？

![12.png-25.5kB][7]


### 11. 对称加密(1)
![](_images/p10.png)

对称加密是“easy piece of cake” :)

- 加密和解密共用一个密钥
- AES 是主流对称加密算法
    - GCM 已成为主流标准，安全性较高、速度快 
- 特点：加解密速度快，需要考虑密钥保存
- 常见陷阱
        - 密钥长度不够，推荐 1024bit 或更高
        - 算法不安全，如 DES
        - 明文存储密钥
        - 自己编写随机数生成器，应使用强随机数生成器(PRNG)


### 12. 非对称加密
- 使用场景
    - 加密：接收方公钥加密，接收方私钥解密
    - 签名：自己私钥加密，接收方用发送方公钥验签
- 具体使用
    - **仅加密短字节**(<64字节)，签名速度慢、验签快(签名比验签慢数十倍)
- 对称加密和非对称加密通常混合使用
- 常见非对称加密算法: RSA、EC(椭圆曲线) 
    - RSA 较为成熟，EC 密钥更短(区块链使用 EC 的原因)


### 13. 非对称加密注意事项

**很多人了解非对称加密，但对它不适合做什么不清楚**。频繁签名、加密大数据是常见误区。如果app或服务器频繁签名，性能损失非常大。

比特币和区块链使用 EC 而不是 RSA，主要原因是相同安全强度 EC 需要的密钥位数更短。国密 SM 的非对称加密和数字签名基于 EC，数学运算更复杂。下图是相同安全强度下 RSA 和 EC 密钥长度对应关系，单位为 bits。

<table>
    <tr>
        <th rowspan="1">RSA</th>
        <th>1024</th>
        <th>2048</th>
        <th>3072</th>
    </tr>
    <tr>
        <th rowspan="1">EC</th>
        <td>160</td>
        <td>224</td>
        <td>256</td>
    </tr>
</table>

**使用 EC 将显著节约带宽，下面是一个定量分析。**

假设金融机构采用区块链支付，每秒处理 10 万笔交易，每笔交易包含密钥和其它信息(假设 1KB)，**使用 RSA(2048 bits)的带宽为 292 MBps, 使用 EC(224 bytes)带宽为 120 MBps，带宽节省近 60%**！


### 14. Hash
- 接收方很容易验证信息完整性，速度极快
- 使用最简单但应用范围广泛的算法，区块链底层技术之一
- 常见误区
    -避免使用 MD5 等不安全算法，使用 SHA256
    -密码存储使用 Hash+salt，防止彩虹表攻击

![hash.jpg-55.1kB][8]

#### Hash 深入分析

Hash 算法使用简单，但使用场景非常丰富，包括数据完整性验证和 POW。比特币的重要参考模型 hash-cash 用于“减缓”垃圾邮件，其 POW 使用了 Hash。

#### Hash 算法有两个特点

* 改变输入的一个字节都将导致计算结果巨大差异。
* 计算速度快，比对称加密和非对称加密快很多，计算时间为亚毫秒级。即使输入为大量数据，计算速度也不会明显降低。
 

目前主流 Hash 算法是 SHA256，避免使用 MD5、SHA-1 等不安全算法。现在破解 MD5、SHA-1 的成本越来越低，国外安全研究人员通过验证，破解 SHA-1 仅需 10 天！破解成本也仅为数十万人民币，见http://news.mydrivers.com/1/450/450291.htm。  

### 15. 密钥交换

![diffie-hellman.png-48.2kB][9]

Diffie-Hellman 算法是现代互联网安全基石，解决不安全信道上安全传输密钥问题；其原理和代码实现简单，也是 DH 得到广泛应用的重要原因。HTTPS 核心流程使用了 DH。2015 年两位发明者被授予图灵奖，下面是两位权威人士对 DH 获奖的评论：

>ACM 主席 Alexander L.Wolf：“今天，加密的科学主宰了传媒，而且被视为影响国家安全、政府和私营企业关系的重要问题，也吸引了几十亿美元用于研究和开发”。 

>Google 杰出科学家 Andrei Broder: “公钥加密是我们行业的根本问题，对私有数据的保护，依赖于对信息所有者信息的确认，以及确保通信的完整和机密性。”


### 16. 最佳实践(1)
- “黄金法则”- 摘自《现代加密应用指南》
    - 不要尝试自己编写加密算法
    - 不要尝试自己设计安全协议
- 加密强度与性能是一对天然矛盾

密钥安全是大家都非常关注的话题，特别是私钥，对称密钥可动态生成。
银行U盾是被证明比较失败的产品。

<i class="icon-pencil"></i>  有多少朋友自己编码实现过加密算法，以及设计安全协议？ 

自己编写加密算法和安全协议在设计和代码层面会有很多安全问题。HTTPS 是设计安全通信协议的最好范本；经过多年不断完善，HTTPS 已非常成熟和安全。

HTTPS 对服务器的性能损耗也较大，百度 2013 年推出全站 HTTPS 之前，花费大半年时间作复杂均衡和调优。如果区块链应用使用全站 HTTPS，海量并发交易对服务器性能考验较大。**强烈建议只做单向握手**！

### 17. 最佳实践(2)
- 明确各类算法使用场景
- 密钥安全保护
- 跨平台算法实现存在差异

如果大家正在使用 openssl，注意 openssl 安全漏洞较多，而且“代码极为糟糕和混乱”，裁剪难度也较大。 

### 18. 最佳实践(3)
- 国密算法(SM)
- 专利/许可证问题

国密标准已公开，需要自己实现代码，目前网上没有标准库。随着国家推广国密标准，SM 会得到更普遍应用。 

国密算法的安全性仍有待验证，因为加密算法的安全性必须得到广泛和公开测试才能得到认可，并最后成为标准(国密标准 2010 年左右公开)。

**License, license, license**!重要的事情说三遍。如果产品准备在 AppStore 和 GooglePlay 上架，应特别注意 license，美国对不遵守 IP 的处罚相当严厉(甚至有破产可能)。

# Part3. 商业创新思考

### 19. 加密商业创新方向
- 数据安全
- 隐私保护
- 区块链
- IoT
- 匿名化

加密商业创新已引起用户和和资本市场极大兴趣，目前主要在美国和以色列。数据安全和隐私保护是未来的爆炸式增长领域，区块链是一个很好的桥梁，国内氛围也在慢慢成熟。

### 20. 几点思考(1)
一些开放问题，分析清楚这些问题有利于相关产品更快成熟，并带来真正价值。

- 互联网共享精神与加密的博弈
- 创新技术能否解决实际问题？
- **区块链是良药还是止痛剂**？
    - 要解决的核心问题是什么？
    - 使用替代/更简单技术能否达到?

--------
**我对区块链的粗浅理解**

区块链的优势是提供 "public accountability"，并不是所有场景都合适，**过于依赖区块链会使我们看不清问题本质**，我把它叫做 "blockchain inhibit"(抑制区块链)。 《哈佛商业评论》2017年第一期文章"区块链的真相"，它把区块链和TCP/IP做类比，足以看出区块链的伟大，同时区块链也是破坏性创新(disruptive innovation)， 而不是与搜索引擎和物联网同级别的延续式创新。所以区块链开始会在小众行业和范围内应用，最后成为全社会标准。

### 21. 几点思考(2)
什么是"叫好又叫座"的创新？ 创新技术并不代表好的产品，有些技术往往使问题更复杂。我认为能发挥价值的创新包含四个维度：

 - **"有趣"问题**
 -  **合理的技术方案**
 -  **技术实现简洁性**
 - **实用价值程度**

下图是针对加密领域的创新评价，各维度满分为 5 分；HTTPS 在各个维度表现都很突出。如果一个产品或方案不能用一两句话说清楚，说明还不够清晰和简洁，但同时需要做非常多的工作达到简洁性。

![创新比较.png-94.5kB][10]

### 22. Be paranoid and inquisitve
![dickson.png-8kB][11]
paranoid-本意是偏执，这里意为独立思考，inquisitive-好奇心。**好奇心驱使发现问题，独立思考促使创造性解决问题**     

zcash 源于一个“有趣问题”即提供区块链交易匿名保护，这是一个简单问题的提出，但匿名化对区块链价值有显著提升。

**(正文完)**

### 23. 参考资料
- 文学读物
    [《失控》][12]、[《千禧年三部曲》][13](最喜欢的小说之一)
- 国密
   - [SM标准][14]，[SM算法库GmSSL][15]
- [Applied Crypto Hardening][16](非常好的加密技术资料)
- [现代密码学实践指南][17](适合进阶阅读)

### 24. Copyrights
- 本文仅代表作者个人立场，欢迎交流
- 联系方式：cowliucd@gmail.com, 微信 yurenliu
- 您可任意复制、转载本文(无 license 问题)
    -转载或引用本文内容时若能联系作者，十分感谢
- 如果有任何问题或 idea, ping me!


### 25. Q&A
上面是本次全部分享内容，希望对社区有帮助。由于时间有限，部分内容还不够深入，欢迎离线交流。
部分内容来源于个人公众号，可参考：

* [互联网时代加密的应用与悖论][18]
* [揭秘潘多拉魔盒-加密原理与实践][19]

---


  [1]: _images/p3.png
  [2]: _images/p4.png
  [3]: _images/p5.png
  [4]: _images/p6.png
  [5]: http://www.btc38.com/news/2017/1/12978.html
  [6]: _images/p9.png
  [7]: _images/p12.png
  [8]: _images/p14.jpg
  [9]: _images/p15.png
  [10]: _images/p21.png
  [11]: _images/p22.png
  [12]: https://book.douban.com/subject/5375620/
  [13]: https://book.douban.com/series/5314
  [14]: http://www.oscca.gov.cn/News/201204/News_1228.htm
  [15]: http://gmssl.org/
  [16]: https://bettercrypto.org/static/applied-crypto-hardening.pdf
  [17]: https://gist.github.com/byronhe/232d22f1d3dcaa0a20cb
  [18]: http://mp.weixin.qq.com/s/Rex_ZNbe3xrfo-pNLAwhJg
  [19]: http://mp.weixin.qq.com/s/_w0JjArenB7jYdnDOrQGWw

## 鼓励支持
如果你喜欢讲座分享的内容，欢迎通过如下微信二维码对专家进行支持和鼓励。

![10](_images/10.png)
![20](_images/20.png)
![50](_images/50.png)
![100](_images/100.png)

===== 关于 TechFirst 公众号 =====

专注云计算、大数据、Fintech、人工智能、分布式相关领域的热门技术与前瞻方向。

发送关键词（如云计算、大数据、容器、区块链），获取热门点评与技术干货。

欢迎投稿！
