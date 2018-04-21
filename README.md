# Fastpay

Fastpay的目标是打造一款开源的、轻量级的、微服务化的、可共私有云部署的、可定制化的集成聚合支付和资金清结算于一体的统一支付系统，满足互联网企业业务系统的收款和资金处理等需求。 

以龙果支付为基础，构建的统一支付系统聚合微信支付宝的扫码、被扫，H5等支付方式，并提供账务和企业资金处理能力，拟分解为：API管理，支付核心，路由渠道，账务账户，清结算、对账中心，商户平台，运营平台，商户通知，分布式任务调度系统，配置系统，客户系统，使用Spring Cloud进行微服务化，可公有云部署亦可私有云部署，提供完备的架构和设计文档、开发文档、API文档和商户/用户向导，并且配合《支付平台架构》一书出版。

感兴趣的小伙伴可以加入我们，为开源事业贡献一份力量，在这里可以学习高大上的支付业务，也可以学习微服务再支付平台的落地，更可以和各位服务架构的作者们一起写作《支付平台架构》一书。

## 业务价值

在国内，网民已经超过6亿人口，其中有至少5亿人口在使用移动支付，因此，对移动支付的需求非常强烈，当前的移动支付入口由微信和支付宝占有，用户已经习惯了使用微信和支付宝来付款，中小型电商等公司有支付需求，当前只能对接完微信后再对接支付宝，其成本高昂，实施周期长，我们这里算一笔账，假设一个电商公司成立统一支付组，共需要5人，3人开发，1人测试，1个产品，一年的投入不下于100万，如果有成熟的开源产品，或者有成熟的云平台，帮助电商公司等进行收款以及附加的资金处理等，对于企业来讲那将是乐此不彼。

## 技术亮点

1. 在支付系统上实施微服务架构，使用最流行的Spring Cloud做服务化。
2. 设计天生可伸缩的数据存储，直接使用分库分表。
3. 使用缓存进行加速交易过程，提高用户体验。
4. 将回调通知、入账等异步化，提高用户响应能力。
5. 使用分布式定时任务系统将任务调度与交易隔离。
6. 使用当前最先进的单元化架构实现可水平伸缩。
7. 有完善的文档，最后配合项目出版《支付平台架构》一书，作为统一支付的白皮书。
8. 通过技术手段构建一站式可定制化的企业支付平台。

## 总体计划(Milestones)

| 序号     |    任务 | 贡献者  | 状态 |完成时间|
| --------: | :--------| :--: | :--:|:--:|
| 1  | 以龙果支付代码为基础，初始化fastpay的代码|  程延   |完成|2018.2.10|
| 2  | 架构设计，拆分模块，定义各个模块之间的关系，模块职责的定义| 艳鹏、张诚、程延、杨老师 | 进行中 ||
| 3  | 核心模块设计|艳鹏、李鹏|||
| 4  | 编码编码实现|艳鹏、李鹏 |||
| 5  | 产品设计、文档整理中，出版《支付平台架构》| 艳鹏、东超、TiRE、雷默|||
| 6  | 持续优化||||
| 7  | DevOps运维，质量测试开发|葛亮|||

## 总体架构

![](doc/images/fastpay-arch.png)

## 分支管理

- 生产分支：master，生产环境发版本
- 稳定分支：develop，对应阿里云QA环境
- 开发分支：dev_chengyan_running、dev_yanpeng......

版本管理流程：每位开发者从develop分支切自己的开发分支，例如：dev_chengyan_running、dev_yanpeng，开发完成并测试，合并到develop上，QA测试后对外发版后，再合并到master。

## 项目结构

1. fast-pay-app-notify: 通知应用工程，独立jar方式启动。
2. fast-pay-app-order-polling: 订单应用工程，独立jar方式启动。
3. fast-pay-app-reconciliation: 对账应用工程，独立jar方式启动。
4. fast-pay-app-settlement: 结算应用工程，独立jar方式启动。
5. fast-pay-common-core: 公共类工程，不用单独部署。
6. fast-pay-service: 核心业务类工程，不用单独部署。
7. fast-pay-web-boss: 运营管理后台，部署tomcat启动。
8. fast-pay-web-gateway: 支付网关工程，部署tomcat启动。
9. fast-pay-web-merchant: 商户后台工程，部署tomcat启动。
10. fast-pay-web-sample-shop: 模拟商城工程，部署tomcat启动。


## 角色划分

- 发起人：艳鹏、东超
- 产品经理：东超
- 架构师：艳鹏、张城(freewolf)、杨彪
- 开发负责人：程延
- 质量测试负责人：葛亮（Software Luke）
- Devops负责人：葛亮（Software Luke）
- 文档负责人：TiRE、雷默
- 账务账户：贾博岩
- 核心交易：李鹏（oldman）、宇涛、孙牧原、梁鹏举
- 运营平台：李鹏（oldman）、布娃娃、梁鹏举
- 商户平台：李鹏（oldman）、布娃娃、梁鹏举
- 客户通知：李栋梁（蜗牛君）
- 清算结算：柯常荣
- 渠道路由：马刚、李勇
- 风控掌门：曲老板


## 密码申请

运营管理系统登录账号密码：admin/123456  
商户后台系统登录账号密码：在boss运营后台添加用户时录入手机和密码

## 饮水思源

目前以龙果支付为基础，虽然处于初级阶段，但是我们对整个实施的过程和思路都是非常清晰的，我们后续会梳理龙果支付的项目代码，进行微服务化，当前可参考龙果支付的演示页面：

在线支付演示：http://demo.pay.roncoo.com

我们坚决拥护Apache开源协议，在原协议的基础上，我们仍然使用Apache协议，任何修改后的项目全部开源，由云时代架构社区来维护。

## 加入项目

加入项目请关注Fastpay快付公众号，后台回复"+fastpay"，然后，提供微信、邮箱、码云账号等。

![](doc/images/云时代架构公众号.jpg)


 




 

















