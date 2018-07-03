---
title: 添加和删除自定义 Functoid 从 Visual Studio 工具箱 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 28f798cc-da97-4332-a842-ba87ac7b13b8
caps.latest.revision: 20
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 8a0ddbab8a116369b6edb39623cd73a16362a3db
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "37013086"
---
# <a name="adding-and-removing-custom-functoids-from-the-visual-studio-toolbox"></a><span data-ttu-id="3e1a6-102">从 Visual Studio 工具箱添加和删除自定义 Functoid</span><span class="sxs-lookup"><span data-stu-id="3e1a6-102">Adding and Removing Custom Functoids from the Visual Studio Toolbox</span></span>
<span data-ttu-id="3e1a6-103">本主题将介绍如何向 [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] 工具箱添加以及从中删除自定义 functoid。</span><span class="sxs-lookup"><span data-stu-id="3e1a6-103">This topic describes how to add custom functoids to and remove custom functoids from the [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] Toolbox.</span></span>  
  
## <a name="adding-custom-functoids-to-visual-studio"></a><span data-ttu-id="3e1a6-104">向 Visual Studio 添加自定义 functoid</span><span class="sxs-lookup"><span data-stu-id="3e1a6-104">Adding Custom Functoids to Visual Studio</span></span>  
 <span data-ttu-id="3e1a6-105">自定义 functoid 只有在添加到 [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] 工具箱后才可以在映射中使用。</span><span class="sxs-lookup"><span data-stu-id="3e1a6-105">Custom functoids must be added to the [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] Toolbox before they can be used in a map.</span></span> <span data-ttu-id="3e1a6-106">使用以下过程可以添加自定义 functoid。</span><span class="sxs-lookup"><span data-stu-id="3e1a6-106">Use the following procedure to add custom functoids.</span></span>  
  
#### <a name="to-add-a-custom-functoid"></a><span data-ttu-id="3e1a6-107">添加自定义 functoid</span><span class="sxs-lookup"><span data-stu-id="3e1a6-107">To add a custom functoid</span></span>  
  
1. <span data-ttu-id="3e1a6-108">向 [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] 工具箱添加 functoid。</span><span class="sxs-lookup"><span data-stu-id="3e1a6-108">Add the functoid to the [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] Toolbox.</span></span>  
  
   1. <span data-ttu-id="3e1a6-109">用 Windows 资源管理器找到实现自定义 functoid 的程序集。</span><span class="sxs-lookup"><span data-stu-id="3e1a6-109">Using Windows Explorer, find the assembly that implements your custom functoids.</span></span>  
  
   2. <span data-ttu-id="3e1a6-110">将复制到的程序集\< *BizTalk Server 安装文件夹*\>**\Developer Tools\Mapper 扩展**目录。</span><span class="sxs-lookup"><span data-stu-id="3e1a6-110">Copy the assembly to the \<*BizTalk Server installation folder*\>**\Developer Tools\Mapper Extensions** directory.</span></span> <span data-ttu-id="3e1a6-111">这是 BizTalk 映射器查找自定义 functoid 的位置。</span><span class="sxs-lookup"><span data-stu-id="3e1a6-111">This is where BizTalk Mapper looks for custom functoids.</span></span>  
  
   3. <span data-ttu-id="3e1a6-112">从[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]BizTalk 项目，在**工具**菜单中，单击**选择工具箱项**。</span><span class="sxs-lookup"><span data-stu-id="3e1a6-112">From a [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] BizTalk project, on the **Tools** menu, click **Choose Toolbox Items**.</span></span>  
  
   4. <span data-ttu-id="3e1a6-113">在中**选择工具箱项**对话框中，单击**BizTalk 映射器 Functoid**选项卡。</span><span class="sxs-lookup"><span data-stu-id="3e1a6-113">In the **Choose Toolbox items** dialog box, click the **BizTalk Mapper Functoids** tab.</span></span>  
  
   5. <span data-ttu-id="3e1a6-114">单击**重置**，然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="3e1a6-114">Click **Reset**, and then click **OK**.</span></span> <span data-ttu-id="3e1a6-115">此进程可能需要花费一些时间。</span><span class="sxs-lookup"><span data-stu-id="3e1a6-115">This process may take a few moments.</span></span>  
  
       <span data-ttu-id="3e1a6-116">现在，自定义 functoid 应该出现在工具箱中的与其类别相匹配的选项卡下。</span><span class="sxs-lookup"><span data-stu-id="3e1a6-116">Your custom functoids should now appear in the Toolbox under tabs matching their category.</span></span>  
  
      <span data-ttu-id="3e1a6-117">\- 或 -</span><span class="sxs-lookup"><span data-stu-id="3e1a6-117">\- OR -</span></span>  
  
   6. <span data-ttu-id="3e1a6-118">从[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]BizTalk 项目，在**工具**菜单中，单击**选择工具箱项**。</span><span class="sxs-lookup"><span data-stu-id="3e1a6-118">From a [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] BizTalk project, on the **Tools** menu, click **Choose Toolbox Items**.</span></span>  
  
   7. <span data-ttu-id="3e1a6-119">在中**选择工具箱项**对话框中，单击**BizTalk 映射器 Functoid**选项卡。</span><span class="sxs-lookup"><span data-stu-id="3e1a6-119">In the **Choose Toolbox items** dialog box, click the **BizTalk Mapper Functoids** tab.</span></span>  
  
   8. <span data-ttu-id="3e1a6-120">单击**重置**，然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="3e1a6-120">Click **Reset**, and then click **OK**.</span></span>  
  
      > [!NOTE]
      >  <span data-ttu-id="3e1a6-121">如果自定义 functoid 没有公开任何内联代码，请确保全局程序集缓存中包含其程序集。</span><span class="sxs-lookup"><span data-stu-id="3e1a6-121">If your custom functoid does not expose any inline code, make sure its assembly is made available in the global assembly cache.</span></span>  
  
   9. <span data-ttu-id="3e1a6-122">上**文件**菜单上，单击**退出**以关闭[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="3e1a6-122">On the **File** menu, click **Exit** to close [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)].</span></span>  
  
   10. <span data-ttu-id="3e1a6-123">启动**Visual Studio 命令提示符**。</span><span class="sxs-lookup"><span data-stu-id="3e1a6-123">Start **Visual Studio Command Prompt**.</span></span>  
  
   11. <span data-ttu-id="3e1a6-124">在命令提示符处，键入**devenv /setup**。</span><span class="sxs-lookup"><span data-stu-id="3e1a6-124">At the command prompt, type **devenv /setup**.</span></span>  
  
   12. <span data-ttu-id="3e1a6-125">启动**Microsoft Visual Studio**。</span><span class="sxs-lookup"><span data-stu-id="3e1a6-125">Start **Microsoft Visual Studio**.</span></span>  
  
        <span data-ttu-id="3e1a6-126">此时自定义 functoid 应出现在相应的选项卡中。</span><span class="sxs-lookup"><span data-stu-id="3e1a6-126">The custom functoid(s) should appear in the appropriate tab.</span></span>  
  
2. <span data-ttu-id="3e1a6-127">将相应程序集添加到全局程序集缓存中。</span><span class="sxs-lookup"><span data-stu-id="3e1a6-127">Add the assembly to the global assembly cache.</span></span> <span data-ttu-id="3e1a6-128">如果程序集只包含内联 functoid，则可以跳过此步骤。</span><span class="sxs-lookup"><span data-stu-id="3e1a6-128">If your assembly contains only inline functoids, then you can skip this step.</span></span>  
  
   1.  <span data-ttu-id="3e1a6-129">启动**Visual Studio 命令提示符**。</span><span class="sxs-lookup"><span data-stu-id="3e1a6-129">Start **Visual Studio Command Prompt**.</span></span>  
  
   2.  <span data-ttu-id="3e1a6-130">切换到包含你的程序集的文件夹。</span><span class="sxs-lookup"><span data-stu-id="3e1a6-130">Switch to the folder containing your assembly.</span></span>  
  
   3.  <span data-ttu-id="3e1a6-131">在命令提示符处，键入**gacutil /if < assembly_path >**。</span><span class="sxs-lookup"><span data-stu-id="3e1a6-131">At the command prompt, type **gacutil /if <assembly_path >**.</span></span> <span data-ttu-id="3e1a6-132">例如，如果程序集名为 FunctoidLibrary.dll，则键入**gacutil /if FunctoidLibrary.dll**。</span><span class="sxs-lookup"><span data-stu-id="3e1a6-132">For example, if your assembly name is FunctoidLibrary.dll, then type **gacutil /if FunctoidLibrary.dll**.</span></span>  
  
   4.  <span data-ttu-id="3e1a6-133">在完成后，请键入**退出**。</span><span class="sxs-lookup"><span data-stu-id="3e1a6-133">When you are finished, type **exit**.</span></span>  
  
## <a name="removing-custom-functoids-from-visual-studio"></a><span data-ttu-id="3e1a6-134">从 Visual Studio 中删除自定义 functoid</span><span class="sxs-lookup"><span data-stu-id="3e1a6-134">Removing Custom Functoids from Visual Studio</span></span>  
 <span data-ttu-id="3e1a6-135">使用以下过程可以删除自定义 functoid。</span><span class="sxs-lookup"><span data-stu-id="3e1a6-135">Use the following procedure to remove custom functoids.</span></span>  
  
#### <a name="to-remove-a-custom-functoid"></a><span data-ttu-id="3e1a6-136">删除自定义 functoid</span><span class="sxs-lookup"><span data-stu-id="3e1a6-136">To remove a custom functoid</span></span>  
  
1. <span data-ttu-id="3e1a6-137">删除 functoid 从[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]工具箱。</span><span class="sxs-lookup"><span data-stu-id="3e1a6-137">Remove the functoid from the [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] Toolbox.</span></span>  
  
   1. <span data-ttu-id="3e1a6-138">从[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]BizTalk 项目，在**工具**菜单中，单击**选择工具箱项**。</span><span class="sxs-lookup"><span data-stu-id="3e1a6-138">From a [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] BizTalk project, on the **Tools** menu, click **Choose Toolbox Items**.</span></span>  
  
   2. <span data-ttu-id="3e1a6-139">在中**选择工具箱项**对话框中，单击**BizTalk 映射器 Functoid**选项卡。</span><span class="sxs-lookup"><span data-stu-id="3e1a6-139">In the **Choose Toolbox items** dialog box, click the **BizTalk Mapper Functoids** tab.</span></span>  
  
   3. <span data-ttu-id="3e1a6-140">在列表中，选择查找自定义 functoid**删除**复选框，然后依次**确定**。</span><span class="sxs-lookup"><span data-stu-id="3e1a6-140">Find the custom functoid in the list, select the **Remove** check box, and then click **OK**.</span></span>  
  
      <span data-ttu-id="3e1a6-141">\- 或 -</span><span class="sxs-lookup"><span data-stu-id="3e1a6-141">\- OR -</span></span>  
  
   4. <span data-ttu-id="3e1a6-142">在编辑中的地图[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]BizTalk 项目中，单击**工具箱**选项卡打开工具箱面板。</span><span class="sxs-lookup"><span data-stu-id="3e1a6-142">While editing a map in a [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] BizTalk project, click the **Toolbox** tab to bring up the Toolbox Palette.</span></span>  
  
   5. <span data-ttu-id="3e1a6-143">单击包含自定义 functoid 的 functoid 组。</span><span class="sxs-lookup"><span data-stu-id="3e1a6-143">Click the functoid group containing your custom functoid.</span></span>  
  
   6. <span data-ttu-id="3e1a6-144">右键单击你想要删除，然后单击的 functoid**删除**或按 delete 键。</span><span class="sxs-lookup"><span data-stu-id="3e1a6-144">Right-click the functoid you want to remove, and then click **Delete** or press the delete key.</span></span>  
  
2. <span data-ttu-id="3e1a6-145">删除 functoid 程序集从**Developer Tools\Mapper Extensions**目录。</span><span class="sxs-lookup"><span data-stu-id="3e1a6-145">Remove the functoid assembly from the **Developer Tools\Mapper Extensions** directory.</span></span>  
  
   > [!CAUTION]
   >  <span data-ttu-id="3e1a6-146">如果程序集包含活动的 functoid，请不要删除它。</span><span class="sxs-lookup"><span data-stu-id="3e1a6-146">If an assembly contains active functoids, then do not remove it.</span></span> <span data-ttu-id="3e1a6-147">因为这样做将中断其他映射。</span><span class="sxs-lookup"><span data-stu-id="3e1a6-147">Doing so will break other maps.</span></span>  
  
   1. <span data-ttu-id="3e1a6-148">启动 Windows 资源管理器并导航到**Developer Tools\Mapper Extensions**目录的[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="3e1a6-148">Start Windows Explorer and navigate to the **Developer Tools\Mapper Extensions** directory of [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].</span></span>  
  
   2. <span data-ttu-id="3e1a6-149">右键单击包含所删除的 functoid 的程序集，然后单击**删除**来删除该文件。</span><span class="sxs-lookup"><span data-stu-id="3e1a6-149">Right-click the assembly containing the removed functoid, and then click **Delete** to remove the file.</span></span>  
  
3. <span data-ttu-id="3e1a6-150">从全局程序集缓存中删除 functoid 程序集。</span><span class="sxs-lookup"><span data-stu-id="3e1a6-150">Remove the functoid assembly from the global assembly cache.</span></span> <span data-ttu-id="3e1a6-151">如果程序集只包含内联 functoid，则可以跳过此步骤。</span><span class="sxs-lookup"><span data-stu-id="3e1a6-151">If your assembly contains only inline functoids, then you can skip this step.</span></span>  
  
   > [!CAUTION]
   >  <span data-ttu-id="3e1a6-152">如果该程序集包含活动的 functoid，请不要从全局程序集缓存中删除它。</span><span class="sxs-lookup"><span data-stu-id="3e1a6-152">If an assembly contains active functoids, then do not remove it from the global assembly cache.</span></span> <span data-ttu-id="3e1a6-153">因为这样做将中断其他映射。</span><span class="sxs-lookup"><span data-stu-id="3e1a6-153">Doing so will break other maps.</span></span>  
  
   1.  <span data-ttu-id="3e1a6-154">启动**Visual Studio 命令提示符**。</span><span class="sxs-lookup"><span data-stu-id="3e1a6-154">Start **Visual Studio Command Prompt**.</span></span>  
  
   2.  <span data-ttu-id="3e1a6-155">在命令提示符处，键入**gacutil /u < assembly_display_name >**。</span><span class="sxs-lookup"><span data-stu-id="3e1a6-155">At the command prompt, type **gacutil /u <assembly_display_name>**.</span></span> <span data-ttu-id="3e1a6-156">例如，如果程序集名为 FunctoidLibrary.dll，则键入**gacutil /if FunctoidLibrary**。</span><span class="sxs-lookup"><span data-stu-id="3e1a6-156">For example, if your assembly name is FunctoidLibrary.dll, then type **gacutil /if FunctoidLibrary**.</span></span>  
  
   3.  <span data-ttu-id="3e1a6-157">在完成后，请键入**退出**。</span><span class="sxs-lookup"><span data-stu-id="3e1a6-157">When you are finished, type **exit**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3e1a6-158">请参阅</span><span class="sxs-lookup"><span data-stu-id="3e1a6-158">See Also</span></span>  
 [<span data-ttu-id="3e1a6-159">开发自定义 Functoid</span><span class="sxs-lookup"><span data-stu-id="3e1a6-159">Developing Custom Functoids</span></span>](../core/developing-custom-functoids.md)