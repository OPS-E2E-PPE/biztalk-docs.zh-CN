---
title: 配置动态端口与 Oracle E-business Suite |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 75a150ea-d957-4a37-81cf-c043a0a7d5cb
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b02dc0cd4a4cf1d031acaf6d5a0e1c905ee225b8
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22215821"
---
# <a name="configure-dynamic-ports-with-oracle-e-business-suite"></a><span data-ttu-id="96999-102">使用 Oracle E-business Suite 配置动态端口</span><span class="sxs-lookup"><span data-stu-id="96999-102">Configure dynamic ports with Oracle E-Business Suite</span></span>
<span data-ttu-id="96999-103">在[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]，你可以配置为动态端口[!INCLUDE[wcfadapter_short](../../includes/wcfadapter-short-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="96999-103">In [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)], you can configure dynamic ports for a [!INCLUDE[wcfadapter_short](../../includes/wcfadapter-short-md.md)].</span></span> <span data-ttu-id="96999-104">因为[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]是一个基于 WCF 的适配器，你可以动态配置的端口[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]通过使用消息上下文属性。</span><span class="sxs-lookup"><span data-stu-id="96999-104">Because the [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] is a WCF-based adapter, you can dynamically configure a port for the [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] by using message context properties.</span></span>  
  
 <span data-ttu-id="96999-105">有关[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]，URI、 操作和绑定可能确定传入消息时，属性，然后中指定**表达式**形状，如下面的示例中所示：</span><span class="sxs-lookup"><span data-stu-id="96999-105">For the [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)], the URI, action, and binding may be determined from a property on an incoming message, and then specified in the **Expression** shape, as shown in the following example:</span></span>  
  
```  
Request2=Request1;  
Request2(WCF.Action)="InterfaceTables/Insert/OFA/FA/FA_BOOKS";  
Request2(WCF.BindingType)="oracleEBSBinding";  
Request2(WCF.UserName)="myuser";  
Request2(WCF.Password)="mypass";  
SendPort(Microsoft.XLANGs.BaseTypes.Address)="oracleebs://ebs_instance";  
SendPort(Microsoft.XLANGs.BaseTypes.TransportType)="WCF-Custom";  
```  
  
> [!NOTE]
>  <span data-ttu-id="96999-106">如果使用中的 WCF OracleEBS 适配器[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理控制台中，你还可以指定的传输类型为`SendPort(Microsoft.XLANGs.BaseTypes.TransportType)="OracleEBSAdapter"`，其中**OracleEBSAdapter**是与其添加中的 WCF OracleEBS 适配器的名称[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理控制台。</span><span class="sxs-lookup"><span data-stu-id="96999-106">If you are using a WCF-OracleEBS adapter in [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] Administration console, you can also specify the transport type as `SendPort(Microsoft.XLANGs.BaseTypes.TransportType)="OracleEBSAdapter"`, where **OracleEBSAdapter** is the name with which you added the WCF-OracleEBS adapter in [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] Administration console.</span></span>  
  
 <span data-ttu-id="96999-107">在前面的示例中，</span><span class="sxs-lookup"><span data-stu-id="96999-107">In the preceding example,</span></span>  
  
-   <span data-ttu-id="96999-108">正在从 Request1 消息创建次数 2 消息。</span><span class="sxs-lookup"><span data-stu-id="96999-108">Request2 message is being created from Request1 message.</span></span> <span data-ttu-id="96999-109">这两个消息映射到操作的架构，这在生成使用[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="96999-109">Both messages map to an operation schema, which is generated using the [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)].</span></span>  
  
-   <span data-ttu-id="96999-110">发送端口是 BizTalk 业务流程中的逻辑发送端口的名称。</span><span class="sxs-lookup"><span data-stu-id="96999-110">SendPort is the name of the logical send port in the BizTalk orchestration.</span></span>  
  
 <span data-ttu-id="96999-111">**表达式**形状是 BizTalk 业务流程的一部分。</span><span class="sxs-lookup"><span data-stu-id="96999-111">The **Expression** shape is part of the BizTalk orchestration.</span></span> <span data-ttu-id="96999-112">部署业务流程还会创建 WCF 自定义发送端口。</span><span class="sxs-lookup"><span data-stu-id="96999-112">Deploying the orchestration also creates a WCF-Custom send port.</span></span>  
  
 <span data-ttu-id="96999-113">有关配置动态端口的详细信息，请参阅[配置动态发送端口使用 WCF 适配器上下文属性](../../core/configuring-dynamic-send-ports-using-wcf-adapters-context-properties.md)。</span><span class="sxs-lookup"><span data-stu-id="96999-113">For more information about configuring dynamic ports, see [Configuring Dynamic Send Ports Using WCF Adapters Context Properties](../../core/configuring-dynamic-send-ports-using-wcf-adapters-context-properties.md).</span></span>
  
## <a name="see-also"></a><span data-ttu-id="96999-114">另请参阅</span><span class="sxs-lookup"><span data-stu-id="96999-114">See Also</span></span>  
[<span data-ttu-id="96999-115">创建 Oracle E-business Suite 应用程序的构建基块</span><span class="sxs-lookup"><span data-stu-id="96999-115">Building blocks to create Oracle E-Business Suite applications</span></span>](../../adapters-and-accelerators/adapter-oracle-ebs/building-blocks-to-create-oracle-e-business-suite-applications.md)