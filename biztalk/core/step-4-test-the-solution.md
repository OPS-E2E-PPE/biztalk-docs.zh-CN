---
title: 步骤 4：测试解决方案 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 60c39521-eee2-49f7-a9f9-2dfb9ab468e9
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 56869aa22ab54efe78838403ae060154b98a001a
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65392474"
---
# <a name="step-4-test-the-solution"></a><span data-ttu-id="6e54c-102">步骤 4：测试解决方案</span><span class="sxs-lookup"><span data-stu-id="6e54c-102">Step 4: Test the Solution</span></span>
<span data-ttu-id="6e54c-103">删除与文件关联的文件夹中的虚拟请求消息测试解决方案本主题中接收端口。</span><span class="sxs-lookup"><span data-stu-id="6e54c-103">In this topic you test the solution by dropping a dummy request message in the folder you associated with the FILE receive port.</span></span> <span data-ttu-id="6e54c-104">如中所述，你放置虚拟请求消息仅仅是为了调用**Wcf-webhttp**发送端口。</span><span class="sxs-lookup"><span data-stu-id="6e54c-104">As explained in, you drop a dummy request message only to invoke the **WCF-WebHttp** send port.</span></span> <span data-ttu-id="6e54c-105">可以创建虚拟请求消息，如下所示：</span><span class="sxs-lookup"><span data-stu-id="6e54c-105">You can create a dummy request message like the following:</span></span>  
  
```  
<Root>  
  <Input>Azure Market Place REST API integration</Input>  
<Root>  
```  
  
### <a name="to-test-the-solution"></a><span data-ttu-id="6e54c-106">若要测试解决方案</span><span class="sxs-lookup"><span data-stu-id="6e54c-106">To test the solution</span></span>  
  
1.  <span data-ttu-id="6e54c-107">从 BizTalk Server 管理控制台中，启动**BizTalk Application 1**。</span><span class="sxs-lookup"><span data-stu-id="6e54c-107">From the BizTalk Server Administration Console, start **BizTalk Application 1**.</span></span> <span data-ttu-id="6e54c-108">这会启动我们在前面的步骤中创建的所有端口。</span><span class="sxs-lookup"><span data-stu-id="6e54c-108">This starts all the ports that we created in previous steps.</span></span>  
  
2.  <span data-ttu-id="6e54c-109">打开 Windows 资源管理器，并导航到与文件关联的位置接收位置。</span><span class="sxs-lookup"><span data-stu-id="6e54c-109">Open Windows Explorer, and navigate to the location that you associated with the FILE receive location.</span></span> <span data-ttu-id="6e54c-110">在此位置，将复制虚拟请求消息。</span><span class="sxs-lookup"><span data-stu-id="6e54c-110">At this location, copy the dummy request message.</span></span>  
  
3.  <span data-ttu-id="6e54c-111">在该文件消失后，检查与处理来自 REST 接口的响应消息的文件发送端口关联的位置。</span><span class="sxs-lookup"><span data-stu-id="6e54c-111">When the file disappears, check the location you associated with FILE send port that consumes the response message from the REST interface.</span></span> <span data-ttu-id="6e54c-112">它应包含一个 XML 响应消息。</span><span class="sxs-lookup"><span data-stu-id="6e54c-112">It should contain an XML response message.</span></span> <span data-ttu-id="6e54c-113">打开要查看航班为从的都延迟的详细信息的 XML 消息。</span><span class="sxs-lookup"><span data-stu-id="6e54c-113">Open the XML message to see the details of flights from US air carries that are delayed.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6e54c-114">请参阅</span><span class="sxs-lookup"><span data-stu-id="6e54c-114">See Also</span></span>  
 [<span data-ttu-id="6e54c-115">教程 5:调用 REST 接口使用 BizTalk Server</span><span class="sxs-lookup"><span data-stu-id="6e54c-115">Tutorial 5: Invoking a REST Interface Using BizTalk Server</span></span>](../core/tutorial-5-invoking-a-rest-interface-using-biztalk-server.md)