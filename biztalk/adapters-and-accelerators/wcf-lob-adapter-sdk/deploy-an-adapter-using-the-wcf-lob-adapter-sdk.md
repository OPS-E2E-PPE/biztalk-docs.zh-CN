---
title: 部署适配器使用 WCF LOB 适配器 SDK |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 376b4dcf-2d2c-4872-a394-67edc0c3d088
caps.latest.revision: 17
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 2c29400aae9a9bcd0cf36d49f9b619dc7642fa5a
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36978470"
---
# <a name="deploy-an-adapter-using-the-wcf-lob-adapter-sdk"></a><span data-ttu-id="37f7c-102">部署适配器使用 WCF LOB 适配器 SDK</span><span class="sxs-lookup"><span data-stu-id="37f7c-102">Deploy an adapter using the WCF LOB adapter SDK</span></span>
<span data-ttu-id="37f7c-103">若要部署一个适配器，必须将适配器程序集安装到全局程序集缓存 (GAC) 中，然后 machine.config 文件中注册该适配器。</span><span class="sxs-lookup"><span data-stu-id="37f7c-103">To deploy an adapter, you must install the adapter assembly into the global assembly cache (GAC), and then register the adapter in the machine.config file.</span></span>  
  
## <a name="install-the-adapter-assembly-into-the-gac"></a><span data-ttu-id="37f7c-104">将适配器程序集安装到 GAC</span><span class="sxs-lookup"><span data-stu-id="37f7c-104">Install the Adapter Assembly into the GAC</span></span>  
 <span data-ttu-id="37f7c-105">使用 Visual Studio 中使用的适配器之前[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]命令或在[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]通过使用[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]功能，必须将程序集安装到 gac。</span><span class="sxs-lookup"><span data-stu-id="37f7c-105">Before consuming an adapter in Visual Studio using the [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)] command or in [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] by using the [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)] feature, you must install the assembly into the GAC.</span></span> <span data-ttu-id="37f7c-106">只有具有强名称的程序集可安装到 gac。</span><span class="sxs-lookup"><span data-stu-id="37f7c-106">Only assemblies that are strong-named can be installed into the GAC.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="37f7c-107">若要完成此过程，必须在 GAC 上具有写权限的帐户登录。</span><span class="sxs-lookup"><span data-stu-id="37f7c-107">To complete this procedure, you must be logged on with an account that has Write permissions on the GAC.</span></span> <span data-ttu-id="37f7c-108">本地计算机的管理员帐户拥有这些权限。</span><span class="sxs-lookup"><span data-stu-id="37f7c-108">The Administrators account on the local computer has these permissions.</span></span>  
  
#### <a name="configure-a-strong-name-assembly-key-file"></a><span data-ttu-id="37f7c-109">配置强名称程序集密钥文件</span><span class="sxs-lookup"><span data-stu-id="37f7c-109">Configure a strong name assembly key file</span></span>  
  
1. <span data-ttu-id="37f7c-110">在[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]，加载需要一个强名称的适配器项目文件。</span><span class="sxs-lookup"><span data-stu-id="37f7c-110">In [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)], load the adapter project file that needs a strong name.</span></span>  
  
2. <span data-ttu-id="37f7c-111">打开[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]命令提示符。</span><span class="sxs-lookup"><span data-stu-id="37f7c-111">Open a [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)] command prompt.</span></span>  
  
3. <span data-ttu-id="37f7c-112">在命令提示符下，从你要存储密钥文件的文件夹，键入以下命令，然后按 Enter 键：</span><span class="sxs-lookup"><span data-stu-id="37f7c-112">At the command prompt, from the folder where you want to store the key file, type the following command, and then press ENTER:</span></span>  
  
    <span data-ttu-id="37f7c-113">**sn /k***file_name* **.snk** </span><span class="sxs-lookup"><span data-stu-id="37f7c-113">**sn /k**  *file_name* **.snk**</span></span>  
  
    <span data-ttu-id="37f7c-114">示例： **sn /k EchoAdapter.snk**</span><span class="sxs-lookup"><span data-stu-id="37f7c-114">Example: **sn /k EchoAdapter.snk**</span></span>  
  
    <span data-ttu-id="37f7c-115">一条确认消息，**密钥对写入** \< *file_name*\>**.snk** `,`显示命令行上。</span><span class="sxs-lookup"><span data-stu-id="37f7c-115">A confirmation message, **Key pair written to** \<*file_name*\>**.snk**`,` displays on the command line.</span></span>  
  
4. <span data-ttu-id="37f7c-116">在 Visual Studio 解决方案资源管理器，右键单击该项目，然后单击**属性**。</span><span class="sxs-lookup"><span data-stu-id="37f7c-116">In Visual Studio Solution Explorer, right-click the project, and then click **Properties**.</span></span>  
  
5. <span data-ttu-id="37f7c-117">在左窗格中，展开**常见属性**，然后单击**程序集**。</span><span class="sxs-lookup"><span data-stu-id="37f7c-117">In the left pane, expand **Common Properties**, and then click **Assembly**.</span></span>  
  
6. <span data-ttu-id="37f7c-118">在右窗格中，向下滚动到**强名称**框。</span><span class="sxs-lookup"><span data-stu-id="37f7c-118">In the right pane, scroll to the **Strong name** box.</span></span>  
  
7. <span data-ttu-id="37f7c-119">在中**强名称**框中，单击该字段旁边**程序集密钥文件**，单击浏览按钮 (**...**)，然后浏览到该密钥文件。</span><span class="sxs-lookup"><span data-stu-id="37f7c-119">In the **Strong name** box, click the field next to **Assembly Key File**, click the browse button (**…**), and then browse to the key file.</span></span>  
  
8. <span data-ttu-id="37f7c-120">单击此密钥文件中，单击**开放**，然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="37f7c-120">Click the key file, click **Open**, and then click **OK**.</span></span>  
  
9. <span data-ttu-id="37f7c-121">在 Visual Studio 菜单上，单击**构建**，然后选择**生成解决方案**。</span><span class="sxs-lookup"><span data-stu-id="37f7c-121">On the Visual Studio menu, click **Build**, and then choose **Build Solution**.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="37f7c-122">如果适配器程序集依赖于任何其他程序集，确保这些引用的程序集进行签名的强名称;否则将收到错误。</span><span class="sxs-lookup"><span data-stu-id="37f7c-122">If your adapter assembly depends on any other assemblies, ensure these referenced assemblies are signed with a strong name; otherwise you will get an error.</span></span>  
  
 <span data-ttu-id="37f7c-123">如果源，您可以重新编译具有强名称中，如前面所示。</span><span class="sxs-lookup"><span data-stu-id="37f7c-123">If you have the source, you can recompile with a strong name as shown previously.</span></span> <span data-ttu-id="37f7c-124">如果引用程序集属于第三方，并且不能确保，将它提供强名称，可以反汇编，并再重新组装具有强名称程序集。</span><span class="sxs-lookup"><span data-stu-id="37f7c-124">If the reference assembly belongs to a third-party and you cannot ensure that it will be given a strong name, you can disassemble and then reassemble the assembly with a strong name.</span></span>  
  
 <span data-ttu-id="37f7c-125">原始程序集将被覆盖，因此如果想要保留的原始版本，请确保您通过执行以下步骤继续操作之前的备份。</span><span class="sxs-lookup"><span data-stu-id="37f7c-125">Your original assembly will be overwritten, so if you want to keep the original version, ensure you make a backup copy of it before proceeding with the following steps.</span></span>  
  
 <span data-ttu-id="37f7c-126">使用 Microsoft 中间语言 (MSIL) 拆装器反汇编程序集：</span><span class="sxs-lookup"><span data-stu-id="37f7c-126">Use Microsoft Intermediate Language (MSIL) Disassembler to disassemble the assembly:</span></span>  
  
- <span data-ttu-id="37f7c-127">ILDASM thirdparty.dll /out:thirdparty.il</span><span class="sxs-lookup"><span data-stu-id="37f7c-127">ILDASM thirdparty.dll /out:thirdparty.il</span></span>  
  
  <span data-ttu-id="37f7c-128">使用 MSIL 汇编程序重新组装具有强名称程序集：</span><span class="sxs-lookup"><span data-stu-id="37f7c-128">Use MSIL Assembler to reassemble the assembly with a strong name:</span></span>  
  
- <span data-ttu-id="37f7c-129">ILASM thirdparty.il /dll /key=strongkeyfile.snk</span><span class="sxs-lookup"><span data-stu-id="37f7c-129">ILASM thirdparty.il /dll /key=strongkeyfile.snk</span></span>  
  
#### <a name="install-an-assembly-in-the-gac"></a><span data-ttu-id="37f7c-130">将程序集安装到 GAC 中</span><span class="sxs-lookup"><span data-stu-id="37f7c-130">Install an assembly in the GAC</span></span>  
  
1. <span data-ttu-id="37f7c-131">验证您的适配器已经过签名。</span><span class="sxs-lookup"><span data-stu-id="37f7c-131">Verify that your adapter has been signed.</span></span>  
  
2. <span data-ttu-id="37f7c-132">打开[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]命令提示符。</span><span class="sxs-lookup"><span data-stu-id="37f7c-132">Open a [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)] command prompt.</span></span>  
  
3. <span data-ttu-id="37f7c-133">键入下列命令：</span><span class="sxs-lookup"><span data-stu-id="37f7c-133">Type the following command:</span></span>  
  
    <span data-ttu-id="37f7c-134">**gacutil.exe /if"\<**  *程序集.dll 文件路径*  **\>"**</span><span class="sxs-lookup"><span data-stu-id="37f7c-134">**gacutil.exe /if "\<** *path to the assembly .dll file* **\>"**</span></span>  
  
4. <span data-ttu-id="37f7c-135">此命令将程序集安装到 GAC，覆盖任何具有相同程序集名称的现有程序集。</span><span class="sxs-lookup"><span data-stu-id="37f7c-135">This installs the assembly to the GAC, overwriting any existing assembly that has the same assembly name.</span></span>  
  
## <a name="register-the-adapter-in-machineconfig"></a><span data-ttu-id="37f7c-136">在 Machine.config 中注册该适配器</span><span class="sxs-lookup"><span data-stu-id="37f7c-136">Register the Adapter in Machine.config</span></span>  
 <span data-ttu-id="37f7c-137">使用适配器开发[!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]呈现为 WCF 绑定。</span><span class="sxs-lookup"><span data-stu-id="37f7c-137">An adapter developed using the [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)] is surfaced as a WCF binding.</span></span>  <span data-ttu-id="37f7c-138">有关详细信息，请参阅 Microsoft.ServiceModel.Channels.Common.AdapterBinding。</span><span class="sxs-lookup"><span data-stu-id="37f7c-138">See Microsoft.ServiceModel.Channels.Common.AdapterBinding for more information.</span></span>  <span data-ttu-id="37f7c-139">向 WCF 注册适配器绑定使用\<bindingExtensions\>节中\<系统。ServiceModel\> ，并使用 WCF 注册适配器的传输绑定元素使用\<bindingElementExtensions\>节中\<系统。ServiceModel\>。</span><span class="sxs-lookup"><span data-stu-id="37f7c-139">The adapter binding is registered with WCF using \<bindingExtensions\> section within \<system.ServiceModel\> and the adapter transport binding element is registered with WCF using \<bindingElementExtensions\> section within \<system.ServiceModel\>.</span></span>  
  
 <span data-ttu-id="37f7c-140">您可以手动编辑 machine.config 文件使用文本编辑器。</span><span class="sxs-lookup"><span data-stu-id="37f7c-140">You can manually edit the machine.config file using a text editor.</span></span>  
  
#### <a name="manually-edit-the-machineconfig-file"></a><span data-ttu-id="37f7c-141">手动编辑 machine.config 文件</span><span class="sxs-lookup"><span data-stu-id="37f7c-141">Manually edit the machine.config file</span></span>  
  
1. <span data-ttu-id="37f7c-142">编辑位于 Microsoft .NET 配置文件夹中的 machine.config 文件。</span><span class="sxs-lookup"><span data-stu-id="37f7c-142">Edit the machine.config file located in the Microsoft .NET configuration folder.</span></span> <span data-ttu-id="37f7c-143">若要执行此操作，请单击**启动**，单击**运行**，键入 notepad \<Windows 安装路径\>\Microsoft.NET\Framework\\< 版本\>\CONFIG\machine.config，并单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="37f7c-143">To do this, click **Start**, click **Run**, type notepad \<Windows install path\>\Microsoft.NET\Framework\\<version\>\CONFIG\machine.config, and then click **OK**.</span></span>  
  
2. <span data-ttu-id="37f7c-144">更新 machine.config 文件。</span><span class="sxs-lookup"><span data-stu-id="37f7c-144">Update the machine.config file.</span></span> <span data-ttu-id="37f7c-145">如果文件不包含 system.serviceModel 节，在配置文件，但之前关闭根标记的结尾处添加以下部分。</span><span class="sxs-lookup"><span data-stu-id="37f7c-145">If the file does not contain a system.serviceModel section, add the following section at the end of the configuration file but before the closing root tag.</span></span>  
  
   > [!NOTE]
   >  <span data-ttu-id="37f7c-146">"MyAdapterBinding"、 版本、 区域性和其他特定于程序集的信息将替换为您的适配器的信息。</span><span class="sxs-lookup"><span data-stu-id="37f7c-146">Replace "myAdapterBinding", version, culture and other assembly-specific information with your adapter's information.</span></span>  
  
   ```  
   <system.serviceModel>  
     <extensions>  
       <bindingExtensions>  
           <add name="myAdapterBinding" type="Microsoft.Adapters.Samples.Echo.EchoAdapterBindingCollectionElement,EchoAdapter, Version=0.0.0.0, Culture=neutral, PublicKeyToken= fafafafafafafafa" />  
       </bindingExtensions>      <bindingElementExtensions>  
           <add name="echoAdapter" type="Microsoft.Adapters.Samples.Echo.EchoAdapterBindingElementExtension,EchoAdapter, Version=0.0.0.0, Culture=neutral, PublicKeyToken=37f23b4adb996dcf" />  
         </bindingElementExtensions>  
     </extensions>  
   </system.serviceModel>  
   ```  
  
   - <span data-ttu-id="37f7c-147">或 -</span><span class="sxs-lookup"><span data-stu-id="37f7c-147">OR -</span></span>  
  
     <span data-ttu-id="37f7c-148">如果您的 machine.config 文件包含 system.serviceModel 部分，确定哪些元素缺少，并将它们，添加"MyAdapter"和其他信息替换为您的适配器的信息。</span><span class="sxs-lookup"><span data-stu-id="37f7c-148">If your machine.config file contains a system.serviceModel section, determine which elements are missing and add them, replacing "MyAdapter" and other information with your adapter's information.</span></span>  
  
   ```  
   <extensions>  
     <bindingExtensions>  
           <add name="myAdapterBinding" type="Microsoft.Adapters.Samples.Echo.EchoAdapterBindingCollectionElement,EchoAdapter, Version=0.0.0.0, Culture=neutral, PublicKeyToken= fafafafafafafafa" />  
     </bindingExtensions>  
         <bindingElementExtensions>  
           <add name="echoAdapter" type="Microsoft.Adapters.Samples.Echo.EchoAdapterBindingElementExtension,EchoAdapter, Version=0.0.0.0, Culture=neutral, PublicKeyToken=37f23b4adb996dcf" />  
         </bindingElementExtensions>  
   </extensions>  
   ```  
  
3. <span data-ttu-id="37f7c-149">关闭并保存 machine.config 文件。</span><span class="sxs-lookup"><span data-stu-id="37f7c-149">Close and save the machine.config file.</span></span>  
  
   <span data-ttu-id="37f7c-150">此外可以使用[服务配置编辑器](https://msdn.microsoft.com/library/ms732009.aspx)修改 machine.config 文件。</span><span class="sxs-lookup"><span data-stu-id="37f7c-150">You can also use the [Service Configuration Editor](https://msdn.microsoft.com/library/ms732009.aspx) to modify the machine.config file.</span></span>
  
#### <a name="edit-the-machineconfig-file-using-the-service-configuration-editor"></a><span data-ttu-id="37f7c-151">编辑 machine.config 文件使用服务配置编辑器</span><span class="sxs-lookup"><span data-stu-id="37f7c-151">Edit the machine.config file using the Service Configuration Editor</span></span>  
  
1.  <span data-ttu-id="37f7c-152">打开**服务配置编辑器**。</span><span class="sxs-lookup"><span data-stu-id="37f7c-152">Open the **Service Configuration Editor**.</span></span> <span data-ttu-id="37f7c-153">请参阅[服务配置编辑器](https://msdn.microsoft.com/library/ms732009.aspx)有关详细信息。</span><span class="sxs-lookup"><span data-stu-id="37f7c-153">See [Service Configuration Editor](https://msdn.microsoft.com/library/ms732009.aspx) for  more information.</span></span>
  
2.  <span data-ttu-id="37f7c-154">在树视图窗格中 (标记为**配置**)，展开节点树。</span><span class="sxs-lookup"><span data-stu-id="37f7c-154">In the tree view pane (labeled **Configuration**), expand the node tree.</span></span> <span data-ttu-id="37f7c-155">单击**高级**文件夹中，单击**扩展**文件夹，，然后选择绑定扩展元素。</span><span class="sxs-lookup"><span data-stu-id="37f7c-155">Click the **Advanced** folder, click the **Extensions** folder, and then select the binding extensions element.</span></span>  
  
     <span data-ttu-id="37f7c-156">![服务配置编辑器。](../../adapters-and-accelerators/wcf-lob-adapter-sdk/media/0a44a070-b788-4287-bd9e-c946fafcf11c.gif "0a44a070-b788-4287-bd9e-c946fafcf11c")</span><span class="sxs-lookup"><span data-stu-id="37f7c-156">![Service configuration editor.](../../adapters-and-accelerators/wcf-lob-adapter-sdk/media/0a44a070-b788-4287-bd9e-c946fafcf11c.gif "0a44a070-b788-4287-bd9e-c946fafcf11c")</span></span>  
  
3.  <span data-ttu-id="37f7c-157">创建一个新的绑定扩展。</span><span class="sxs-lookup"><span data-stu-id="37f7c-157">Create a new binding extension.</span></span> <span data-ttu-id="37f7c-158">单击**新建**按钮以打开该扩展**配置元素编辑器**对话框。</span><span class="sxs-lookup"><span data-stu-id="37f7c-158">Click the **New** button to open the Extension **Configuration Element Editor** dialog box.</span></span> <span data-ttu-id="37f7c-159">在中**配置名称**，输入唯一的名称包含扩展，例如*MyAdapterExtension*。</span><span class="sxs-lookup"><span data-stu-id="37f7c-159">In **Configuration Name**, enter a unique name for the extensions, for example *MyAdapterExtension*.</span></span>  
  
     <span data-ttu-id="37f7c-160">![扩展配置元素编辑器](../../adapters-and-accelerators/wcf-lob-adapter-sdk/media/1398a256-00fa-4591-99ee-54298a8cf6e3.gif "1398a256-00fa-4591-99ee-54298a8cf6e3")</span><span class="sxs-lookup"><span data-stu-id="37f7c-160">![Extension configuration element editor](../../adapters-and-accelerators/wcf-lob-adapter-sdk/media/1398a256-00fa-4591-99ee-54298a8cf6e3.gif "1398a256-00fa-4591-99ee-54298a8cf6e3")</span></span>  
  
4.  <span data-ttu-id="37f7c-161">单击**类型**字段，，然后单击省略号按钮 (**...**) 以打开**绑定扩展类型浏览器**对话框。</span><span class="sxs-lookup"><span data-stu-id="37f7c-161">Click the **Type** field, and then click the ellipsis button (**...**) to open the **Binding Extension Type Browser** dialog box.</span></span>  
  
5.  <span data-ttu-id="37f7c-162">单击全局程序集缓存 (GAC) 图标以列出 GAC 中的 Dll。</span><span class="sxs-lookup"><span data-stu-id="37f7c-162">Click the global assembly cache (GAC) icon to list the DLLs in the GAC.</span></span>  
  
6.  <span data-ttu-id="37f7c-163">单击您的适配器程序集。</span><span class="sxs-lookup"><span data-stu-id="37f7c-163">Click your adapter assembly.</span></span>  
  
     <span data-ttu-id="37f7c-164">![构建扩展类型浏览器。](../../adapters-and-accelerators/wcf-lob-adapter-sdk/media/7528e218-8930-4b01-b29d-8ec125a9b818.gif "7528e218-8930-4b01-b29d-8ec125a9b818")</span><span class="sxs-lookup"><span data-stu-id="37f7c-164">![Building extension type browser.](../../adapters-and-accelerators/wcf-lob-adapter-sdk/media/7528e218-8930-4b01-b29d-8ec125a9b818.gif "7528e218-8930-4b01-b29d-8ec125a9b818")</span></span>  
  
7.  <span data-ttu-id="37f7c-165">单击**打开**按钮以选择的程序集。</span><span class="sxs-lookup"><span data-stu-id="37f7c-165">Click the **Open** button to select the assembly.</span></span>  
  
8.  <span data-ttu-id="37f7c-166">在中**绑定扩展类型浏览器**对话框框中，单击实现绑定集合元素的类型名称。</span><span class="sxs-lookup"><span data-stu-id="37f7c-166">In the **Binding Extension Type Browser** dialog box, click the type name that implements the binding collection element.</span></span>  
  
     <span data-ttu-id="37f7c-167">![构建扩展类型浏览器。](../../adapters-and-accelerators/wcf-lob-adapter-sdk/media/a5db2c6b-cdf7-4cd9-8cc4-6b0fb960b1ce.gif "a5db2c6b-cdf7-4cd9-8cc4-6b0fb960b1ce")</span><span class="sxs-lookup"><span data-stu-id="37f7c-167">![Building extension type browser.](../../adapters-and-accelerators/wcf-lob-adapter-sdk/media/a5db2c6b-cdf7-4cd9-8cc4-6b0fb960b1ce.gif "a5db2c6b-cdf7-4cd9-8cc4-6b0fb960b1ce")</span></span>  
  
9. <span data-ttu-id="37f7c-168">单击**打开**按钮以选择的类型。</span><span class="sxs-lookup"><span data-stu-id="37f7c-168">Click the **Open** button to select the type.</span></span>  
  
10. <span data-ttu-id="37f7c-169">单击**确定**以关闭**扩展配置元素编辑器**对话框。</span><span class="sxs-lookup"><span data-stu-id="37f7c-169">Click **OK** to close the **Extension Configuration Element Editor** dialog box.</span></span>  
  
11. <span data-ttu-id="37f7c-170">中的详细信息窗格**绑定扩展编辑器**，验证是否显示绑定扩展。</span><span class="sxs-lookup"><span data-stu-id="37f7c-170">In the details pane of the **Binding Extensions Editor**, verify that your binding extension appears.</span></span> <span data-ttu-id="37f7c-171">下图中突出显示 MyAdapterExtension。</span><span class="sxs-lookup"><span data-stu-id="37f7c-171">In the following figure, MyAdapterExtension is highlighted.</span></span>  
  
     <span data-ttu-id="37f7c-172">![具有添加的扩展的服务配置编辑器。](../../adapters-and-accelerators/wcf-lob-adapter-sdk/media/955d37ea-cba5-49db-90de-0f8feb49c0e0.gif "955d37ea-cba5-49db-90de-0f8feb49c0e0")</span><span class="sxs-lookup"><span data-stu-id="37f7c-172">![Service configuration editor with added extension.](../../adapters-and-accelerators/wcf-lob-adapter-sdk/media/955d37ea-cba5-49db-90de-0f8feb49c0e0.gif "955d37ea-cba5-49db-90de-0f8feb49c0e0")</span></span>  
  
12. <span data-ttu-id="37f7c-173">关闭**服务配置编辑器**。</span><span class="sxs-lookup"><span data-stu-id="37f7c-173">Close the **Service Configuration Editor**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="37f7c-174">请参阅</span><span class="sxs-lookup"><span data-stu-id="37f7c-174">See Also</span></span>  
 [<span data-ttu-id="37f7c-175">部署适配器使用 WCF LOB 适配器 SDK</span><span class="sxs-lookup"><span data-stu-id="37f7c-175">Deploy an adapter using the WCF LOB adapter SDK</span></span>](../../adapters-and-accelerators/wcf-lob-adapter-sdk/deploy-an-adapter-using-the-wcf-lob-adapter-sdk.md)