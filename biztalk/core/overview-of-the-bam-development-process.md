---
title: BAM 开发过程的概述 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 098db3f6-2a61-4cc8-88c7-2299c2e2a55e
caps.latest.revision: 14
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 4a5665e5c8b9cdf098972b6d2c82d772c5cdfee7
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65393402"
---
# <a name="overview-of-the-bam-development-process"></a><span data-ttu-id="63e26-102">BAM 开发过程概述</span><span class="sxs-lookup"><span data-stu-id="63e26-102">Overview of the BAM Development Process</span></span>
<span data-ttu-id="63e26-103">本主题介绍在开发过程的数据库和存储 BAM 数据的表。</span><span class="sxs-lookup"><span data-stu-id="63e26-103">This topic describes the development process and the database and tables that store BAM data.</span></span>  
  
## <a name="prerequisites-for-developing-with-bam"></a><span data-ttu-id="63e26-104">BAM 开发必备条件</span><span class="sxs-lookup"><span data-stu-id="63e26-104">Prerequisites for Developing with BAM</span></span>  
 <span data-ttu-id="63e26-105">在开始 BAM 开发之前，请注意以下先决条件：</span><span class="sxs-lookup"><span data-stu-id="63e26-105">Note the following prerequisites before you begin developing with BAM:</span></span>  
  
-   <span data-ttu-id="63e26-106">若要检测应用程序必须部署活动。</span><span class="sxs-lookup"><span data-stu-id="63e26-106">To instrument an application you must have an activity deployed.</span></span>  
  
-   <span data-ttu-id="63e26-107">您必须具有 SQL Server 数据库的 DBO 权限，并且是 BAM 事件写入者角色安全上下文的成员。</span><span class="sxs-lookup"><span data-stu-id="63e26-107">You must have DBO rights to the SQL Server databases and be a member of the BAM Event Writer Role security context.</span></span>  
  
-   <span data-ttu-id="63e26-108">必须使用 Microsoft.NET 4 开发应用程序。</span><span class="sxs-lookup"><span data-stu-id="63e26-108">You must use Microsoft .NET 4 to develop your application.</span></span> <span data-ttu-id="63e26-109">可以使用任何.NET 语言一样，尽管我们建议你使用C#。</span><span class="sxs-lookup"><span data-stu-id="63e26-109">You can use any .NET language, although we recommend that you use C#.</span></span>  
  
-   <span data-ttu-id="63e26-110">您必须具有在计算机上安装 Microsoft.BizTalk.BAM.EventObservation.dll。</span><span class="sxs-lookup"><span data-stu-id="63e26-110">You must have the Microsoft.BizTalk.BAM.EventObservation.dll installed on your computer.</span></span> <span data-ttu-id="63e26-111">你可以获取以下两种方式的 DLL:</span><span class="sxs-lookup"><span data-stu-id="63e26-111">You can obtain the DLL in two ways:</span></span>  
  
    -   <span data-ttu-id="63e26-112">使用 BizTalk Server 配置管理器安装 BAM 工具。</span><span class="sxs-lookup"><span data-stu-id="63e26-112">Use the BizTalk Server Configuration Manager to install the BAM tools.</span></span> <span data-ttu-id="63e26-113">我们建议使用配置管理器，因为它便于升级在注册表中将相应的条目。</span><span class="sxs-lookup"><span data-stu-id="63e26-113">We recommend that you use the Configuration Manager because it places appropriate entries in the registry that facilitate upgrades.</span></span> <span data-ttu-id="63e26-114">有关配置 BAM 的详细信息，请参阅[使用配置管理器配置 BAM 工具](http://go.microsoft.com/fwlink/?LinkId=70561)(http://go.microsoft.com/fwlink/?LinkId=70561)。</span><span class="sxs-lookup"><span data-stu-id="63e26-114">For more information about configuring BAM, see [Configuring BAM Tools Using the Configuration Manager](http://go.microsoft.com/fwlink/?LinkId=70561) (http://go.microsoft.com/fwlink/?LinkId=70561).</span></span>  
  
    -   <span data-ttu-id="63e26-115">从其在已安装的计算机复制 DLL。</span><span class="sxs-lookup"><span data-stu-id="63e26-115">Copy the DLL from a computer on which they have already been installed.</span></span> <span data-ttu-id="63e26-116">此 DLL 位于 Microsoft BizTalk Server\<版本\>\Tracking 文件夹。</span><span class="sxs-lookup"><span data-stu-id="63e26-116">The DLL resides in the Microsoft BizTalk Server \<version\>\Tracking folder.</span></span>  
  
## <a name="bam-development-process"></a><span data-ttu-id="63e26-117">BAM 开发过程</span><span class="sxs-lookup"><span data-stu-id="63e26-117">BAM Development Process</span></span>  
 <span data-ttu-id="63e26-118">下图描述了 BAM 开发流程。</span><span class="sxs-lookup"><span data-stu-id="63e26-118">The following figure describes the BAM development flow.</span></span>  
  
 <span data-ttu-id="63e26-119">![BAM 开发工作流](../core/media/dwb-bamdevelopmentflowc.gif "dwb_bamdevelopmentflowc")</span><span class="sxs-lookup"><span data-stu-id="63e26-119">![BAM development work flow](../core/media/dwb-bamdevelopmentflowc.gif "dwb_bamdevelopmentflowc")</span></span>  
  
 <span data-ttu-id="63e26-120">以下过程列出了开发 BAM 解决方案的基本步骤。</span><span class="sxs-lookup"><span data-stu-id="63e26-120">The following procedure lists the basic steps for developing a solution with BAM.</span></span>  
  
#### <a name="to-develop-a-bam-enabled-solution"></a><span data-ttu-id="63e26-121">若要开发启用了 BAM 的解决方案</span><span class="sxs-lookup"><span data-stu-id="63e26-121">To develop a BAM-enabled solution</span></span>  
  
1.  <span data-ttu-id="63e26-122">为 Excel 的 BAM 外接程序创建观察模型。</span><span class="sxs-lookup"><span data-stu-id="63e26-122">Create an observation model with the BAM Add-in for Excel.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="63e26-123">可以在 BAM API （BizTalk Server 示例） 中找到的在此过程中所述的步骤示例[ http://go.microsoft.com/fwlink/?LinkId=69968 ](http://go.microsoft.com/fwlink/?LinkId=69968)。</span><span class="sxs-lookup"><span data-stu-id="63e26-123">Examples of the steps noted in this procedure can be found in the BAM API (BizTalk Server sample) at [http://go.microsoft.com/fwlink/?LinkId=69968](http://go.microsoft.com/fwlink/?LinkId=69968).</span></span>  
  
2.  <span data-ttu-id="63e26-124">使用 BAM 管理实用程序将活动部署到 PID。</span><span class="sxs-lookup"><span data-stu-id="63e26-124">Use the BAM Management utility to deploy the activity to the PID.</span></span>  
  
3.  <span data-ttu-id="63e26-125">通过添加 BAM EventStream 代码来检测应用程序。</span><span class="sxs-lookup"><span data-stu-id="63e26-125">Instrument the application by adding your BAM EventStream code.</span></span>  
  
4.  <span data-ttu-id="63e26-126">运行应用程序。</span><span class="sxs-lookup"><span data-stu-id="63e26-126">Run the application.</span></span> <span data-ttu-id="63e26-127">当执行此操作时，代码将：</span><span class="sxs-lookup"><span data-stu-id="63e26-127">When you do this, the code will:</span></span>  
  
    -   <span data-ttu-id="63e26-128">将占位符记录添加到 BAM_\<*活动名称*\>_Active 表。</span><span class="sxs-lookup"><span data-stu-id="63e26-128">Add a placeholder record to the BAM_\<*activity name*\>_Active table.</span></span>  
  
    -   <span data-ttu-id="63e26-129">更新记录中的数据项目。</span><span class="sxs-lookup"><span data-stu-id="63e26-129">Update the data items in the record.</span></span>  
  
    -   <span data-ttu-id="63e26-130">结束活动并将该记录移到 BAM_\<\* 活动名称 \* \*\>_completed 表。</span><span class="sxs-lookup"><span data-stu-id="63e26-130">End the activity and move the record to the BAM_\<\*activity name\*\*\>_completed table.</span></span>  
  
## <a name="where-bam-data-is-stored"></a><span data-ttu-id="63e26-131">BAM 数据的存储位置</span><span class="sxs-lookup"><span data-stu-id="63e26-131">Where BAM Data Is Stored</span></span>  
 <span data-ttu-id="63e26-132">BAM 提供 EventObservation 命名空间，其中包含用于处理 BAM 事件的 EventStream 类。</span><span class="sxs-lookup"><span data-stu-id="63e26-132">BAM provides the EventObservation namespace that contains the EventStream classes that are used to handle BAM events.</span></span>  
  
 <span data-ttu-id="63e26-133">BAM 跟踪数据存储在 BAM 主导入数据库 (PID)。</span><span class="sxs-lookup"><span data-stu-id="63e26-133">BAM tracking data is stored in the BAM Primary Import database (PID).</span></span> <span data-ttu-id="63e26-134">部署观察模型使用 BAM 管理实用程序时，PID 中创建以下五个表。</span><span class="sxs-lookup"><span data-stu-id="63e26-134">When you deploy an observation model using the BAM Management utility, the following five tables are created in the PID.</span></span>  
  
|<span data-ttu-id="63e26-135">“属性”</span><span class="sxs-lookup"><span data-stu-id="63e26-135">Name</span></span>|<span data-ttu-id="63e26-136">Description</span><span class="sxs-lookup"><span data-stu-id="63e26-136">Description</span></span>|  
|----------|-----------------|  
|<span data-ttu-id="63e26-137">活动表</span><span class="sxs-lookup"><span data-stu-id="63e26-137">Active table</span></span>|<span data-ttu-id="63e26-138">名为 bam_\<*活动名称*\>_Active，此表用于存储尚未完成此类型的活动。</span><span class="sxs-lookup"><span data-stu-id="63e26-138">Named bam_\<*activity name*\>_Active, this table holds the activities of this type that have not yet completed.</span></span>|  
|<span data-ttu-id="63e26-139">活动关系表</span><span class="sxs-lookup"><span data-stu-id="63e26-139">Active relationships table</span></span>|<span data-ttu-id="63e26-140">名为 bam_\<*活动名称*\>_ActiveRelationships，此表包含尚未完成的活动的相关的活动。</span><span class="sxs-lookup"><span data-stu-id="63e26-140">Named bam_\<*activity name*\>_ActiveRelationships, this table contains the related activities for the activity that have not yet completed.</span></span>|  
|<span data-ttu-id="63e26-141">继续符表</span><span class="sxs-lookup"><span data-stu-id="63e26-141">Continuations table</span></span>|<span data-ttu-id="63e26-142">名为 bam_\<*活动名称*\>_continuations，此表列出了活动的继续符活动。</span><span class="sxs-lookup"><span data-stu-id="63e26-142">Named bam_\<*activity name*\>_continuations, this table lists the continuations activities for the activity.</span></span>|  
|<span data-ttu-id="63e26-143">已完成的表</span><span class="sxs-lookup"><span data-stu-id="63e26-143">Completed table</span></span>|<span data-ttu-id="63e26-144">名为 bam_\<*活动名称*\>_completed。</span><span class="sxs-lookup"><span data-stu-id="63e26-144">Named bam_\<*activity name*\>_completed.</span></span>|  
|<span data-ttu-id="63e26-145">已完成的关系表</span><span class="sxs-lookup"><span data-stu-id="63e26-145">Completed Relationships table</span></span>|<span data-ttu-id="63e26-146">名为 bam_\<*活动名称*\>_CompletedRelationships，此表包含的活动已完成的相关的活动。</span><span class="sxs-lookup"><span data-stu-id="63e26-146">Named bam_\<*activity name*\>_CompletedRelationships, this table contains the completed related activities for the activity.</span></span>|  
  
 <span data-ttu-id="63e26-147">捕获 BAM 活动中的数据的四种类型：</span><span class="sxs-lookup"><span data-stu-id="63e26-147">You capture four types of data in a BAM activity:</span></span>  
  
-   <span data-ttu-id="63e26-148">String</span><span class="sxs-lookup"><span data-stu-id="63e26-148">String</span></span>  
  
-   <span data-ttu-id="63e26-149">日期/时间 （通常称为里程碑）</span><span class="sxs-lookup"><span data-stu-id="63e26-149">Data/Time (commonly referred to as milestones)</span></span>  
  
-   <span data-ttu-id="63e26-150">Integer</span><span class="sxs-lookup"><span data-stu-id="63e26-150">Integer</span></span>  
  
-   <span data-ttu-id="63e26-151">float</span><span class="sxs-lookup"><span data-stu-id="63e26-151">Float</span></span>