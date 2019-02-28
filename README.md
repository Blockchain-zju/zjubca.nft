# ZJUBCA Non-Fungible Token (NFT) 

非同质化Token合约，供协会内部使用。

Non-Fungible tokens circulate in ZJUBCA.

## Abstract

根据下列标准API，我们实现了基于EOS的非同质化合约（下简称为NFT），并提供了用于追踪和转移NFT的基础方法。

The following standard allows the implementation of a standard API for NFTs within EOS smart contracts. This standard provides basic functionality to track and transfer NFTs.

何为NFT？NFT最初诞生于以太坊标准ERC721，用于表征具有唯一性的数字资产：

- 现实资产 - 房产、艺术品等
- 加密藏品 - 唯一性或限量版的数字收藏品
- 具有“负值”属性的资产 - 贷款、负债或其他未尽责任的表征。

NFTs can represent ownership over digital or physical assets:

- Physical property — houses, unique artwork
- Cryptocollectibles — unique collectibles or  instances which are part of limited-edition collections. 
- "Negative value" assets — loans, burdens and other responsibilities

NFT是**互不相同**的。在使用时你必须确认每一个Token的所有权。

NFTs are *distinguishable* and you must track the ownership of each one separately.

## Specification

一个NFT包含如下字段:

- id `uint64` - 全局唯一的id
- uri `string` - 统一资源标识符，遵循[RFC 3986](https://www.ietf.org/rfc/rfc3986.txt)
- owner `name`  - 所有者名称
- value `asset` - Token价值，固定为1
- tokenName `string` - Token的名称

A nft contains several fields below:

- id `uint64` - unique identifier
- uri `string` - uniform resource identifier, follow [RFC 3986](https://www.ietf.org/rfc/rfc3986.txt)
- owner `name` - owner name
- value `asset` - token value, always 1
- tokenName `string` - token name

### URI [RFC 3986](https://www.ietf.org/rfc/rfc3986.txt)

统一资源标识符（英语：Uniform Resource Identifier，缩写：URI）是一个用于标识某一互联网资源名称的字符串。该种标识允许用户对网络中的资源通过特定的协议进行交互操作。

通用URI的格式如下：

```
scheme:[//[user[:password]@]host[:port]][/path][?query][#fragment]
```

一个符合URI格式的互联网URL例子:
```
http://www.google.com/search
```

在协会Dapp的使用场景中，如果您想发行NFT，我们建议您遵循以下格式来设计Token的URI:

```
nft://[Dapp英文名称]/[种类/用途]
```

如发行NFT用于表征订单系统(order.system)的代金券(coupon)，则我们推荐的URI格式如下:

```
nft://order.system/coupon/...(自定义字段)
```

## How to build and deploy
1. `npm install`
2. `js4eos dapp compile zjubca.nft`
3. `js4eos dapp deploy zjubca.nft`
