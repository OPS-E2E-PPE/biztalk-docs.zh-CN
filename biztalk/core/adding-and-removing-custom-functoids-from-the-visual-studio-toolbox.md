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
ms.openlocfilehash: 7e3493608606df11a5237287a89cbf79d384800a
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65360907"
---
# <a name="adding-and-removing-custom-functoids-from-the-visual-studio-toolbox"></a><span data-ttu-id="d9b89-102">添加和从 Visual Studio 工具箱中删除自定义 Functoid</span><span class="sxs-lookup"><span data-stu-id="d9b89-102">Adding and Removing Custom Functoids from the Visual Studio Toolbox</span></span>
<span data-ttu-id="d9b89-103">本主题介绍如何添加到自定义 functoid 和删除自定义 functoid 从[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]工具箱。</span><span class="sxs-lookup"><span data-stu-id="d9b89-103">This topic describes how to add custom functoids to and remove custom functoids from the [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] Toolbox.</span></span>  
  
## <a name="adding-custom-functoids-to-visual-studio"></a><span data-ttu-id="d9b89-104">向 Visual Studio 添加自定义 Functoid</span><span class="sxs-lookup"><span data-stu-id="d9b89-104">Adding Custom Functoids to Visual Studio</span></span>  
 <span data-ttu-id="d9b89-105">必须将自定义 functoid 添加到[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]工具箱后才可以映射中使用它们。</span><span class="sxs-lookup"><span data-stu-id="d9b89-105">Custom functoids must be added to the [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] Toolbox before they can be used in a map.</span></span> <span data-ttu-id="d9b89-106">使用以下过程添加自定义 functoid。</span><span class="sxs-lookup"><span data-stu-id="d9b89-106">Use the following procedure to add custom functoids.</span></span>  
  
#### <a name="to-add-a-custom-functoid"></a><span data-ttu-id="d9b89-107">若要添加自定义 functoid</span><span class="sxs-lookup"><span data-stu-id="d9b89-107">To add a custom functoid</span></span>  
  
1. <span data-ttu-id="d9b89-108">添加到 functoid[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]工具箱。</span><span class="sxs-lookup"><span data-stu-id="d9b89-108">Add the functoid to the [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] Toolbox.</span></span>  
  
   1. <span data-ttu-id="d9b89-109">使用 Windows 资源管理器，找到实现自定义 functoid 的程序集。</span><span class="sxs-lookup"><span data-stu-id="d9b89-109">Using Windows Explorer, find the assembly that implements your custom functoids.</span></span>  
  
   2. <span data-ttu-id="d9b89-110">将复制到的程序集\< *BizTalk Server 安装文件夹*\>**\Developer Tools\Mapper 扩展**目录。</span><span class="sxs-lookup"><span data-stu-id="d9b89-110">Copy the assembly to the \<*BizTalk Server installation folder*\>**\Developer Tools\Mapper Extensions** directory.</span></span> <span data-ttu-id="d9b89-111">这是 BizTalk 映射器查找自定义 functoid。</span><span class="sxs-lookup"><span data-stu-id="d9b89-111">This is where BizTalk Mapper looks for custom functoids.</span></span>  
  
   3. <span data-ttu-id="d9b89-112">从[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]BizTalk 项目，在**工具**菜单中，单击**选择工具箱项**。</span><span class="sxs-lookup"><span data-stu-id="d9b89-112">From a [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] BizTalk project, on the **Tools** menu, click **Choose Toolbox Items**.</span></span>  
  
   4. <span data-ttu-id="d9b89-113">在中**选择工具箱项**对话框中，单击**BizTalk 映射器 Functoid**选项卡。</span><span class="sxs-lookup"><span data-stu-id="d9b89-113">In the **Choose Toolbox items** dialog box, click the **BizTalk Mapper Functoids** tab.</span></span>  
  
   5. <span data-ttu-id="d9b89-114">单击**重置**，然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="d9b89-114">Click **Reset**, and then click **OK**.</span></span> <span data-ttu-id="d9b89-115">此过程可能需要一些时间。</span><span class="sxs-lookup"><span data-stu-id="d9b89-115">This process may take a few moments.</span></span>  
  
       <span data-ttu-id="d9b89-116">现在，自定义 functoid 应出现在与其类别相匹配的选项卡下的工具箱。</span><span class="sxs-lookup"><span data-stu-id="d9b89-116">Your custom functoids should now appear in the Toolbox under tabs matching their category.</span></span>  
  
      <span data-ttu-id="d9b89-117">\- 或 -</span><span class="sxs-lookup"><span data-stu-id="d9b89-117">\- OR -</span></span>  
  
   6. <span data-ttu-id="d9b89-118">从[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]BizTalk 项目，在**工具**菜单中，单击**选择工具箱项**。</span><span class="sxs-lookup"><span data-stu-id="d9b89-118">From a [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] BizTalk project, on the **Tools** menu, click **Choose Toolbox Items**.</span></span>  
  
   7. <span data-ttu-id="d9b89-119">在中**选择工具箱项**对话框中，单击**BizTalk 映射器 Functoid**选项卡。</span><span class="sxs-lookup"><span data-stu-id="d9b89-119">In the **Choose Toolbox items** dialog box, click the **BizTalk Mapper Functoids** tab.</span></span>  
  
   8. <span data-ttu-id="d9b89-120">单击**重置**，然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="d9b89-120">Click **Reset**, and then click **OK**.</span></span>  
  
      > [!NOTE]
      >  <span data-ttu-id="d9b89-121">如果自定义 functoid 没有公开任何内联代码，请确保它的程序集可在全局程序集缓存中。</span><span class="sxs-lookup"><span data-stu-id="d9b89-121">If your custom functoid does not expose any inline code, make sure its assembly is made available in the global assembly cache.</span></span>  
  
   9. <span data-ttu-id="d9b89-122">上**文件**菜单上，单击**退出**以关闭[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="d9b89-122">On the **File** menu, click **Exit** to close [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)].</span></span>  
  
   10. <span data-ttu-id="d9b89-123">启动**Visual Studio 命令提示符**。</span><span class="sxs-lookup"><span data-stu-id="d9b89-123">Start **Visual Studio Command Prompt**.</span></span>  
  
   11. <span data-ttu-id="d9b89-124">在命令提示符处，键入**devenv /setup**。</span><span class="sxs-lookup"><span data-stu-id="d9b89-124">At the command prompt, type **devenv /setup**.</span></span>  
  
   12. <span data-ttu-id="d9b89-125">启动**Microsoft Visual Studio**。</span><span class="sxs-lookup"><span data-stu-id="d9b89-125">Start **Microsoft Visual Studio**.</span></span>  
  
        <span data-ttu-id="d9b89-126">自定义 functoid 应出现在相应的选项卡中。</span><span class="sxs-lookup"><span data-stu-id="d9b89-126">The custom functoid(s) should appear in the appropriate tab.</span></span>  
  
2. <span data-ttu-id="d9b89-127">将程序集添加到全局程序集缓存中。</span><span class="sxs-lookup"><span data-stu-id="d9b89-127">Add the assembly to the global assembly cache.</span></span> <span data-ttu-id="d9b89-128">如果您的程序集只包含内联 functoid，则可以跳过此步骤。</span><span class="sxs-lookup"><span data-stu-id="d9b89-128">If your assembly contains only inline functoids, then you can skip this step.</span></span>  
  
   1.  <span data-ttu-id="d9b89-129">启动**Visual Studio 命令提示符**。</span><span class="sxs-lookup"><span data-stu-id="d9b89-129">Start **Visual Studio Command Prompt**.</span></span>  
  
   2.  <span data-ttu-id="d9b89-130">切换到包含您的程序集的文件夹。</span><span class="sxs-lookup"><span data-stu-id="d9b89-130">Switch to the folder containing your assembly.</span></span>  
  
   3.  <span data-ttu-id="d9b89-131">在命令提示符处，键入**gacutil /if < assembly_path >**。</span><span class="sxs-lookup"><span data-stu-id="d9b89-131">At the command prompt, type **gacutil /if <assembly_path >**.</span></span> <span data-ttu-id="d9b89-132">例如，如果程序集名为 FunctoidLibrary.dll，则键入**gacutil /if FunctoidLibrary.dll**。</span><span class="sxs-lookup"><span data-stu-id="d9b89-132">For example, if your assembly name is FunctoidLibrary.dll, then type **gacutil /if FunctoidLibrary.dll**.</span></span>  
  
   4.  <span data-ttu-id="d9b89-133">在完成后，请键入**退出**。</span><span class="sxs-lookup"><span data-stu-id="d9b89-133">When you are finished, type **exit**.</span></span>  
  
## <a name="removing-custom-functoids-from-visual-studio"></a><span data-ttu-id="d9b89-134">从 Visual Studio 中删除自定义 Functoid</span><span class="sxs-lookup"><span data-stu-id="d9b89-134">Removing Custom Functoids from Visual Studio</span></span>  
 <span data-ttu-id="d9b89-135">使用以下过程删除自定义 functoid。</span><span class="sxs-lookup"><span data-stu-id="d9b89-135">Use the following procedure to remove custom functoids.</span></span>  
  
#### <a name="to-remove-a-custom-functoid"></a><span data-ttu-id="d9b89-136">若要删除自定义 functoid</span><span class="sxs-lookup"><span data-stu-id="d9b89-136">To remove a custom functoid</span></span>  
  
1. <span data-ttu-id="d9b89-137">删除 functoid 从[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]工具箱。</span><span class="sxs-lookup"><span data-stu-id="d9b89-137">Remove the functoid from the [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] Toolbox.</span></span>  
  
   1. <span data-ttu-id="d9b89-138">从[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]BizTalk 项目，在**工具**菜单中，单击**选择工具箱项**。</span><span class="sxs-lookup"><span data-stu-id="d9b89-138">From a [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] BizTalk project, on the **Tools** menu, click **Choose Toolbox Items**.</span></span>  
  
   2. <span data-ttu-id="d9b89-139">在中**选择工具箱项**对话框中，单击**BizTalk 映射器 Functoid**选项卡。</span><span class="sxs-lookup"><span data-stu-id="d9b89-139">In the **Choose Toolbox items** dialog box, click the **BizTalk Mapper Functoids** tab.</span></span>  
  
   3. <span data-ttu-id="d9b89-140">在列表中，选择查找自定义 functoid**删除**复选框，然后依次**确定**。</span><span class="sxs-lookup"><span data-stu-id="d9b89-140">Find the custom functoid in the list, select the **Remove** check box, and then click **OK**.</span></span>  
  
      <span data-ttu-id="d9b89-141">\- 或 -</span><span class="sxs-lookup"><span data-stu-id="d9b89-141">\- OR -</span></span>  
  
   4. <span data-ttu-id="d9b89-142">在编辑中的地图[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]BizTalk 项目中，单击**工具箱**选项卡打开工具箱面板。</span><span class="sxs-lookup"><span data-stu-id="d9b89-142">While editing a map in a [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] BizTalk project, click the **Toolbox** tab to bring up the Toolbox Palette.</span></span>  
  
   5. <span data-ttu-id="d9b89-143">单击包含自定义 functoid 的 functoid 组。</span><span class="sxs-lookup"><span data-stu-id="d9b89-143">Click the functoid group containing your custom functoid.</span></span>  
  
   6. <span data-ttu-id="d9b89-144">右键单击你想要删除，然后单击的 functoid**删除**或按 delete 键。</span><span class="sxs-lookup"><span data-stu-id="d9b89-144">Right-click the functoid you want to remove, and then click **Delete** or press the delete key.</span></span>  
  
2. <span data-ttu-id="d9b89-145">删除 functoid 程序集从**Developer Tools\Mapper Extensions**目录。</span><span class="sxs-lookup"><span data-stu-id="d9b89-145">Remove the functoid assembly from the **Developer Tools\Mapper Extensions** directory.</span></span>  
  
   > [!CAUTION]
   >  <span data-ttu-id="d9b89-146">如果程序集包含活动的 functoid，请不要删除它。</span><span class="sxs-lookup"><span data-stu-id="d9b89-146">If an assembly contains active functoids, then do not remove it.</span></span> <span data-ttu-id="d9b89-147">执行此操作将中断其他映射。</span><span class="sxs-lookup"><span data-stu-id="d9b89-147">Doing so will break other maps.</span></span>  
  
   1. <span data-ttu-id="d9b89-148">启动 Windows 资源管理器并导航到**Developer Tools\Mapper Extensions**目录的[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="d9b89-148">Start Windows Explorer and navigate to the **Developer Tools\Mapper Extensions** directory of [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].</span></span>  
  
   2. <span data-ttu-id="d9b89-149">右键单击包含所删除的 functoid 的程序集，然后单击**删除**来删除该文件。</span><span class="sxs-lookup"><span data-stu-id="d9b89-149">Right-click the assembly containing the removed functoid, and then click **Delete** to remove the file.</span></span>  
  
3. <span data-ttu-id="d9b89-150">从全局程序集缓存中删除 functoid 程序集。</span><span class="sxs-lookup"><span data-stu-id="d9b89-150">Remove the functoid assembly from the global assembly cache.</span></span> <span data-ttu-id="d9b89-151">如果您的程序集只包含内联 functoid，则可以跳过此步骤。</span><span class="sxs-lookup"><span data-stu-id="d9b89-151">If your assembly contains only inline functoids, then you can skip this step.</span></span>  
  
   > [!CAUTION]
   >  <span data-ttu-id="d9b89-152">如果程序集包含活动的 functoid，请不要删除它从全局程序集缓存。</span><span class="sxs-lookup"><span data-stu-id="d9b89-152">If an assembly contains active functoids, then do not remove it from the global assembly cache.</span></span> <span data-ttu-id="d9b89-153">执行此操作将中断其他映射。</span><span class="sxs-lookup"><span data-stu-id="d9b89-153">Doing so will break other maps.</span></span>  
  
   1.  <span data-ttu-id="d9b89-154">启动**Visual Studio 命令提示符**。</span><span class="sxs-lookup"><span data-stu-id="d9b89-154">Start **Visual Studio Command Prompt**.</span></span>  
  
   2.  <span data-ttu-id="d9b89-155">在命令提示符处，键入**gacutil /u < assembly_display_name >**。</span><span class="sxs-lookup"><span data-stu-id="d9b89-155">At the command prompt, type **gacutil /u <assembly_display_name>**.</span></span> <span data-ttu-id="d9b89-156">例如，如果程序集名为 FunctoidLibrary.dll，则键入**gacutil /if FunctoidLibrary**。</span><span class="sxs-lookup"><span data-stu-id="d9b89-156">For example, if your assembly name is FunctoidLibrary.dll, then type **gacutil /if FunctoidLibrary**.</span></span>  
  
   3.  <span data-ttu-id="d9b89-157">在完成后，请键入**退出**。</span><span class="sxs-lookup"><span data-stu-id="d9b89-157">When you are finished, type **exit**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d9b89-158">请参阅</span><span class="sxs-lookup"><span data-stu-id="d9b89-158">See Also</span></span>  
 [<span data-ttu-id="d9b89-159">开发自定义 Functoid</span><span class="sxs-lookup"><span data-stu-id="d9b89-159">Developing Custom Functoids</span></span>](../core/developing-custom-functoids.md)