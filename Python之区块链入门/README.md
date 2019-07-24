# Python 区块链入门
区块链(BlockChain)由一个共享的，容错的分布式数据库和多节点网络组成。  
简单来说，区块链就是把加密数据（区块）按照时间顺序进行叠加（链）生成的永久、不可逆向修改的记录。具体来说，它区块链是由一串使用密码学方法产生的数据块组成的，每一个区块都包含了上一个区块的哈希值（hash），从创始区块（genesis block）开始连接到当前区块，形成块链。每一个区块都确保按照时间顺序在上一个区块之后产生，否则前一个区块的哈希值是未知的。它是比特币的一个重要概念。  

## 特点
   - 去中心化:区块链不依赖于某个中心节点，而是依赖于分布式的各个节点。  
   - 无须信任系统:区块链中基于密码学算法，数据需要网络内其他用户的批准，所以不需要一套第三方中介结构或信任机构背书。  
   - 不可篡改和加密安全性:区块链采取单向哈希算法，同时每个新产生的区块严格按照时间线形顺序推进，时间的不可逆性导致任何试图入侵篡改区块链内数据 信息的行为都很容易被追溯，导致被其他节点的排斥，从而可以限制相关不法行为。  
以上特点使得区块链在银行、证券市场和金融等诸多领域有着越来越多的应用。  
## 区块链的Python实现
```
   # block.py
   import hashlib
   import uuid


   class Block(object):
       def __init__(self, data=None, previous_hash=None):
           self.identifier = uuid.uuid4().hex   # 产生唯一标示
           self.nonce = None                    # nonce值
           self.data = data                     # 区块内容
           self.previous_hash = previous_hash   # 父节点哈希值
        
   def hash(self, nonce=None):
     
   # 计算区块的哈希值
        
        message = hashlib.sha256()
        message.update(self.identifier.encode('utf-8'))
        message.update(str(nonce).encode('utf-8'))
        message.update(str(self.data).encode('utf-8'))
        message.update(str(self.previous_hash).encode('utf-8'))

        return message.hexdigest()

  def hash_is_valid(self, the_hash):
  # 校验区块哈希值有否有效
      return the_hash.startswith('0000')

  def __repr__(self):
        return 'Block<Hash: {}, Nonce: {}>'.format(self.hash(), self.nonce)
  ```
以上就是一个区块结构，这里实现的是一个简化版，没有完全对应比特币中的区块。这里的区块包含一个唯一标识符、父节点的哈希值、nonce值和该区块的内容字段。可以看到一个区块的哈希值必须满足一定的条件才是有效的，比如以0000开始。下面对这个区块结构进行初始化。

