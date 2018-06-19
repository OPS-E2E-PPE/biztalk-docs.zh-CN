---
title: 配置 BizTalk Accelerator for SWIFT |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: e34b0b2d-f563-468b-b6b9-536f0df96f52
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: eaa9812243ef7d5ff4bb8b902ac7aee48e54ab99
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22210853"
---
# <a name="configure-biztalk-accelerator-for-swift"></a><span data-ttu-id="25453-102">配置 BizTalk Accelerator for SWIFT</span><span class="sxs-lookup"><span data-stu-id="25453-102">Configure BizTalk Accelerator for SWIFT</span></span>

<span data-ttu-id="25453-103">配置[!INCLUDE[A4SWIFT_CurrentVersion_FirstRef_md](../../includes/a4swift-currentversion-firstref-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="25453-103">Configure the [!INCLUDE[A4SWIFT_CurrentVersion_FirstRef_md](../../includes/a4swift-currentversion-firstref-md.md)].</span></span> 

<span data-ttu-id="25453-104">当你安装[!INCLUDE[A4SWIFT_CurrentVersion_abbrev_md](../../includes/a4swift-currentversion-abbrev-md.md)]，没有一个复选框，让你自动运行配置。</span><span class="sxs-lookup"><span data-stu-id="25453-104">When you install [!INCLUDE[A4SWIFT_CurrentVersion_abbrev_md](../../includes/a4swift-currentversion-abbrev-md.md)], there is a checkbox that lets you run the configuration automatically.</span></span> <span data-ttu-id="25453-105">或者，你可以打开 BizTalk Accelerator for SWIFT (A4SWIFT) 配置你的应用程序中列出。</span><span class="sxs-lookup"><span data-stu-id="25453-105">Or, you can open the BizTalk Accelerator for SWIFT (A4SWIFT) Configuration listed in your apps.</span></span>

<span data-ttu-id="25453-106">本主题演示如何配置[!INCLUDE[A4SWIFT_CurrentVersion_abbrev_md](../../includes/a4swift-currentversion-abbrev-md.md)]快捷键，如何导出或导入配置，以及列表后配置步骤。</span><span class="sxs-lookup"><span data-stu-id="25453-106">This topic shows you how to configure the [!INCLUDE[A4SWIFT_CurrentVersion_abbrev_md](../../includes/a4swift-currentversion-abbrev-md.md)] accelerator, how to export or import a configuration, and also lists the post-configuration steps.</span></span>

## <a name="configure-a4swift"></a><span data-ttu-id="25453-107">配置 A4SWIFT</span><span class="sxs-lookup"><span data-stu-id="25453-107">Configure A4SWIFT</span></span>

1. <span data-ttu-id="25453-108">打开 BizTalk Accelerator for SWIFT (A4SWIFT) 配置。</span><span class="sxs-lookup"><span data-stu-id="25453-108">Open the BizTalk Accelerator for SWIFT (A4SWIFT) Configuration.</span></span>
2. <span data-ttu-id="25453-109">选择**MCRR**。</span><span class="sxs-lookup"><span data-stu-id="25453-109">Select **MCRR**.</span></span> <span data-ttu-id="25453-110">MCRR 可仅当你安装**消息修复和新提交**组件。</span><span class="sxs-lookup"><span data-stu-id="25453-110">MCRR is available only if you installed the **Message Repair and New Submission** components.</span></span>
3. <span data-ttu-id="25453-111">当系统询问**你想要创建新的数据库组**:</span><span class="sxs-lookup"><span data-stu-id="25453-111">When asked **Do you want to create a new database group**:</span></span>

  * <span data-ttu-id="25453-112">选择此选项以创建新组中所示**组**窗格。</span><span class="sxs-lookup"><span data-stu-id="25453-112">Select this option to create the new groups shown in the **Group** pane.</span></span> 
  * <span data-ttu-id="25453-113">若要加入现有的数据库组，请取消选中此选项。</span><span class="sxs-lookup"><span data-stu-id="25453-113">To join an existing database group, uncheck this option.</span></span>

3. <span data-ttu-id="25453-114">如果你安装**用于消息修复和新提交的 Web 组件**，然后选择**WebService**。</span><span class="sxs-lookup"><span data-stu-id="25453-114">If you installed **Web Components for Message Repair and New Submission**, then select **WebService**.</span></span>
4. <span data-ttu-id="25453-115">选择要承载 A4SWIFT Web 服务的 web 站点。</span><span class="sxs-lookup"><span data-stu-id="25453-115">Select the web site to host the A4SWIFT Web service.</span></span> <span data-ttu-id="25453-116">默认情况下，选择 Default Web Site。</span><span class="sxs-lookup"><span data-stu-id="25453-116">By default, the Default Web Site is selected.</span></span>
5. <span data-ttu-id="25453-117">选择**应用配置**。</span><span class="sxs-lookup"><span data-stu-id="25453-117">Select **Apply Configuration**.</span></span>
6. <span data-ttu-id="25453-118">在**摘要**，验证配置设置，然后单击**配置**。</span><span class="sxs-lookup"><span data-stu-id="25453-118">In **Summary**, verify the configuration settings, and then click **Configure**.</span></span> 

    > [!TIP] 
    > <span data-ttu-id="25453-119">如有需要，可以将配置设置另存为 XML 文件。</span><span class="sxs-lookup"><span data-stu-id="25453-119">You can save the configuration settings as an XML file, if desired.</span></span>

7. <span data-ttu-id="25453-120">选择**完成**当配置完成。</span><span class="sxs-lookup"><span data-stu-id="25453-120">Select **Finish** when the configuration completes.</span></span>

## <a name="export-or-import-a-configuration"></a><span data-ttu-id="25453-121">导出或导入配置</span><span class="sxs-lookup"><span data-stu-id="25453-121">Export or import a configuration</span></span>
<span data-ttu-id="25453-122">可以将 A4SWIFT 的配置设置导出到 XML 文件。</span><span class="sxs-lookup"><span data-stu-id="25453-122">You can export the configuration settings of A4SWIFT to an XML file.</span></span> <span data-ttu-id="25453-123">这些设置然后可以导入配置另一个 A4SWIFT 安装。</span><span class="sxs-lookup"><span data-stu-id="25453-123">These settings can then be imported to configure another A4SWIFT installation.</span></span> 

### <a name="export-the-configuration"></a><span data-ttu-id="25453-124">导出配置</span><span class="sxs-lookup"><span data-stu-id="25453-124">Export the configuration</span></span>

1. <span data-ttu-id="25453-125">打开 Microsoft BizTalk Accelerator for SWIFT 配置，并选择**导出配置**。</span><span class="sxs-lookup"><span data-stu-id="25453-125">Open the Microsoft BizTalk Accelerator for SWIFT Configuration, and select **Export Configuration**.</span></span>
2. <span data-ttu-id="25453-126">在**另存为**，浏览到你想要保存配置文件中，输入配置文件的名称的文件夹，然后**保存**。</span><span class="sxs-lookup"><span data-stu-id="25453-126">In **Save As**, browse to the folder where you want to save the configuration file, enter a name for the configuration file, and then **Save**.</span></span>
3. <span data-ttu-id="25453-127">当导出成功，则选择**确定**。</span><span class="sxs-lookup"><span data-stu-id="25453-127">When exported successfully, select **OK**.</span></span>

### <a name="import-a-configuration"></a><span data-ttu-id="25453-128">导入配置</span><span class="sxs-lookup"><span data-stu-id="25453-128">Import a configuration</span></span>
1. <span data-ttu-id="25453-129">打开 Microsoft BizTalk Accelerator for SWIFT 配置，并选择**导入配置**。</span><span class="sxs-lookup"><span data-stu-id="25453-129">Open the Microsoft BizTalk Accelerator for SWIFT Configuration, and select **Import Configuration**.</span></span>
2. <span data-ttu-id="25453-130">浏览到包含配置文件的文件夹，选择的文件，然后选择**导入**。</span><span class="sxs-lookup"><span data-stu-id="25453-130">Browse to the folder that contains the configuration file, select the file, and then select **Import**.</span></span>

## <a name="post-configuration-steps"></a><span data-ttu-id="25453-131">后配置步骤</span><span class="sxs-lookup"><span data-stu-id="25453-131">Post-configuration steps</span></span>

### <a name="add-users-to-the-a4swift-users-group"></a><span data-ttu-id="25453-132">将用户添加到 A4SWIFT 用户组</span><span class="sxs-lookup"><span data-stu-id="25453-132">Add users to the A4SWIFT Users group</span></span>

<span data-ttu-id="25453-133">在配置之后[!INCLUDE[A4SWIFT_CurrentVersion_FirstRef_md](../../includes/a4swift-currentversion-firstref-md.md)]，将运行到 BizTalkServerApplication 主机实例的帐户添加**A4SWIFT 用户**组 (*不* **A4SWIFT 管理员**组)。</span><span class="sxs-lookup"><span data-stu-id="25453-133">After you configure the [!INCLUDE[A4SWIFT_CurrentVersion_FirstRef_md](../../includes/a4swift-currentversion-firstref-md.md)], add the account that runs the BizTalkServerApplication host instance to the **A4SWIFT Users** group (*not* the **A4SWIFT Administrators** group).</span></span> 

<span data-ttu-id="25453-134">**步骤**:</span><span class="sxs-lookup"><span data-stu-id="25453-134">**Steps**:</span></span>

1. <span data-ttu-id="25453-135">打开**服务**。</span><span class="sxs-lookup"><span data-stu-id="25453-135">Open **Services**.</span></span> <span data-ttu-id="25453-136">服务还会显示在**服务器管理器**，，然后**工具**。</span><span class="sxs-lookup"><span data-stu-id="25453-136">Services is also available in **Server Manager**, and then **Tools**.</span></span> 
2. <span data-ttu-id="25453-137">在列表中，查找**BizTalk 服务 BizTalk 组： BizTalkServerApplication**。</span><span class="sxs-lookup"><span data-stu-id="25453-137">In the list, find **BizTalk Service BizTalk Group: BizTalkServerApplication**.</span></span> 
3. <span data-ttu-id="25453-138">双击选择以打开其属性。</span><span class="sxs-lookup"><span data-stu-id="25453-138">Double-select to open its properties.</span></span>
4. <span data-ttu-id="25453-139">在**Log On**选项卡上，注意用户帐户列为**此帐户**。</span><span class="sxs-lookup"><span data-stu-id="25453-139">In the **Log On** tab, note the user account listed as **This account**.</span></span>
5. <span data-ttu-id="25453-140">打开**本地用户和组**（在计算机管理），然后找到**A4SWIFT 用户**组。</span><span class="sxs-lookup"><span data-stu-id="25453-140">Open **Local Users and Groups** (in Computer Management), and then find the **A4SWIFT Users** group.</span></span> <span data-ttu-id="25453-141">将用户帐户添加到此组。</span><span class="sxs-lookup"><span data-stu-id="25453-141">Add the user account to this group.</span></span>

> [!TIP] 
> <span data-ttu-id="25453-142">主机实例的帐户需要此组成员身份主机消息修复运行时组件以访问 BizTalk Server 数据库。</span><span class="sxs-lookup"><span data-stu-id="25453-142">The host instance account needs this group membership for the host Message Repair runtime component to access the BizTalk Server database.</span></span>

### <a name="check-the-identity-of-the-application-pool"></a><span data-ttu-id="25453-143">检查应用程序池的标识</span><span class="sxs-lookup"><span data-stu-id="25453-143">Check the identity of the application pool</span></span>
<span data-ttu-id="25453-144">A4SWIFT_MRSR web 服务承载于 IIS 中的应用程序。</span><span class="sxs-lookup"><span data-stu-id="25453-144">The A4SWIFT_MRSR web service is hosted in an application in IIS.</span></span> <span data-ttu-id="25453-145">应用程序池标识*无法*是网络服务。</span><span class="sxs-lookup"><span data-stu-id="25453-145">The application pool identity *cannot* be Network Service.</span></span> <span data-ttu-id="25453-146">将应用程序池标识更改为本地或域帐户是成员的**A4SWIFT 用户**组。</span><span class="sxs-lookup"><span data-stu-id="25453-146">Change the identity of the application pool to a local or domain account that is a member of the **A4SWIFT Users** group.</span></span>

<span data-ttu-id="25453-147">**步骤**:</span><span class="sxs-lookup"><span data-stu-id="25453-147">**Steps**:</span></span>

1. <span data-ttu-id="25453-148">打开**Internet Information Services 管理器**。</span><span class="sxs-lookup"><span data-stu-id="25453-148">Open **Internet Information Services Manager**.</span></span> <span data-ttu-id="25453-149">IIS 管理器还会显示在**服务器管理器**，，然后**工具**。</span><span class="sxs-lookup"><span data-stu-id="25453-149">The IIS Manager is also available in **Server Manager**, and then **Tools**.</span></span> 
2. <span data-ttu-id="25453-150">展开**Default Web Site**，并选择 A4SWIFT_MRSR web 服务。</span><span class="sxs-lookup"><span data-stu-id="25453-150">Expand the **Default Web Site**, and select the A4SWIFT_MRSR web service.</span></span> 
3. <span data-ttu-id="25453-151">选择**基本设置**。</span><span class="sxs-lookup"><span data-stu-id="25453-151">Select **Basic Settings**.</span></span> <span data-ttu-id="25453-152">列出应用程序池的名称。</span><span class="sxs-lookup"><span data-stu-id="25453-152">The name of the application pool is listed.</span></span>
4. <span data-ttu-id="25453-153">在左窗格中，选择**应用程序池**，然后选择你的应用程序池。</span><span class="sxs-lookup"><span data-stu-id="25453-153">In the left pane, select **Application Pools**, and then select your application pool.</span></span>
5. <span data-ttu-id="25453-154">选择**高级设置**，并更改**标识**必要。</span><span class="sxs-lookup"><span data-stu-id="25453-154">Select **Advanced Settings**, and change the **Identity** if needed.</span></span>