---
title: 步骤 3 （适用于 Azure):创建服务总线队列 |Microsoft Docs
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
ms.openlocfilehash: f7fe6744ab7f12b539efb9a91627abe9111373e4
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65392615"
---
# <a name="step-3-for-azure-create-a-service-bus-queue"></a><span data-ttu-id="fb2f2-102">步骤 3 （适用于 Azure):创建服务总线队列</span><span class="sxs-lookup"><span data-stu-id="fb2f2-102">Step 3 (For Azure): Create a Service Bus Queue</span></span>
<span data-ttu-id="fb2f2-103">在本主题中，你创建服务总线队列到 X12 销售订单发送后它处理并转换使用 EDI 协议。</span><span class="sxs-lookup"><span data-stu-id="fb2f2-103">In this topic, you create a Service Bus Queue to which the X12 sales order is sent after it is processed and transformed using the EDI agreement.</span></span>  
  
### <a name="to-create-a-service-bus-queue"></a><span data-ttu-id="fb2f2-104">若要创建服务总线队列</span><span class="sxs-lookup"><span data-stu-id="fb2f2-104">To create a Service Bus Queue</span></span>  
  
1.  <span data-ttu-id="fb2f2-105">登录到[Windows Azure CTP 管理门户](http://go.microsoft.com/fwlink/p/?LinkId=202886)使用你的 Microsoft 帐户。</span><span class="sxs-lookup"><span data-stu-id="fb2f2-105">Log in to the [Windows Azure CTP Management Portal](http://go.microsoft.com/fwlink/p/?LinkId=202886) using your Microsoft account.</span></span>  
  
2.  <span data-ttu-id="fb2f2-106">在较低的页的左侧，单击**AppFabric**。</span><span class="sxs-lookup"><span data-stu-id="fb2f2-106">On the lower left-hand side of the page, click **AppFabric**.</span></span>  
  
3.  <span data-ttu-id="fb2f2-107">在左侧树中展开服务，展开你的订阅，然后单击你必须已创建的命名空间。</span><span class="sxs-lookup"><span data-stu-id="fb2f2-107">Expand Services in the tree on the left-hand side, expand your subscription, and click a namespace that you must have already created.</span></span> <span data-ttu-id="fb2f2-108">如果你尚未拥有一个命名空间，请参阅[如何：创建或修改 Windows Azure CTP 服务 Namespace](http://msdn.microsoft.com/library/windowsazure/hh697699.aspx)。</span><span class="sxs-lookup"><span data-stu-id="fb2f2-108">If you don’t have a namespace already, see [How to: Create or Modify a Windows Azure CTP Service Namespace](http://msdn.microsoft.com/library/windowsazure/hh697699.aspx).</span></span>  
  
4.  <span data-ttu-id="fb2f2-109">若要创建一个队列依次单击**新队列**从**管理实体**在页面顶部工具栏中的类别。</span><span class="sxs-lookup"><span data-stu-id="fb2f2-109">To create a Queue click **New Queue** from the **Manage Entities** category from the toolbar at the top of the page.</span></span>  
  
5.  <span data-ttu-id="fb2f2-110">在中**新队列**对话框框中，输入队列的名称。</span><span class="sxs-lookup"><span data-stu-id="fb2f2-110">In the **New Queue** dialog box, enter a name for the Queue.</span></span> <span data-ttu-id="fb2f2-111">对于本教程中，输入作为名称`queueordersedi`，然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="fb2f2-111">For this tutorial, enter the name as `queueordersedi`, and then click **OK**.</span></span> <span data-ttu-id="fb2f2-112">此名称指定为一部分的 EDI 协议中创建[步骤 2 (用于 Azure):创建 EDI 协议](../core/step-2-for-azure-create-an-edi-agreement.md)。</span><span class="sxs-lookup"><span data-stu-id="fb2f2-112">You specified this name as part of the EDI agreement you created in [Step 2 (For Azure): Create an EDI Agreement](../core/step-2-for-azure-create-an-edi-agreement.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fb2f2-113">请参阅</span><span class="sxs-lookup"><span data-stu-id="fb2f2-113">See Also</span></span>  
 [<span data-ttu-id="fb2f2-114">教程 4：创建混合应用程序使用 BizTalk Server 2013</span><span class="sxs-lookup"><span data-stu-id="fb2f2-114">Tutorial 4: Creating a Hybrid Application Using BizTalk Server 2013</span></span>](../core/tutorial-4-creating-a-hybrid-application-using-biztalk-server-2013.md)