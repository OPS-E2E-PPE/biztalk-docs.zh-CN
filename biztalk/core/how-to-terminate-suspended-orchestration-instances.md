---
title: 如何终止挂起的业务流程实例 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- pipelines, terminating [HAT]
- messages, saving [HAT]
- HAT, saving messages
- HAT, terminating pipelines
- HAT, terminiating orchestrations
- orchestrations, terminating [HAT]
ms.assetid: b5d44cce-b05c-47f9-9015-5b10c2312bf1
caps.latest.revision: 17
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 37de5e1153e9d361b76900ca206351e8b9549dc3
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36991966"
---
# <a name="how-to-terminate-suspended-orchestration-instances"></a><span data-ttu-id="3c01d-102">如何终止挂起的业务流程实例</span><span class="sxs-lookup"><span data-stu-id="3c01d-102">How to Terminate Suspended Orchestration Instances</span></span>
<span data-ttu-id="3c01d-103">可以从 BizTalk Server 管理控制台中的查询结果或预览窗格终止所有挂起的业务流程实例或端口。</span><span class="sxs-lookup"><span data-stu-id="3c01d-103">You can terminate any suspended orchestration instances or ports from the Query results or preview pane in the BizTalk Server Administration Console.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="3c01d-104">按序送达发送端口的每个实例可能具有与之关联的多条消息。</span><span class="sxs-lookup"><span data-stu-id="3c01d-104">Each instance of an ordered delivery a send port may have several messages associated with it.</span></span> <span data-ttu-id="3c01d-105">为了防止意外终止或数据丢失，请确保您在终止某一实例前查看了所有此类关联。</span><span class="sxs-lookup"><span data-stu-id="3c01d-105">To prevent accidental termination or data loss, be sure you have reviewed all such associations before terminating an instance.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="3c01d-106">必要條件</span><span class="sxs-lookup"><span data-stu-id="3c01d-106">Prerequisites</span></span>  
 <span data-ttu-id="3c01d-107">必须以 BizTalk Server Operators 组成员的身份登录，才能执行此过程。</span><span class="sxs-lookup"><span data-stu-id="3c01d-107">You must be logged on as a member of the BizTalk Server Operators group to perform this procedure.</span></span>  
  
### <a name="to-terminate-suspended-orchestration-instances"></a><span data-ttu-id="3c01d-108">终止挂起的业务流程实例</span><span class="sxs-lookup"><span data-stu-id="3c01d-108">To terminate suspended orchestration instances</span></span>  
  
1. <span data-ttu-id="3c01d-109">单击**启动**，单击**程序**，单击[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]，然后单击**BizTalk Server 管理**。</span><span class="sxs-lookup"><span data-stu-id="3c01d-109">Click **Start**, click **Programs**, click [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)], and then click **BizTalk Server Administration**.</span></span>  
  
2. <span data-ttu-id="3c01d-110">在控制台树中，展开“[!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)]”，然后单击“BizTalk 组”。</span><span class="sxs-lookup"><span data-stu-id="3c01d-110">In the console tree, expand [!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)], and then click the BizTalk group.</span></span>  
  
3. <span data-ttu-id="3c01d-111">在详细信息窗格中，单击**新查询**选项卡。</span><span class="sxs-lookup"><span data-stu-id="3c01d-111">In the details pane, click the **New Query** tab.</span></span>  
  
4. <span data-ttu-id="3c01d-112">在中**查询表达式**组中，在**值**列中，选择**挂起服务实例**从下拉列表框。</span><span class="sxs-lookup"><span data-stu-id="3c01d-112">In the **Query Expression** group, in the **Value** column, select **Suspended Service Instances** from the drop-down list box.</span></span>  
  
5. <span data-ttu-id="3c01d-113">执行以下操作之一：</span><span class="sxs-lookup"><span data-stu-id="3c01d-113">Do one of the following:</span></span>  
  
   - <span data-ttu-id="3c01d-114">若要终止单个实例，在**字段名**列，星号旁边的空下拉列表框中 (**\\**<em>)，选择 \**服务名称</em>* 筛选器，然后在**值**列中，指定服务名称。</span><span class="sxs-lookup"><span data-stu-id="3c01d-114">To terminate a single instance, in the **Field Name** column, in the empty drop-down list box next to the asterisk (**\\**<em>), select the \**Service Name</em>* filter and then in the **Value** column, specify the service name.</span></span>  
  
   - <span data-ttu-id="3c01d-115">若要终止实例，请在**字段名**列，星号旁边的空下拉列表框中 (**\\**<em>)，选择 \**结果分组依据</em>* ，然后在**值**列中，指定服务名称。</span><span class="sxs-lookup"><span data-stu-id="3c01d-115">To terminate instances in bulk, in the **Field Name** column, in the empty drop-down list box next to the asterisk (**\\**<em>), select \**Group Results By</em>* and then in the **Value** column, specify the service name.</span></span>  
  
6. <span data-ttu-id="3c01d-116">单击**运行查询**。</span><span class="sxs-lookup"><span data-stu-id="3c01d-116">Click **Run Query**.</span></span>  
  
7. <span data-ttu-id="3c01d-117">在查询结果列表中，右键单击业务流程实例或组以终止，然后单击所需的实例**终止的实例**或**终止实例**。</span><span class="sxs-lookup"><span data-stu-id="3c01d-117">In the query results list, right-click the orchestration instance or group of instances you want to terminate, and then click **Terminate Instance** or **Terminate Instances**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3c01d-118">请参阅</span><span class="sxs-lookup"><span data-stu-id="3c01d-118">See Also</span></span>  
 [<span data-ttu-id="3c01d-119">调查业务流程、端口和消息失败</span><span class="sxs-lookup"><span data-stu-id="3c01d-119">Investigating Orchestration, Port, and Message Failures</span></span>](../core/investigating-orchestration-port-and-message-failures.md)