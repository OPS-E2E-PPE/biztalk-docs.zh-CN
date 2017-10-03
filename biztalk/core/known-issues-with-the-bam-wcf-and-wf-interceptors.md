---
title: "已知问题的 BAM WCF 和 WF 拦截器 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: f2407809-1f71-41a9-b305-722a7f86af5b
caps.latest.revision: "8"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 42078eb2b1272072016ded9a117e88ddf4fda038
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="known-issues-with-the-bam-wcf-and-wf-interceptors"></a>BAM WCF 和 WF 侦听器的已知问题
本部分介绍在将 BAM 侦听器用于 Windows Workflow Foundation 或 Windows Communication Foundation 时可能遇到的已知问题。  
  
## <a name="intercepting-a-dynamically-generated-wcf-assembly-hosted-in-iis"></a>侦听以 IIS 为宿主的动态生成的 WCF 程序集  
 在使用 IIS 承载某个嵌入的 Windows Communication Foundation 应用程序（例如，某个指定了程序集源文件的服务文件）时，将动态生成 WCF 程序集并随意为其赋予一个文件名，然后将其放置在 asp.net 临时文件夹中。 由于侦听器配置文件需要清单信息，而且在为侦听器配置文件指定清单时不能使用通配符或其他动态方法，所以在部署了所有包含嵌入式 WCF 代码的 asp.net 网页之后，必须重新编译服务然后生成侦听器配置文件，或者重新部署您的侦听器配置文件。  
  
## <a name="use-of-the-bam-interceptor-for-windows-workflow-foundation-is-not-supported-in-office-and-sharepoint-server"></a>在 Office 和 Sharepoint Server 中不支持将 BAM 侦听器用于 Windows Workflow Foundation。  
 在对 WF 运行时进行初始化时，Office 和 Windows Sharepoint Server 不会读取应用程序配置文件。 因此，可以为应用程序配置针对 WF 的 BAM 侦听器，但是当应用程序在上述环境中进行承载时，不会将针对 WF 的 BAM 侦听器加载到工作流运行时中。  
  
## <a name="client-service-locks-when-intiating-a-distributed-transaction"></a>在初始化某个分布式事务时，客户端服务将锁定。  
 如果服务操作不参与由客户端发起的事务并且客户端从事务作用域的上下文中调用服务，可能会发生死锁，在发送请求前要从客户端收集数据并且用于相同活动的接收请求要从服务收集数据时尤为如此。  
  
 若要避免这种情况，你应指定，客户端将不参与该事务通过声明"Enlist = false"在客户端`ConnectionString`如下所示属性，则为客户端的 app.config 文件中的 BAM 行为扩展。  
  
```  
<behavior name="bamClientBehavior">  
  <bamClientBehaviorExtension ConnectionString="Integrated Security=SSPI;Initial Catalog=BAMPrimaryImport;Data Source=.;  Enlist=false"  PollingIntervalSec="1500" />  
</behavior>  
```  
  
## <a name="open-wcf-channel-before-sending-a-message-when-bam-interceptors-are-used"></a>使用 BAM 侦听器时，发送消息之前请打开 WCF 通道  
 当为具有 BasicHttp 绑定的 WCF 启用 BAM 侦听器时，代理会调用 l proxy.Open() 来显式打开频道。 如果不显式打开通道，BAM 截获可能会失败并出现异常。