---
title: WCF 适配器有哪些？ | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 18ca8535-3386-4018-8b5b-d32bdb9ebf70
caps.latest.revision: 12
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f82973bce0ae79a151d0336d788c07fa99b7e8d4
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65244078"
---
# <a name="what-are-the-wcf-adapters"></a>WCF 适配器有哪些？
有两个 Windows Communication Foundation (WCF) 适配器，接收适配器和一个发送适配器。 使用 WCF 接收适配器接收 WCF 服务请求。 WCF 接收适配器收到的请求，创建一个 BizTalk 消息对象，并升级到消息上下文关联的属性。 使用 WCF 发送适配器来调用 WCF 服务。 WCF 发送适配器调用通过无类型协定的 WCF 服务。  

> [!NOTE]
>  WCF 适配器不支持使用远程过程调用 (RPC) 的 Web services，因为 RPC 型 Web services 中的消息部分引用消息类型而不是在 WCF 适配器有使用元素的消息的消息元素部分。 我们建议使用 BizTalk 项目中的 Web 服务添加通过添加 Web 引用向导的 RPC 样式的 Web 服务。  

## <a name="web-services-standards-support"></a>Web Services 标准支持  
 WCF 适配器支持 WS-* 标准如 Ws-addressing、 Ws-security 和 WS-AtomicTransaction。 在此版本的 WCF 适配器不支持 WS-ReliableMessaging。 有关 WCF 支持的规范的列表，请参阅[ http://go.microsoft.com/fwlink/?LinkId=88314 ](http://go.microsoft.com/fwlink/?LinkId=88314)。  

### <a name="ws-addressing"></a>WS-Addressing  
 WCF 适配器依赖 WCF 提供的 Ws-addressing 的标准支持。 WCF 适配器中提供了以下功能：  

-   在元数据交换请求过程中获取的发送端口终结点地址的配置。  

-   发送端口终结点地址的寻址标头的配置。  

-   在 BizTalk 中公开的终结点的寻址标头的配置接收位置。  

### <a name="ws-security"></a>WS-Security  
 WCF 适配器依赖 WCF 提供的安全标准支持。 WCF 适配器支持以下标准：  

-   Web 服务安全：SOAP 消息安全性 (Ws-security) 1.0 和 1.1 版  

-   Web 服务安全对话语言 (Ws-secureconversation)  

-   Web 服务信任语言 （WS 信任）  

-   Web 服务安全 X.509 证书令牌配置文件  

-   Web 服务安全用户名令牌配置文件 1.0  

-   Web 服务安全 Kerberos 令牌配置文件 1.0  

#### <a name="service-authentication-types"></a>服务身份验证类型  
 支持以下 WCF 服务身份验证类型：  

-   None  

-   Windows  

-   证书  

#### <a name="client-authentication-types"></a>客户端身份验证类型  
 支持以下 WCF 客户端身份验证类型：  

-   匿名  

-   UserName  

-   Windows  

-   证书  

#### <a name="security-modes"></a>安全模式  
 支持以下安全模式：  

-   Transport  

-   消息  

-   混合 （传输级安全和消息级别的身份验证）  

### <a name="ws-atomictransaction"></a>WS-AtomicTransaction  
 Wcf-wshttp、 Wcf-nettcp 和 Wcf-netmsmq 适配器支持 WS-AtomicTransaction 协议。 此支持允许使用下列方案：  

-   到 MessageBox 数据库的消息事务性提交。  

-   事务方式传输消息从 MessageBox 到事务性目标。  

> [!NOTE]
>  事务作用域受 MessageBox 限制。 例如，BizTalk 业务流程不能参与客户端的事务。 同样，目标终结点不能参与由 BizTalk 业务流程启动的事务。  

#### <a name="transactional-submission"></a>事务性提交  
 对于 Wcf-wshttp 和 Wcf-nettcp 适配器，事务性提交到 BizTalk Server 选择启用**启用事务**接收位置传输属性对话框中的复选框。 Wcf-netmsmq 适配器**事务性**默认情况下选中复选框。 如果您正在从其请求消息的消息队列未标记为事务性，则需要清除此复选框;否则，将收到一条错误消息。  

 如果启用事务功能，则消息通过使用客户端的事务提交到 MessageBox 数据库。 如果客户端尝试提交事务作用域之外的消息，适配器将向客户端返回一个异常。 但是，将不挂起任何消息。 如果禁用事务功能，则将消息提交到 MessageBox 不使用客户端的事务。 如果客户端尝试提交事务作用域内的消息，适配器将返回一个异常返回给客户端，并将挂起任何消息。  

#### <a name="transactions-and-receive-location-type"></a>事务和接收位置类型  
 事务提交是仅适用于单向接收位置。 如果客户端尝试提交事务作用域中的双向消息的接收位置，将返回异常返回给客户端，并将挂起任何消息。  

#### <a name="transactional-transmission"></a>事务性传输  
 对于 Wcf-wshttp 和 Wcf-nettcp 适配器，BizTalk Server 的事务性传输选择启用**启用事务**发送端口传输属性对话框中的复选框。 Wcf-netmsmq 适配器**事务性**默认情况下选中复选框。 如果向其发送消息的消息队列未标记为事务性，则需要清除此复选框;否则，将收到一条错误消息。  

 如果启用事务功能，则消息传输并从 MessageBox 数据库在事务中删除。 如果目标服务执行了任何工作之后接收的消息和从 MessageBox 未删除该消息，然后将中止事务并在服务上的所有事务都工作将回滚。 如果禁用事务功能，则消息传送并不使用事务从 MessageBox 中删除。  

## <a name="single-sign-on-support"></a>单一登录支持  
 您可以模拟并获取使用 SSO 与 WCF 适配器的企业单一登录 (SSO) 票证。 有关如何通过 WCF 适配器使用 SSO 的详细信息，请参阅[WCF 适配器的单一登录支持](../core/single-sign-on-support-for-the-wcf-adapters.md)。  

 下表汇总了不受支持的方案使用 SSO 支持与 WCF 接收适配器时。  

|安全模式|凭据|  
|-------------------|----------------|  
|None|None|  
|Transport|None|  
|消息|None|  
|TransportWithMessageCredentials|None|  
|TransportCredentialOnly|None|  

## <a name="wcf-extensibility"></a>WCF 扩展性  
 通过开发下列扩展并使用通过 Wcf-custom 和 Wcf-customisolated 适配器，可以扩展 WCF 的功能：  

-   自定义绑定  

-   自定义绑定元素  

### <a name="custom-bindings"></a>自定义绑定  
 自定义绑定到容器中公开的特定使用方案的配置属性的一部分开发的打包各个绑定元素。 需要注册绑定扩展，通过该程序集安装到全局程序集缓存 (GAC) 然后将扩展元素添加到计算机配置文件。 若要使用自定义绑定，需要设置 BizTalk 组中的每个服务器上的绑定。 安装绑定后，将会显示为 Wcf-custom 和 Wcf-customisolated 适配器。 Wcf-custom 和 Wcf-customisolated 适配器将通过绑定配置元素上使用反射获取的绑定配置属性。  

### <a name="custom-binding-elements"></a>自定义绑定元素  
 通过添加或修改特定传输通道组件来开发自定义绑定元素。 例如，自定义解压缩组件打包为绑定元素，或 UDP 传输表示为绑定元素。 可以在 WCF 适配器内使用这些绑定元素。 您可以定义与其他全新的或自定义绑定元素结合使用自定义绑定元素的通道堆栈。 您需要通过将程序集安装到 GAC 然后将扩展元素添加到计算机配置文件注册的绑定元素扩展。 若要使用自定义绑定，需要设置 BizTalk 组中的每个服务器上的绑定。 若要使用自定义绑定元素，可以选择**CustomBinding**绑定类型然后添加、 修改或重新排列顺序所需的绑定元素。  

## <a name="in-this-section"></a>本节内容  

-   [WCF 接收适配器](../core/wcf-receive-adapter.md)  

-   [WCF 发送适配器](../core/wcf-send-adapter.md)  

## <a name="see-also"></a>请参阅  
- [WCF 适配器](../core/wcf-adapters.md)   
- **WCF 适配器服务协定引用** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]
