---
title: 如何测试 HTTP 节点 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- HTTP node, testing
- testing HTTP node
ms.assetid: f6881e8f-9f92-4312-bb5e-06bbfb9fe0bb
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 2790a4e3fa0ff1ed9a9b9b0c2018108c9cbb1282
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22255525"
---
# <a name="how-to-test-the-http-node"></a><span data-ttu-id="dcf16-102">如何测试 HTTP 节点</span><span class="sxs-lookup"><span data-stu-id="dcf16-102">How to Test the HTTP Node</span></span>
<span data-ttu-id="dcf16-103">请按照以下步骤来测试 HTTP 节点。</span><span class="sxs-lookup"><span data-stu-id="dcf16-103">Follow these steps to test the HTTP node.</span></span>  
  
### <a name="to-test-the-http-node"></a><span data-ttu-id="dcf16-104">测试 HTTP 节点</span><span class="sxs-lookup"><span data-stu-id="dcf16-104">To test the HTTP node</span></span>  
  
1.  <span data-ttu-id="dcf16-105">在 PeopleSoft 企业中，导航到**PeopleTools**，**集成 Broker**，**监视器**，**监视器消息**。</span><span class="sxs-lookup"><span data-stu-id="dcf16-105">In PeopleSoft Enterprise, navigate to **PeopleTools**, **Integration Broker**, **Monitor**, **Monitor Message**.</span></span>  
  
     ![](../core/media/psadapter-40-task-gatewaytestnode.gif "PSAdapter_40_Task_GatewayTestNode")  
  
2.  <span data-ttu-id="dcf16-106">单击**节点状态**选项卡。</span><span class="sxs-lookup"><span data-stu-id="dcf16-106">Click the **Node Status** tab.</span></span>  
  
3.  <span data-ttu-id="dcf16-107">在**消息节点名称**字段中，输入`MSEXTERNAL`，然后单击**查找**图标。</span><span class="sxs-lookup"><span data-stu-id="dcf16-107">In the **Message Node Name** field, enter `MSEXTERNAL`, and then click the **Lookup** icon.</span></span>  
  
4.  <span data-ttu-id="dcf16-108">下**消息节点名称**，选择**MSEXTERNAL**。</span><span class="sxs-lookup"><span data-stu-id="dcf16-108">Under **Message Node Name**, select **MSEXTERNAL**.</span></span>  
  
     <span data-ttu-id="dcf16-109">将显示一条消息，表明 PeopleSoft 正在通过 HTTP 进行通信。</span><span class="sxs-lookup"><span data-stu-id="dcf16-109">A message appears and indicates that PeopleSoft is communicating through HTTP.</span></span>  
  
     ![](../core/media/psadapter-41-task-gatewaytestsuccess.gif "PSAdapter_41_Task_GatewayTestSuccess")  
  
     <span data-ttu-id="dcf16-110">如果没有收到该消息，请验证以下内容：</span><span class="sxs-lookup"><span data-stu-id="dcf16-110">If you do not receive the message, verify the following:</span></span>  
  
    1.  <span data-ttu-id="dcf16-111">接收端口和节点间的 IP 地址和端口是否匹配。</span><span class="sxs-lookup"><span data-stu-id="dcf16-111">The IP addresses and ports match between the receive port and the node.</span></span>  
  
    2.  <span data-ttu-id="dcf16-112">BizTalk Server 是否正在运行。</span><span class="sxs-lookup"><span data-stu-id="dcf16-112">BizTalk Server is running.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="dcf16-113">另请参阅</span><span class="sxs-lookup"><span data-stu-id="dcf16-113">See Also</span></span>  
 [<span data-ttu-id="dcf16-114">创建 PeopleSoft HTTP 主机和端口</span><span class="sxs-lookup"><span data-stu-id="dcf16-114">Creating a PeopleSoft HTTP Host and Port</span></span>](../core/creating-a-peoplesoft-http-host-and-port.md)