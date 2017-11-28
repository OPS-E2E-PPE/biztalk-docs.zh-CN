---
title: "处理与 Oracle E-business Suite 适配器的事务 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: b443be9d-a93d-4836-8717-5ee9dad4442f
caps.latest.revision: "6"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e00b31230760d1bb811b987c3b1a926bad803b6d
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="handle-transactions-with-the-oracle-e-business-suite-adapter"></a><span data-ttu-id="b1b75-102">处理与 Oracle E-business Suite 适配器的事务</span><span class="sxs-lookup"><span data-stu-id="b1b75-102">Handle transactions with the Oracle E-Business Suite adapter</span></span>
[!INCLUDE[adapteroracleebusinesslong](../../includes/adapteroracleebusinesslong-md.md)]<span data-ttu-id="b1b75-103">并不会启动 Oracle E-business Suite 中执行操作时事务。</span><span class="sxs-lookup"><span data-stu-id="b1b75-103"> does not initiate a transaction while performing an operation in Oracle E-Business Suite.</span></span> <span data-ttu-id="b1b75-104">相反，适配器执行的操作使用提供的适配器客户端的事务上下文。</span><span class="sxs-lookup"><span data-stu-id="b1b75-104">Instead, the adapter performs the operations using the transaction context provided by the adapter clients.</span></span> <span data-ttu-id="b1b75-105">若要执行操作在事务中使用[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]，你必须：</span><span class="sxs-lookup"><span data-stu-id="b1b75-105">In order to perform operations in a transaction using the [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)], you must:</span></span>  
  
-   <span data-ttu-id="b1b75-106">启用适配器客户端中的事务。</span><span class="sxs-lookup"><span data-stu-id="b1b75-106">Enable transactions in the adapter clients.</span></span> <span data-ttu-id="b1b75-107">例如，若要启用中的事务[!INCLUDE[btsBizTalkServer2006r3](../../includes/btsbiztalkserver2006r3-md.md)]，您必须选择**使用事务**中的复选框**事务**区域**消息**有关选项卡WCF 自定义或 WCF OracleEBS 端口。</span><span class="sxs-lookup"><span data-stu-id="b1b75-107">For example, to enable transactions in [!INCLUDE[btsBizTalkServer2006r3](../../includes/btsbiztalkserver2006r3-md.md)], you must select the **Use Transaction** check box in the **Transactions** area of the **Messages** tab for a WCF-Custom or WCF-OracleEBS port.</span></span>  
  
-   <span data-ttu-id="b1b75-108">设置的值**UseAmbientTransaction**属性绑定到**True**适配器中。</span><span class="sxs-lookup"><span data-stu-id="b1b75-108">Set the value of the **UseAmbientTransaction** binding property to **True** in the adapter.</span></span> <span data-ttu-id="b1b75-109">有关绑定属性的详细信息，请参阅[了解针对 Oracle E-business Suite 绑定属性的 BizTalk 适配器](../../adapters-and-accelerators/adapter-oracle-ebs/read-about-the-biztalk-adapter-for-oracle-e-business-suite-binding-properties.md)。</span><span class="sxs-lookup"><span data-stu-id="b1b75-109">For more information about the binding property, see [Read about the BizTalk Adapter for Oracle E-Business Suite Binding Properties](../../adapters-and-accelerators/adapter-oracle-ebs/read-about-the-biztalk-adapter-for-oracle-e-business-suite-binding-properties.md).</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="b1b75-110">若要使用该适配器在 Oracle E-business Suite 中执行事务，你必须安装**Microsoft Transaction Server 的 Oracle 服务**组件时，运行适配器的计算机上安装 Oracle 客户端，时客户端。</span><span class="sxs-lookup"><span data-stu-id="b1b75-110">To use the adapter to perform transactions in Oracle E-Business Suite, you must have installed the **Oracle Services For Microsoft Transaction Server** component, while installing the Oracle client, on the computer running the adapter client.</span></span>  
  
## <a name="transactions-in-the-outbound-operations"></a><span data-ttu-id="b1b75-111">中的出站操作的事务</span><span class="sxs-lookup"><span data-stu-id="b1b75-111">Transactions in the Outbound Operations</span></span>  
 <span data-ttu-id="b1b75-112">[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]在单个事务中执行的出站操作。</span><span class="sxs-lookup"><span data-stu-id="b1b75-112">The [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] performs an outbound operation in a single transaction.</span></span> <span data-ttu-id="b1b75-113">对于复合操作，所有操作都执行在单个事务，而是使用不同的 ODP.NET 连接。</span><span class="sxs-lookup"><span data-stu-id="b1b75-113">For composite operations, all the operations are performed in a single transaction but using different ODP.NET connections.</span></span> <span data-ttu-id="b1b75-114">有关显示的出站操作详细信息[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]，请参阅[原理适配器面 Oracle E-business Suite 元数据？](https://msdn.microsoft.com/library/dd788431.aspx)。</span><span class="sxs-lookup"><span data-stu-id="b1b75-114">For more information about the outbound operations surfaced by the [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)], see [How Does the Adapter Surface Oracle E-Business Suite Metadata?](https://msdn.microsoft.com/library/dd788431.aspx).</span></span>  
  
## <a name="transactions-in-the-inbound-operations"></a><span data-ttu-id="b1b75-115">中的入站操作的事务</span><span class="sxs-lookup"><span data-stu-id="b1b75-115">Transactions in the Inbound Operations</span></span>  
 <span data-ttu-id="b1b75-116">[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]公开以下两个入站的操作：</span><span class="sxs-lookup"><span data-stu-id="b1b75-116">The [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] exposes the following two inbound operations:</span></span>  
  
-   <span data-ttu-id="b1b75-117">**轮询**： 轮询语句和后轮询语句 （如果指定） 的执行在事务中，而在不同事务中执行的轮询的数据可用语句。</span><span class="sxs-lookup"><span data-stu-id="b1b75-117">**Polling**: The polling statement and the post-poll statement (if specified) are executed in a transaction, whereas, the polled data available statement is executed in a different transaction.</span></span> <span data-ttu-id="b1b75-118">同样，轮询语句后轮询语句执行和使用相同的 ODP.NET 连接，而使用不同的 ODP.NET 连接执行轮询的数据可用语句。</span><span class="sxs-lookup"><span data-stu-id="b1b75-118">Similarly, the polling statement and the post-poll statement are executed using the same ODP.NET connection, whereas, the polled data available statement is executed using a different ODP.NET connection.</span></span>  
  
-   <span data-ttu-id="b1b75-119">**通知**： 在使用单个 ODP.NET 连接事务中执行通知操作。</span><span class="sxs-lookup"><span data-stu-id="b1b75-119">**Notification**: The notification operation is performed in a transaction using a single ODP.NET connection.</span></span>  
  
 <span data-ttu-id="b1b75-120">有关显示的入站操作详细信息[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]，请参阅[原理适配器面 Oracle E-business Suite 元数据？](https://msdn.microsoft.com/library/dd788431.aspx)。</span><span class="sxs-lookup"><span data-stu-id="b1b75-120">For more information about the inbound operations surfaced by the [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)], see [How Does the Adapter Surface Oracle E-Business Suite Metadata?](https://msdn.microsoft.com/library/dd788431.aspx).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b1b75-121">另请参阅</span><span class="sxs-lookup"><span data-stu-id="b1b75-121">See Also</span></span>  
[<span data-ttu-id="b1b75-122">了解有关 Oracle E-business Suite 的 BizTalk Adapter</span><span class="sxs-lookup"><span data-stu-id="b1b75-122">Understand BizTalk Adapter for Oracle E-Business Suite</span></span>](../../adapters-and-accelerators/adapter-oracle-ebs/understand-biztalk-adapter-for-oracle-e-business-suite.md)