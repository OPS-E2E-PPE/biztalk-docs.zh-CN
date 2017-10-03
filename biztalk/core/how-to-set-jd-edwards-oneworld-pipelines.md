---
title: "如何设置博士 Edwards OneWorld 管道 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- receive pipelines
- send pipelines
- setting pipelines
- pipelines, setting
ms.assetid: 821d4081-a2d4-4957-abc0-d6370e719ba8
caps.latest.revision: "9"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e45ec6f6eb3be74e150e77de9ef6dbbe461a361a
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-set-jd-edwards-oneworld-pipelines"></a><span data-ttu-id="2097f-102">如何设置 D Edwards OneWorld 管道</span><span class="sxs-lookup"><span data-stu-id="2097f-102">How to Set JD Edwards OneWorld Pipelines</span></span>
<span data-ttu-id="2097f-103">用于 JD Edwards OneWorld 的 Microsoft BizTalk 适配器要求你选择 XMLTransmit 和 XMLReceive 分别用于发送和接收管道。</span><span class="sxs-lookup"><span data-stu-id="2097f-103">Microsoft BizTalk Adapter for JD Edwards OneWorld requires that you select XMLTransmit and XMLReceive for the send and receive pipelines respectively.</span></span>  
  
### <a name="to-set-pipelines"></a><span data-ttu-id="2097f-104">若要设置管道</span><span class="sxs-lookup"><span data-stu-id="2097f-104">To set pipelines</span></span>  
  
1.  <span data-ttu-id="2097f-105">上**启动**菜单上，指向**Program Files**，指向**Microsoft BizTalk Server** ，然后单击**BizTalk Server 管理**若要启动 BizTalk Server 管理控制台。</span><span class="sxs-lookup"><span data-stu-id="2097f-105">On the **Start** menu, point to **Program Files**, point to **Microsoft BizTalk Server** , and then click **BizTalk Server Administration** to start the BizTalk Server Administration Console.</span></span>  
  
2.  <span data-ttu-id="2097f-106">展开 BizTalk Server 管理中，展开**BizTalk 组**，展开**应用程序**，然后展开所需应用程序。</span><span class="sxs-lookup"><span data-stu-id="2097f-106">Expand BizTalk Server Administration, expand **BizTalk Group**, expand **Applications**, and then expand the desired application.</span></span>  
  
3.  <span data-ttu-id="2097f-107">选择**发送端口**。</span><span class="sxs-lookup"><span data-stu-id="2097f-107">Select **Send Ports**.</span></span> <span data-ttu-id="2097f-108">在详细信息窗格中，右键单击所选的发送端口，然后单击**属性**。</span><span class="sxs-lookup"><span data-stu-id="2097f-108">In the details pane, right-click the selected send port and click **Properties**.</span></span>  
  
4.  <span data-ttu-id="2097f-109">在**发送端口属性**对话框框中，执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="2097f-109">In the **Send Ports Properties** dialog box, do the following:</span></span>  
  
    1.  <span data-ttu-id="2097f-110">选择从发送管道**发送管道**下拉列表。</span><span class="sxs-lookup"><span data-stu-id="2097f-110">Select the send pipeline from the **Send Pipeline** drop-down list.</span></span>  
  
    2.  <span data-ttu-id="2097f-111">选择从接收管道**接收管道**下拉列表。</span><span class="sxs-lookup"><span data-stu-id="2097f-111">Select the Receive pipeline from the **Receive Pipeline** drop-down list.</span></span>  
  
5.  <span data-ttu-id="2097f-112">单击 **“确定”**。</span><span class="sxs-lookup"><span data-stu-id="2097f-112">Click **OK**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2097f-113">另请参阅</span><span class="sxs-lookup"><span data-stu-id="2097f-113">See Also</span></span>  
 [<span data-ttu-id="2097f-114">创建博士 Edwards OneWorld 发送处理程序</span><span class="sxs-lookup"><span data-stu-id="2097f-114">Creating JD Edwards OneWorld Send Handlers</span></span>](../core/creating-jd-edwards-oneworld-send-handlers.md)