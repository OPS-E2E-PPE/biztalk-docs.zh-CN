---
title: 如何恢复已挂起的业务流程实例 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- instances, resuming [HAT]
- HAT, resuming orchestrations
- HAT, resuming pipelines
- orchestrations, resuming
- resuming, pipelines
- resuming, orchestrations
- HAT, debug mode
ms.assetid: da133183-68d9-48d1-9601-8f6d4d5b8898
caps.latest.revision: 18
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 6696547ce3e918dc8d84b7cfcb4f24e31c8b70a0
ms.sourcegitcommit: 8418b1a8f38b7f56979cd6e203f0b591e2f40fe1
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/28/2018
ms.locfileid: "22316889"
---
# <a name="how-to-resume-suspended-orchestration-instances"></a><span data-ttu-id="e91b3-102">如何恢复挂起的业务流程实例</span><span class="sxs-lookup"><span data-stu-id="e91b3-102">How to Resume Suspended Orchestration Instances</span></span>
<span data-ttu-id="e91b3-103">如果你已挂起被列为“可恢复的挂起”的业务流程实例，则可以尝试从查询结果或预览窗格中恢复该业务流程实例。</span><span class="sxs-lookup"><span data-stu-id="e91b3-103">If you have suspended orchestration instances that are listed as "suspended resumable," you can attempt to resume the orchestration instance from the query results or preview pane.</span></span> <span data-ttu-id="e91b3-104">只有在导致业务流程实例挂起的根本问题也得到解决后，才能成功恢复该业务流程实例。</span><span class="sxs-lookup"><span data-stu-id="e91b3-104">Resuming the orchestration instance will only succeed if the underlying problem that caused the orchestration instance to become suspended has also been fixed.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="e91b3-105">先决条件</span><span class="sxs-lookup"><span data-stu-id="e91b3-105">Prerequisites</span></span>  
 <span data-ttu-id="e91b3-106">必须以 BizTalk Server Operators 组成员的身份登录，才能执行此过程。</span><span class="sxs-lookup"><span data-stu-id="e91b3-106">You must be logged on as a member of the BizTalk Server Operators group to perform this procedure.</span></span>  
  
### <a name="to-resume-suspended-orchestration-instances"></a><span data-ttu-id="e91b3-107">恢复挂起的业务流程实例</span><span class="sxs-lookup"><span data-stu-id="e91b3-107">To resume suspended orchestration instances</span></span>  
  
1.  <span data-ttu-id="e91b3-108">单击**启动**，单击**程序**，单击[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]，然后单击**BizTalk Server 管理**。</span><span class="sxs-lookup"><span data-stu-id="e91b3-108">Click **Start**, click **Programs**, click [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)], and then click **BizTalk Server Administration**.</span></span>  
  
2.  <span data-ttu-id="e91b3-109">在控制台树中，展开 **BizTalk Server 管理**, ，然后单击 BizTalk 组。</span><span class="sxs-lookup"><span data-stu-id="e91b3-109">In the console tree, expand **BizTalk Server Administration**, and then click the BizTalk group.</span></span>  
  
3.  <span data-ttu-id="e91b3-110">在详细信息窗格中，单击 **新查询** 选项卡。</span><span class="sxs-lookup"><span data-stu-id="e91b3-110">In the details pane, click the **New Query** tab.</span></span>  
  
4.  <span data-ttu-id="e91b3-111">在 **查询表达式** 组中，在 **值** 列中，选择 **挂起服务实例** 从下拉列表框。</span><span class="sxs-lookup"><span data-stu-id="e91b3-111">In the **Query Expression** group, in the **Value** column, select **Suspended Service Instances** from the drop-down list box.</span></span>  
  
5.  <span data-ttu-id="e91b3-112">执行以下操作之一：</span><span class="sxs-lookup"><span data-stu-id="e91b3-112">Do one of the following:</span></span>  
  
    -   <span data-ttu-id="e91b3-113">若要在中恢复的单个实例， **字段名称** 旁边星号的空下拉列表框中的列，(**\***)，选择 **服务名称** 筛选器，然后在 **值** 列中，指定服务名称。</span><span class="sxs-lookup"><span data-stu-id="e91b3-113">To resume a single instance, in the **Field Name** column, in the empty drop-down list box next to the asterisk (**\***), select the **Service Name** filter and then in the **Value** column, specify the service name.</span></span>  
  
    -   <span data-ttu-id="e91b3-114">若要在恢复实例成批情况下， **字段名称** 旁边星号的空下拉列表框中的列，(**\***)，选择 **结果分组依据** 然后在 **值** 列中，指定服务名称。</span><span class="sxs-lookup"><span data-stu-id="e91b3-114">To resume instances in bulk, in the **Field Name** column, in the empty drop-down list box next to the asterisk (**\***), select **Group Results By** and then in the **Value** column, specify the service name.</span></span>  
  
6.  <span data-ttu-id="e91b3-115">单击 **运行查询**。</span><span class="sxs-lookup"><span data-stu-id="e91b3-115">Click **Run Query**.</span></span>  
  
7.  <span data-ttu-id="e91b3-116">在查询结果列表中，右键单击你想要恢复，然后单击该业务流程实例**恢复实例**或**恢复实例**。</span><span class="sxs-lookup"><span data-stu-id="e91b3-116">In the query results list, right-click the orchestration instance you want to resume, and then click **Resume Instance** or **Resume Instances**.</span></span> <span data-ttu-id="e91b3-117">这允许你选择要恢复的实例。</span><span class="sxs-lookup"><span data-stu-id="e91b3-117">This allows you to select which instances to resume.</span></span>  
  
     <span data-ttu-id="e91b3-118">[服务实例状态](../core/service-instance-states.md)提供有关详细信息上挂起状态。</span><span class="sxs-lookup"><span data-stu-id="e91b3-118">[Service Instance States](../core/service-instance-states.md) provides more information on the on the suspended state.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e91b3-119">另请参阅</span><span class="sxs-lookup"><span data-stu-id="e91b3-119">See Also</span></span>  
 [<span data-ttu-id="e91b3-120">调查业务流程、端口和消息失败</span><span class="sxs-lookup"><span data-stu-id="e91b3-120">Investigating Orchestration, Port, and Message Failures</span></span>](../core/investigating-orchestration-port-and-message-failures.md)
