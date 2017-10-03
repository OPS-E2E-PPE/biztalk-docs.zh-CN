---
title: "导入或导出 BizTalk 设置使用设置仪表板 |Microsoft 文档"
description: "使用 BizTalk Server 管理导入或导出 BizTalk Server 环境之间的设置"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: cc2f0b44-d79b-4f95-811a-0843e3d6d1c8
caps.latest.revision: "11"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 5e33b8659701ab991f7b7467c8ab3edd8b79def4
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="use-settings-dashboard-to-import-or-export-biztalk-settings"></a><span data-ttu-id="91d1f-103">使用设置仪表板来导入或导出 BizTalk 设置</span><span class="sxs-lookup"><span data-stu-id="91d1f-103">Use Settings Dashboard to import or export BizTalk Settings</span></span> 

## <a name="overview"></a><span data-ttu-id="91d1f-104">概述</span><span class="sxs-lookup"><span data-stu-id="91d1f-104">Overview</span></span>
<span data-ttu-id="91d1f-105">使用“BizTalk 设置仪表板”，您可以从 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 环境导出设置，然后将其导入到另一 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 环境，从而减少整个解决方案的时间。 </span><span class="sxs-lookup"><span data-stu-id="91d1f-105">Using the BizTalk Settings Dashboard, you can export the settings from a [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] environment and import them to another [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] environment, thereby reducing the overall time-to-solution.</span></span> <span data-ttu-id="91d1f-106">这在以下情况时尤为有用：当 BizTalk 管理员尝试在临时环境中调整 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 性能，一旦达到预期结果，他们就会将设置导入生产环境。</span><span class="sxs-lookup"><span data-stu-id="91d1f-106">This is especially useful in scenarios where the administrators try to tune [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] performance in a staging environment, and upon achieving the desired results, they can import the settings into a production environment.</span></span> <span data-ttu-id="91d1f-107">本主题提供了使用设置仪表板导入 BizTalk 组、主机和的主机实例设置的分步过程。</span><span class="sxs-lookup"><span data-stu-id="91d1f-107">This topic provides step-by-step procedure to import the BizTalk Group, Host, and Host Instance settings using Settings Dashboard.</span></span>  

> [!TIP]
> <span data-ttu-id="91d1f-108">BTSTask 命令行实用工具还可用来导入或导出的组、 主机和主机实例的设置。</span><span class="sxs-lookup"><span data-stu-id="91d1f-108">The BTSTask command-line utility can also be used to import or export the Group, Host, and Host Instance settings.</span></span> <span data-ttu-id="91d1f-109">请参阅[导入或导出 BizTalk 设置使用 BTSTask](how-to-import-biztalk-settings-using-btstask.md)。</span><span class="sxs-lookup"><span data-stu-id="91d1f-109">See [Import or export BizTalk Settings Using BTSTask](how-to-import-biztalk-settings-using-btstask.md).</span></span>

  
## <a name="prerequisites"></a><span data-ttu-id="91d1f-110">先决条件</span><span class="sxs-lookup"><span data-stu-id="91d1f-110">Prerequisites</span></span>  
 <span data-ttu-id="91d1f-111">若要执行此操作，你必须作为 BizTalk Server Administrators 组的成员身份登录。</span><span class="sxs-lookup"><span data-stu-id="91d1f-111">To perform this operation, you must be signed in as a member of the BizTalk Server Administrators group.</span></span>  
  
## <a name="import-the-biztalk-group-host-and-host-instance-settings"></a><span data-ttu-id="91d1f-112">导入 BizTalk 组、 主机和主机实例设置</span><span class="sxs-lookup"><span data-stu-id="91d1f-112">Import the BizTalk group, host, and host instance settings</span></span>  

> [!IMPORTANT]
>  <span data-ttu-id="91d1f-113">若要从某个环境导入 BizTalk Server 设置，您应已保存这些设置并将它们导出到 XML 文件中。</span><span class="sxs-lookup"><span data-stu-id="91d1f-113">To import the BizTalk Server settings from a certain environment, you should have already saved and exported those settings in an XML file.</span></span> <span data-ttu-id="91d1f-114">**导出 BizTalk 设置**（本主题中） 或[导入或导出 BizTalk 设置使用 BTSTask](how-to-import-biztalk-settings-using-btstask.md)可以帮助。</span><span class="sxs-lookup"><span data-stu-id="91d1f-114">**Export BizTalk Settings** (in this topic) or [Import or export BizTalk Settings Using BTSTask](how-to-import-biztalk-settings-using-btstask.md) can help.</span></span>
  
 <span data-ttu-id="91d1f-115">通过导入到 XML 文件，您可以在目标计算机上复制所需的 BizTalk Server 设置。</span><span class="sxs-lookup"><span data-stu-id="91d1f-115">By importing the XML file, you can replicate the required BizTalk Server settings on the target machine.</span></span> <span data-ttu-id="91d1f-116">使用设置仪表板，您可以导入组、主机和主机实例设置，并将一个设置的属性映射到另一个设置的属性。</span><span class="sxs-lookup"><span data-stu-id="91d1f-116">Using the Settings dashboard, you can import the Group, Host, and Host Instance settings and map the properties of one to another.</span></span> <span data-ttu-id="91d1f-117">以下是有关导入设置的必要假设：</span><span class="sxs-lookup"><span data-stu-id="91d1f-117">Following are the necessary assumptions for importing the settings:</span></span>  
  
-   <span data-ttu-id="91d1f-118">BizTalk Server 拓扑从源环境到目标环境是一致的。</span><span class="sxs-lookup"><span data-stu-id="91d1f-118">The BizTalk Server topology is consistent from the source environment to the destination environment.</span></span>  
  
-   <span data-ttu-id="91d1f-119">可以映射源和目标环境的主机定义。</span><span class="sxs-lookup"><span data-stu-id="91d1f-119">The host definitions across source and destination environments can be mapped.</span></span> <span data-ttu-id="91d1f-120">您应该能够使用目标环境中的主机映射源环境中的全部主机。</span><span class="sxs-lookup"><span data-stu-id="91d1f-120">You should be able to map all hosts in the source environment with those in the destination environment.</span></span>  
  
-   <span data-ttu-id="91d1f-121">目标环境具有与源环境相似的硬件（即使不完全相同）。</span><span class="sxs-lookup"><span data-stu-id="91d1f-121">The destination environment has hardware similar (if not identical) to the source environment.</span></span> <span data-ttu-id="91d1f-122">因为某些设置取决于基础硬件，所以这很重要。</span><span class="sxs-lookup"><span data-stu-id="91d1f-122">This is essential as some of the settings depend on the underlying hardware.</span></span>  

### <a name="import-steps"></a><span data-ttu-id="91d1f-123">导入步骤</span><span class="sxs-lookup"><span data-stu-id="91d1f-123">Import steps</span></span>
  
1.  <span data-ttu-id="91d1f-124">在**BizTalk Server 管理控制台**，展开[!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)]，右键单击**BizTalk 组**，然后单击**设置**。</span><span class="sxs-lookup"><span data-stu-id="91d1f-124">In the **BizTalk Server Administration Console**, expand [!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)], right-click **BizTalk Group**, and then click **Settings**.</span></span>  
  
2.  <span data-ttu-id="91d1f-125">在**BizTalk 设置仪表板**对话框中，单击**导入**。</span><span class="sxs-lookup"><span data-stu-id="91d1f-125">In the **BizTalk Settings Dashboard** dialog box, click **Import**.</span></span> <span data-ttu-id="91d1f-126">**导入设置向导**对话框随即出现。</span><span class="sxs-lookup"><span data-stu-id="91d1f-126">The **Import Settings Wizard** dialog box appears.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="91d1f-127">**目标组**显示你想要导入设置目标计算机的组信息。</span><span class="sxs-lookup"><span data-stu-id="91d1f-127">The **Destination Group** displays the group information of the target machine where you want to import the settings.</span></span>  
  
     <span data-ttu-id="91d1f-128">![指定要导入设置的文件位置](../core/media/importsettings-filelocation.jpg "ImportSettings_FileLocation")</span><span class="sxs-lookup"><span data-stu-id="91d1f-128">![Specify the file location to import settings](../core/media/importsettings-filelocation.jpg "ImportSettings_FileLocation")</span></span>  
  
3.  <span data-ttu-id="91d1f-129">单击**指定文件位置**页，，然后单击![浏览设置文件](../core/media/importsettings-filelocationbrowse.gif "ImportSettings_FileLocationBrowse")。</span><span class="sxs-lookup"><span data-stu-id="91d1f-129">Click the **Specify File Location** page, and then click ![Browse the settings file](../core/media/importsettings-filelocationbrowse.gif "ImportSettings_FileLocationBrowse").</span></span> <span data-ttu-id="91d1f-130">此时会出现文件资源管理器。</span><span class="sxs-lookup"><span data-stu-id="91d1f-130">The file explorer appears.</span></span>  
  
4.  <span data-ttu-id="91d1f-131">选择包含源环境设置的 XML 文件，然后单击**打开**。</span><span class="sxs-lookup"><span data-stu-id="91d1f-131">Select the XML file containing the source environment settings, and then click **Open**.</span></span> <span data-ttu-id="91d1f-132">**文件位置**显示 XML 文件的路径和**源组**填入源计算机的组信息。</span><span class="sxs-lookup"><span data-stu-id="91d1f-132">The **File Location** displays the path of the XML file and the **Source Group** is populated with the group information of the source machine.</span></span> <span data-ttu-id="91d1f-133">单击 **“下一步”**。</span><span class="sxs-lookup"><span data-stu-id="91d1f-133">Click **Next**.</span></span>  
  
5.  <span data-ttu-id="91d1f-134">上**主机映射**页上，执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="91d1f-134">On the **Host Mapping** page, do the following:</span></span>  
  
    1.  <span data-ttu-id="91d1f-135">从**目标主机**列表中，选择你想要指定源主机，然后单击目标主机**添加**。</span><span class="sxs-lookup"><span data-stu-id="91d1f-135">From the **Destination Hosts** list, select a destination host for which you want to specify the source host, and then click **Add**.</span></span>  
  
         <span data-ttu-id="91d1f-136">![承载映射](../core/media/importsettings-hostmapping.gif "ImportSettings_HostMapping")</span><span class="sxs-lookup"><span data-stu-id="91d1f-136">![Host Mapping](../core/media/importsettings-hostmapping.gif "ImportSettings_HostMapping")</span></span>  
  
    2.  <span data-ttu-id="91d1f-137">在**选择源实体**对话框中，选择源主机，然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="91d1f-137">In the **Select Source Entity** dialog box, select the source host, and then click **OK**.</span></span>  
  
        > [!NOTE]
        >  <span data-ttu-id="91d1f-138">若要将映射到单个源主机的多个目标主机，请重复步骤**5a**和**5b**。</span><span class="sxs-lookup"><span data-stu-id="91d1f-138">To map multiple destination hosts to a single source host, repeat the steps **5a** and **5b**.</span></span>  
  
    3.  <span data-ttu-id="91d1f-139">在**主机映射**页上，单击**下一步**。</span><span class="sxs-lookup"><span data-stu-id="91d1f-139">In the **Host Mapping** page, click **Next**.</span></span>  
  
6.  <span data-ttu-id="91d1f-140">在**主机实例映射**页上，执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="91d1f-140">In the **Host Instance Mapping** page, do the following:</span></span>  
  
    1.  <span data-ttu-id="91d1f-141">从目标主机实例列表中，选择你想要指定源主机实例，，然后单击一个目标主机实例**添加**。</span><span class="sxs-lookup"><span data-stu-id="91d1f-141">From the list of destination host instances, select a destination host instance for which you want to specify the source host instance, and then click **Add**.</span></span>  
  
        > [!NOTE]
        >  <span data-ttu-id="91d1f-142">主机实例只能映射到已在主机映射中创建的对应主机。</span><span class="sxs-lookup"><span data-stu-id="91d1f-142">Host instances can be mapped only to the corresponding host that has been created in the Host Mapping.</span></span> <span data-ttu-id="91d1f-143">例如，如果指定的映射其中**SourceHost1**映射到**DestinationHost1**，然后的实例**DestinationHost1**只能映射到的实例**SourceHost1**。</span><span class="sxs-lookup"><span data-stu-id="91d1f-143">For example, if you specify a mapping where **SourceHost1** is mapped to **DestinationHost1**, then the instances of **DestinationHost1** can only be mapped to the instances of **SourceHost1**.</span></span>  
        >   
        >  <span data-ttu-id="91d1f-144">导入向导会管理上述约束，您需要遵循此约束，否则 BizTalk 任务将会引发错误。</span><span class="sxs-lookup"><span data-stu-id="91d1f-144">The import wizard manages the above constraint, you need to follow this constraint else BizTalk tasks will throw errors.</span></span>  
        >   
        >  <span data-ttu-id="91d1f-145">你需要使用约定**HostName:MachineName**在映射文件中指定的主机实例。</span><span class="sxs-lookup"><span data-stu-id="91d1f-145">You need to use the convention **HostName:MachineName** to specify a host instance in a map file.</span></span> <span data-ttu-id="91d1f-146">例如， **Host1:Server1**映射中文件表示的实例**Host1**是正在运行或可供使用**Server1**。</span><span class="sxs-lookup"><span data-stu-id="91d1f-146">For example, **Host1:Server1** in a map file denotes that the instance of **Host1** is running or available on **Server1**.</span></span>  
  
         <span data-ttu-id="91d1f-147">![托管实例的映射](../core/media/importsettings-hostinstancemapping.gif "ImportSettings_HostInstanceMapping")</span><span class="sxs-lookup"><span data-stu-id="91d1f-147">![Host Instance Mapping](../core/media/importsettings-hostinstancemapping.gif "ImportSettings_HostInstanceMapping")</span></span>  
  
    2.  <span data-ttu-id="91d1f-148">在**选择源实体**对话框中，选择源主机实例，，然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="91d1f-148">In the **Select Source Entity** dialog box, select the source host instance, and then click **OK**.</span></span>  
  
        > [!NOTE]
        >  <span data-ttu-id="91d1f-149">若要将多个目标主机实例映射到单个源主机实例，请重复步骤**6a**到**6b**。</span><span class="sxs-lookup"><span data-stu-id="91d1f-149">To map multiple destination host instances to a single source host instance, repeat the steps **6a** to **6b**.</span></span>  
  
    3.  <span data-ttu-id="91d1f-150">在**主机实例映射**选项卡上，单击**下一步**。</span><span class="sxs-lookup"><span data-stu-id="91d1f-150">In the **Host Instance Mapping** tab, click **Next**.</span></span>  
  
7.  <span data-ttu-id="91d1f-151">在**导入摘要**对话框中，验证你创建的目标和源环境的所有导入设置是否为所需，，然后单击**导入**。</span><span class="sxs-lookup"><span data-stu-id="91d1f-151">In the **Import Summary** dialog box, verify if all the import settings for destination and source environments you created are as desired, and then click **Import**.</span></span> <span data-ttu-id="91d1f-152">**进度**页将显示导入的设置的进度。</span><span class="sxs-lookup"><span data-stu-id="91d1f-152">The **Progress** page shows the progress of import of the settings.</span></span>  
  
    > [!WARNING]
    >  <span data-ttu-id="91d1f-153">不能撤销 BizTalk Server 设置的导入。</span><span class="sxs-lookup"><span data-stu-id="91d1f-153">You cannot undo the import of BizTalk Server settings.</span></span> <span data-ttu-id="91d1f-154">如果你单击**导入**，启动从源环境的设置导入到目标环境的过程和**取消**处于禁用状态。</span><span class="sxs-lookup"><span data-stu-id="91d1f-154">If you click **Import**, the process for importing the settings from source environment to destination environment is initiated and **Cancel** is disabled.</span></span> <span data-ttu-id="91d1f-155">确保你想要继续进行之前单击导入**导入**。</span><span class="sxs-lookup"><span data-stu-id="91d1f-155">Ensure you want to proceed with import before clicking **Import**.</span></span>  
  
8.  <span data-ttu-id="91d1f-156">在**导入结果**选项卡上，检查的组、 主机和主机实例的设置，导入状态，然后单击**完成**完成导入操作。</span><span class="sxs-lookup"><span data-stu-id="91d1f-156">In the **Import Results** tab, check the import status of the Group, Host, and Host Instance settings, and then click **Finish** to complete the import operation.</span></span> <span data-ttu-id="91d1f-157">此时，所有导入的源环境设置都已应用到目标环境。</span><span class="sxs-lookup"><span data-stu-id="91d1f-157">All the imported source environment settings are applied to the destination environment.</span></span>  
  
     <span data-ttu-id="91d1f-158">![将结果导入](../core/media/importsettings-importresults.gif "ImportSettings_ImportResults")</span><span class="sxs-lookup"><span data-stu-id="91d1f-158">![Import Results](../core/media/importsettings-importresults.gif "ImportSettings_ImportResults")</span></span>  

## <a name="export-the-biztalk-group-host-and-host-instance-settings"></a><span data-ttu-id="91d1f-159">导出 BizTalk 组、 主机和主机实例设置</span><span class="sxs-lookup"><span data-stu-id="91d1f-159">Export the BizTalk group, host, and host instance settings</span></span>  

1.  <span data-ttu-id="91d1f-160">在**BizTalk Server 管理控制台**，展开[!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)]，右键单击**BizTalk 组**，然后单击**设置**。</span><span class="sxs-lookup"><span data-stu-id="91d1f-160">In the **BizTalk Server Administration Console**, expand [!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)], right-click **BizTalk Group**, and then click **Settings**.</span></span>  
  
2.  <span data-ttu-id="91d1f-161">在**BizTalk 设置仪表板**对话框中，单击**导出**。</span><span class="sxs-lookup"><span data-stu-id="91d1f-161">In the **BizTalk Settings Dashboard** dialog box, click **Export**.</span></span> <span data-ttu-id="91d1f-162">将显示 **“另存为”** 对话框。</span><span class="sxs-lookup"><span data-stu-id="91d1f-162">The **Save As** dialog box appears.</span></span>  
  
3.  <span data-ttu-id="91d1f-163">浏览至要保存当前 BizTalk 设置的位置。</span><span class="sxs-lookup"><span data-stu-id="91d1f-163">Browse to the location where you want to save the current BizTalk settings.</span></span> <span data-ttu-id="91d1f-164">输入的文件名，将类型选择为 XML 格式，然后单击**保存**。</span><span class="sxs-lookup"><span data-stu-id="91d1f-164">Enter the filename, select the type as XML format, and then click **Save**.</span></span>  

> [!IMPORTANT]
>  <span data-ttu-id="91d1f-165">我们不建议手动更新导出的 XML 文件。</span><span class="sxs-lookup"><span data-stu-id="91d1f-165">We do not not recommended manually updating the exported XML file.</span></span> <span data-ttu-id="91d1f-166">时将更新的 XML 文件导入到生产环境中，导入过程可能会由于某些数据类型不匹配或通过手动编辑引入其他错误而失败。</span><span class="sxs-lookup"><span data-stu-id="91d1f-166">When you import an updated XML file to a production environment, the import process might fail due to some data type mismatch or other errors introduced by manual editing.</span></span>  

## <a name="see-also"></a><span data-ttu-id="91d1f-167">另请参阅</span><span class="sxs-lookup"><span data-stu-id="91d1f-167">See Also</span></span>  
 [<span data-ttu-id="91d1f-168">设置仪表板用于 BizTalk Server 性能优化</span><span class="sxs-lookup"><span data-stu-id="91d1f-168">Using Settings Dashboard for BizTalk Server Performance Tuning</span></span>](../core/using-settings-dashboard-for-biztalk-server-performance-tuning.md)