---
title: 如何挂起业务流程实例或端口 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- pipelines, suspending
- instances, suspending
- suspending
- HAT, suspending orchestrations
- HAT, suspending pipelines
- suspending, ports
- suspending, orchestrations
- orchestrations, suspending
- HAT, suspending ports
- suspending, instances
- ports, suspending
ms.assetid: cacc7e58-7d3e-4d6b-adb0-618fdc4f0d89
caps.latest.revision: 11
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 10f6923df37b5cce3a500ed6e02014f09d1c2c0f
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36994926"
---
# <a name="how-to-suspend-orchestration-instances-or-ports"></a><span data-ttu-id="4a6eb-102">如何挂起业务流程实例或端口</span><span class="sxs-lookup"><span data-stu-id="4a6eb-102">How to Suspend Orchestration Instances or Ports</span></span>
<span data-ttu-id="4a6eb-103">可以从 BizTalk Server 管理控制台中的查询结果列表中挂起业务流程实例或端口。</span><span class="sxs-lookup"><span data-stu-id="4a6eb-103">You can suspend orchestration instances or ports from a query results list in the BizTalk Server Administration Console.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="4a6eb-104">必要條件</span><span class="sxs-lookup"><span data-stu-id="4a6eb-104">Prerequisites</span></span>  
 <span data-ttu-id="4a6eb-105">必须以 BizTalk Server Operators 组成员的身份登录，才能执行此过程。</span><span class="sxs-lookup"><span data-stu-id="4a6eb-105">You must be logged on as a member of the BizTalk Server Operators group to perform this procedure.</span></span>  
  
### <a name="to-suspend-orchestration-instances-or-ports"></a><span data-ttu-id="4a6eb-106">挂起业务流程实例或端口</span><span class="sxs-lookup"><span data-stu-id="4a6eb-106">To suspend orchestration instances or ports</span></span>  
  
1. <span data-ttu-id="4a6eb-107">单击**启动**，单击**程序**，单击[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]，然后单击**BizTalk Server 管理**。</span><span class="sxs-lookup"><span data-stu-id="4a6eb-107">Click **Start**, click **Programs**, click [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)], and then click **BizTalk Server Administration**.</span></span>  
  
2. <span data-ttu-id="4a6eb-108">在控制台树中，展开**BizTalk Server 管理**，然后单击 BizTalk 组。</span><span class="sxs-lookup"><span data-stu-id="4a6eb-108">In the console tree, expand **BizTalk Server Administration**, and then click the BizTalk group.</span></span>  
  
3. <span data-ttu-id="4a6eb-109">在详细信息窗格中，单击**新查询**选项卡。</span><span class="sxs-lookup"><span data-stu-id="4a6eb-109">In the details pane, click the **New Query** tab.</span></span>  
  
4. <span data-ttu-id="4a6eb-110">在中**查询表达式**组中，在**值**列中，选择**正在运行的服务实例**从下拉列表框。</span><span class="sxs-lookup"><span data-stu-id="4a6eb-110">In the **Query Expression** group, in the **Value** column, select **Running Service Instances** from the drop-down list box.</span></span>  
  
5. <span data-ttu-id="4a6eb-111">执行以下操作之一：</span><span class="sxs-lookup"><span data-stu-id="4a6eb-111">Do one of the following:</span></span>  
  
   - <span data-ttu-id="4a6eb-112">若要挂起单个实例，在**字段名**列，星号旁边的空下拉列表框中 (**\\**<em>)，选择 \**服务名称</em>* 筛选器，然后在**值**列中，指定服务名称。</span><span class="sxs-lookup"><span data-stu-id="4a6eb-112">To suspend a single instance, in the **Field Name** column, in the empty drop-down list box next to the asterisk (**\\**<em>), select the \**Service Name</em>* filter and then in the **Value** column, specify the service name.</span></span>  
  
   - <span data-ttu-id="4a6eb-113">若要挂起实例，请在**字段名**列，星号旁边的空下拉列表框中 (**\\**<em>)，选择 \**结果分组依据</em>* ，然后在**值**列中，指定服务名称。</span><span class="sxs-lookup"><span data-stu-id="4a6eb-113">To suspend instances in bulk, in the **Field Name** column, in the empty drop-down list box next to the asterisk (**\\**<em>), select \**Group Results By</em>* and then in the **Value** column, specify the service name.</span></span>  
  
6. <span data-ttu-id="4a6eb-114">单击**运行查询**。</span><span class="sxs-lookup"><span data-stu-id="4a6eb-114">Click **Run Query**.</span></span>  
  
7. <span data-ttu-id="4a6eb-115">在查询结果列表中，右键单击你想要挂起，，然后单击活动业务流程的一个或多个端口**挂起单个实例**或**挂起多个实例**。</span><span class="sxs-lookup"><span data-stu-id="4a6eb-115">In the query results list, right-click the active orchestration or port you want to suspend, and then click **Suspend Instance** or **Suspend Instances**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4a6eb-116">请参阅</span><span class="sxs-lookup"><span data-stu-id="4a6eb-116">See Also</span></span>  
 [<span data-ttu-id="4a6eb-117">调查业务流程、端口和消息失败</span><span class="sxs-lookup"><span data-stu-id="4a6eb-117">Investigating Orchestration, Port, and Message Failures</span></span>](../core/investigating-orchestration-port-and-message-failures.md)