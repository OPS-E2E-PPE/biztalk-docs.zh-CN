---
title: "更新或卸载 BizTalk 适配器包 2016年 |Microsoft 文档"
description: "使用安装向导或 msiexec 来更改或卸载 BAP 2016 附带 BizTalk Server;包括删除绑定，删除了自定义的 Rfc"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: d3d6c001-1005-4d7b-a143-eaa37b48f898
caps.latest.revision: "2"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: bb0dd0b9d778f878df9a06efdfc0f41754403690
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/28/2017
---
# <a name="update-or-uninstall-the-biztalk-adapter-pack-2016"></a><span data-ttu-id="c4945-103">更新或卸载 BizTalk 适配器包 2016</span><span class="sxs-lookup"><span data-stu-id="c4945-103">Update or uninstall the BizTalk Adapter Pack 2016</span></span>
<span data-ttu-id="c4945-104">如何更改或卸载[!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="c4945-104">How to change or uninstall the [!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)].</span></span>

<a name="BKMK_Modify_Adap"></a>
## <a name="change-or-update-the-installation"></a><span data-ttu-id="c4945-105">更改或更新安装</span><span class="sxs-lookup"><span data-stu-id="c4945-105">Change or update the installation</span></span>  
<span data-ttu-id="c4945-106">在运行安装向导以修改之前[!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)]安装，请确保[!INCLUDE[afproductnameshort](../includes/afproductnameshort-md.md)]安装。</span><span class="sxs-lookup"><span data-stu-id="c4945-106">Before you run the setup wizard to modify the [!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)] installation, make sure the [!INCLUDE[afproductnameshort](../includes/afproductnameshort-md.md)] is installed.</span></span> 
  
 <span data-ttu-id="c4945-107">你可以修改安装在交互模式下 （安装程序向导），或在静默模式下 （命令行）。</span><span class="sxs-lookup"><span data-stu-id="c4945-107">You can modify the installation in interactive mode (the setup wizard), or in silent mode (the command line).</span></span>
  
### <a name="use-the-setup-wizard"></a><span data-ttu-id="c4945-108">使用安装向导</span><span class="sxs-lookup"><span data-stu-id="c4945-108">Use the setup wizard</span></span>  
  
1.  <span data-ttu-id="c4945-109">使用 BizTalk Server Administrators 组的成员的帐户登录。</span><span class="sxs-lookup"><span data-stu-id="c4945-109">Sign in with an account that is a member of the BizTalk Server Administrators group.</span></span>  
  
2.  <span data-ttu-id="c4945-110">在**程序和功能**，选择**卸载程序**。</span><span class="sxs-lookup"><span data-stu-id="c4945-110">In **Programs and features**, select **Uninstall a program**.</span></span>  
  
3.  <span data-ttu-id="c4945-111">右键单击**Microsoft BizTalk 适配器包**，然后选择**更改**。</span><span class="sxs-lookup"><span data-stu-id="c4945-111">Right-click **Microsoft BizTalk Adapter Pack**, and then select **Change**.</span></span>  
  
4.  <span data-ttu-id="c4945-112">在欢迎屏幕上，选择**下一步**。</span><span class="sxs-lookup"><span data-stu-id="c4945-112">On the Welcome screen, select **Next**.</span></span>  
  
5.  <span data-ttu-id="c4945-113">在**更改、 修复或删除安装**:</span><span class="sxs-lookup"><span data-stu-id="c4945-113">In **Change, repair, or remove installation**:</span></span>  
  
    -   <span data-ttu-id="c4945-114">若要选择你想要安装的组件，选择**更改**并转到步骤 6。</span><span class="sxs-lookup"><span data-stu-id="c4945-114">To select the components you want to install, select **Change** and go to Step 6.</span></span>  
  
    -   <span data-ttu-id="c4945-115">若要修复最新安装中的错误，选择**修复**并转到步骤 7。</span><span class="sxs-lookup"><span data-stu-id="c4945-115">To repair errors in the most recent installation, select **Repair** and go to Step 7.</span></span>  
  
    -   <span data-ttu-id="c4945-116">若要删除[!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)]从计算机上，选择**删除**，然后转到步骤 10。</span><span class="sxs-lookup"><span data-stu-id="c4945-116">To remove the [!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)] from the computer, select **Remove** and then go to Step 10.</span></span>  
  
6.  <span data-ttu-id="c4945-117">如果你选择要修改安装：</span><span class="sxs-lookup"><span data-stu-id="c4945-117">If you chose to modify the installation:</span></span>  
  
    -   <span data-ttu-id="c4945-118">展开**Microsoft BizTalk 适配器包**节点，以选择要安装的基的适配器和 / 或.NET Framework 数据提供程序。</span><span class="sxs-lookup"><span data-stu-id="c4945-118">Expand the **Microsoft BizTalk Adapter Pack** node to choose to install the base adapters, the .NET Framework Data Providers, or both.</span></span>  
  
    -   <span data-ttu-id="c4945-119">展开**基适配器**节点，以选择安装所有适配器或特定的适配器。</span><span class="sxs-lookup"><span data-stu-id="c4945-119">Expand the **Base Adapters** node to choose to install all the adapters or specific adapters.</span></span>  
  
    -   <span data-ttu-id="c4945-120">展开**ADO 提供程序**节点，以选择安装所有提供程序或特定的提供程序安装。</span><span class="sxs-lookup"><span data-stu-id="c4945-120">Expand the **ADO Providers** node to choose to install all the providers or specific providers.</span></span>  
  
    -   <span data-ttu-id="c4945-121">选择“下一步” 。</span><span class="sxs-lookup"><span data-stu-id="c4945-121">Select **Next**.</span></span>  
  
    -   <span data-ttu-id="c4945-122">选择**更改**，然后选择**完成**。</span><span class="sxs-lookup"><span data-stu-id="c4945-122">Select **Change**, and then select **Finish**.</span></span>  
  
7.  <span data-ttu-id="c4945-123">如果你选择在修复安装，**准备好修复 Microsoft BizTalk 适配器包**对话框中，选择**修复**。</span><span class="sxs-lookup"><span data-stu-id="c4945-123">If you chose to repair the installation, in the **Ready to repair Microsoft BizTalk Adapter Pack** dialog box, select **Repair**.</span></span> <span data-ttu-id="c4945-124">启动向导，修复安装。</span><span class="sxs-lookup"><span data-stu-id="c4945-124">The wizard starts repairing the installation.</span></span>  
  
8.  <span data-ttu-id="c4945-125">如果需要，更改你的首选项有关选择加入的 CEIP，，然后选择**确定**。</span><span class="sxs-lookup"><span data-stu-id="c4945-125">If required, change your preferences regarding opting for CEIP, and then select **OK**.</span></span> 
  
9. <span data-ttu-id="c4945-126">选择“完成”。</span><span class="sxs-lookup"><span data-stu-id="c4945-126">Select **Finish**.</span></span>  
  
10. <span data-ttu-id="c4945-127">如果您选择中删除适配器，**准备好删除 Microsoft BizTalk 适配器包**对话框中，选择**删除**，然后选择**完成**。</span><span class="sxs-lookup"><span data-stu-id="c4945-127">If you chose to remove the adapters, in the **Ready to remove Microsoft BizTalk Adapter Pack** dialog box, select **Remove**, and then select **Finish**.</span></span>  
  
### <a name="use-msiexec-in-silent-mode"></a><span data-ttu-id="c4945-128">在静默模式下使用 msiexec</span><span class="sxs-lookup"><span data-stu-id="c4945-128">Use msiexec in silent mode</span></span>  
  
1.  <span data-ttu-id="c4945-129">打开命令提示符，并转到根目录下的[!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)]安装程序。</span><span class="sxs-lookup"><span data-stu-id="c4945-129">Open a command prompt, and go to the root directory of the [!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)] installer.</span></span>  
  
2.  <span data-ttu-id="c4945-130">运行如下命令：</span><span class="sxs-lookup"><span data-stu-id="c4945-130">Run a command similar to the following:</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="c4945-131">若要修改[!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)]在基于 x64 的平台上，在以下命令，以无提示模式安装替换`AdaptersSetup.msi`与`AdaptersSetup64.msi`。</span><span class="sxs-lookup"><span data-stu-id="c4945-131">To modify the [!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)] installation in a silent mode on an x64-based platform, in the following commands, replace `AdaptersSetup.msi` with `AdaptersSetup64.msi`.</span></span>  
  
    ```  
    msiexec /i AdaptersSetup.msi /qn REMOVE=DbFeature ADDLOCAL=SapBaseAdapterFeature  
    ```  
  
     <span data-ttu-id="c4945-132">此命令删除[!INCLUDE[adapteroracle_short](../includes/adapteroracle-short-md.md)]，并安装[!INCLUDE[adaptersap_short](../includes/adaptersap-short-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="c4945-132">This command removes the [!INCLUDE[adapteroracle_short](../includes/adapteroracle-short-md.md)], and installs the [!INCLUDE[adaptersap_short](../includes/adaptersap-short-md.md)].</span></span>  
  
     <span data-ttu-id="c4945-133">通过使用不同的值`REMOVE`和`ADDLOCAL`属性，可以添加或删除特定的组件。</span><span class="sxs-lookup"><span data-stu-id="c4945-133">By using different values for the `REMOVE` and `ADDLOCAL` properties, you can add or remove specific components.</span></span> <span data-ttu-id="c4945-134">中的表是指**在无提示模式下安装**在[安装 BAP](../adapters-and-accelerators/installing-the-biztalk-adapter-pack-2016.md)有关你可以使用这些属性的值。</span><span class="sxs-lookup"><span data-stu-id="c4945-134">Refer to the table in **Install in silent mode** at [Installing BAP](../adapters-and-accelerators/installing-the-biztalk-adapter-pack-2016.md) for information about the values that you can use for these properties.</span></span>  
  
     <span data-ttu-id="c4945-135">你还可以通过为 msiexec 命令的一部分使用 /f 选项来执行无提示的修复。</span><span class="sxs-lookup"><span data-stu-id="c4945-135">You can also do a silent repair by using the /f option as part of the msiexec command.</span></span> <span data-ttu-id="c4945-136">例如：</span><span class="sxs-lookup"><span data-stu-id="c4945-136">For example:</span></span>  
  
    ```  
    msiexec /i AdaptersSetup.msi /qn /f  
    ```  
  
     <span data-ttu-id="c4945-137">带 /f 选项，可以使用各种不同的组合。</span><span class="sxs-lookup"><span data-stu-id="c4945-137">You can use various different combinations with the /f option.</span></span> <span data-ttu-id="c4945-138">有关 msiexec 命令类型的详细信息`msiexec`上的命令行和按`ENTER`。</span><span class="sxs-lookup"><span data-stu-id="c4945-138">For more information about the msiexec command type `msiexec` on the command line, and press `ENTER`.</span></span> <span data-ttu-id="c4945-139">或转到[http://go.microsoft.com/fwlink/p/?LinkId=103199](http://go.microsoft.com/fwlink/p/?LinkId=103199)。</span><span class="sxs-lookup"><span data-stu-id="c4945-139">Or go to [http://go.microsoft.com/fwlink/p/?LinkId=103199](http://go.microsoft.com/fwlink/p/?LinkId=103199).</span></span>  
  
    > [!IMPORTANT]
    >  <span data-ttu-id="c4945-140">修改时[!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)]在静默模式下的安装，不能更改用于选择加入或退出 CEIP 首选项。</span><span class="sxs-lookup"><span data-stu-id="c4945-140">While modifying the [!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)] installation in the silent mode, you cannot change your preferences for opting in or out of CEIP.</span></span> <span data-ttu-id="c4945-141">在过程中选择该安装将保持，即使你显式设置为 true 或 false 的 CEIP_OPTIN 首选项。</span><span class="sxs-lookup"><span data-stu-id="c4945-141">The preferences you chose during the installation remains, even if you explicitly set the CEIP_OPTIN to true or false.</span></span>  

## <a name="uninstall-or-remove-the-biztalk-adapter-pack"></a><span data-ttu-id="c4945-142">卸载或删除 BizTalk 适配器包</span><span class="sxs-lookup"><span data-stu-id="c4945-142">Uninstall or remove the BizTalk Adapter Pack</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="c4945-143">如果你在要使用的 tRFC 功能的 SQL Server 数据库中创建表[!INCLUDE[adaptersap_short](../includes/adaptersap-short-md.md)]，你必须手动卸载之前删除它们[!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="c4945-143">If you created tables in the SQL Server database to work with the tRFC feature of the [!INCLUDE[adaptersap_short](../includes/adaptersap-short-md.md)], you must manually remove them before uninstalling the [!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)].</span></span> <span data-ttu-id="c4945-144">[!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)]安装副本`SapAdapter-DbScript-Uninstall.sql`文件通常在*\<安装驱动器\>: files\microsoft [!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)]* 。</span><span class="sxs-lookup"><span data-stu-id="c4945-144">The [!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)] installation copies a `SapAdapter-DbScript-Uninstall.sql` file typically at *\<installation drive\>:\Program Files\Microsoft [!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)]*.</span></span> <span data-ttu-id="c4945-145">运行此文件，以删除你创建的表。</span><span class="sxs-lookup"><span data-stu-id="c4945-145">Run this file to remove the tables you created.</span></span>  
  
<span data-ttu-id="c4945-146">完成以下步骤以删除[!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)]从您的计算机。</span><span class="sxs-lookup"><span data-stu-id="c4945-146">Complete the following steps to remove the [!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)] from your computer.</span></span> <span data-ttu-id="c4945-147">请确保你具有[!INCLUDE[afproductnameshort](../includes/afproductnameshort-md.md)]安装之前您运行安装向导。</span><span class="sxs-lookup"><span data-stu-id="c4945-147">Make sure you have the [!INCLUDE[afproductnameshort](../includes/afproductnameshort-md.md)] installed before you run the setup wizard.</span></span>  
  
 <span data-ttu-id="c4945-148">你可以删除[!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)]在交互模式 （安装程序向导） 中或在静默模式下 （命令行）。</span><span class="sxs-lookup"><span data-stu-id="c4945-148">You can remove the [!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)] in interactive mode (setup wizard), or in silent mode (command line).</span></span>
  
### <a name="uninstall-using-the-setup-wizard"></a><span data-ttu-id="c4945-149">卸载使用安装向导</span><span class="sxs-lookup"><span data-stu-id="c4945-149">Uninstall using the setup wizard</span></span>  
  
1.  <span data-ttu-id="c4945-150">在**程序和功能**，选择**卸载程序**。</span><span class="sxs-lookup"><span data-stu-id="c4945-150">In **Programs and features**, select **Uninstall a program**.</span></span>  
  
2.  <span data-ttu-id="c4945-151">右键单击**Microsoft BizTalk 适配器包**，然后选择**卸载**。</span><span class="sxs-lookup"><span data-stu-id="c4945-151">Right-click **Microsoft BizTalk Adapter Pack**, and then select **Uninstall**.</span></span>  
  
### <a name="uninstall-in-silent-mode"></a><span data-ttu-id="c4945-152">在静默模式下卸载</span><span class="sxs-lookup"><span data-stu-id="c4945-152">Uninstall in silent mode</span></span>  
  
1.  <span data-ttu-id="c4945-153">打开命令提示符，并转到根目录下的[!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)]安装程序。</span><span class="sxs-lookup"><span data-stu-id="c4945-153">Open a command prompt, and go to the root directory of the [!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)] installer.</span></span>  
  
2.  <span data-ttu-id="c4945-154">运行以下命令：</span><span class="sxs-lookup"><span data-stu-id="c4945-154">Run the following command:</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="c4945-155">若要删除[!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)]在静默模式下，在基于 x64 的平台上，在以下命令，将`AdaptersSetup.msi`与`AdaptersSetup64.msi`。</span><span class="sxs-lookup"><span data-stu-id="c4945-155">To remove the [!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)] in silent mode on an x64-based platform, in the following commands, replace `AdaptersSetup.msi` with `AdaptersSetup64.msi`.</span></span>  
  
    ```  
    msiexec /i AdaptersSetup.msi /qn REMOVE=DbFeature  
    ```  
  
     <span data-ttu-id="c4945-156">此命令删除[!INCLUDE[adapteroracle_short](../includes/adapteroracle-short-md.md)]从[!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)]安装。</span><span class="sxs-lookup"><span data-stu-id="c4945-156">This command removes the [!INCLUDE[adapteroracle_short](../includes/adapteroracle-short-md.md)] from the [!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)] installation.</span></span>  
  
     <span data-ttu-id="c4945-157">通过提供不同的值`REMOVE`属性，您可以删除从特定组件[!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)]安装。</span><span class="sxs-lookup"><span data-stu-id="c4945-157">By providing different values for the `REMOVE` property, you can remove specific components from the [!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)] installation.</span></span> <span data-ttu-id="c4945-158">中的表是指**在无提示模式下安装**在[安装 BAP](../adapters-and-accelerators/installing-the-biztalk-adapter-pack-2016.md)有关你可以使用此属性的值。</span><span class="sxs-lookup"><span data-stu-id="c4945-158">Refer to the table in **Install in silent mode** at [Installing BAP](../adapters-and-accelerators/installing-the-biztalk-adapter-pack-2016.md) for information about the values that you can use for this property.</span></span>  
  
     <span data-ttu-id="c4945-159">若要完全删除[!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)]，执行以下命令：</span><span class="sxs-lookup"><span data-stu-id="c4945-159">To completely remove the [!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)], execute the following command:</span></span>  
  
    ```  
    msiexec /x AdaptersSetup.msi /qn  
    ```  
  
     <span data-ttu-id="c4945-160">有关 msiexec 命令类型的详细信息`msiexec`上的命令行和按`ENTER`。</span><span class="sxs-lookup"><span data-stu-id="c4945-160">For more information about the msiexec command type `msiexec` on the command line, and press `ENTER`.</span></span> <span data-ttu-id="c4945-161">或转到[http://go.microsoft.com/fwlink/p/?LinkId=103199](http://go.microsoft.com/fwlink/p/?LinkId=103199)。</span><span class="sxs-lookup"><span data-stu-id="c4945-161">Or go to [http://go.microsoft.com/fwlink/p/?LinkId=103199](http://go.microsoft.com/fwlink/p/?LinkId=103199).</span></span>
  
## <a name="remove-the-bindings"></a><span data-ttu-id="c4945-162">删除绑定</span><span class="sxs-lookup"><span data-stu-id="c4945-162">Remove the bindings</span></span>  
 <span data-ttu-id="c4945-163">完成这些步骤*仅*如果安装向导无法从 machine.config 文件中删除适配器绑定或.NET Framework 数据提供程序注册。</span><span class="sxs-lookup"><span data-stu-id="c4945-163">Complete these steps *only* if the setup wizard fails to remove the adapter bindings or .NET Framework Data Provider registration from the machine.config file.</span></span>  
  
1.  <span data-ttu-id="c4945-164">转到计算机上的 machine.config 文件。</span><span class="sxs-lookup"><span data-stu-id="c4945-164">Go to the machine.config file on the computer.</span></span> <span data-ttu-id="c4945-165">例如，在 32 位平台上，machine.config 位于下*\<系统驱动器\>: \WINDOWS\Microsoft.NET\Framework\\< 版本\>\CONFIG*。</span><span class="sxs-lookup"><span data-stu-id="c4945-165">For example, on a 32-bit platform, the machine.config is available under *\<system drive\>:\WINDOWS\Microsoft.NET\Framework\\<version\>\CONFIG*.</span></span>  
  
2.  <span data-ttu-id="c4945-166">打开使用文本编辑器的文件。</span><span class="sxs-lookup"><span data-stu-id="c4945-166">Open the file using a text editor.</span></span>  
  
3.  <span data-ttu-id="c4945-167">删除适配器绑定注册：</span><span class="sxs-lookup"><span data-stu-id="c4945-167">Remove the adapter binding registration:</span></span>  
  
    1.  <span data-ttu-id="c4945-168">搜索`system.serviceModel`元素，并删除以下从元素：</span><span class="sxs-lookup"><span data-stu-id="c4945-168">Search for the `system.serviceModel` element, and remove the following from under the element:</span></span>  
  
        ```  
        <client>  
          <endpoint binding="sapBinding" contract="IMetadataExchange" name="sap" />  
          <endpoint binding="siebelBinding" contract="IMetadataExchange" name="siebel" />  
          <endpoint binding="oracleDBBinding" contract="IMetadataExchange" name="oracleDb" />  
          <endpoint binding="OracleEBSBinding" contract="IMetadataExchange" name="oracleEBS" />  
          <endpoint binding="sqlBinding" contract="IMetadataExchange" name="mssql" />  
        </client>  
  
        ```  
  
    2.  <span data-ttu-id="c4945-169">搜索`bindingElementExtensions`system.serviceModel\extensions 下的元素。</span><span class="sxs-lookup"><span data-stu-id="c4945-169">Search for the `bindingElementExtensions` element under system.serviceModel\extensions.</span></span>  
  
    3.  <span data-ttu-id="c4945-170">删除以下各节下的`bindingElementExtensions`节点，具体取决于可用的适配器绑定。</span><span class="sxs-lookup"><span data-stu-id="c4945-170">Remove the following sections under the `bindingElementExtensions` node, depending on the available adapter binding.</span></span> <span data-ttu-id="c4945-171">如果安装向导删除任何失败，则必须删除所有绑定。</span><span class="sxs-lookup"><span data-stu-id="c4945-171">You must remove all the bindings if the setup wizard fails to remove any.</span></span>  
  
         <span data-ttu-id="c4945-172">有关[!INCLUDE[adaptersap_short](../includes/adaptersap-short-md.md)]，删除：</span><span class="sxs-lookup"><span data-stu-id="c4945-172">For [!INCLUDE[adaptersap_short](../includes/adaptersap-short-md.md)], remove:</span></span>  
  
        ```  
        <add name="sapAdapter" type="Microsoft.Adapters.SAP.SAPAdapterExtensionElement,Microsoft.Adapters.SAP, Version=<version>, Culture=neutral, PublicKeyToken=<public key>" />  
        ```  
  
         <span data-ttu-id="c4945-173">有关[!INCLUDE[adaptersiebel_short](../includes/adaptersiebel-short-md.md)]，删除：</span><span class="sxs-lookup"><span data-stu-id="c4945-173">For [!INCLUDE[adaptersiebel_short](../includes/adaptersiebel-short-md.md)], remove:</span></span>  
  
        ```  
        <add name="siebelAdapter" type="Microsoft.Adapters.Siebel.SiebelAdapterExtensionElement,Microsoft.Adapters.Siebel, Version=<version>, Culture=neutral, PublicKeyToken=<public key>" />  
        ```  
  
         <span data-ttu-id="c4945-174">有关[!INCLUDE[adapteroracle_short](../includes/adapteroracle-short-md.md)]，删除：</span><span class="sxs-lookup"><span data-stu-id="c4945-174">For [!INCLUDE[adapteroracle_short](../includes/adapteroracle-short-md.md)], remove:</span></span>  
  
        ```  
        <add name="oracleDBAdapter" type="Microsoft.Adapters.OracleDB.OracleDBAdapterExtensionElement,Microsoft.Adapters.OracleDB, Version=<version>, Culture=neutral, PublicKeyToken=<public key>" />  
        ```  
  
         <span data-ttu-id="c4945-175">有关[!INCLUDE[adapteroraclebusinessshort](../includes/adapteroraclebusinessshort-md.md)]，删除：</span><span class="sxs-lookup"><span data-stu-id="c4945-175">For [!INCLUDE[adapteroraclebusinessshort](../includes/adapteroraclebusinessshort-md.md)], remove:</span></span>  
  
        ```  
        <add name="OracleEBSAdapter" type="Microsoft.Adapters.OracleEBS.OracleEBSBindingElementExtensionElement, Microsoft.Adapters.OracleEBS, Version=<version>, Culture=neutral, PublicKeyToken=<public key>" />  
        ```  
  
         <span data-ttu-id="c4945-176">有关[!INCLUDE[adaptersqlshort](../includes/adaptersqlshort-md.md)]，删除：</span><span class="sxs-lookup"><span data-stu-id="c4945-176">For [!INCLUDE[adaptersqlshort](../includes/adaptersqlshort-md.md)], remove:</span></span>  
  
        ```  
        <add name="sqlAdapter" type="Microsoft.Adapters.Sql.SqlAdapterBindingElementExtensionElement,Microsoft.Adapters.Sql, Version=<version>, Culture=neutral, PublicKeyToken=<public key>" />  
        ```  
  
    4.  <span data-ttu-id="c4945-177">搜索`bindingExtensions`system.serviceModel\extensions 下的元素。</span><span class="sxs-lookup"><span data-stu-id="c4945-177">Search for the `bindingExtensions` element under system.serviceModel\extensions.</span></span>  
  
    5.  <span data-ttu-id="c4945-178">删除以下各节下的`bindingExtensions`节点，具体取决于可用的适配器绑定。</span><span class="sxs-lookup"><span data-stu-id="c4945-178">Remove the following sections under the `bindingExtensions` node, depending on the available adapter binding.</span></span> <span data-ttu-id="c4945-179">如果安装向导删除任何失败，则必须删除所有绑定。</span><span class="sxs-lookup"><span data-stu-id="c4945-179">You must remove all the bindings if the setup wizard fails to remove any.</span></span>  
  
         <span data-ttu-id="c4945-180">有关[!INCLUDE[adaptersap_short](../includes/adaptersap-short-md.md)]，删除：</span><span class="sxs-lookup"><span data-stu-id="c4945-180">For [!INCLUDE[adaptersap_short](../includes/adaptersap-short-md.md)], remove:</span></span>  
  
        ```  
        <add name="sapBinding" type="Microsoft.Adapters.SAP.SAPAdapterBindingSection,Microsoft.Adapters.SAP, Version=<version>, Culture=neutral, PublicKeyToken=<public key>" />  
        ```  
  
         <span data-ttu-id="c4945-181">有关[!INCLUDE[adaptersiebel_short](../includes/adaptersiebel-short-md.md)]，删除：</span><span class="sxs-lookup"><span data-stu-id="c4945-181">For [!INCLUDE[adaptersiebel_short](../includes/adaptersiebel-short-md.md)], remove:</span></span>  
  
        ```  
        <add name="siebelBinding" type="Microsoft.Adapters.Siebel.SiebelAdapterBindingSection,Microsoft.Adapters.Siebel, Version=<version>, Culture=neutral, PublicKeyToken=<public key>" />  
        ```  
  
         <span data-ttu-id="c4945-182">有关[!INCLUDE[adapteroracle_short](../includes/adapteroracle-short-md.md)]，删除：</span><span class="sxs-lookup"><span data-stu-id="c4945-182">For [!INCLUDE[adapteroracle_short](../includes/adapteroracle-short-md.md)], remove:</span></span>  
  
        ```  
        <add name="oracleDBBinding" type="Microsoft.Adapters.OracleDB.OracleDBAdapterBindingSection,Microsoft.Adapters.OracleDB, Version=<version>, Culture=neutral, PublicKeyToken=<public key>" />  
        ```  
  
         <span data-ttu-id="c4945-183">有关[!INCLUDE[adapteroraclebusinessshort](../includes/adapteroraclebusinessshort-md.md)]，删除：</span><span class="sxs-lookup"><span data-stu-id="c4945-183">For [!INCLUDE[adapteroraclebusinessshort](../includes/adapteroraclebusinessshort-md.md)], remove:</span></span>  
  
        ```  
        <add name="OracleEBSBinding" type="Microsoft.Adapters.OracleEBS.OracleEBSBindingCollectionElement, Microsoft.Adapters.OracleEBS, Version=<version>, Culture=neutral, PublicKeyToken=<public key>" />  
        ```  
  
         <span data-ttu-id="c4945-184">有关[!INCLUDE[adaptersqlshort](../includes/adaptersqlshort-md.md)]，删除：</span><span class="sxs-lookup"><span data-stu-id="c4945-184">For [!INCLUDE[adaptersqlshort](../includes/adaptersqlshort-md.md)], remove:</span></span>  
  
        ```  
        <add name="sqlBinding" type="Microsoft.Adapters.Sql.SqlAdapterBindingCollectionElement,Microsoft.Adapters.Sql, Version=<version>, Culture=neutral, PublicKeyToken=<public key>" />  
        ```  
  
4.  <span data-ttu-id="c4945-185">删除.NET Framework 数据提供程序注册：</span><span class="sxs-lookup"><span data-stu-id="c4945-185">Remove the .NET Framework Data Provider registration:</span></span>  
  
    -   <span data-ttu-id="c4945-186">搜索`DbProviderFactories`system.data 节点下的元素。</span><span class="sxs-lookup"><span data-stu-id="c4945-186">Search for the `DbProviderFactories` element under the system.data node.</span></span>  
  
    -   <span data-ttu-id="c4945-187">查找仍有注册.NET Framework 数据提供程序。</span><span class="sxs-lookup"><span data-stu-id="c4945-187">Look for the .NET Framework Data Providers that are still registered.</span></span> <span data-ttu-id="c4945-188">删除以下各节下的`DbProviderFactories`节点，具体取决于现有的.NET Framework 数据提供程序。</span><span class="sxs-lookup"><span data-stu-id="c4945-188">Remove the following sections under the `DbProviderFactories` node, depending on the existing .NET Framework Data Providers.</span></span> <span data-ttu-id="c4945-189">如果它们存在，则必须删除所有提供程序。</span><span class="sxs-lookup"><span data-stu-id="c4945-189">You must remove all the providers if they exist.</span></span>  
  
         <span data-ttu-id="c4945-190">有关[!INCLUDE[adoprovidersapshort](../includes/adoprovidersapshort-md.md)]，删除：</span><span class="sxs-lookup"><span data-stu-id="c4945-190">For [!INCLUDE[adoprovidersapshort](../includes/adoprovidersapshort-md.md)], remove:</span></span>  
  
        ```  
        <add name="SAPClient Data Provider" invariant="Microsoft.Data.SAPClient"   
            description=".NET Framework Data Provider for mySAP Business Suite"    type="Microsoft.Data.SAPClient.SAPClientFactory,Microsoft.Data.SAPClient, Version=<version>, Culture=neutral, PublicKeyToken=<public key>" />  
        ```  
  
         <span data-ttu-id="c4945-191">有关[!INCLUDE[adoprovidersiebelshort](../includes/adoprovidersiebelshort-md.md)]，删除：</span><span class="sxs-lookup"><span data-stu-id="c4945-191">For [!INCLUDE[adoprovidersiebelshort](../includes/adoprovidersiebelshort-md.md)], remove:</span></span>  
  
        ```  
        <add name="SiebelClient Data Provider" invariant="Microsoft.Data.SiebelClient"  
            description=".NET Framework Data Provider for Siebel eBusiness Applications"  
            type="Microsoft.Data.SiebelClient.SiebelProviderFactory,Microsoft.Data.SiebelClient, Version=<version>, Culture=neutral, PublicKeyToken=<public key>" />  
        ```  
  
5.  <span data-ttu-id="c4945-192">保存并关闭 machine.config 文件。</span><span class="sxs-lookup"><span data-stu-id="c4945-192">Save and close the machine.config file.</span></span>  
  
## <a name="remove-the-custom-rfcs"></a><span data-ttu-id="c4945-193">删除自定义的 Rfc</span><span class="sxs-lookup"><span data-stu-id="c4945-193">Remove the custom RFCs</span></span>  
<span data-ttu-id="c4945-194">完成此步骤以删除 SAP 系统中安装了自定义 Rfc。</span><span class="sxs-lookup"><span data-stu-id="c4945-194">Complete this step to remove the custom RFCs that you installed in the SAP system.</span></span> <span data-ttu-id="c4945-195">请参阅[安装或删除自定义的 Rfc](../adapters-and-accelerators/adapter-sap/install-custom-rfcs-for-the-data-provider-for-sap.md)。</span><span class="sxs-lookup"><span data-stu-id="c4945-195">See [Install or remove custom RFCs](../adapters-and-accelerators/adapter-sap/install-custom-rfcs-for-the-data-provider-for-sap.md).</span></span>  
  
