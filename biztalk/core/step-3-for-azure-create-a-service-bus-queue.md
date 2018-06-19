---
title: （适用于 Azure) 中的步骤 3： 创建 Service Bus 队列 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: b7192c3c-4ebf-49c4-b8ce-46a6e9fb5f4a
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: d55b3222798edb245000cdde8de52565c39758a7
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22277333"
---
# <a name="step-3-for-azure-create-a-service-bus-queue"></a><span data-ttu-id="9c2f5-102">（适用于 Azure) 中的步骤 3： 创建 Service Bus 队列</span><span class="sxs-lookup"><span data-stu-id="9c2f5-102">Step 3 (For Azure): Create a Service Bus Queue</span></span>
<span data-ttu-id="9c2f5-103">在本主题中，你将创建一个 Service Bus 队列，在使用 EDI 协议处理并转换 X12 销售订单后会将其发送至该队列。</span><span class="sxs-lookup"><span data-stu-id="9c2f5-103">In this topic, you create a Service Bus Queue to which the X12 sales order is sent after it is processed and transformed using the EDI agreement.</span></span>  
  
### <a name="to-create-a-service-bus-queue"></a><span data-ttu-id="9c2f5-104">创建 Service Bus 队列的步骤</span><span class="sxs-lookup"><span data-stu-id="9c2f5-104">To create a Service Bus Queue</span></span>  
  
1.  <span data-ttu-id="9c2f5-105">登录到[Windows Azure CTP 管理门户](http://go.microsoft.com/fwlink/p/?LinkId=202886)使用你的 Microsoft 帐户。</span><span class="sxs-lookup"><span data-stu-id="9c2f5-105">Log in to the [Windows Azure CTP Management Portal](http://go.microsoft.com/fwlink/p/?LinkId=202886) using your Microsoft account.</span></span>  
  
2.  <span data-ttu-id="9c2f5-106">在该页的较低的左侧，单击**AppFabric**。</span><span class="sxs-lookup"><span data-stu-id="9c2f5-106">On the lower left-hand side of the page, click **AppFabric**.</span></span>  
  
3.  <span data-ttu-id="9c2f5-107">展开左侧树中的服务，展开你的订阅，然后单击你必定已创建的一个命名空间。</span><span class="sxs-lookup"><span data-stu-id="9c2f5-107">Expand Services in the tree on the left-hand side, expand your subscription, and click a namespace that you must have already created.</span></span> <span data-ttu-id="9c2f5-108">如果你已没有命名空间，请参阅[如何： 创建或修改 Windows Azure CTP 服务 Namespace](http://msdn.microsoft.com/library/windowsazure/hh697699.aspx)。</span><span class="sxs-lookup"><span data-stu-id="9c2f5-108">If you don’t have a namespace already, see [How to: Create or Modify a Windows Azure CTP Service Namespace](http://msdn.microsoft.com/library/windowsazure/hh697699.aspx).</span></span>  
  
4.  <span data-ttu-id="9c2f5-109">若要创建队列单击**新队列**从**管理实体**从页面顶部的工具栏的类别。</span><span class="sxs-lookup"><span data-stu-id="9c2f5-109">To create a Queue click **New Queue** from the **Manage Entities** category from the toolbar at the top of the page.</span></span>  
  
5.  <span data-ttu-id="9c2f5-110">在**新队列**对话框框中，输入队列的名称。</span><span class="sxs-lookup"><span data-stu-id="9c2f5-110">In the **New Queue** dialog box, enter a name for the Queue.</span></span> <span data-ttu-id="9c2f5-111">对于本教程中，输入作为名称`queueordersedi`，然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="9c2f5-111">For this tutorial, enter the name as `queueordersedi`, and then click **OK**.</span></span> <span data-ttu-id="9c2f5-112">在指定此名称为的 EDI 协议的一部分中创建[(为 Azure) 的步骤 2： 创建 EDI 协议](../core/step-2-for-azure-create-an-edi-agreement.md)。</span><span class="sxs-lookup"><span data-stu-id="9c2f5-112">You specified this name as part of the EDI agreement you created in [Step 2 (For Azure): Create an EDI Agreement](../core/step-2-for-azure-create-an-edi-agreement.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9c2f5-113">另请参阅</span><span class="sxs-lookup"><span data-stu-id="9c2f5-113">See Also</span></span>  
 [<span data-ttu-id="9c2f5-114">教程 4： 创建使用 BizTalk Server 2013 的混合应用程序</span><span class="sxs-lookup"><span data-stu-id="9c2f5-114">Tutorial 4: Creating a Hybrid Application Using BizTalk Server 2013</span></span>](../core/tutorial-4-creating-a-hybrid-application-using-biztalk-server-2013.md)