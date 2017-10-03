---
title: "WCF 适配器有哪些？ | Microsoft Docs"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 18ca8535-3386-4018-8b5b-d32bdb9ebf70
caps.latest.revision: "12"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 41c942c7c2ef870b2a61c519e79fb8a124059f03
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="what-are-the-wcf-adapters"></a>WCF 适配器有哪些？
共有两种 Windows Communication Foundation (WCF) 适配器：一个接收适配器和一个发送适配器。 使用 WCF 接收适配器可以接收 WCF 服务请求。 WCF 接收适配器接收一个请求、创建一个 BizTalk 消息对象，并将关联的属性升级到消息上下文中。 使用 WCF 发送适配器可调用 WCF 服务。 WCF 发送适配器通过无类型的协定调用 WCF 服务。  
  
> [!NOTE]
>  WCF 适配器不支持使用远程过程调用 (RPC) 型的 Web Services，因为 RPC 型 Web Services 中的消息部分引用消息类型而不是消息元素，WCF 适配器在其中使用消息部分的元素。 我们建议您通过“添加 Web 引用”向导添加 RPC 型 Web Services 以在 BizTalk 项目中使用 Web Services。  
  
## <a name="web-services-standards-support"></a>Web Services 标准支持  
 WCF 适配器支持 WS-* 标准，比如 WS-Addressing、WS-Security 和 WS-AtomicTransaction。 此版本 WCF 适配器中不支持 WS-ReliableMessaging。 有关支持的 WCF 规范的列表，请参阅[http://go.microsoft.com/fwlink/?LinkId=88314](http://go.microsoft.com/fwlink/?LinkId=88314)。  
  
### <a name="ws-addressing"></a>WS-Addressing  
 WCF 适配器依赖 WCF 提供的 WS-Addressing 标准支持。 WCF 适配器具有下列功能：  
  
-   配置在元数据交换请求过程中获得的发送端口终结点地址。  
  
-   配置发送端口终结点地址的寻址标头。  
  
-   配置在 BizTalk 接收位置中公开的终结点的寻址标头。  
  
### <a name="ws-security"></a>WS-安全性  
 WCF 适配器依赖 WCF 提供的安全标准支持。 WCF 适配器支持下列标准：  
  
-   Web 服务安全： SOAP 消息安全 (Ws-security) 1.0 和 1.1 版  
  
-   Web Services 安全对话语言 (WS-SecureConversation)  
  
-   Web Services 信任语言 (WS-Trust)  
  
-   Web Services 安全 X.509 证书令牌配置文件  
  
-   Web Services 安全用户名令牌配置文件 1.0  
  
-   Web Services 安全 Kerberos 令牌配置文件 1.0  
  
#### <a name="service-authentication-types"></a>服务验证类型  
 支持以下 WCF 服务验证类型：  
  
-   无  
  
-   Windows  
  
-   证书  
  
#### <a name="client-authentication-types"></a>客户端身份验证类型  
 支持下列 WCF 客户端验证类型：  
  
-   匿名  
  
-   UserName  
  
-   Windows  
  
-   证书  
  
#### <a name="security-modes"></a>安全模式  
 支持下列安全模式：  
  
-   Transport  
  
-   消息  
  
-   混合（传输级别安全性和消息级别验证）  
  
### <a name="ws-atomictransaction"></a>Ws-atomictransaction  
 WCF-WsHttp、WCF-NetTcp 和 WCF-NetMsmq 适配器支持 WS-AtomicTransaction 协议。 此支持允许使用下列方案：  
  
-   将消息事务性提交到 MessageBox 数据库。  
  
-   将来自 MessageBox 的消息事务性提交到事务性目标。  
  
> [!NOTE]
>  事务作用域受 MessageBox 限制。 例如，一个 BizTalk 业务流程无法参与一个客户端的事务。 与此类似，一个目标终结点无法参与由 BizTalk 业务流程启动的事务。  
  
#### <a name="transactional-submission"></a>事务性提交  
 为 WCF WsHttp 和 WCF NetTcp 适配器，事务提交到 BizTalk Server 启用通过选择**启用事务**在接收位置传输属性对话框中的复选框。 为 WCF NetMsmq 适配器**事务**默认情况下选中复选框。 如果您正在请求消息的消息队列未标记为事务性，则需要清除此复选框；否则，将会接收到一个错误消息。  
  
 如果已启用事务功能，则将使用客户端的事务将消息提交到 MessageBox 数据库。 如果客户端尝试提交事务作用域之外的消息，则适配器将向客户端返回一个异常。 但是，将不会挂起任何消息。 如果已禁用事务功能，则将不使用客户端的事务将消息提交到 MessageBox 数据库。 如果客户端尝试提交事务作用域之内的消息，则适配器将向客户端返回一个异常，且不挂起任何消息。  
  
#### <a name="transactions-and-receive-location-type"></a>事务和接收位置类型  
 事务性提交只可用于单向接收位置。 如果客户端尝试为双向接收位置提交事务作用域之内的消息，则将向客户端返回一个异常，且不挂起任何消息。  
  
#### <a name="transactional-transmission"></a>事务性传输  
 为 WCF WsHttp 和 WCF NetTcp 适配器，BizTalk Server 中的事务传输启用通过选择**启用事务**发送端口传输属性对话框中的复选框。 为 WCF NetMsmq 适配器**事务**默认情况下选中复选框。 如果您正在向其发送消息的消息队列未标记为事务性，则需要清除此复选框；否则，将会接收到一个错误消息。  
  
 如果已启用事务功能，则将使用事务从 MessageBox 数据库传输或删除消息。 如果目标服务在接收消息后执行了任何工作，则不会从 MessageBox 删除消息，但会在随后中止该事务并回滚该服务上的所有事务工作。 如果已禁用事务功能，则将不使用事务从 MessageBox 传输或删除消息。  
  
## <a name="single-sign-on-support"></a>单一登录支持  
 您可模拟并获取企业单一登录 (SSO) 票证以将 SSO 与 WCF 适配器一起使用。 有关如何使用 WCF 适配器 SSO 的详细信息，请参阅[WCF 适配器的单一登录支持](../core/single-sign-on-support-for-the-wcf-adapters.md)。  
  
 下表总结了将 SSO 支持与 WCF 服务适配器一起使用时不支持的方案。  
  
|安全模式|凭据|  
|-------------------|----------------|  
|无|无|  
|Transport|无|  
|消息|无|  
|TransportWithMessageCredentials|无|  
|TransportCredentialOnly|无|  
  
## <a name="wcf-extensibility"></a>WCF 扩展性  
 您可扩展 WCF 的功能，方法是开发下列扩展功能并将它们与 WCF-Custom 和 WCF-CustomIsolated 适配器一起使用：  
  
-   自定义绑定  
  
-   自定义绑定元素  
  
### <a name="custom-bindings"></a>自定义绑定  
 自定义绑定是将单个绑定元素打包到一个容器中来开发的，该容器为特定使用方案公开一个配置属性子集。 您需要注册该绑定扩展，方法是将程序集安装到全局程序集缓存 (GAC) 然后将扩展元素添加到计算机配置文件中。 若要使用自定义绑定，需要在 BizTalk 组中的每台服务器上设置绑定。 安装绑定后，WCF-Custom 和 WCF-CustomIsolated 适配器将可以看到该绑定。 WCF-Custom 和 WCF-CustomIsolated 适配器将使用绑定配置元素上的反射来获取绑定配置属性。  
  
### <a name="custom-binding-elements"></a>自定义绑定元素  
 自定义绑定元素是通过添加或修改特定传输通道组件来开发的。 例如，自定义解压缩组件打包为绑定元素，或 UDP 传输表示为绑定元素。 这些绑定元素可在 WCF 适配器内使用。 您可定义一个通道堆栈以结合使用自定义绑定元素和其他预装或自定义绑定元素。 您需要注册该绑定元素扩展，方法是将程序集安装到 GAC 然后将扩展元素添加到计算机配置文件中。 若要使用自定义绑定，需要在 BizTalk 组中的每台服务器上设置绑定。 若要使用自定义绑定元素，可以选择**CustomBinding**绑定类型然后添加、 修改或重新排列的绑定元素所需的顺序。  
  
## <a name="in-this-section"></a>本节内容  
  
-   [WCF 接收适配器](../core/wcf-receive-adapter.md)  
  
-   [WCF 发送适配器](../core/wcf-send-adapter.md)  
  
## <a name="see-also"></a>另请参阅  
-  [WCF 适配器](../core/wcf-adapters.md)   
-  **WCF 适配器服务协定参考**[!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]