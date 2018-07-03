---
title: 取消部署适配器使用 WCF LOB 适配器 SDK |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 98f9a124-9e63-4451-af0e-ffee752fbeac
caps.latest.revision: 13
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 84932fa0a140df157408ad77d9fc6bec8c0823fe
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36974582"
---
# <a name="undeploy-an-adapter-using-the-wcf-lob-adapter-sdk"></a><span data-ttu-id="6d968-102">取消部署适配器使用 WCF LOB 适配器 SDK</span><span class="sxs-lookup"><span data-stu-id="6d968-102">Undeploy an adapter using the WCF LOB adapter SDK</span></span>
<span data-ttu-id="6d968-103">若要取消部署适配器从一台计算机，用户必须执行以下两项任务：</span><span class="sxs-lookup"><span data-stu-id="6d968-103">To undeploy an adapter from a computer, the user needs to perform the following two tasks:</span></span>  
  
1.  <span data-ttu-id="6d968-104">从全局程序集缓存 (GAC) 卸载适配器程序集 （和所有相关程序集）。</span><span class="sxs-lookup"><span data-stu-id="6d968-104">Uninstall the adapter assembly (and any dependent assemblies) from the global assembly cache (GAC).</span></span>  
  
2.  <span data-ttu-id="6d968-105">在 machine.config 文件中删除适配器绑定和适配器绑定元素。</span><span class="sxs-lookup"><span data-stu-id="6d968-105">Remove the adapter binding and adapter binding element in the machine.config file.</span></span>  
  
## <a name="uninstall-an-assembly-from-the-gac"></a><span data-ttu-id="6d968-106">从 GAC 卸载程序集</span><span class="sxs-lookup"><span data-stu-id="6d968-106">Uninstall an Assembly from the GAC</span></span>  
  
#### <a name="use-the-windows-interface"></a><span data-ttu-id="6d968-107">使用 Windows 界面</span><span class="sxs-lookup"><span data-stu-id="6d968-107">Use the Windows interface</span></span>  
  
1.  <span data-ttu-id="6d968-108">打开 Windows 资源管理器，如下所示： 单击**启动**，指向**所有程序**，指向**附件**，然后单击**Windows 资源管理器**.</span><span class="sxs-lookup"><span data-stu-id="6d968-108">Open Windows Explorer as follows: Click **Start**, point to **All Programs**, point to **Accessories**, and then click **Windows Explorer**.</span></span>  
  
2.  <span data-ttu-id="6d968-109">浏览到 GAC 中，它位于 systemdrive%\Windows\Assembly。</span><span class="sxs-lookup"><span data-stu-id="6d968-109">Browse to the GAC, which is located at %systemdrive%\Windows\Assembly.</span></span>  
  
3.  <span data-ttu-id="6d968-110">右键单击你的应用程序中包含每个程序集文件中，单击**卸载**，然后单击**是**以确认。</span><span class="sxs-lookup"><span data-stu-id="6d968-110">Right-click each assembly file that is included in your application, click **Uninstall**, and then click **Yes** to confirm.</span></span>  
  
#### <a name="use-the-command-line"></a><span data-ttu-id="6d968-111">使用命令行</span><span class="sxs-lookup"><span data-stu-id="6d968-111">Use the command line</span></span>  
  
1. <span data-ttu-id="6d968-112">打开[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]命令提示符。</span><span class="sxs-lookup"><span data-stu-id="6d968-112">Open a [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)] command prompt.</span></span>  
  
2. <span data-ttu-id="6d968-113">在命令提示符下，键入以下命令：</span><span class="sxs-lookup"><span data-stu-id="6d968-113">At the command prompt, type the following command:</span></span>  
  
    <span data-ttu-id="6d968-114">**gacutil /u** \<*的完全限定*<em>程序集名称</em>\></span><span class="sxs-lookup"><span data-stu-id="6d968-114">**gacutil /u** \<*fully qualified*<em>assembly name</em>\></span></span>  
  
    <span data-ttu-id="6d968-115">在此命令中，程序集名称是要从 GAC 卸载程序集的名称。</span><span class="sxs-lookup"><span data-stu-id="6d968-115">In this command, the assembly name is the name of the assembly to uninstall from the GAC.</span></span>  
  
    <span data-ttu-id="6d968-116">下面的示例从 GAC 中移除名为 hello.dll 的程序集。</span><span class="sxs-lookup"><span data-stu-id="6d968-116">The following example removes an assembly named hello.dll from the GAC.</span></span>  
  
    `gacutil /u "MyAdapter,Version=1.0.0.0, Culture=neutral, PublicKeyToken=fafafafafafafafa"`
  
## <a name="remove-the-adapter-binding-from-the-machineconfig-file"></a><span data-ttu-id="6d968-117">从 Machine.config 文件中删除适配器绑定</span><span class="sxs-lookup"><span data-stu-id="6d968-117">Remove the Adapter Binding from the Machine.config File</span></span>  
 <span data-ttu-id="6d968-118">可以手动编辑 machine.config 文件来删除适配器绑定，或使用服务配置编辑器。</span><span class="sxs-lookup"><span data-stu-id="6d968-118">You can manually edit the machine.config file to remove the adapter binding, or use the Service Configuration Editor.</span></span> <span data-ttu-id="6d968-119">本部分列出了这两个步骤。</span><span class="sxs-lookup"><span data-stu-id="6d968-119">This section lists both steps.</span></span> 
  
#### <a name="manually-edit-the-machineconfig-file"></a><span data-ttu-id="6d968-120">手动编辑 machine.config 文件</span><span class="sxs-lookup"><span data-stu-id="6d968-120">Manually edit the machine.config file</span></span>  
  
1.  <span data-ttu-id="6d968-121">编辑位于 Microsoft .NET 配置文件夹中的 machine.config 文件。</span><span class="sxs-lookup"><span data-stu-id="6d968-121">Edit the machine.config file located in the Microsoft .NET configuration folder.</span></span> <span data-ttu-id="6d968-122">若要执行此操作，请单击**启动**，单击**运行**，类型**记事本\<Windows 安装路径\>\Microsoft.NET\Framework\\< 版本\>\CONFIG\machine.config**，然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="6d968-122">To do this, click **Start**, click **Run**, type **notepad \<Windows install path\>\Microsoft.NET\Framework\\<version\>\CONFIG\machine.config**, and then click **OK**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="6d968-123">在进行更改，以防止受到编辑错误之前请 machine.config 文件的备份。</span><span class="sxs-lookup"><span data-stu-id="6d968-123">Make a backup of the machine.config file before you make changes to guard against editing mistakes.</span></span>  
  
2.  <span data-ttu-id="6d968-124">更新 machine.config 文件。</span><span class="sxs-lookup"><span data-stu-id="6d968-124">Update the machine.config file.</span></span> <span data-ttu-id="6d968-125">找到你想要删除的适配器 bindingExtensions 元素。</span><span class="sxs-lookup"><span data-stu-id="6d968-125">Find the bindingExtensions element for the adapter you want to remove.</span></span> <span data-ttu-id="6d968-126">根据存在的其他信息，执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="6d968-126">Based on the other information that is present, do one of the following:</span></span>  
  
    -   <span data-ttu-id="6d968-127">如果有其他 bindingExtensions，删除你的适配器扩展。</span><span class="sxs-lookup"><span data-stu-id="6d968-127">If there are other bindingExtensions, remove only your adapter extension.</span></span>  
  
    -   <span data-ttu-id="6d968-128">如果不有任何其他 bindingExtensions，您可以删除 bindingExtensions 部分 （包括适配器扩展名）。</span><span class="sxs-lookup"><span data-stu-id="6d968-128">If there are no other bindingExtensions, you can remove the bindingExtensions section (including your adapter extension).</span></span>  
  
    -   <span data-ttu-id="6d968-129">如果没有任何其他 bindingExtensions 或扩展，则可以删除扩展部分。</span><span class="sxs-lookup"><span data-stu-id="6d968-129">If there are no other bindingExtensions or extensions, you can remove the extensions section.</span></span>  
  
    -   <span data-ttu-id="6d968-130">最后，如果 system.serviceModel 包含您的适配器扩展，则可以删除整个 system.serviceModel 节。</span><span class="sxs-lookup"><span data-stu-id="6d968-130">Finally, if system.serviceModel contains only your adapter extension, you can remove the entire system.serviceModel section.</span></span>  
  
3.  <span data-ttu-id="6d968-131">BindingElementExtensions 元素重复步骤 2。</span><span class="sxs-lookup"><span data-stu-id="6d968-131">Repeat step 2 for the bindingElementExtensions element.</span></span>  
  
4.  <span data-ttu-id="6d968-132">关闭并保存 machine.config 文件。</span><span class="sxs-lookup"><span data-stu-id="6d968-132">Close and save the machine.config file.</span></span>  
  
#### <a name="use-the-service-configuration-editor-do-change-the-machineconfig-file"></a><span data-ttu-id="6d968-133">使用服务配置编辑器更改 machine.config 文件</span><span class="sxs-lookup"><span data-stu-id="6d968-133">Use the Service Configuration Editor do change the machine.config file</span></span>  
  
1.  <span data-ttu-id="6d968-134">打开服务配置编辑器。</span><span class="sxs-lookup"><span data-stu-id="6d968-134">Open Service Configuration Editor.</span></span> <span data-ttu-id="6d968-135">请参阅[服务配置编辑器](https://msdn.microsoft.com/library/ms732009.aspx)有关详细信息。</span><span class="sxs-lookup"><span data-stu-id="6d968-135">See [Service Configuration Editor](https://msdn.microsoft.com/library/ms732009.aspx) for more information.</span></span>
  
2.  <span data-ttu-id="6d968-136">在树视图窗格中 (标记为**配置**)，展开节点树。</span><span class="sxs-lookup"><span data-stu-id="6d968-136">In the tree view pane (labeled **Configuration**), expand the node tree.</span></span> <span data-ttu-id="6d968-137">单击**高级**文件夹中，单击**扩展**文件夹，，然后选择绑定扩展元素。</span><span class="sxs-lookup"><span data-stu-id="6d968-137">Click the **Advanced** folder, click the **Extensions** folder, and then select the binding extensions element.</span></span>  
  
3.  <span data-ttu-id="6d968-138">在绑定扩展编辑器的详细信息窗格中，单击你想要删除，然后单击该绑定扩展**删除**。</span><span class="sxs-lookup"><span data-stu-id="6d968-138">In the details pane of the Binding Extensions Editor, click the binding extension that you want to delete, and then click **Delete**.</span></span> <span data-ttu-id="6d968-139">在下图中，MyAdapterExtension 突出显示，并将被删除。</span><span class="sxs-lookup"><span data-stu-id="6d968-139">In the following figure, MyAdapterExtension is highlighted and will be deleted.</span></span>  
  
     <span data-ttu-id="6d968-140">![具有添加的扩展的服务配置编辑器。] (../../adapters-and-accelerators/wcf-lob-adapter-sdk/media/955d37ea-cba5-49db-90de-0f8feb49c0e0.gif "955d37ea-cba5-49db-90de-0f8feb49c0e0")</span><span class="sxs-lookup"><span data-stu-id="6d968-140">![Service configuration editor with added extension.](../../adapters-and-accelerators/wcf-lob-adapter-sdk/media/955d37ea-cba5-49db-90de-0f8feb49c0e0.gif "955d37ea-cba5-49db-90de-0f8feb49c0e0")</span></span>  
  
4.  <span data-ttu-id="6d968-141">关闭服务配置编辑器。</span><span class="sxs-lookup"><span data-stu-id="6d968-141">Close the Service Configuration Editor.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6d968-142">请参阅</span><span class="sxs-lookup"><span data-stu-id="6d968-142">See Also</span></span>  
 [<span data-ttu-id="6d968-143">部署适配器使用 WCF LOB 适配器 SDK</span><span class="sxs-lookup"><span data-stu-id="6d968-143">Deploy an adapter using the WCF LOB adapter SDK</span></span>](../../adapters-and-accelerators/wcf-lob-adapter-sdk/deploy-an-adapter-using-the-wcf-lob-adapter-sdk.md)