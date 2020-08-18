# 简介

本接口为 conflux-scan-backend 开发用接口, 数据来源于 Conflux Oceanus 主网数据, 
旨在为有需要的使用者临时提供一个快速查询工具, 实际数据请访问 [Conflux-Scan 官网](http://www.confluxscan.io/)

## 数据说明

* 返回数据中带有 "listLimit" 的接口有翻页限制, 最多只展示 page * pageSize <= listLimit 条查询项.
* 返回数据中的 timestamp 为所在 epoch 的时间.

## 免责申明:

* 本接口为开发用接口, 不保证接口稳定性, 随着新功能开发, 接口形式可能变化.
* 本接口不保证可靠性, 在开发新功能时可能中断服务.
* 本接口不保证数据的完整性, 在重启时数据可能请空或部分清空, 届时接口返回的 total 和 list 数据将不准确.
* 本接口不对其中涉及到的金额负责, 实际值以官网为准.

# API

## address

* 查看用户(address)信息

http://scan-dev-service.conflux-chain.org:8885/api/address/query?address=0x176c45928d7c26b0175dec8bf6051108563c62c5

## block

* 查看所有区块列表 (无翻页限制)

http://scan-dev-service.conflux-chain.org:8885/api/block/list?pageSize=10&page=1

* 查看指定纪元区间(minEpochNumber, maxEpochNumber)内区块列表

http://scan-dev-service.conflux-chain.org:8885/api/block/list?pageSize=10&page=1&minEpochNumber=0&maxEpochNumber=1

* 查看矿工(miner)挖去区块列表

http://scan-dev-service.conflux-chain.org:8885/api/block/list?pageSize=10&page=1&miner=0x128986afd2fbb689c072e09150b5bc6c1b22c7a3

## transaction

* 查看所有交易列表 (无翻页限制)

http://scan-dev-service.conflux-chain.org:8885/api/transaction/list?pageSize=10&page=1

* 查看区块(blockHash)中的交易 (无翻页)

http://scan-dev-service.conflux-chain.org:8885/api/transaction/list?blockHash=0x428eb34cb1a4e56a626a30c11c046362f94e70cebc513f25742ed4442b6a6104

* 查看指定纪元区间(minEpochNumber, maxEpochNumber)内交易

http://scan-dev-service.conflux-chain.org:8885/api/transaction/list?pageSize=10&page=1&minEpochNumber=2119608&maxEpochNumber=2119608

* 查看用户或合约(accountAddress)交易

http://scan-dev-service.conflux-chain.org:8885/api/transaction/list?pageSize=10&page=1&accountAddress=0x176c45928d7c26b0175dec8bf6051108563c62c5

* 查看用户或合约(accountAddress)指定纪元区间(minEpochNumber, maxEpochNumber)内交易

http://scan-dev-service.conflux-chain.org:8885/api/transaction/list?pageSize=10&page=1&accountAddress=0x176c45928d7c26b0175dec8bf6051108563c62c5&minEpochNumber=2119608&maxEpochNumber=2119608

* 查看用户或合约(accountAddress)发送交易

http://scan-dev-service.conflux-chain.org:8885/api/transaction/list?pageSize=10&page=1&accountAddress=0x176c45928d7c26b0175dec8bf6051108563c62c5&txType=outgoing

* 查看用户或合约(accountAddress)接收交易

http://scan-dev-service.conflux-chain.org:8885/api/transaction/list?pageSize=10&page=1&accountAddress=0x176c45928d7c26b0175dec8bf6051108563c62c5&txType=incoming

* 查看用户或合约(accountAddress)失败交易

http://scan-dev-service.conflux-chain.org:8885/api/transaction/list?pageSize=10&page=1&accountAddress=0x176c45928d7c26b0175dec8bf6051108563c62c5&status=1

## contract

* 查看合约(address)详情

http://scan-dev-service.conflux-chain.org:8885/api/contract/query?address=0x87010faf5964d67ed070bc4b8dcafa1e1adc0997&fields=name,abi,sourceCode

## transfer 

注: 0x87010faf5964d67ed070bc4b8dcafa1e1adc0997 为 Oceanus 网络的 FansCoin

* 查看代币(address)转移 

http://scan-dev-service.conflux-chain.org:8885/api/transfer/list?pageSize=10&page=1&address=0x87010faf5964d67ed070bc4b8dcafa1e1adc0997

* 查看用户代币(address)转移

http://scan-dev-service.conflux-chain.org:8885/api/transfer/list?pageSize=10&page=1&address=0x87010faf5964d67ed070bc4b8dcafa1e1adc0997&accountAddress=0x1eff4db4696253106ae18ca96e092a0f354ef7c8

* 查看用户指定纪元区间(minEpochNumber, maxEpochNumber)内代币(address)转移

http://scan-dev-service.conflux-chain.org:8885/api/transfer/list?pageSize=10&page=1&address=0x87010faf5964d67ed070bc4b8dcafa1e1adc0997&accountAddress=0x1eff4db4696253106ae18ca96e092a0f354ef7c8&minEpochNumber=121627&maxEpochNumber=121627
