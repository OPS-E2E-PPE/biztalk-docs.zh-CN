---
title: "添加和删除自定义 Functoid 从 Visual Studio 工具箱 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 28f798cc-da97-4332-a842-ba87ac7b13b8
caps.latest.revision: "20"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 8b34d546de0bbb2a79300c4f672bdfcecdab5958
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="adding-and-removing-custom-functoids-from-the-visual-studio-toolbox"></a><span data-ttu-id="bf464-102">从 Visual Studio 工具箱添加和删除自定义 Functoid</span><span class="sxs-lookup"><span data-stu-id="bf464-102">Adding and Removing Custom Functoids from the Visual Studio Toolbox</span></span>
<span data-ttu-id="bf464-103">本主题将介绍如何向 [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] 工具箱添加以及从中删除自定义 functoid。</span><span class="sxs-lookup"><span data-stu-id="bf464-103">This topic describes how to add custom functoids to and remove custom functoids from the [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] Toolbox.</span></span>  
  
## <a name="adding-custom-functoids-to-visual-studio"></a><span data-ttu-id="bf464-104">向 Visual Studio 添加自定义 functoid</span><span class="sxs-lookup"><span data-stu-id="bf464-104">Adding Custom Functoids to Visual Studio</span></span>  
 <span data-ttu-id="bf464-105">自定义 functoid 只有在添加到 [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] 工具箱后才可以在映射中使用。</span><span class="sxs-lookup"><span data-stu-id="bf464-105">Custom functoids must be added to the [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] Toolbox before they can be used in a map.</span></span> <span data-ttu-id="bf464-106">使用以下过程可以添加自定义 functoid。</span><span class="sxs-lookup"><span data-stu-id="bf464-106">Use the following procedure to add custom functoids.</span></span>  
  
#### <a name="to-add-a-custom-functoid"></a><span data-ttu-id="bf464-107">添加自定义 functoid</span><span class="sxs-lookup"><span data-stu-id="bf464-107">To add a custom functoid</span></span>  
  
1.  <span data-ttu-id="bf464-108">向 [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] 工具箱添加 functoid。</span><span class="sxs-lookup"><span data-stu-id="bf464-108">Add the functoid to the [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] Toolbox.</span></span>  
  
    1.  <span data-ttu-id="bf464-109">用 Windows 资源管理器找到实现自定义 functoid 的程序集。</span><span class="sxs-lookup"><span data-stu-id="bf464-109">Using Windows Explorer, find the assembly that implements your custom functoids.</span></span>  
  
    2.  <span data-ttu-id="bf464-110">将复制到的程序集\< *BizTalk Server 安装文件夹*>**\Developer Tools\Mapper 扩展**目录。</span><span class="sxs-lookup"><span data-stu-id="bf464-110">Copy the assembly to the \<*BizTalk Server installation folder*>**\Developer Tools\Mapper Extensions** directory.</span></span> <span data-ttu-id="bf464-111">这是 BizTalk 映射器查找自定义 functoid 的位置。</span><span class="sxs-lookup"><span data-stu-id="bf464-111">This is where BizTalk Mapper looks for custom functoids.</span></span>  
  
    3.  <span data-ttu-id="bf464-112">从[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]BizTalk 项目，在**工具**菜单上，单击**选择工具箱项**。</span><span class="sxs-lookup"><span data-stu-id="bf464-112">From a [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] BizTalk project, on the **Tools** menu, click **Choose Toolbox Items**.</span></span>  
  
    4.  <span data-ttu-id="bf464-113">在**选择工具箱项**对话框中，单击**BizTalk 映射程序 Functoid**选项卡。</span><span class="sxs-lookup"><span data-stu-id="bf464-113">In the **Choose Toolbox items** dialog box, click the **BizTalk Mapper Functoids** tab.</span></span>  
  
    5.  <span data-ttu-id="bf464-114">单击**重置**，然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="bf464-114">Click **Reset**, and then click **OK**.</span></span> <span data-ttu-id="bf464-115">此进程可能需要花费一些时间。</span><span class="sxs-lookup"><span data-stu-id="bf464-115">This process may take a few moments.</span></span>  
  
         <span data-ttu-id="bf464-116">现在，自定义 functoid 应该出现在工具箱中的与其类别相匹配的选项卡下。</span><span class="sxs-lookup"><span data-stu-id="bf464-116">Your custom functoids should now appear in the Toolbox under tabs matching their category.</span></span>  
  
     <span data-ttu-id="bf464-117">\- 或 -</span><span class="sxs-lookup"><span data-stu-id="bf464-117">\- OR -</span></span>  
  
    1.  <span data-ttu-id="bf464-118">从[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]BizTalk 项目，在**工具**菜单上，单击**选择工具箱项**。</span><span class="sxs-lookup"><span data-stu-id="bf464-118">From a [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] BizTalk project, on the **Tools** menu, click **Choose Toolbox Items**.</span></span>  
  
    2.  <span data-ttu-id="bf464-119">在**选择工具箱项**对话框中，单击**BizTalk 映射程序 Functoid**选项卡。</span><span class="sxs-lookup"><span data-stu-id="bf464-119">In the **Choose Toolbox items** dialog box, click the **BizTalk Mapper Functoids** tab.</span></span>  
  
    3.  <span data-ttu-id="bf464-120">单击**重置**，然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="bf464-120">Click **Reset**, and then click **OK**.</span></span>  
  
        > [!NOTE]
        >  <span data-ttu-id="bf464-121">如果自定义 functoid 没有公开任何内联代码，请确保全局程序集缓存中包含其程序集。</span><span class="sxs-lookup"><span data-stu-id="bf464-121">If your custom functoid does not expose any inline code, make sure its assembly is made available in the global assembly cache.</span></span>  
  
    4.  <span data-ttu-id="bf464-122">上**文件**菜单上，单击**退出**关闭[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="bf464-122">On the **File** menu, click **Exit** to close [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)].</span></span>  
  
    5.  <span data-ttu-id="bf464-123">启动**Visual Studio 命令提示**。</span><span class="sxs-lookup"><span data-stu-id="bf464-123">Start **Visual Studio Command Prompt**.</span></span>  
  
    6.  <span data-ttu-id="bf464-124">在命令提示符处，键入**devenv /setup**。</span><span class="sxs-lookup"><span data-stu-id="bf464-124">At the command prompt, type **devenv /setup**.</span></span>  
  
    7.  <span data-ttu-id="bf464-125">启动**Microsoft Visual Studio**。</span><span class="sxs-lookup"><span data-stu-id="bf464-125">Start **Microsoft Visual Studio**.</span></span>  
  
         <span data-ttu-id="bf464-126">此时自定义 functoid 应出现在相应的选项卡中。</span><span class="sxs-lookup"><span data-stu-id="bf464-126">The custom functoid(s) should appear in the appropriate tab.</span></span>  
  
2.  <span data-ttu-id="bf464-127">将相应程序集添加到全局程序集缓存中。</span><span class="sxs-lookup"><span data-stu-id="bf464-127">Add the assembly to the global assembly cache.</span></span> <span data-ttu-id="bf464-128">如果程序集只包含内联 functoid，则可以跳过此步骤。</span><span class="sxs-lookup"><span data-stu-id="bf464-128">If your assembly contains only inline functoids, then you can skip this step.</span></span>  
  
    1.  <span data-ttu-id="bf464-129">启动**Visual Studio 命令提示**。</span><span class="sxs-lookup"><span data-stu-id="bf464-129">Start **Visual Studio Command Prompt**.</span></span>  
  
    2.  <span data-ttu-id="bf464-130">切换到包含你的程序集的文件夹。</span><span class="sxs-lookup"><span data-stu-id="bf464-130">Switch to the folder containing your assembly.</span></span>  
  
    3.  <span data-ttu-id="bf464-131">在命令提示符处，键入**gacutil /if < assembly_path >**。</span><span class="sxs-lookup"><span data-stu-id="bf464-131">At the command prompt, type **gacutil /if <assembly_path >**.</span></span> <span data-ttu-id="bf464-132">例如，如果你的程序集名称为 FunctoidLibrary.dll，然后键入**gacutil /if FunctoidLibrary.dll**。</span><span class="sxs-lookup"><span data-stu-id="bf464-132">For example, if your assembly name is FunctoidLibrary.dll, then type **gacutil /if FunctoidLibrary.dll**.</span></span>  
  
    4.  <span data-ttu-id="bf464-133">当完成后时，请键入**退出**。</span><span class="sxs-lookup"><span data-stu-id="bf464-133">When you are finished, type **exit**.</span></span>  
  
## <a name="removing-custom-functoids-from-visual-studio"></a><span data-ttu-id="bf464-134">从 Visual Studio 中删除自定义 functoid</span><span class="sxs-lookup"><span data-stu-id="bf464-134">Removing Custom Functoids from Visual Studio</span></span>  
 <span data-ttu-id="bf464-135">使用以下过程可以删除自定义 functoid。</span><span class="sxs-lookup"><span data-stu-id="bf464-135">Use the following procedure to remove custom functoids.</span></span>  
  
#### <a name="to-remove-a-custom-functoid"></a><span data-ttu-id="bf464-136">删除自定义 functoid</span><span class="sxs-lookup"><span data-stu-id="bf464-136">To remove a custom functoid</span></span>  
  
1.  <span data-ttu-id="bf464-137">删除从 functoid[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]工具箱。</span><span class="sxs-lookup"><span data-stu-id="bf464-137">Remove the functoid from the [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] Toolbox.</span></span>  
  
    1.  <span data-ttu-id="bf464-138">从[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]BizTalk 项目，在**工具**菜单上，单击**选择工具箱项**。</span><span class="sxs-lookup"><span data-stu-id="bf464-138">From a [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] BizTalk project, on the **Tools** menu, click **Choose Toolbox Items**.</span></span>  
  
    2.  <span data-ttu-id="bf464-139">在**选择工具箱项**对话框中，单击**BizTalk 映射程序 Functoid**选项卡。</span><span class="sxs-lookup"><span data-stu-id="bf464-139">In the **Choose Toolbox items** dialog box, click the **BizTalk Mapper Functoids** tab.</span></span>  
  
    3.  <span data-ttu-id="bf464-140">查找在列表中，选择自定义 functoid**删除**复选框，并依次**确定**。</span><span class="sxs-lookup"><span data-stu-id="bf464-140">Find the custom functoid in the list, select the **Remove** check box, and then click **OK**.</span></span>  
  
     <span data-ttu-id="bf464-141">\- 或 -</span><span class="sxs-lookup"><span data-stu-id="bf464-141">\- OR -</span></span>  
  
    1.  <span data-ttu-id="bf464-142">编辑映射中的时[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]BizTalk 项目，单击**工具箱**选项卡以打开工具箱调色板。</span><span class="sxs-lookup"><span data-stu-id="bf464-142">While editing a map in a [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] BizTalk project, click the **Toolbox** tab to bring up the Toolbox Palette.</span></span>  
  
    2.  <span data-ttu-id="bf464-143">单击包含自定义 functoid 的 functoid 组。</span><span class="sxs-lookup"><span data-stu-id="bf464-143">Click the functoid group containing your custom functoid.</span></span>  
  
    3.  <span data-ttu-id="bf464-144">右键单击你想要删除，，然后单击的 functoid**删除**或按 delete 键。</span><span class="sxs-lookup"><span data-stu-id="bf464-144">Right-click the functoid you want to remove, and then click **Delete** or press the delete key.</span></span>  
  
2.  <span data-ttu-id="bf464-145">删除 functoid 集**开发人员 Tools\Mapper 扩展**目录。</span><span class="sxs-lookup"><span data-stu-id="bf464-145">Remove the functoid assembly from the **Developer Tools\Mapper Extensions** directory.</span></span>  
  
    > [!CAUTION]
    >  <span data-ttu-id="bf464-146">如果程序集包含活动的 functoid，请不要删除它。</span><span class="sxs-lookup"><span data-stu-id="bf464-146">If an assembly contains active functoids, then do not remove it.</span></span> <span data-ttu-id="bf464-147">因为这样做将中断其他映射。</span><span class="sxs-lookup"><span data-stu-id="bf464-147">Doing so will break other maps.</span></span>  
  
    1.  <span data-ttu-id="bf464-148">启动 Windows 资源管理器并导航到**开发人员 Tools\Mapper 扩展**目录[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="bf464-148">Start Windows Explorer and navigate to the **Developer Tools\Mapper Extensions** directory of [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].</span></span>  
  
    2.  <span data-ttu-id="bf464-149">右键单击删除 functoid，包含的程序集，然后单击**删除**来删除该文件。</span><span class="sxs-lookup"><span data-stu-id="bf464-149">Right-click the assembly containing the removed functoid, and then click **Delete** to remove the file.</span></span>  
  
3.  <span data-ttu-id="bf464-150">从全局程序集缓存中删除 functoid 程序集。</span><span class="sxs-lookup"><span data-stu-id="bf464-150">Remove the functoid assembly from the global assembly cache.</span></span> <span data-ttu-id="bf464-151">如果程序集只包含内联 functoid，则可以跳过此步骤。</span><span class="sxs-lookup"><span data-stu-id="bf464-151">If your assembly contains only inline functoids, then you can skip this step.</span></span>  
  
    > [!CAUTION]
    >  <span data-ttu-id="bf464-152">如果该程序集包含活动的 functoid，请不要从全局程序集缓存中删除它。</span><span class="sxs-lookup"><span data-stu-id="bf464-152">If an assembly contains active functoids, then do not remove it from the global assembly cache.</span></span> <span data-ttu-id="bf464-153">因为这样做将中断其他映射。</span><span class="sxs-lookup"><span data-stu-id="bf464-153">Doing so will break other maps.</span></span>  
  
    1.  <span data-ttu-id="bf464-154">启动**Visual Studio 命令提示**。</span><span class="sxs-lookup"><span data-stu-id="bf464-154">Start **Visual Studio Command Prompt**.</span></span>  
  
    2.  <span data-ttu-id="bf464-155">在命令提示符处，键入**gacutil /u < assembly_display_name >**。</span><span class="sxs-lookup"><span data-stu-id="bf464-155">At the command prompt, type **gacutil /u <assembly_display_name>**.</span></span> <span data-ttu-id="bf464-156">例如，如果你的程序集名称为 FunctoidLibrary.dll，然后键入**gacutil /if FunctoidLibrary**。</span><span class="sxs-lookup"><span data-stu-id="bf464-156">For example, if your assembly name is FunctoidLibrary.dll, then type **gacutil /if FunctoidLibrary**.</span></span>  
  
    3.  <span data-ttu-id="bf464-157">当完成后时，请键入**退出**。</span><span class="sxs-lookup"><span data-stu-id="bf464-157">When you are finished, type **exit**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bf464-158">另请参阅</span><span class="sxs-lookup"><span data-stu-id="bf464-158">See Also</span></span>  
 [<span data-ttu-id="bf464-159">开发自定义 Functoid</span><span class="sxs-lookup"><span data-stu-id="bf464-159">Developing Custom Functoids</span></span>](../core/developing-custom-functoids.md)