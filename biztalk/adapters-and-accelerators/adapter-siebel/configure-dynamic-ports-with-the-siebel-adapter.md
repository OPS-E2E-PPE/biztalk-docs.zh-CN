---
title: "配置动态端口与 Siebel 适配器 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- dynamic ports, configuring
- configuring, dynamic ports
ms.assetid: a3516c2c-d40e-426b-bf3f-f9dc3de105ef
caps.latest.revision: "6"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b036bf772e3e9580c84616f74786d4908aca7515
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="configure-dynamic-ports-with-the-siebel-adapter"></a><span data-ttu-id="07184-102">与 Siebel 适配器配置动态端口</span><span class="sxs-lookup"><span data-stu-id="07184-102">Configure dynamic ports with the Siebel adapter</span></span>
<span data-ttu-id="07184-103">在[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]，你可以配置为动态端口[!INCLUDE[wcfadapter_short](../../includes/wcfadapter-short-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="07184-103">In [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)], you can configure dynamic ports for a [!INCLUDE[wcfadapter_short](../../includes/wcfadapter-short-md.md)].</span></span> <span data-ttu-id="07184-104">因为[!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]是一个基于 WCF 的适配器，你可以动态配置的端口[!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]通过使用消息上下文属性。</span><span class="sxs-lookup"><span data-stu-id="07184-104">Because [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)] is a WCF-based adapter, you can dynamically configure a port for the [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)] by using message context properties.</span></span>  
  
 <span data-ttu-id="07184-105">有关[!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]，URI、 操作和绑定可能会确定传入消息时，属性，然后中指定**表达式**形状，如下面的示例中所示：</span><span class="sxs-lookup"><span data-stu-id="07184-105">For the [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)], the URI, action, and binding might be determined from a property on an incoming message, and then specified in the **Expression** shape, as shown in the following example:</span></span>  
  
```  
Request2=Request1;  
Request2(WCF.Action)="http://Microsoft.LobServices.Siebel/2007/03/BusinessObjects/Account/Account/Insert";  
Request2(WCF.BindingType)="siebelBinding";  
Request2(WCF.UserName)="YourUserName";  
Request2(WCF.Password)="YourPassword";  
SendPort(Microsoft.XLANGs.BaseTypes.Address)="siebel://mySiebelServer:1234?SiebelObjectManager=SSEObjMgr&SiebelEnterpriseServer=myEnterpriseServer&Language=enu";  
SendPort(Microsoft.XLANGs.BaseTypes.TransportType)="WCF-Custom";  
  
```  
  
> [!NOTE]
>  <span data-ttu-id="07184-106">如果使用中的 WCF Siebel 适配器[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理控制台中，你还可以指定的传输类型为`SendPort(Microsoft.XLANGs.BaseTypes.TransportType)="SiebelAdapter"`，其中**SiebelAdapter**是与其添加中的WCFSiebel适配器的名称[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理控制台。</span><span class="sxs-lookup"><span data-stu-id="07184-106">If you are using a WCF-Siebel adapter in [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] Administration console, you can also specify the transport type as `SendPort(Microsoft.XLANGs.BaseTypes.TransportType)="SiebelAdapter"`, where **SiebelAdapter** is the name with which you added the WCF-Siebel adapter in [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] Administration console.</span></span>  
  
 <span data-ttu-id="07184-107">在前面的示例：</span><span class="sxs-lookup"><span data-stu-id="07184-107">In the preceding example:</span></span>  
  
-   <span data-ttu-id="07184-108">正在从 Request1 消息创建次数 2 消息。</span><span class="sxs-lookup"><span data-stu-id="07184-108">Request2 message is being created from Request1 message.</span></span> <span data-ttu-id="07184-109">两条消息映射到操作的架构，这在生成使用[!INCLUDE[consumeadapterservlong](../../includes/consumeadapterservlong-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="07184-109">Both the messages map to an operation schema, which is generated using the [!INCLUDE[consumeadapterservlong](../../includes/consumeadapterservlong-md.md)].</span></span>  
  
-   <span data-ttu-id="07184-110">发送端口是 BizTalk 业务流程中的逻辑发送端口的名称。</span><span class="sxs-lookup"><span data-stu-id="07184-110">SendPort is the name of the logical send port in the BizTalk orchestration.</span></span>  
  
 <span data-ttu-id="07184-111">表达式形状是 BizTalk 业务流程的一部分。</span><span class="sxs-lookup"><span data-stu-id="07184-111">The Expression shape is part of the BizTalk orchestration.</span></span> <span data-ttu-id="07184-112">当你部署的业务流程时，也将创建 WCF 自定义发送端口。</span><span class="sxs-lookup"><span data-stu-id="07184-112">When you deploy the orchestration, the WCF-Custom send port is also created.</span></span>  
  
 <span data-ttu-id="07184-113">配置动态端口的详细信息，请参阅[配置动态发送端口使用 WCF 适配器上下文属性](../../core/configuring-dynamic-send-ports-using-wcf-adapters-context-properties.md)。</span><span class="sxs-lookup"><span data-stu-id="07184-113">For more information on configuring dynamic ports, see [Configuring Dynamic Send Ports Using WCF Adapters Context Properties](../../core/configuring-dynamic-send-ports-using-wcf-adapters-context-properties.md).</span></span>
  
## <a name="see-also"></a><span data-ttu-id="07184-114">另请参阅</span><span class="sxs-lookup"><span data-stu-id="07184-114">See Also</span></span>  
[<span data-ttu-id="07184-115">构建基块创建带有 Siebel 适配器 BizTalk 应用程序</span><span class="sxs-lookup"><span data-stu-id="07184-115">Building blocks to create BizTalk applications with the Siebel adapter</span></span>](../../adapters-and-accelerators/adapter-siebel/building-blocks-to-create-biztalk-applications-with-the-siebel-adapter.md)