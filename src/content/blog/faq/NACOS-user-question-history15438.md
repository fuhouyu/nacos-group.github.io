---
id: "question-history-15438"
title: "k8s部署nacos集群，访问域名提示1080端口 nacos-opensource"
date: "2024-06-17"
category: "expertConsultation"
description: "根据您提供的信息，您遇到了在K8s部署Nacos集群后，通过访问域名提示1080端口的问题。首先，让我们分析这个问题的原因：1. **端口暴露问题**：Nacos 默认使用的端口是8848，而您提到的是1080端口，这可能意味着Nacos服务并没有正确地映射到预期的8848端口，或者是存在其他服务占"
---

## 用户问题 ： 
 k8s部署nacos集群，访问域名提示1080端口 nacos-opensource 

---------------
## 专家官方解答 ：

根据您提供的信息，您遇到了在K8s部署Nacos集群后，通过访问域名提示1080端口的问题。首先，让我们分析这个问题的原因：

1. **端口暴露问题**：Nacos 默认使用的端口是8848，而您提到的是1080端口，这可能意味着Nacos服务并没有正确地映射到预期的8848端口，或者是存在其他服务占用了或配置错误指向了1080端口。

2. **DNS解析与服务发现**：访问域名时直接提示端口号而非正常响应服务，可能是因为DNS解析正确，但服务发现配置不正确，导致请求没有被正确路由到Nacos服务上。

依托于提供的知识内容，特别是关于[Nacos-K8s部署](https://github.com/nacos-group/nacos-k8s)的部分，我们可以尝试以下步骤解决该问题：

### 解决步骤：

#### 步骤1：检查Nacos服务的YAML配置
- 确认在Kubernetes部署Nacos时的YAML配置文件是否正确设置了服务的端口映射，确保8848端口被正确暴露。例如，服务类型（Service Type）应设置为`NodePort`或`LoadBalancer`以允许外部访问，并且端口映射部分应有如`targetPort: 8848 port: 8848`的配置。

#### 步骤2：检查服务发现与负载均衡配置
- 确认Ingress或Service的配置是否正确指向了Nacos服务的8848端口，而不是1080端口。如果有使用Ingress，检查路径和端口重写规则是否正确。

#### 步骤3：检查域名解析设置
- 确保域名正确解析到了Kubernetes集群中Nacos服务对应的IP地址，并且没有额外的端口信息附加在域名访问路径上。

#### 步骤4：查看Nacos服务日志
- 登录到Nacos服务器容器内部，查看启动日志确认Nacos服务是否正常启动并且监听在8848端口。

#### 步骤5：排查网络策略与防火墙
- 检查集群的网络策略(NetworkPolicy)是否有阻止外部访问8848端口，以及云服务提供商或本地防火墙设置是否允许8848端口的入站连接。

### 解释：
以上步骤旨在从服务配置、服务发现、域名解析、服务运行状态以及网络策略等多个角度排查和解决问题。通过逐个检查这些环节，通常能够定位并解决访问域名时提示非预期端口的问题。如果问题依然存在，可能需要更深入地调查Kubernetes集群的网络配置或考虑是否存在特定于环境的配置问题。

如果上述步骤不能解决问题，或者需要更多针对性的帮助，请提供更详细的服务部署配置信息或错误日志，以便进行进一步分析。


<font color="#949494">---------------</font> 


## 参考链接 ：

*[Nacos功能和需求列表](https://nacos.io/docs/latest/archive/feature-list)
 
 *专家经验：NACOS 配置中心和注册中心是分两个集群部署还是放在一个集群中 
 
 *专家经验：nacos的部署 


 <font color="#949494">---------------</font> 
 


## <font color="#FF0000">答疑服务说明：</font> 

本内容经由技术专家审阅的用户问答的镜像生成，我们提供了<font color="#FF0000">专家智能答疑服务</font>，在<font color="#FF0000">页面的右下的浮窗”专家答疑“</font>。您也可以访问 : [全局专家答疑](https://opensource.alibaba.com/chatBot) 。 咨询其他产品的的问题

### 反馈
如问答有错漏，欢迎点：[差评](https://ai.nacos.io/user/feedbackByEnhancerGradePOJOID?enhancerGradePOJOId=15508)给我们反馈。