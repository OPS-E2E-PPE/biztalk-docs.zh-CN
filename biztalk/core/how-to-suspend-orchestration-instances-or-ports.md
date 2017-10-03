---
title: "如何挂起业务流程实例或端口 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
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
caps.latest.revision: "11"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 62d91c8d1e02b7283a430f7c82c572b6a989d108
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-suspend-orchestration-instances-or-ports"></a><span data-ttu-id="89fc0-102">如何挂起业务流程实例或端口</span><span class="sxs-lookup"><span data-stu-id="89fc0-102">How to Suspend Orchestration Instances or Ports</span></span>
<span data-ttu-id="89fc0-103">可以从 BizTalk Server 管理控制台中的查询结果列表中挂起业务流程实例或端口。</span><span class="sxs-lookup"><span data-stu-id="89fc0-103">You can suspend orchestration instances or ports from a query results list in the BizTalk Server Administration Console.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="89fc0-104">先决条件</span><span class="sxs-lookup"><span data-stu-id="89fc0-104">Prerequisites</span></span>  
 <span data-ttu-id="89fc0-105">必须以 BizTalk Server Operators 组成员的身份登录，才能执行此过程。</span><span class="sxs-lookup"><span data-stu-id="89fc0-105">You must be logged on as a member of the BizTalk Server Operators group to perform this procedure.</span></span>  
  
### <a name="to-suspend-orchestration-instances-or-ports"></a><span data-ttu-id="89fc0-106">挂起业务流程实例或端口</span><span class="sxs-lookup"><span data-stu-id="89fc0-106">To suspend orchestration instances or ports</span></span>  
  
1.  <span data-ttu-id="89fc0-107">单击**启动**，单击**程序**，单击[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]，然后单击**BizTalk Server 管理**。</span><span class="sxs-lookup"><span data-stu-id="89fc0-107">Click **Start**, click **Programs**, click [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)], and then click **BizTalk Server Administration**.</span></span>  
  
2.  <span data-ttu-id="89fc0-108">在控制台树中，展开**BizTalk Server 管理**，然后单击 BizTalk 组。</span><span class="sxs-lookup"><span data-stu-id="89fc0-108">In the console tree, expand **BizTalk Server Administration**, and then click the BizTalk group.</span></span>  
  
3.  <span data-ttu-id="89fc0-109">在详细信息窗格中，单击**新查询**选项卡。</span><span class="sxs-lookup"><span data-stu-id="89fc0-109">In the details pane, click the **New Query** tab.</span></span>  
  
4.  <span data-ttu-id="89fc0-110">在**查询表达式**组中，在**值**列中，选择**运行服务实例**从下拉列表框。</span><span class="sxs-lookup"><span data-stu-id="89fc0-110">In the **Query Expression** group, in the **Value** column, select **Running Service Instances** from the drop-down list box.</span></span>  
  
5.  <span data-ttu-id="89fc0-111">执行以下操作之一：</span><span class="sxs-lookup"><span data-stu-id="89fc0-111">Do one of the following:</span></span>  
  
    -   <span data-ttu-id="89fc0-112">若要在中暂停的单个实例，**字段名称**旁边星号的空下拉列表框中的列，(**\***)，选择**服务名称**筛选器和然后在**值**列中，指定服务名称。</span><span class="sxs-lookup"><span data-stu-id="89fc0-112">To suspend a single instance, in the **Field Name** column, in the empty drop-down list box next to the asterisk (**\***), select the **Service Name** filter and then in the **Value** column, specify the service name.</span></span>  
  
    -   <span data-ttu-id="89fc0-113">若要在中暂停成批情况下，实例**字段名称**旁边星号的空下拉列表框中的列，(**\***)，选择**结果分组依据**然后在**值**列中，指定服务名称。</span><span class="sxs-lookup"><span data-stu-id="89fc0-113">To suspend instances in bulk, in the **Field Name** column, in the empty drop-down list box next to the asterisk (**\***), select **Group Results By** and then in the **Value** column, specify the service name.</span></span>  
  
6.  <span data-ttu-id="89fc0-114">单击**运行查询**。</span><span class="sxs-lookup"><span data-stu-id="89fc0-114">Click **Run Query**.</span></span>  
  
7.  <span data-ttu-id="89fc0-115">在查询结果列表中，右键单击你想要挂起，，然后单击活动的业务流程的一个或多个端口**挂起实例**或**挂起实例**。</span><span class="sxs-lookup"><span data-stu-id="89fc0-115">In the query results list, right-click the active orchestration or port you want to suspend, and then click **Suspend Instance** or **Suspend Instances**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="89fc0-116">另请参阅</span><span class="sxs-lookup"><span data-stu-id="89fc0-116">See Also</span></span>  
 [<span data-ttu-id="89fc0-117">调查业务流程、 端口和消息失败</span><span class="sxs-lookup"><span data-stu-id="89fc0-117">Investigating Orchestration, Port, and Message Failures</span></span>](../core/investigating-orchestration-port-and-message-failures.md)