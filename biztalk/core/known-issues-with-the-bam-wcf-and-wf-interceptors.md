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
# <a name="known-issues-with-the-bam-wcf-and-wf-interceptors"></a><span data-ttu-id="eecb5-102">BAM WCF 和 WF 侦听器的已知的问题</span><span class="sxs-lookup"><span data-stu-id="eecb5-102">Known Issues with the BAM WCF and WF Interceptors</span></span>
<span data-ttu-id="eecb5-103">本部分提供有关用于 Windows Workflow Foundation 或 Windows Communication Foundation 的 BAM 侦听器时可能会遇到的已知问题的信息。</span><span class="sxs-lookup"><span data-stu-id="eecb5-103">This section provides information about known issues that you may experience when using the BAM interceptors for Windows Workflow Foundation or Windows Communication Foundation.</span></span>  
  
## <a name="intercepting-a-dynamically-generated-wcf-assembly-hosted-in-iis"></a><span data-ttu-id="eecb5-104">截获承载于 IIS 中的动态生成的 WCF 程序集</span><span class="sxs-lookup"><span data-stu-id="eecb5-104">Intercepting a dynamically generated WCF assembly hosted in IIS</span></span>  
 <span data-ttu-id="eecb5-105">当使用 IIS 来承载嵌入式的 Windows Communication Foundation 应用程序 （例如，指定程序集源的服务文件） 时，WCF 程序集将动态生成，分配的任意文件名称，并放置在 asp.net临时文件夹。</span><span class="sxs-lookup"><span data-stu-id="eecb5-105">When you are using IIS to host an embedded Windows Communication Foundation application (for example, a service file that specifies the assembly source), the WCF assembly will be dynamically generated, assigned an arbitrary file name, and placed in the asp.net temporary folder.</span></span> <span data-ttu-id="eecb5-106">由于侦听器配置文件需要清单信息和由于通配符或其他指定清单的动态方法不是用于侦听器配置文件，必须重新编译你的服务，然后生成在侦听器配置文件或重新部署侦听器配置文件后的已部署的所有 asp.net web 页面包含嵌入式 WCF 代码。</span><span class="sxs-lookup"><span data-stu-id="eecb5-106">Since the interceptor configuration file requires manifest information and since wildcard characters or other dynamic methods for specifying the manifest are not available with interceptor configuration files, you must recompile your service and then build your interceptor configuration file or redeploy your interceptor configuration file after you have deployed all of the asp.net web pages containing embedded WCF code.</span></span>  
  
## <a name="use-of-the-bam-interceptor-for-windows-workflow-foundation-is-not-supported-in-office-and-sharepoint-server"></a><span data-ttu-id="eecb5-107">BAM 侦听器用于 Windows Workflow Foundation 不支持 Office 和 Sharepoint Server 中</span><span class="sxs-lookup"><span data-stu-id="eecb5-107">Use of the BAM interceptor for Windows Workflow Foundation is not supported in Office and Sharepoint Server</span></span>  
 <span data-ttu-id="eecb5-108">Office 和 Windows Sharepoint Server 不从读取应用程序配置文件时初始化 WF 运行时。</span><span class="sxs-lookup"><span data-stu-id="eecb5-108">Both office and Windows Sharepoint Server do not read from the application configuration file when initializing the WF runtime.</span></span> <span data-ttu-id="eecb5-109">结果是，WF 的 BAM 侦听器可能配置为应用程序，但它不加载到工作流运行时在这些环境中托管。</span><span class="sxs-lookup"><span data-stu-id="eecb5-109">As a result, the BAM interceptor for WF may be configured for an application but it will not be loaded into the workflow runtime when hosted within these environments.</span></span>  
  
## <a name="client-service-locks-when-intiating-a-distributed-transaction"></a><span data-ttu-id="eecb5-110">客户端服务将锁定时初始化分布式事务</span><span class="sxs-lookup"><span data-stu-id="eecb5-110">Client service locks when intiating a distributed transaction</span></span>  
 <span data-ttu-id="eecb5-111">如果服务操作不会参与由客户端发起的事务，并且客户端调用了事务作用域上下文中的服务，可能导致死锁，尤其是当正在从之前在客户端收集的数据发送请求和从同一个活动的接收请求的服务。</span><span class="sxs-lookup"><span data-stu-id="eecb5-111">If the service operation will not be participating in the transaction initiated by the client and the client is invoking the service from the context of a transaction scope, a deadlock could result, especially if there is data being collected from the client before the send request and from the service by the receive request for the same activity.</span></span>  
  
 <span data-ttu-id="eecb5-112">若要避免这种情况下，应指定客户端不会不参与该事务中通过声明"Enlist = false"客户端中`ConnectionString`属性的客户端的 app.config 文件中的 BAM 行为扩展，如下所示。</span><span class="sxs-lookup"><span data-stu-id="eecb5-112">To avoid this situation, you should specify that the client does not participate in the transaction by declaring "Enlist = false" in the client `ConnectionString` attribute for the BAM behavior extension in the client's app.config file as demonstrated below.</span></span>  
  
```  
<behavior name="bamClientBehavior">  
  <bamClientBehaviorExtension ConnectionString="Integrated Security=SSPI;Initial Catalog=BAMPrimaryImport;Data Source=.;  Enlist=false"  PollingIntervalSec="1500" />  
</behavior>  
```  
  
## <a name="open-wcf-channel-before-sending-a-message-when-bam-interceptors-are-used"></a><span data-ttu-id="eecb5-113">打开 WCF 通道发送消息之前时使用 BAM 侦听器</span><span class="sxs-lookup"><span data-stu-id="eecb5-113">Open WCF Channel Before Sending a Message when BAM Interceptors are used</span></span>  
 <span data-ttu-id="eecb5-114">为 WCF 启用 BAM 侦听器时使用 BasicHttp 绑定，则代理会调用代理。Open （） 方法来显式打开通道。</span><span class="sxs-lookup"><span data-stu-id="eecb5-114">When BAM interceptor is enabled for WCF with BasicHttp binding, proxy should call proxy.Open() to explicitly open the channel.</span></span> <span data-ttu-id="eecb5-115">如果未显式打开频道，BAM 侦听可能失败并出现异常。</span><span class="sxs-lookup"><span data-stu-id="eecb5-115">If the channel is not opened explicitly, BAM interception can fail with an exception.</span></span>