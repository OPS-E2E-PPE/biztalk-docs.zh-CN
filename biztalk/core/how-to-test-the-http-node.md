---
title: 如何测试 HTTP 节点 |Microsoft Docs
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
ms.openlocfilehash: 27e3ebdc1c75ba0e42e5af8a57e194d3ab363753
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65333882"
---
# <a name="how-to-test-the-http-node"></a><span data-ttu-id="eda81-102">如何测试 HTTP 节点</span><span class="sxs-lookup"><span data-stu-id="eda81-102">How to Test the HTTP Node</span></span>
<span data-ttu-id="eda81-103">请按照以下步骤来测试 HTTP 节点。</span><span class="sxs-lookup"><span data-stu-id="eda81-103">Follow these steps to test the HTTP node.</span></span>  
  
### <a name="to-test-the-http-node"></a><span data-ttu-id="eda81-104">若要测试 HTTP 节点</span><span class="sxs-lookup"><span data-stu-id="eda81-104">To test the HTTP node</span></span>  
  
1.  <span data-ttu-id="eda81-105">在 PeopleSoft Enterprise 中，导航到**PeopleTools**， **Integration Broker**，**监视器**，**监视器消息**。</span><span class="sxs-lookup"><span data-stu-id="eda81-105">In PeopleSoft Enterprise, navigate to **PeopleTools**, **Integration Broker**, **Monitor**, **Monitor Message**.</span></span>  
  
     <span data-ttu-id="eda81-106">![](../core/media/psadapter-40-task-gatewaytestnode.gif "PSAdapter_40_Task_GatewayTestNode")</span><span class="sxs-lookup"><span data-stu-id="eda81-106">![](../core/media/psadapter-40-task-gatewaytestnode.gif "PSAdapter_40_Task_GatewayTestNode")</span></span>  
  
2.  <span data-ttu-id="eda81-107">单击**节点状态**选项卡。</span><span class="sxs-lookup"><span data-stu-id="eda81-107">Click the **Node Status** tab.</span></span>  
  
3.  <span data-ttu-id="eda81-108">在中**消息节点名称**字段中，输入`MSEXTERNAL`，然后单击**查找**图标。</span><span class="sxs-lookup"><span data-stu-id="eda81-108">In the **Message Node Name** field, enter `MSEXTERNAL`, and then click the **Lookup** icon.</span></span>  
  
4.  <span data-ttu-id="eda81-109">下**消息节点名称**，选择**MSEXTERNAL**。</span><span class="sxs-lookup"><span data-stu-id="eda81-109">Under **Message Node Name**, select **MSEXTERNAL**.</span></span>  
  
     <span data-ttu-id="eda81-110">显示消息，指示 PeopleSoft 通过 HTTP 进行通信。</span><span class="sxs-lookup"><span data-stu-id="eda81-110">A message appears and indicates that PeopleSoft is communicating through HTTP.</span></span>  
  
     <span data-ttu-id="eda81-111">![](../core/media/psadapter-41-task-gatewaytestsuccess.gif "PSAdapter_41_Task_GatewayTestSuccess")</span><span class="sxs-lookup"><span data-stu-id="eda81-111">![](../core/media/psadapter-41-task-gatewaytestsuccess.gif "PSAdapter_41_Task_GatewayTestSuccess")</span></span>  
  
     <span data-ttu-id="eda81-112">如果未收到消息，确认下列条件：</span><span class="sxs-lookup"><span data-stu-id="eda81-112">If you do not receive the message, verify the following:</span></span>  
  
    1.  <span data-ttu-id="eda81-113">接收端口和节点之间的 IP 地址和端口匹配。</span><span class="sxs-lookup"><span data-stu-id="eda81-113">The IP addresses and ports match between the receive port and the node.</span></span>  
  
    2.  <span data-ttu-id="eda81-114">BizTalk Server 正在运行。</span><span class="sxs-lookup"><span data-stu-id="eda81-114">BizTalk Server is running.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="eda81-115">请参阅</span><span class="sxs-lookup"><span data-stu-id="eda81-115">See Also</span></span>  
 [<span data-ttu-id="eda81-116">创建 PeopleSoft HTTP 主机和端口</span><span class="sxs-lookup"><span data-stu-id="eda81-116">Creating a PeopleSoft HTTP Host and Port</span></span>](../core/creating-a-peoplesoft-http-host-and-port.md)