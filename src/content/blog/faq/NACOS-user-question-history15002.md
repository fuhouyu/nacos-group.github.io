---
id: "question-history-15002"
title: "nacos控制台服务列表中新建服务，其中服务器路由类型“标签”和“默认”分别代表什么 nacos-opensource"
date: "2024-06-05"
category: "expertConsultation"
description: "在Nacos控制台服务列表中新建服务时，服务器路由类型提到的“标签”和“默认”代表的是服务实例的分组策略。1. **标签（Tag）**：选择“标签”作为路由类型意味着你在为服务实例分配一个或多个自定义标签。这些标签可以用来实现服务实例的逻辑分组，便于在服务调用时根据特定的标签路由到对应的实例集合。这"
---

## 用户问题 ： 
 nacos控制台服务列表中新建服务，其中服务器路由类型“标签”和“默认”分别代表什么 nacos-opensource 

---------------
## 专家官方解答 ：

在Nacos控制台服务列表中新建服务时，服务器路由类型提到的“标签”和“默认”代表的是服务实例的分组策略。

1. **标签（Tag）**：选择“标签”作为路由类型意味着你在为服务实例分配一个或多个自定义标签。这些标签可以用来实现服务实例的逻辑分组，便于在服务调用时根据特定的标签路由到对应的实例集合。这种方式支持灵活的路由策略和更细粒度的服务管理，适用于蓝绿部署、灰度发布等场景，通过标签筛选确保流量能够精确地导向到目标服务实例集合。

2. **默认（Default）**：若选择“默认”，通常意味着服务实例不附加任何额外的路由标签。在这种情况下，服务实例会被视为属于一个默认的、未特别标记的分组。所有对该服务的请求在没有特定标签路由规则干预下，都会被负载均衡到这个默认分组下的所有实例中。这适用于大多数标准的服务发现和负载均衡需求，不涉及复杂的路由策略。

根据提供的知识内容，这里没有直接关联到新建服务时关于路由类型选择的具体操作步骤或界面指导，但可以结合知识概述Nacos服务管理的核心概念来理解这些选项的含义。如果需要更详细的操作指南，可能需要查阅Nacos官方文档或用户手册。

综上所述，"标签"代表带有自定义逻辑分组的服务实例路由方式，适用于复杂的服务管理需求；而"默认"则代表无特殊标签的常规服务实例分组，适用于基本的服务发现与负载均衡场景。


<font color="#949494">---------------</font> 


## 参考链接 ：

*[Nacos 2.0 升级文档](https://nacos.io/docs/latest/upgrading/200-upgrading)
 
 *专家经验：nacos支持服务列表分组隔离了嘛 
 
 *专家经验：微服务引擎(MSE）介绍 


 <font color="#949494">---------------</font> 
 


## <font color="#FF0000">答疑服务说明：</font> 

本内容经由技术专家审阅的用户问答的镜像生成，我们提供了<font color="#FF0000">专家智能答疑服务</font>，在<font color="#FF0000">页面的右下的浮窗”专家答疑“</font>。您也可以访问 : [全局专家答疑](https://opensource.alibaba.com/chatBot) 。 咨询其他产品的的问题

### 反馈
如问答有错漏，欢迎点：[差评](https://ai.nacos.io/user/feedbackByEnhancerGradePOJOID?enhancerGradePOJOId=15055)给我们反馈。