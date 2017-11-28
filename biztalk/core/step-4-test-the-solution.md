---
title: "步骤 4： 测试解决方案 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 60c39521-eee2-49f7-a9f9-2dfb9ab468e9
caps.latest.revision: "4"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 64f0ae6cb124ea9d8710797790b9176289faafc3
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="step-4-test-the-solution"></a><span data-ttu-id="ecd91-102">步骤 4： 测试解决方案</span><span class="sxs-lookup"><span data-stu-id="ecd91-102">Step 4: Test the Solution</span></span>
<span data-ttu-id="ecd91-103">在本主题中，你将在与 FILE 接收端口关联的文件夹中放置一个虚拟请求消息，以便对解决方案进行测试。</span><span class="sxs-lookup"><span data-stu-id="ecd91-103">In this topic you test the solution by dropping a dummy request message in the folder you associated with the FILE receive port.</span></span> <span data-ttu-id="ecd91-104">只是为了调用 dummy 请求消息中所述，放置**WCF WebHttp**发送端口。</span><span class="sxs-lookup"><span data-stu-id="ecd91-104">As explained in, you drop a dummy request message only to invoke the **WCF-WebHttp** send port.</span></span> <span data-ttu-id="ecd91-105">你可以创建如下所示的虚拟请求消息：</span><span class="sxs-lookup"><span data-stu-id="ecd91-105">You can create a dummy request message like the following:</span></span>  
  
```  
<Root>  
  <Input>Azure Market Place REST API integration</Input>  
<Root>  
```  
  
### <a name="to-test-the-solution"></a><span data-ttu-id="ecd91-106">若要测试解决方案</span><span class="sxs-lookup"><span data-stu-id="ecd91-106">To test the solution</span></span>  
  
1.  <span data-ttu-id="ecd91-107">从 BizTalk Server 管理控制台中，启动**BizTalk 应用程序 1**。</span><span class="sxs-lookup"><span data-stu-id="ecd91-107">From the BizTalk Server Administration Console, start **BizTalk Application 1**.</span></span> <span data-ttu-id="ecd91-108">这将启动你在上述步骤中创建的所有端口。</span><span class="sxs-lookup"><span data-stu-id="ecd91-108">This starts all the ports that we created in previous steps.</span></span>  
  
2.  <span data-ttu-id="ecd91-109">打开 Windows 资源管理器，然后导航到与 FILE 接收位置关联的位置。</span><span class="sxs-lookup"><span data-stu-id="ecd91-109">Open Windows Explorer, and navigate to the location that you associated with the FILE receive location.</span></span> <span data-ttu-id="ecd91-110">在此位置复制虚拟请求消息。</span><span class="sxs-lookup"><span data-stu-id="ecd91-110">At this location, copy the dummy request message.</span></span>  
  
3.  <span data-ttu-id="ecd91-111">当文件消失时，检查与 FILE 发送端口（处理来自 REST 接口的响应消息）关联的位置。</span><span class="sxs-lookup"><span data-stu-id="ecd91-111">When the file disappears, check the location you associated with FILE send port that consumes the response message from the REST interface.</span></span> <span data-ttu-id="ecd91-112">其中应包含一个 XML 响应消息。</span><span class="sxs-lookup"><span data-stu-id="ecd91-112">It should contain an XML response message.</span></span> <span data-ttu-id="ecd91-113">打开该 XML 消息可查看延误的美国航空公司航班的详细信息。</span><span class="sxs-lookup"><span data-stu-id="ecd91-113">Open the XML message to see the details of flights from US air carries that are delayed.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ecd91-114">另请参阅</span><span class="sxs-lookup"><span data-stu-id="ecd91-114">See Also</span></span>  
 [<span data-ttu-id="ecd91-115">教程 5： 调用 REST 接口使用 BizTalk Server</span><span class="sxs-lookup"><span data-stu-id="ecd91-115">Tutorial 5: Invoking a REST Interface Using BizTalk Server</span></span>](../core/tutorial-5-invoking-a-rest-interface-using-biztalk-server.md)