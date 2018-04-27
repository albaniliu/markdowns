# 比特币

比特币是一种peer-to-peer的电子货币系统
1. 支付网络
2. 货币

# 传统电子支付

依赖可信赖的第三方金融机构
不存在完全不可逆的交易
中介的存在，增加了交易的成本

# 防止币被盗刷
定义bitcoin为一串数字签名
![transaction](https://github.com/albaniliu/markdowns/blob/master/images/bitcion_transaction.png)

# 防止一枚币被花了多次
传统方式：通过像银行这样的中介，记录所有的交易
比特币：所有参与者都记录所有的交易。交易需要公开宣布，并得到大部分节点的同意

# 交易记录
区块链
![block_chain](https://github.com/albaniliu/markdowns/blob/master/images/bitcion_block_chain.png)
Tx: 交易记录
Prev Hash: 前一个block的hash值
Nonce：POW（Proof-Of-Work）计算出来的值

# Proof-Of-Work
找到Nonce值，让Block的hash值前面有n个0
如果大部分节点是诚实节点，真实链长得比欺骗链快

# 交易网络
1. 新的交易广播给所有节点
2. 每个节点接收新的交易记录到block里
3. 每个节点为自己的block计算Nonce值
4. 当一个节点找到了Nonce值，它广播这个block给所有节点
5. 当一个block里的所有交易都是有效的，并且是没有被花掉的时候节点就会接受这个block
6. 一个节点接受了一个block后，它会新建一个block指向接受的这个block，然后在新block上记录

节点认为更长的链是正确的链。当一个节点丢失block的时候，它会请求中间丢掉的block。

# 激励机制
一个block的第一条是个特殊交易，奖励给block的创建者。
当币发完后，也可以用交易费作为激励机制。

# 存储结构
![merkle_tree](https://github.com/albaniliu/markdowns/blob/master/images/bitcoin_merkle_tree.png)

block header没有交易数据，80 bytes。可以把block chain全部保存在内存中。

# 简单支付验证
![simplified_verification](https://github.com/albaniliu/markdowns/blob/master/images/bitcoin_simplified_verification.png)

并非所有参与网络节点都保存完整的记录
一个用户可以只保存最长链的header信息
当一个block到来时，他会访问网络上其它节点，是否已经接收接收这个block了
有一些超级节点保存所有的交易记录

# 隐私
所有交易都是公开的
交易中只包含了public key，没有个人信息

# 总结
1. 比特币是一个不基于信用的电子交易系统
2. 用了数字签名保证币的所有权
3. 在一个peer-to-peer网络中，使用POW来保证一致性，记录所有的交易记录，来防止一币多花









