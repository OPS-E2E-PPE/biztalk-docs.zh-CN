---
title: "使用绑定文件导入或导出 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: f9a2a82a-f8d4-4ec2-b8c1-be6cda3f993a
caps.latest.revision: "2"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e3707726eb9e8e77e0536f36700fe098d83ad414
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="use-binding-files-to-import-or-export"></a><span data-ttu-id="24178-102">使用绑定文件导入或导出</span><span class="sxs-lookup"><span data-stu-id="24178-102">Use binding files to import or export</span></span>

<span data-ttu-id="24178-103">从开始[!INCLUDE[bts2016_md](../includes/bts2016-md.md)]，你可以导出并导入绑定文件在**方**和**协议**级别。</span><span class="sxs-lookup"><span data-stu-id="24178-103">Starting with [!INCLUDE[bts2016_md](../includes/bts2016-md.md)], you can export and import binding files at the **Parties** and **Agreement** levels.</span></span> <span data-ttu-id="24178-104">对于早期 BizTalk 版本，你导出应用程序级别中所述：</span><span class="sxs-lookup"><span data-stu-id="24178-104">For previous BizTalk versions, you export at the application level, as described at:</span></span> 

* [<span data-ttu-id="24178-105">如何导出 EDI AS2 解决方案的绑定</span><span class="sxs-lookup"><span data-stu-id="24178-105">How to Export Bindings for an EDI-AS2 Solution</span></span>](../core/how-to-export-bindings-for-an-edi-as2-solution.md)
* [<span data-ttu-id="24178-106">如何导入绑定 EDI AS2 解决方案</span><span class="sxs-lookup"><span data-stu-id="24178-106">How to Import Bindings for an EDI-AS2 Solution</span></span>](../core/how-to-import-bindings-for-an-edi-as2-solution.md)

<span data-ttu-id="24178-107">本主题说明如何导入和导出方、 自己的配置文件、 协议、 回退设置，和详细使用[!INCLUDE[btsBizTalkServerAdminConsoleui_md](../includes/btsbiztalkserveradminconsoleui-md.md)]和 BTSTask。</span><span class="sxs-lookup"><span data-stu-id="24178-107">This topic shows you how to import and exports parties, their profiles, agreements, fallback settings, and more using [!INCLUDE[btsBizTalkServerAdminConsoleui_md](../includes/btsbiztalkserveradminconsoleui-md.md)] and BTSTask.</span></span> 

## <a name="overview"></a><span data-ttu-id="24178-108">概述</span><span class="sxs-lookup"><span data-stu-id="24178-108">Overview</span></span>

<span data-ttu-id="24178-109">一些导入和导出功能包括：</span><span class="sxs-lookup"><span data-stu-id="24178-109">Some of the import and export features include:</span></span>

* <span data-ttu-id="24178-110">从 XML 绑定文件导入方、 业务配置文件和协议</span><span class="sxs-lookup"><span data-stu-id="24178-110">Import parties, business profiles, and agreements from an XML binding file</span></span>
* <span data-ttu-id="24178-111">将参与方、 业务配置文件、 协议和 EDI 回退设置导出到 XML 绑定文件</span><span class="sxs-lookup"><span data-stu-id="24178-111">Export parties, business profiles, agreements, and EDI fallback settings to an XML binding file</span></span>
* <span data-ttu-id="24178-112">在导入绑定文件，你可以选择不导入的参与方或回退设置</span><span class="sxs-lookup"><span data-stu-id="24178-112">When importing a binding file, you can chose to not import the parties, or the fallback settings</span></span>
* <span data-ttu-id="24178-113">在导入在方级别，将导入方和绑定文件中的协议</span><span class="sxs-lookup"><span data-stu-id="24178-113">When importing at the Parties-level, only the parties and agreements within the binding file are imported</span></span>
* <span data-ttu-id="24178-114">将特定方导出到相同的绑定文件，并选择还导出这些方与关联的所有协议</span><span class="sxs-lookup"><span data-stu-id="24178-114">Export specific parties to the same binding file, and choose to also export all the agreements associated with those parties</span></span>
* <span data-ttu-id="24178-115">应用程序导入绑定向导允许你选择要导入的跟踪设置，或排除方。</span><span class="sxs-lookup"><span data-stu-id="24178-115">The application import binding wizard lets you choose to import the tracking settings, or exclude the parties.</span></span>
* <span data-ttu-id="24178-116">BTSTask 包括`ImportParties`和`ExportParties`命令</span><span class="sxs-lookup"><span data-stu-id="24178-116">BTSTask includes the `ImportParties` and `ExportParties` commands</span></span> 

## <a name="prerequisites"></a><span data-ttu-id="24178-117">先决条件</span><span class="sxs-lookup"><span data-stu-id="24178-117">Prerequisites</span></span>

* <span data-ttu-id="24178-118">你必须是的成员的帐户登录 * * BizTalk Server 管理员 * * 组。</span><span class="sxs-lookup"><span data-stu-id="24178-118">You must be logged on with an account that is a member of the** BizTalk Server Administrators** group.</span></span> <span data-ttu-id="24178-119">请参阅[用于部署和管理 BizTalk 应用程序所需权限](../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md)。</span><span class="sxs-lookup"><span data-stu-id="24178-119">See [Permissions Required for Deploying and Managing a BizTalk Application](../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md).</span></span>  

* <span data-ttu-id="24178-120">你必须添加对引用**BizTalk EDI 应用程序**从 BizTalk 应用程序将用作 EDI 应用程序。</span><span class="sxs-lookup"><span data-stu-id="24178-120">You must have added a reference to the **BizTalk EDI Application** from a BizTalk application that will be used as an EDI application.</span></span> <span data-ttu-id="24178-121">请参阅[后配置步骤](../install-and-config-guides/post-configuration-steps-to-optimize-your-environment.md)。</span><span class="sxs-lookup"><span data-stu-id="24178-121">See [Post-configuration steps](../install-and-config-guides/post-configuration-steps-to-optimize-your-environment.md).</span></span>

## <a name="import-or-export-all-the-trading-partners"></a><span data-ttu-id="24178-122">导入或导出所有贸易合作伙伴</span><span class="sxs-lookup"><span data-stu-id="24178-122">Import or export all the trading partners</span></span>
1. <span data-ttu-id="24178-123">打开 **[!INCLUDE[btsBizTalkServerAdminConsoleui_md](../includes/btsbiztalkserveradminconsoleui-md.md)]** ，展开的 BizTalk 组。</span><span class="sxs-lookup"><span data-stu-id="24178-123">Open **[!INCLUDE[btsBizTalkServerAdminConsoleui_md](../includes/btsbiztalkserveradminconsoleui-md.md)]**, and expand the BizTalk group.</span></span>
2. <span data-ttu-id="24178-124">右键单击**方**，然后选择**导出**。</span><span class="sxs-lookup"><span data-stu-id="24178-124">Right-click **Parties**, and select **Export**.</span></span> 

    <span data-ttu-id="24178-125">在导出时**方**-级别时，要导出所有贸易合作伙伴。</span><span class="sxs-lookup"><span data-stu-id="24178-125">When you export at the **parties**-level, you are exporting all the trading partners.</span></span> <span data-ttu-id="24178-126">这还将导出所有内容使用贸易合作伙伴，包括业务配置文件和到 XML 文件的协议。</span><span class="sxs-lookup"><span data-stu-id="24178-126">This also exports everything used by the trading partners, including business profiles, and agreements into an XML file.</span></span> 

3. <span data-ttu-id="24178-127">右键单击**方**，选择**导入**，并选择绑定的 XML 文件。</span><span class="sxs-lookup"><span data-stu-id="24178-127">Right-click **Parties**, select **Import**, and select the binding XML file.</span></span> 

      <span data-ttu-id="24178-128">选择**排除方**，或**排除 EDI 回退设置**以便它们不会导入。</span><span class="sxs-lookup"><span data-stu-id="24178-128">Choose to **Exclude Parties**, or **Exclude EDI Fallback Settings** so they are not imported.</span></span> <span data-ttu-id="24178-129">否则，绑定文件中的所有内容导入，包括贸易合作伙伴、 业务配置文件和协议。</span><span class="sxs-lookup"><span data-stu-id="24178-129">Otherwise, everything in the binding file is imported, including the trading partners, business profiles, and agreements.</span></span>     

### <a name="btstask-example"></a><span data-ttu-id="24178-130">BTSTask 示例</span><span class="sxs-lookup"><span data-stu-id="24178-130">BTSTask example</span></span>

`BTSTask ImportParties  -Source:"C:\Temp\MyParties.Xml" -ExcludeEdiFallbackSettings`

<span data-ttu-id="24178-131">请参阅[ImportParties 命令](../core/importparties-command.md)。</span><span class="sxs-lookup"><span data-stu-id="24178-131">See [ImportParties command](../core/importparties-command.md).</span></span>

    
## <a name="export-individual-partners"></a><span data-ttu-id="24178-132">导出各个合作伙伴</span><span class="sxs-lookup"><span data-stu-id="24178-132">Export individual partners</span></span>
1. <span data-ttu-id="24178-133">在 **[!INCLUDE[btsBizTalkServerAdminConsoleui_md](../includes/btsbiztalkserveradminconsoleui-md.md)]** ，选择**方**。</span><span class="sxs-lookup"><span data-stu-id="24178-133">In **[!INCLUDE[btsBizTalkServerAdminConsoleui_md](../includes/btsbiztalkserveradminconsoleui-md.md)]**, select **Parties**.</span></span>
2. <span data-ttu-id="24178-134">在**方和业务配置文件**窗格中，右键单击一个参与方，然后选择**导出**。</span><span class="sxs-lookup"><span data-stu-id="24178-134">In the **Parties and business profiles** pane, right-click a party, and select **Export**.</span></span>

    <span data-ttu-id="24178-135">在导出特定方时，你可以选择要导出所有各方，并由该方使用的所有协议。</span><span class="sxs-lookup"><span data-stu-id="24178-135">When you export a specific party, you are given the choice to export all the parties, and all the agreements used by that party.</span></span> <span data-ttu-id="24178-136">你可以取消选中**导出所选的方和中所选的参与方的所有协议**若要仅导出你选择的当事方。</span><span class="sxs-lookup"><span data-stu-id="24178-136">You can uncheck **Export selected parties and all the agreements within the selected parties** to only export the party you select.</span></span>

3. <span data-ttu-id="24178-137">选择“确定”。</span><span class="sxs-lookup"><span data-stu-id="24178-137">Select **OK**.</span></span> 

> [!TIP]
> <span data-ttu-id="24178-138">在**方和业务配置文件**窗格中，你还可以使用**CTRL**和**Shift**键以选择多个方列表中。</span><span class="sxs-lookup"><span data-stu-id="24178-138">In the **Parties and business profiles** pane, you can also use the **CTRL** and **Shift** keys to select multiple parties in the list.</span></span> <span data-ttu-id="24178-139">所有参与方，选择将导出到相同的绑定文件。</span><span class="sxs-lookup"><span data-stu-id="24178-139">All of the parties you select export into the same binding file.</span></span>

### <a name="btstask-example"></a><span data-ttu-id="24178-140">BTSTask 示例</span><span class="sxs-lookup"><span data-stu-id="24178-140">BTSTask example</span></span>

`BTSTask ExportParties -Destination:"C:\Temp\MyParties.Xml"`

<span data-ttu-id="24178-141">请参阅[ExportParties 命令](../core/exportparties-command.md)。</span><span class="sxs-lookup"><span data-stu-id="24178-141">See [ExportParties command](../core/exportparties-command.md).</span></span>


## <a name="import-application-binding-file"></a><span data-ttu-id="24178-142">导入应用程序绑定文件</span><span class="sxs-lookup"><span data-stu-id="24178-142">Import application binding file</span></span>

<span data-ttu-id="24178-143">在应用程序级别，你可以与 EDI 和 AS2 方导绑定文件。</span><span class="sxs-lookup"><span data-stu-id="24178-143">At the application-level, you can import a binding file with EDI and AS2 parties.</span></span> 

1. <span data-ttu-id="24178-144">在 **[!INCLUDE[btsBizTalkServerAdminConsoleui_md](../includes/btsbiztalkserveradminconsoleui-md.md)]** ，展开**应用程序**</span><span class="sxs-lookup"><span data-stu-id="24178-144">In **[!INCLUDE[btsBizTalkServerAdminConsoleui_md](../includes/btsbiztalkserveradminconsoleui-md.md)]**, expand **Applications**</span></span>
2. <span data-ttu-id="24178-145">右键单击你的应用程序，然后选择**导入**。</span><span class="sxs-lookup"><span data-stu-id="24178-145">Right-click your application, and select **Import**.</span></span>
3. <span data-ttu-id="24178-146">**导入跟踪设置**和**排除方**选项才可用。</span><span class="sxs-lookup"><span data-stu-id="24178-146">**Import Tracking Settings** and **Exclude Parties** options are available.</span></span> <span data-ttu-id="24178-147">使用这些选项，你可以选择要导入任何现有的跟踪设置，或排除所有绑定文件中的 EDI/AS2 参与方。</span><span class="sxs-lookup"><span data-stu-id="24178-147">Using these options, you can choose to import any existing tracking settings, or exclude any EDI/AS2 parties within the binding file.</span></span>

    | <span data-ttu-id="24178-148">设置</span><span class="sxs-lookup"><span data-stu-id="24178-148">Setting</span></span> | <span data-ttu-id="24178-149">详细信息</span><span class="sxs-lookup"><span data-stu-id="24178-149">Details</span></span> |
    |---|---|
    |<span data-ttu-id="24178-150">**导入跟踪设置**</span><span class="sxs-lookup"><span data-stu-id="24178-150">**Import Tracking Settings**</span></span> | <span data-ttu-id="24178-151">导入应用程序，例如跟踪消息正文和跟踪事件中不同的项目上启用的跟踪设置。</span><span class="sxs-lookup"><span data-stu-id="24178-151">Imports the tracking settings enabled on the different artifacts within the application, such as track message bodies, and track events.</span></span> <br/><br/><span data-ttu-id="24178-152">默认启用，以确保向后兼容性。</span><span class="sxs-lookup"><span data-stu-id="24178-152">Enabled by default to ensure backwards-compatibility.</span></span> |
    | <span data-ttu-id="24178-153">**排除方**</span><span class="sxs-lookup"><span data-stu-id="24178-153">**Exclude Parties**</span></span>|<span data-ttu-id="24178-154">执行不导入方、 配置文件，以及协议现有文件中。</span><span class="sxs-lookup"><span data-stu-id="24178-154">Does not import parties, profiles, and agreements that existing within the file.</span></span> <br/><br/><span data-ttu-id="24178-155">默认情况下，以确保向后兼容性已禁用。</span><span class="sxs-lookup"><span data-stu-id="24178-155">Disabled by default to ensure backwards-compatibility.</span></span>|

     > [!IMPORTANT] 
     > <span data-ttu-id="24178-156">全局跟踪设置替代**导入跟踪设置**。</span><span class="sxs-lookup"><span data-stu-id="24178-156">The global tracking settings override **Import Tracking Settings**.</span></span> <span data-ttu-id="24178-157">因此如果已禁用跟踪在全局级别，任何不导入设置的跟踪，即使**导入跟踪设置**已选中。</span><span class="sxs-lookup"><span data-stu-id="24178-157">So if you've disabled tracking at the global level, any tracking settings are not imported, even if **Import Tracking Settings** is checked.</span></span>
     > 
     > <span data-ttu-id="24178-158">**BizTalk 设置仪表板，组页**[!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]说明**允许导入的跟踪设置**全局设置。</span><span class="sxs-lookup"><span data-stu-id="24178-158">**BizTalk Settings Dashboard, Group Page** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)] explains the **Allow import of tracking settings** global setting.</span></span>

### <a name="btstask-example"></a><span data-ttu-id="24178-159">BTSTask 示例</span><span class="sxs-lookup"><span data-stu-id="24178-159">BTSTask example</span></span>

`BTSTask ImportBindings -ApplicationName:MyApplication -Source:C:\Bindings\Binding1.xml -ImportTrackingSettings:true`

<span data-ttu-id="24178-160">请参阅[ImportBindings 命令](../core/importbindings-command.md)。</span><span class="sxs-lookup"><span data-stu-id="24178-160">See [ImportBindings command](../core/importbindings-command.md).</span></span>

## <a name="in-this-section"></a><span data-ttu-id="24178-161">在本节中</span><span class="sxs-lookup"><span data-stu-id="24178-161">In this section</span></span>
<span data-ttu-id="24178-162">若要导入或导出以前 BizTalk 版本上的 EDI 和 AS2 绑定文件，请参阅：</span><span class="sxs-lookup"><span data-stu-id="24178-162">To import or export EDI and AS2 binding files on previous BizTalk versions, see:</span></span> 

* [<span data-ttu-id="24178-163">如何导出 EDI AS2 解决方案的绑定</span><span class="sxs-lookup"><span data-stu-id="24178-163">How to Export Bindings for an EDI-AS2 Solution</span></span>](../core/how-to-export-bindings-for-an-edi-as2-solution.md)
* [<span data-ttu-id="24178-164">如何导入绑定 EDI AS2 解决方案</span><span class="sxs-lookup"><span data-stu-id="24178-164">How to Import Bindings for an EDI-AS2 Solution</span></span>](../core/how-to-import-bindings-for-an-edi-as2-solution.md)
