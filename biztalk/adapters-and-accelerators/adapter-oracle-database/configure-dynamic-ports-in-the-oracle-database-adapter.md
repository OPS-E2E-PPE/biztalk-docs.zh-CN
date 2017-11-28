---
title: "在 Oracle 数据库适配器中配置动态端口 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: dynamic ports, configuring
ms.assetid: c4f67707-76a0-4d72-913f-03219b412e2a
caps.latest.revision: "5"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 6c58243ba2c953000cbccd7dc9d6c1da34889058
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="configure-dynamic-ports-in-the-oracle-database-adapter"></a><span data-ttu-id="21868-102">在 Oracle 数据库适配器中配置动态端口</span><span class="sxs-lookup"><span data-stu-id="21868-102">Configure dynamic ports in the Oracle Database Adapter</span></span>
<span data-ttu-id="21868-103">在[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]，你可以配置为动态端口[!INCLUDE[wcfadapter_short](../../includes/wcfadapter-short-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="21868-103">In [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)], you can configure dynamic ports for a [!INCLUDE[wcfadapter_short](../../includes/wcfadapter-short-md.md)].</span></span> <span data-ttu-id="21868-104">因为[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]是一个基于 WCF 的适配器，你可以动态配置的端口[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]通过使用消息上下文属性。</span><span class="sxs-lookup"><span data-stu-id="21868-104">Because the [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] is a WCF-based adapter, you can dynamically configure a port for the [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] by using message context properties.</span></span>  
  
 <span data-ttu-id="21868-105">有关[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]，URI、 操作和绑定可能确定传入消息时，属性，然后中指定**表达式**形状，如下面的示例中所示：</span><span class="sxs-lookup"><span data-stu-id="21868-105">For the [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)], the URI, action, and binding may be determined from a property on an incoming message, and then specified in the **Expression** shape, as shown in the following example:</span></span>  
  
```  
Request2=Request1;  
Request2(WCF.Action)="http://Microsoft.LobServices.OracleDB/2007/03/SCOTT/Table/ACCOUNTACTIVITY/Select";  
Request2(WCF.BindingType)="oracleDBBinding";  
Request2(WCF.UserName)="SCOTT";  
Request2(WCF.Password)="TIGER";  
SendPort(Microsoft.XLANGs.BaseTypes.Address)="oracledb://adapdoc/";  
SendPort(Microsoft.XLANGs.BaseTypes.TransportType)="WCF-Custom";  
  
```  
  
> [!NOTE]
>  <span data-ttu-id="21868-106">如果使用中的 WCF OracleDB 适配器[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理控制台中，你还可以指定的传输类型为`SendPort(Microsoft.XLANGs.BaseTypes.TransportType)="OracleDatabaseAdapter"`，其中**OracleDatabaseAdapter**是与其添加中的 WCF OracleDB 适配器的名称[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理控制台。</span><span class="sxs-lookup"><span data-stu-id="21868-106">If you are using a WCF-OracleDB adapter in [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] Administration console, you can also specify the transport type as `SendPort(Microsoft.XLANGs.BaseTypes.TransportType)="OracleDatabaseAdapter"`, where **OracleDatabaseAdapter** is the name with which you added the WCF-OracleDB adapter in [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] Administration console.</span></span>  
  
 <span data-ttu-id="21868-107">在上面的示例中，</span><span class="sxs-lookup"><span data-stu-id="21868-107">In the above example,</span></span>  
  
-   <span data-ttu-id="21868-108">正在从 Request1 消息创建次数 2 消息。</span><span class="sxs-lookup"><span data-stu-id="21868-108">Request2 message is being created from Request1 message.</span></span> <span data-ttu-id="21868-109">两条消息映射到操作的架构，这在生成使用[!INCLUDE[consumeadapterservlong](../../includes/consumeadapterservlong-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="21868-109">Both the messages map to an operation schema, which is generated using the [!INCLUDE[consumeadapterservlong](../../includes/consumeadapterservlong-md.md)].</span></span>  
  
-   <span data-ttu-id="21868-110">发送端口是 BizTalk 业务流程中的逻辑发送端口的名称。</span><span class="sxs-lookup"><span data-stu-id="21868-110">SendPort is the name of the logical send port in the BizTalk orchestration.</span></span>  
  
 <span data-ttu-id="21868-111">**表达式**形状是 BizTalk 业务流程的一部分。</span><span class="sxs-lookup"><span data-stu-id="21868-111">The **Expression** shape is part of the BizTalk orchestration.</span></span> <span data-ttu-id="21868-112">当你部署的业务流程时，也将创建 WCF 自定义发送端口。</span><span class="sxs-lookup"><span data-stu-id="21868-112">When you deploy the orchestration, the WCF-custom send port is also created.</span></span>  
  
 <span data-ttu-id="21868-113">配置动态端口的详细信息，请参阅[配置动态发送端口使用 WCF 适配器上下文属性](../../core/configuring-dynamic-send-ports-using-wcf-adapters-context-properties.md)。</span><span class="sxs-lookup"><span data-stu-id="21868-113">For more information on configuring dynamic ports, see [Configuring Dynamic Send Ports Using WCF Adapters Context Properties](../../core/configuring-dynamic-send-ports-using-wcf-adapters-context-properties.md).</span></span>
  
## <a name="see-also"></a><span data-ttu-id="21868-114">另请参阅</span><span class="sxs-lookup"><span data-stu-id="21868-114">See Also</span></span>  
[<span data-ttu-id="21868-115">开发与 Oracle 数据库的 BizTalk 应用程序的构建基块</span><span class="sxs-lookup"><span data-stu-id="21868-115">Building Blocks to develop BizTalk Applications with Oracle Database</span></span>](../../adapters-and-accelerators/adapter-oracle-database/building-blocks-to-develop-biztalk-applications-with-oracle-database.md)