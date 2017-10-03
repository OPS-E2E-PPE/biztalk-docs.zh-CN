---
title: "开发使用 Oracle E-business Suite 适配器的 BizTalk 应用程序 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: bf3374a2-2fca-4df4-a1b1-d11cdc05d393
caps.latest.revision: "19"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: d201987490d9395b07d043c67fa50a31400fe7cd
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="develop-biztalk-applications-using-the-oracle-e-business-suite-adapter"></a><span data-ttu-id="3cf3b-102">开发使用 Oracle E-business Suite 适配器的 BizTalk 应用程序</span><span class="sxs-lookup"><span data-stu-id="3cf3b-102">Develop BizTalk applications using the Oracle E-Business Suite adapter</span></span>
<span data-ttu-id="3cf3b-103">开发 BizTalk 应用程序涉及到创建中的 BizTalk 项目[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]，并使用 **[!INCLUDE[consumeadapterservlong](../../includes/consumeadapterservlong-md.md)]** 或 **[!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)]** 生成 XML 架构。</span><span class="sxs-lookup"><span data-stu-id="3cf3b-103">Developing BizTalk applications involves creating a BizTalk project in [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)], and using the **[!INCLUDE[consumeadapterservlong](../../includes/consumeadapterservlong-md.md)]** or **[!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)]** to generate XML schema.</span></span> <span data-ttu-id="3cf3b-104">一旦你已生成架构，你可以使用基于内容的路由 (CBR)，或创建 BizTalk 业务流程，以发送和接收符合您生成架构的消息。</span><span class="sxs-lookup"><span data-stu-id="3cf3b-104">Once you have generated the schema, you can either use Content-Based Routing (CBR) or create BizTalk orchestrations to send and receive messages that conform to your generated schema.</span></span>  
  
 <span data-ttu-id="3cf3b-105">CBR 可以用于的方案发送到 Oracle E-business Suite 的消息不需要任何密集型处理。</span><span class="sxs-lookup"><span data-stu-id="3cf3b-105">CBR can be used in scenarios where the messages being sent to Oracle E-Business Suite do not require any intensive processing.</span></span> <span data-ttu-id="3cf3b-106">例如，如果你知道，某一类型的仅接收端口接收消息，你可以将筛选器添加到筛选器与表达式匹配的对发送端口将消息路由到发送端口。</span><span class="sxs-lookup"><span data-stu-id="3cf3b-106">For example, if you know that the receive port receive messages only of a certain type, you can add a filter to the send port to route messages that match the filter expression to the send port.</span></span>  

## <a name="use-orchestration"></a><span data-ttu-id="3cf3b-107">使用业务流程</span><span class="sxs-lookup"><span data-stu-id="3cf3b-107">Use orchestration</span></span>  
 <span data-ttu-id="3cf3b-108">在 BizTalk 业务流程中创建发送和接收端口发送和接收消息，并从[!INCLUDE[wcfadapter_short](../../includes/wcfadapter-short-md.md)]，这反过来将消息发送到[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="3cf3b-108">In BizTalk orchestrations, you create send and receive ports to send and receive messages to and from the [!INCLUDE[wcfadapter_short](../../includes/wcfadapter-short-md.md)], which in turn sends the messages to [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)].</span></span> 
 
 <span data-ttu-id="3cf3b-109">本部分提供有关使用 BizTalk 业务流程执行的任务以及使用 Oracle E-business Suite 操作的信息[!INCLUDE[adapteroraclebusinessshort_md](../../includes/adapteroraclebusinessshort-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="3cf3b-109">This section provides information about using BizTalk orchestrations to perform tasks and operations on Oracle E-Business Suite using the [!INCLUDE[adapteroraclebusinessshort_md](../../includes/adapteroraclebusinessshort-md.md)].</span></span> <span data-ttu-id="3cf3b-110">[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]反过来使用[!INCLUDE[wcfadapter_short](../../includes/wcfadapter-short-md.md)]，这可以与的 WCF 绑定进行交互。</span><span class="sxs-lookup"><span data-stu-id="3cf3b-110">The [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] in turn uses the [!INCLUDE[wcfadapter_short](../../includes/wcfadapter-short-md.md)], which can interact with a WCF binding.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="3cf3b-111">若要使用[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]与 Microsoft [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]，始终必须设置**EnableBizTalkCompatibilityMode**属性绑定到**True**。</span><span class="sxs-lookup"><span data-stu-id="3cf3b-111">To use the [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] with Microsoft [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)], you must always set the **EnableBizTalkCompatibilityMode** binding property to **True**.</span></span> <span data-ttu-id="3cf3b-112">有关步骤，请参阅[为 Oracle E-business Suite 配置的绑定属性](../../adapters-and-accelerators/adapter-oracle-ebs/configure-the-binding-properties-for-oracle-e-business-suite.md)。</span><span class="sxs-lookup"><span data-stu-id="3cf3b-112">For the steps, see [Configure the binding properties for Oracle E-Business Suite](../../adapters-and-accelerators/adapter-oracle-ebs/configure-the-binding-properties-for-oracle-e-business-suite.md).</span></span>  
  

  
## <a name="see-also"></a><span data-ttu-id="3cf3b-113">另请参阅</span><span class="sxs-lookup"><span data-stu-id="3cf3b-113">See Also</span></span>  
[<span data-ttu-id="3cf3b-114">开发 Oracle E-business Suite 应用程序</span><span class="sxs-lookup"><span data-stu-id="3cf3b-114">Develop your Oracle E-Business Suite applications</span></span>](../../adapters-and-accelerators/adapter-oracle-ebs/develop-your-oracle-e-business-suite-applications.md)