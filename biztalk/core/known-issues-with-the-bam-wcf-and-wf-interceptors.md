---
title: 使用 BAM WCF 和 WF 侦听器的已知问题 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: f2407809-1f71-41a9-b305-722a7f86af5b
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b938dff130ae08e75f54fc1b619fad109515a5d4
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65330068"
---
# <a name="known-issues-with-the-bam-wcf-and-wf-interceptors"></a>BAM WCF 和 WF 侦听器的已知的问题
本部分提供有关用于 Windows Workflow Foundation 或 Windows Communication Foundation 的 BAM 侦听器时可能会遇到的已知问题的信息。  
  
## <a name="intercepting-a-dynamically-generated-wcf-assembly-hosted-in-iis"></a>截获承载于 IIS 中的动态生成的 WCF 程序集  
 当使用 IIS 来承载嵌入式的 Windows Communication Foundation 应用程序 （例如，指定程序集源的服务文件） 时，WCF 程序集将动态生成，分配的任意文件名称，并放置在 asp.net临时文件夹。 由于侦听器配置文件需要清单信息和由于通配符或其他指定清单的动态方法不是用于侦听器配置文件，必须重新编译你的服务，然后生成在侦听器配置文件或重新部署侦听器配置文件后的已部署的所有 asp.net web 页面包含嵌入式 WCF 代码。  
  
## <a name="use-of-the-bam-interceptor-for-windows-workflow-foundation-is-not-supported-in-office-and-sharepoint-server"></a>BAM 侦听器用于 Windows Workflow Foundation 不支持 Office 和 Sharepoint Server 中  
 Office 和 Windows Sharepoint Server 不从读取应用程序配置文件时初始化 WF 运行时。 结果是，WF 的 BAM 侦听器可能配置为应用程序，但它不加载到工作流运行时在这些环境中托管。  
  
## <a name="client-service-locks-when-intiating-a-distributed-transaction"></a>客户端服务将锁定时初始化分布式事务  
 如果服务操作不会参与由客户端发起的事务，并且客户端调用了事务作用域上下文中的服务，可能导致死锁，尤其是当正在从之前在客户端收集的数据发送请求和从同一个活动的接收请求的服务。  
  
 若要避免这种情况下，应指定客户端不会不参与该事务中通过声明"Enlist = false"客户端中`ConnectionString`属性的客户端的 app.config 文件中的 BAM 行为扩展，如下所示。  
  
```  
<behavior name="bamClientBehavior">  
  <bamClientBehaviorExtension ConnectionString="Integrated Security=SSPI;Initial Catalog=BAMPrimaryImport;Data Source=.;  Enlist=false"  PollingIntervalSec="1500" />  
</behavior>  
```  
  
## <a name="open-wcf-channel-before-sending-a-message-when-bam-interceptors-are-used"></a>打开 WCF 通道发送消息之前时使用 BAM 侦听器  
 为 WCF 启用 BAM 侦听器时使用 BasicHttp 绑定，则代理会调用代理。Open （） 方法来显式打开通道。 如果未显式打开频道，BAM 侦听可能失败并出现异常。