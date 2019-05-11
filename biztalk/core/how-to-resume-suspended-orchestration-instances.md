---
title: 如何恢复挂起的业务流程实例 |Microsoft Docs
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
ms.openlocfilehash: 9e5e712f0ec845c4f895833908954711cdce0698
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65334907"
---
# <a name="how-to-resume-suspended-orchestration-instances"></a><span data-ttu-id="63119-102">如何恢复挂起的业务流程实例</span><span class="sxs-lookup"><span data-stu-id="63119-102">How to Resume Suspended Orchestration Instances</span></span>
<span data-ttu-id="63119-103">如果你已挂起被列为"可恢复挂起"的业务流程实例，可以尝试恢复该业务流程实例从查询结果或预览窗格。</span><span class="sxs-lookup"><span data-stu-id="63119-103">If you have suspended orchestration instances that are listed as "suspended resumable," you can attempt to resume the orchestration instance from the query results or preview pane.</span></span> <span data-ttu-id="63119-104">如果导致业务流程实例挂起的根本问题也得到解决，才会成功恢复业务流程实例。</span><span class="sxs-lookup"><span data-stu-id="63119-104">Resuming the orchestration instance will only succeed if the underlying problem that caused the orchestration instance to become suspended has also been fixed.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="63119-105">先决条件</span><span class="sxs-lookup"><span data-stu-id="63119-105">Prerequisites</span></span>  
 <span data-ttu-id="63119-106">您必须为要执行此过程的 BizTalk Server Operators 组的成员身份登录。</span><span class="sxs-lookup"><span data-stu-id="63119-106">You must be logged on as a member of the BizTalk Server Operators group to perform this procedure.</span></span>  
  
### <a name="to-resume-suspended-orchestration-instances"></a><span data-ttu-id="63119-107">若要恢复挂起的业务流程实例</span><span class="sxs-lookup"><span data-stu-id="63119-107">To resume suspended orchestration instances</span></span>  
  
1. <span data-ttu-id="63119-108">单击**启动**，单击**程序**，单击[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]，然后单击**BizTalk Server 管理**。</span><span class="sxs-lookup"><span data-stu-id="63119-108">Click **Start**, click **Programs**, click [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)], and then click **BizTalk Server Administration**.</span></span>  
  
2. <span data-ttu-id="63119-109">在控制台树中，展开**BizTalk Server 管理**，然后单击 BizTalk 组。</span><span class="sxs-lookup"><span data-stu-id="63119-109">In the console tree, expand **BizTalk Server Administration**, and then click the BizTalk group.</span></span>  
  
3. <span data-ttu-id="63119-110">在详细信息窗格中，单击**新查询**选项卡。</span><span class="sxs-lookup"><span data-stu-id="63119-110">In the details pane, click the **New Query** tab.</span></span>  
  
4. <span data-ttu-id="63119-111">在中**查询表达式**组中，在**值**列中，选择**挂起服务实例**从下拉列表框。</span><span class="sxs-lookup"><span data-stu-id="63119-111">In the **Query Expression** group, in the **Value** column, select **Suspended Service Instances** from the drop-down list box.</span></span>  
  
5. <span data-ttu-id="63119-112">执行以下操作之一：</span><span class="sxs-lookup"><span data-stu-id="63119-112">Do one of the following:</span></span>  
  
   - <span data-ttu-id="63119-113">若要恢复单个实例，在**字段名**列，星号旁边的空下拉列表框中 (**\\**<em>)，选择 \**服务名称</em>* 筛选器，然后在**值**列中，指定服务名称。</span><span class="sxs-lookup"><span data-stu-id="63119-113">To resume a single instance, in the **Field Name** column, in the empty drop-down list box next to the asterisk (**\\**<em>), select the \**Service Name</em>* filter and then in the **Value** column, specify the service name.</span></span>  
  
   - <span data-ttu-id="63119-114">若要恢复实例，请在**字段名**列，星号旁边的空下拉列表框中 (**\\**<em>)，选择 \**结果分组依据</em>* ，然后在**值**列中，指定服务名称。</span><span class="sxs-lookup"><span data-stu-id="63119-114">To resume instances in bulk, in the **Field Name** column, in the empty drop-down list box next to the asterisk (**\\**<em>), select \**Group Results By</em>* and then in the **Value** column, specify the service name.</span></span>  
  
6. <span data-ttu-id="63119-115">单击**运行查询**。</span><span class="sxs-lookup"><span data-stu-id="63119-115">Click **Run Query**.</span></span>  
  
7. <span data-ttu-id="63119-116">在查询结果列表中，右键单击你想要继续，然后单击该业务流程实例**恢复实例**或**恢复实例**。</span><span class="sxs-lookup"><span data-stu-id="63119-116">In the query results list, right-click the orchestration instance you want to resume, and then click **Resume Instance** or **Resume Instances**.</span></span> <span data-ttu-id="63119-117">这允许您选择要恢复哪些实例。</span><span class="sxs-lookup"><span data-stu-id="63119-117">This allows you to select which instances to resume.</span></span>  
  
    <span data-ttu-id="63119-118">[服务实例状态](../core/service-instance-states.md)上提供了详细信息上挂起状态。</span><span class="sxs-lookup"><span data-stu-id="63119-118">[Service Instance States](../core/service-instance-states.md) provides more information on the on the suspended state.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="63119-119">请参阅</span><span class="sxs-lookup"><span data-stu-id="63119-119">See Also</span></span>  
 [<span data-ttu-id="63119-120">调查业务流程、端口和消息失败</span><span class="sxs-lookup"><span data-stu-id="63119-120">Investigating Orchestration, Port, and Message Failures</span></span>](../core/investigating-orchestration-port-and-message-failures.md)
