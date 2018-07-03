---
title: 使用跟踪活动定义文件 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- tracking, activity definition file
- activity definition file
- activity definition file, about activity definition file
- tracking, managing views
- activity definition file, activity fields
ms.assetid: 0592a844-aad7-4054-b1e7-344f1086f0b1
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 0be795daa7e08707c113d8230dc8d324bc71f951
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36991910"
---
# <a name="working-with-the-tracking-activity-definition-file"></a><span data-ttu-id="143d7-102">使用跟踪活动定义文件</span><span class="sxs-lookup"><span data-stu-id="143d7-102">Working with the Tracking Activity Definition File</span></span>
<span data-ttu-id="143d7-103">活动定义文件包含有关跟踪的信息在 Microsoft® 流程和消息活动[!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="143d7-103">The activity definition file contains information about the tracking process and message activities in Microsoft® [!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)].</span></span> [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]<span data-ttu-id="143d7-104"> 使用此文件来管理数据跟踪在 BizTalk 业务活动监视 (BAM)。</span><span class="sxs-lookup"><span data-stu-id="143d7-104"> uses this file to manage data tracking in BizTalk Business Activity Monitoring (BAM).</span></span> <span data-ttu-id="143d7-105">定义文件是一个 XML 文件 (Tracking.xml)，[!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)]安装程序将安装\<*驱动器*\>: files\microsoft BizTalk 2013 Accelerator for RosettaNet \BAMTracking 文件夹。</span><span class="sxs-lookup"><span data-stu-id="143d7-105">The definition file is an XML file (Tracking.xml) that [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] setup installs in the \<*drive*\>:\Program Files\Microsoft BizTalk 2013 Accelerator for RosettaNet \BAMTracking folder.</span></span> <span data-ttu-id="143d7-106">Tracking.xml 中定义的活动可能足以满足你的需要。</span><span class="sxs-lookup"><span data-stu-id="143d7-106">The activities defined in Tracking.xml may be sufficient for your purposes.</span></span>  
  
 <span data-ttu-id="143d7-107">有关跟踪活动、 视图和表的详细信息，请参阅[增强跟踪](../../adapters-and-accelerators/accelerator-rosettanet/enhanced-tracking.md)。</span><span class="sxs-lookup"><span data-stu-id="143d7-107">For more information about the tracking activities, views, and tables, see [Enhanced Tracking](../../adapters-and-accelerators/accelerator-rosettanet/enhanced-tracking.md).</span></span> <span data-ttu-id="143d7-108">有关 BAM 的详细信息，请参阅"业务活动监视 (BAM)"BizTalk Server 帮助中。</span><span class="sxs-lookup"><span data-stu-id="143d7-108">For more information about BAM, see "Business Activity Monitoring (BAM)" in BizTalk Server Help.</span></span>  
  
## <a name="managing-tracking-views"></a><span data-ttu-id="143d7-109">管理跟踪视图</span><span class="sxs-lookup"><span data-stu-id="143d7-109">Managing Tracking Views</span></span>  
 <span data-ttu-id="143d7-110">不使用与 BizTalk 跟踪配置文件编辑器[!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)]跟踪。</span><span class="sxs-lookup"><span data-stu-id="143d7-110">You do not use the BizTalk Tracking Profile Editor with [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] tracking.</span></span> <span data-ttu-id="143d7-111">跟踪点无法自定义；不要更改活动定义。</span><span class="sxs-lookup"><span data-stu-id="143d7-111">The tracking points are not customizable; do not change activity definitions.</span></span> <span data-ttu-id="143d7-112">但是，你可以管理 BAM 视图和部署。</span><span class="sxs-lookup"><span data-stu-id="143d7-112">However, you can manage BAM views and deployment.</span></span> <span data-ttu-id="143d7-113">若要执行此操作，你修改[!INCLUDE[btsExcel](../../includes/btsexcel-md.md)]电子表格 (Tracking.xls)，[!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)]安装程序将安装\<*驱动器*\>: \Program Files\Microsoft BizTalk 2013 Accelerator for RosettaNet\BAMTracking 文件夹。</span><span class="sxs-lookup"><span data-stu-id="143d7-113">To do so, you modify an [!INCLUDE[btsExcel](../../includes/btsexcel-md.md)] spreadsheet (Tracking.xls) that [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] setup installs in the \<*drive*\>:\Program Files\Microsoft BizTalk 2013 Accelerator for RosettaNet\BAMTracking folder.</span></span> <span data-ttu-id="143d7-114">有关详细信息，请参阅下述“管理跟踪视图”。</span><span class="sxs-lookup"><span data-stu-id="143d7-114">For more information, see "Managing Tracking Views" below.</span></span>  
  
 <span data-ttu-id="143d7-115">如果 Tracking.xml 中定义的视图不能够满足你的需要，你可以按下述方法为 BAM 中跟踪的信息定义其他视图。</span><span class="sxs-lookup"><span data-stu-id="143d7-115">If the views defined in Tracking.xml are not sufficient for your needs, you can define different views of the information tracked in BAM as follows.</span></span>  
  
#### <a name="to-create-different-tracking-views"></a><span data-ttu-id="143d7-116">创建其他跟踪视图</span><span class="sxs-lookup"><span data-stu-id="143d7-116">To create different tracking views</span></span>  
  
1. <span data-ttu-id="143d7-117">单击 **“启动”**，再单击 **“运行”**。</span><span class="sxs-lookup"><span data-stu-id="143d7-117">Click **Start**, and then click **Run**.</span></span> <span data-ttu-id="143d7-118">输入**cmd**的运行对话框，然后单击打开的文本框中**确定**。</span><span class="sxs-lookup"><span data-stu-id="143d7-118">Enter **cmd** in the Open text box of the Run dialog box, and then click **OK**.</span></span> <span data-ttu-id="143d7-119">在命令行对话框中，输入以下代码取消部署 tracking.xml，然后单击**确定**:</span><span class="sxs-lookup"><span data-stu-id="143d7-119">In the command line dialog box, enter the following code to undeploy tracking.xml, then click **OK**:</span></span>  
  
   ```  
   cd %ProgramFiles%\Microsoft BizTalk Server 2013\Tracking  
   bm remove-all  -DefinitionFile:"%ProgramFiles%\Microsoft BizTalk 2013 Accelerator for RosettaNet\BAMTracking\<filename\>.xml"  
   ```  
  
2. <span data-ttu-id="143d7-120">在中[!INCLUDE[btsWinNoVersion](../../includes/btswinnoversion-md.md)]资源管理器，转到*\<驱动器\>*: \Program Files\Microsoft BizTalk 2013 Accelerator for RosettaNet \BAM 跟踪。</span><span class="sxs-lookup"><span data-stu-id="143d7-120">In [!INCLUDE[btsWinNoVersion](../../includes/btswinnoversion-md.md)] Explorer, move to *\<drive\>*:\Program Files\Microsoft BizTalk 2013 Accelerator for RosettaNet \BAM Tracking.</span></span> <span data-ttu-id="143d7-121">双击 Tracking.xls。</span><span class="sxs-lookup"><span data-stu-id="143d7-121">Double-click Tracking.xls.</span></span>  
  
3. <span data-ttu-id="143d7-122">在业务活动监视中创建新视图。</span><span class="sxs-lookup"><span data-stu-id="143d7-122">Create a new view in Business Activity Monitoring.</span></span> <span data-ttu-id="143d7-123">有关如何执行此操作的信息，请参阅"管理业务活动监视"BizTalk Server 帮助中。</span><span class="sxs-lookup"><span data-stu-id="143d7-123">For information about how to do so, see "Managing Business Activity Monitoring" in BizTalk Server Help.</span></span>  
  
4. <span data-ttu-id="143d7-124">单击**BAM**，然后单击**导出到 XML**。</span><span class="sxs-lookup"><span data-stu-id="143d7-124">Click **BAM**, and then click **Export XML**.</span></span> <span data-ttu-id="143d7-125">将移动到所需的位置，输入文件的名称 （不能是 Tracking.xml)，并单击**保存**。</span><span class="sxs-lookup"><span data-stu-id="143d7-125">Move to the desired location, enter a file name (other than Tracking.xml), and then click **Save**.</span></span>  
  
   > [!IMPORTANT]
   >  <span data-ttu-id="143d7-126">当你在跟踪 XLS 文件中定义新的跟踪视图并从该跟踪 XLS 文件导出 XML 文件时，某些新字段名可能会稍做修改。</span><span class="sxs-lookup"><span data-stu-id="143d7-126">When you define new tracking views in a tracking XLS file, and export an XML file from the tracking XLS file, some of the new field names may be slightly modified.</span></span> <span data-ttu-id="143d7-127">将你的自定义跟踪 XML 文件中的字段与 BTARN 安装程序所安装的标准 tracking.xml 字段进行查验，更正此问题。</span><span class="sxs-lookup"><span data-stu-id="143d7-127">Correct this by verifying the fields in your customized tracking XML file against the standard tracking.xml field installed by BTARN setup.</span></span>  
  
5. <span data-ttu-id="143d7-128">部署新的跟踪 XML 文件。</span><span class="sxs-lookup"><span data-stu-id="143d7-128">Deploy the new tracking XML file.</span></span> <span data-ttu-id="143d7-129">若要执行此操作，请单击**启动**，然后单击**运行**。</span><span class="sxs-lookup"><span data-stu-id="143d7-129">To do so, click **Start**, and then click **Run**.</span></span> <span data-ttu-id="143d7-130">输入**cmd**的运行对话框，然后单击打开的文本框中**确定**。</span><span class="sxs-lookup"><span data-stu-id="143d7-130">Enter **cmd** in the Open text box of the Run dialog box, and then click **OK**.</span></span> <span data-ttu-id="143d7-131">在命令行对话框中，输入以下代码以部署新的跟踪文件，然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="143d7-131">In the command line dialog box, enter the following code to deploy your new tracking file, then click **OK**.</span></span> <span data-ttu-id="143d7-132">建议重命名跟踪 XML 文件，以便不会覆盖默认的 tracking.xml 文件。</span><span class="sxs-lookup"><span data-stu-id="143d7-132">It is recommended that you rename the tracking XML file so that you do not overwrite the default tracking.xml file.</span></span>  
  
   ```  
   cd %ProgramFiles%\Microsoft BizTalk Server 2013\Tracking  
   bm.exe deploy-all -DefinitionFile:"%ProgramFiles%\Microsoft BizTalk 2030 Accelerator for RosettaNet\BAMTracking\<filename\>.xml"  
   ```  
  
   <span data-ttu-id="143d7-133">在 BAM 中跟踪的信息不包括消息内容，因为存储在[!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)]数据库。</span><span class="sxs-lookup"><span data-stu-id="143d7-133">The information tracked in BAM does not include the message content, because that is stored in a [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] database.</span></span>  
  
   <span data-ttu-id="143d7-134">可以使用业务活动监视管理实用工具管理 BAM 跟踪的部署。</span><span class="sxs-lookup"><span data-stu-id="143d7-134">You can manage deployment of BAM tracking by using the Business Activity Monitoring Management Utility.</span></span> <span data-ttu-id="143d7-135">有关此实用工具的详细信息，请参阅"使用业务活动监视管理实用工具"BizTalk Server 帮助中。</span><span class="sxs-lookup"><span data-stu-id="143d7-135">For more information about this utility, see "Using the Business Activity Monitoring Management Utility" in BizTalk Server Help.</span></span>  
  
## <a name="activity-fields"></a><span data-ttu-id="143d7-136">活动字段</span><span class="sxs-lookup"><span data-stu-id="143d7-136">Activity Fields</span></span>  
 <span data-ttu-id="143d7-137">以下是活动定义文件中消息活动的字段：</span><span class="sxs-lookup"><span data-stu-id="143d7-137">The fields of the message activity in the activity definition file are the following:</span></span>  
  
- <span data-ttu-id="143d7-138">ActivityName</span><span class="sxs-lookup"><span data-stu-id="143d7-138">ActivityName</span></span>  
  
- <span data-ttu-id="143d7-139">类别</span><span class="sxs-lookup"><span data-stu-id="143d7-139">Category</span></span>  
  
- <span data-ttu-id="143d7-140">ContentKey</span><span class="sxs-lookup"><span data-stu-id="143d7-140">ContentKey</span></span>  
  
- <span data-ttu-id="143d7-141">DestinationPartyName</span><span class="sxs-lookup"><span data-stu-id="143d7-141">DestinationPartyName</span></span>  
  
- <span data-ttu-id="143d7-142">ErrorDescription</span><span class="sxs-lookup"><span data-stu-id="143d7-142">ErrorDescription</span></span>  
  
- <span data-ttu-id="143d7-143">HasError</span><span class="sxs-lookup"><span data-stu-id="143d7-143">HasError</span></span>  
  
- <span data-ttu-id="143d7-144">InReplyToMessageID</span><span class="sxs-lookup"><span data-stu-id="143d7-144">InReplyToMessageID</span></span>  
  
- <span data-ttu-id="143d7-145">IsReceived</span><span class="sxs-lookup"><span data-stu-id="143d7-145">IsReceived</span></span>  
  
- <span data-ttu-id="143d7-146">MessageTrackingID</span><span class="sxs-lookup"><span data-stu-id="143d7-146">MessageTrackingID</span></span>  
  
- <span data-ttu-id="143d7-147">NoFPipInstance</span><span class="sxs-lookup"><span data-stu-id="143d7-147">NoFPipInstance</span></span>  
  
- <span data-ttu-id="143d7-148">PipCode</span><span class="sxs-lookup"><span data-stu-id="143d7-148">PipCode</span></span>  
  
- <span data-ttu-id="143d7-149">PipInstanceID</span><span class="sxs-lookup"><span data-stu-id="143d7-149">PipInstanceID</span></span>  
  
- <span data-ttu-id="143d7-150">PiPVersion</span><span class="sxs-lookup"><span data-stu-id="143d7-150">PiPVersion</span></span>  
  
- <span data-ttu-id="143d7-151">SourcePartName</span><span class="sxs-lookup"><span data-stu-id="143d7-151">SourcePartName</span></span>  
  
- <span data-ttu-id="143d7-152">时间戳</span><span class="sxs-lookup"><span data-stu-id="143d7-152">Timestamp</span></span>  
  
  <span data-ttu-id="143d7-153">以下是活动定义文件中流程活动的字段：</span><span class="sxs-lookup"><span data-stu-id="143d7-153">The fields of the process activity in the activity definition file are the following:</span></span>  
  
- <span data-ttu-id="143d7-154">EndTime</span><span class="sxs-lookup"><span data-stu-id="143d7-154">EndTime</span></span>  
  
- <span data-ttu-id="143d7-155">InitiatorPartyName</span><span class="sxs-lookup"><span data-stu-id="143d7-155">InitiatorPartyName</span></span>  
  
- <span data-ttu-id="143d7-156">IsInitiatorRole</span><span class="sxs-lookup"><span data-stu-id="143d7-156">IsInitiatorRole</span></span>  
  
- <span data-ttu-id="143d7-157">PipCode</span><span class="sxs-lookup"><span data-stu-id="143d7-157">PipCode</span></span>  
  
- <span data-ttu-id="143d7-158">PipInstanceID</span><span class="sxs-lookup"><span data-stu-id="143d7-158">PipInstanceID</span></span>  
  
- <span data-ttu-id="143d7-159">PipName</span><span class="sxs-lookup"><span data-stu-id="143d7-159">PipName</span></span>  
  
- <span data-ttu-id="143d7-160">PipVersion</span><span class="sxs-lookup"><span data-stu-id="143d7-160">PipVersion</span></span>  
  
- <span data-ttu-id="143d7-161">ResponderPartyName</span><span class="sxs-lookup"><span data-stu-id="143d7-161">ResponderPartyName</span></span>  
  
- <span data-ttu-id="143d7-162">StartTime</span><span class="sxs-lookup"><span data-stu-id="143d7-162">StartTime</span></span>  
  
- <span data-ttu-id="143d7-163">“登录属性”</span><span class="sxs-lookup"><span data-stu-id="143d7-163">Status</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="143d7-164">请参阅</span><span class="sxs-lookup"><span data-stu-id="143d7-164">See Also</span></span>  
 <span data-ttu-id="143d7-165">[增强的跟踪](../../adapters-and-accelerators/accelerator-rosettanet/enhanced-tracking.md) </span><span class="sxs-lookup"><span data-stu-id="143d7-165">[Enhanced Tracking](../../adapters-and-accelerators/accelerator-rosettanet/enhanced-tracking.md) </span></span>  
 [<span data-ttu-id="143d7-166">管理配置、证书、数据库和安全性</span><span class="sxs-lookup"><span data-stu-id="143d7-166">Manage configuration, certificates, databases, and security</span></span>](manage-configuration-certificates-databases-security.md)