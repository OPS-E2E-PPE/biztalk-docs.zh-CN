---
title: 步骤 9： 生成并部署 Echo 适配器 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 1ead10ab-1acf-47c5-ad16-dc6938601906
caps.latest.revision: 13
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 58e0bae620c43504091c29ed2b03a33e0c7710c5
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36980502"
---
# <a name="step-9-build-and-deploy-the-echo-adapter"></a><span data-ttu-id="b6822-102">步骤 9： 生成并部署 Echo 适配器</span><span class="sxs-lookup"><span data-stu-id="b6822-102">Step 9: Build and Deploy the Echo Adapter</span></span>
<span data-ttu-id="b6822-103">![步骤 9 的 9](../../adapters-and-accelerators/wcf-lob-adapter-sdk/media/step-9of9.gif "Step_9of9")</span><span class="sxs-lookup"><span data-stu-id="b6822-103">![Step 9 of 9](../../adapters-and-accelerators/wcf-lob-adapter-sdk/media/step-9of9.gif "Step_9of9")</span></span>  
  
 <span data-ttu-id="b6822-104">**完成时间：** 10 分钟</span><span class="sxs-lookup"><span data-stu-id="b6822-104">**Time to complete:** 10 minutes</span></span>  
  
 <span data-ttu-id="b6822-105">在此步骤中，将执行部署 Echo 适配器所需的任务。</span><span class="sxs-lookup"><span data-stu-id="b6822-105">In this step, you will perform the tasks necessary to deploy the Echo Adapter.</span></span> <span data-ttu-id="b6822-106">这涉及到以下所有内容的：</span><span class="sxs-lookup"><span data-stu-id="b6822-106">This involves all of the following:</span></span>  
  
- <span data-ttu-id="b6822-107">创建一个强名称文件并将其分配给 Echo 适配器程序集</span><span class="sxs-lookup"><span data-stu-id="b6822-107">Create a strong name file and assign it to the Echo Adapter assembly</span></span>  
  
- <span data-ttu-id="b6822-108">生成 Echo 适配器</span><span class="sxs-lookup"><span data-stu-id="b6822-108">Build the Echo Adapter</span></span>  
  
- <span data-ttu-id="b6822-109">发布到 GAC 的程序集</span><span class="sxs-lookup"><span data-stu-id="b6822-109">Publish the assembly into the GAC</span></span>  
  
- <span data-ttu-id="b6822-110">注册使用 Echo 适配器 [!INCLUDE[firstref_btsWinCommFoundation](../../includes/firstref-btswincommfoundation-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b6822-110">Register the Echo Adapter with the [!INCLUDE[firstref_btsWinCommFoundation](../../includes/firstref-btswincommfoundation-md.md)]</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="b6822-111">必要條件</span><span class="sxs-lookup"><span data-stu-id="b6822-111">Prerequisites</span></span>  
 <span data-ttu-id="b6822-112">若要成功完成此步骤中，您应熟悉强名称文件和 gac。</span><span class="sxs-lookup"><span data-stu-id="b6822-112">To successfully complete this step, you should be familiar with strong name files and the GAC.</span></span> <span data-ttu-id="b6822-113">基本了解[!INCLUDE[firstref_btsWinCommFoundation](../../includes/firstref-btswincommfoundation-md.md)]配置是有所帮助，但并不是必需。</span><span class="sxs-lookup"><span data-stu-id="b6822-113">A basic understanding of [!INCLUDE[firstref_btsWinCommFoundation](../../includes/firstref-btswincommfoundation-md.md)] configuration is helpful but not required.</span></span>  
  
### <a name="to-assign-a-strong-name-to-your-assembly"></a><span data-ttu-id="b6822-114">指定程序集的强名称</span><span class="sxs-lookup"><span data-stu-id="b6822-114">To assign a strong name to your assembly</span></span>  
  
1.  <span data-ttu-id="b6822-115">在解决方案资源管理器中右键单击**EchoAdapter**项目，并单击**属性**。</span><span class="sxs-lookup"><span data-stu-id="b6822-115">In Solution Explorer, right-click the **EchoAdapter** project, and then click **Properties**.</span></span>  
  
2.  <span data-ttu-id="b6822-116">在 EchoAdapter 属性页对话框中，选择**签名**在左窗格中。</span><span class="sxs-lookup"><span data-stu-id="b6822-116">In the EchoAdapter Property Pages dialog box, select **Signing** from the left pane.</span></span>  
  
3.  <span data-ttu-id="b6822-117">单击**为程序集签名**选项卡。</span><span class="sxs-lookup"><span data-stu-id="b6822-117">Click the **Sign the assembly** tab.</span></span>  
  
4.  <span data-ttu-id="b6822-118">选择**\<新...\>** 强名称文件。</span><span class="sxs-lookup"><span data-stu-id="b6822-118">Choose **\<new…\>** for the strong name file.</span></span> <span data-ttu-id="b6822-119">当系统提示输入文件的名称，键入**EchoAdapter.snk**，取消选择保护密钥文件的密码选项，然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="b6822-119">When prompted for a file name, type **EchoAdapter.snk**,deselect the protect my key file with a password option, then click **OK**.</span></span>  
  
5.  <span data-ttu-id="b6822-120">单击**应用程序**选项卡。</span><span class="sxs-lookup"><span data-stu-id="b6822-120">Click the **Application** tab.</span></span>  
  
6.  <span data-ttu-id="b6822-121">将程序集名称更改为**Microsoft.Adapters.Samples.EchoV2**。</span><span class="sxs-lookup"><span data-stu-id="b6822-121">Change the assembly name to **Microsoft.Adapters.Samples.EchoV2**.</span></span>  
  
7.  <span data-ttu-id="b6822-122">单击**文件**上的 Visual Studio 菜单然后选择**全部保存**。</span><span class="sxs-lookup"><span data-stu-id="b6822-122">Click **File** on the Visual Studio menu then choose **Save All**.</span></span>  
  
### <a name="to-build-and-deploy-echo-adapter"></a><span data-ttu-id="b6822-123">若要生成并部署 Echo 适配器</span><span class="sxs-lookup"><span data-stu-id="b6822-123">To build and deploy Echo Adapter</span></span>  
  
1.  <span data-ttu-id="b6822-124">在解决方案资源管理器中右键单击**EchoAdapter**项目，并单击**生成**。</span><span class="sxs-lookup"><span data-stu-id="b6822-124">In Solution Explorer, right-click the **EchoAdapter** project, and then click **Build**.</span></span> <span data-ttu-id="b6822-125">如果生成不成功，修复所有错误并尝试重新生成 Echo 适配器。</span><span class="sxs-lookup"><span data-stu-id="b6822-125">If the build does not succeed, fix any errors and try rebuilding the Echo Adapter.</span></span>  
  
2.  <span data-ttu-id="b6822-126">打开 Visual Studio 命令提示符。</span><span class="sxs-lookup"><span data-stu-id="b6822-126">Open a Visual Studio command prompt.</span></span>  
  
3.  <span data-ttu-id="b6822-127">键入下列命令：</span><span class="sxs-lookup"><span data-stu-id="b6822-127">Type the following command:</span></span>  
  
     <span data-ttu-id="b6822-128">**gacutil.exe /if"\<**  *assembly\Microsoft.Adapters.Samples.EchoV2.dll 路径*  **\>"**</span><span class="sxs-lookup"><span data-stu-id="b6822-128">**gacutil.exe /if "\<** *path to assembly\Microsoft.Adapters.Samples.EchoV2.dll* **\>"**</span></span>  
  
     <span data-ttu-id="b6822-129">此命令将程序集安装到 GAC，覆盖任何具有相同程序集名称的现有程序集。</span><span class="sxs-lookup"><span data-stu-id="b6822-129">This installs the assembly to the GAC, overwriting any existing assembly that has the same assembly name.</span></span>  
  
### <a name="to-register-the-echo-adapter-with-windows-communication-foundation"></a><span data-ttu-id="b6822-130">若要使用 Windows Communication Foundation 注册 Echo 适配器</span><span class="sxs-lookup"><span data-stu-id="b6822-130">To register the Echo Adapter with Windows Communication Foundation</span></span>  
  
1. <span data-ttu-id="b6822-131">编辑位于 Microsoft .NET 配置文件夹中的 machine.config 文件。</span><span class="sxs-lookup"><span data-stu-id="b6822-131">Edit the machine.config file located in the Microsoft .NET configuration folder.</span></span> <span data-ttu-id="b6822-132">若要执行此操作，请单击**启动**，单击**运行**，类型**记事本\<Windows 安装路径\>\Microsoft.NET\Framework\\< 版本\>\CONFIG\machine.config**，然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="b6822-132">To do this, click **Start**, click **Run**, type **notepad \<Windows install path\>\Microsoft.NET\Framework\\<version\>\CONFIG\machine.config**, and then click **OK**.</span></span>  
  
2. <span data-ttu-id="b6822-133">更新 machine.config 文件。</span><span class="sxs-lookup"><span data-stu-id="b6822-133">Update the machine.config file.</span></span> <span data-ttu-id="b6822-134">如果在 machine.config 中不包含 system.serviceModel 部分，配置文件，但之前关闭根标记的结尾处添加以下部分。</span><span class="sxs-lookup"><span data-stu-id="b6822-134">If your machine.config does not contain a system.serviceModel section, add the following section at the end of the configuration file but before the closing root tag.</span></span>  
  
   > [!NOTE]
   >  <span data-ttu-id="b6822-135">版本、 区域性、 公钥标记和其他特定于程序集的信息将替换为您的适配器的信息。</span><span class="sxs-lookup"><span data-stu-id="b6822-135">Replace the version, culture, public key token and other assembly-specific information with your adapter's information.</span></span>  
  
   ```  
   <system.serviceModel>  
     <client>  
       <endpoint binding="echoAdapterBindingV2" contract="IMetadataExchange"  
         name="echov2" />  
     </client>  
     <extensions>  
       <bindingElementExtensions>  
         <add name="echoAdapterV2" type="Microsoft.Adapters.Samples.EchoV2.EchoAdapterBindingElementExtensionElement,Microsoft.Adapters.Samples.EchoV2, Version=1.0.0.0, Culture=neutral, PublicKeyToken=xxxxxxxxxxxxxxxx" />  
       </bindingElementExtensions>  
       <bindingExtensions>  
         <add name="echoAdapterBindingV2" type="Microsoft.Adapters.Samples.EchoV2.EchoAdapterBindingCollectionElement,Microsoft.Adapters.Samples.EchoV2, Version=1.0.0.0, Culture=neutral, PublicKeyToken=xxxxxxxxxxxxxxxx" />  
       </bindingExtensions>  
     </extensions>  
   </system.serviceModel>  
   ```  
  
   - <span data-ttu-id="b6822-136">或 -</span><span class="sxs-lookup"><span data-stu-id="b6822-136">OR -</span></span>  
  
     <span data-ttu-id="b6822-137">如果您的 machine.config 包含 system.serviceModel 部分，确定哪些元素缺少，并将其添加。</span><span class="sxs-lookup"><span data-stu-id="b6822-137">If your machine.config contains a system.serviceModel section, determine which elements are missing and add them.</span></span>  
  
   > [!NOTE]
   >  <span data-ttu-id="b6822-138">版本、 区域性、 公钥标记和其他特定于程序集的信息将替换为您的适配器的信息。</span><span class="sxs-lookup"><span data-stu-id="b6822-138">Replace the version, culture, public key token and other assembly-specific information with your adapter's information.</span></span>  
  
   ```  
   <client>  
     <endpoint binding="echoAdapterBindingV2" contract="IMetadataExchange"  
       name="echov2" />  
   </client>  
   <extensions>  
     <bindingElementExtensions>  
       <add name="echoAdapterV2" type="Microsoft.Adapters.Samples.EchoV2.EchoAdapterBindingElementExtensionElement,Microsoft.Adapters.Samples.EchoV2, Version=1.0.0.0, Culture=neutral, PublicKeyToken=xxxxxxxxxxxxxxxx" />  
     </bindingElementExtensions>  
     <bindingExtensions>  
       <add name="echoAdapterBindingV2" type="Microsoft.Adapters.Samples.EchoV2.EchoAdapterBindingCollectionElement,Microsoft.Adapters.Samples.EchoV2, Version=1.0.0.0, Culture=neutral, PublicKeyToken=xxxxxxxxxxxxxxxx" />  
     </bindingExtensions>  
   </extensions>  
   ```  
  
3. <span data-ttu-id="b6822-139">保存 machine.config 文件。</span><span class="sxs-lookup"><span data-stu-id="b6822-139">Save the machine.config file.</span></span>  
  
## <a name="what-did-i-just-do"></a><span data-ttu-id="b6822-140">我只需做了什么？</span><span class="sxs-lookup"><span data-stu-id="b6822-140">What Did I Just Do?</span></span>  
 <span data-ttu-id="b6822-141">在 Echo 适配器教程的此最后一步，您将添加到 Echo 适配器的强名称，生成和部署该适配器，然后修改 Machine.config，包括有关适配器的信息。</span><span class="sxs-lookup"><span data-stu-id="b6822-141">In this final step of the Echo Adapter tutorial, you added a strong name to the Echo Adapter, built and deployed the adapter, then modified Machine.config to include information about the adapter.</span></span> <span data-ttu-id="b6822-142">此时，Echo 适配器应可供使用方应用程序。</span><span class="sxs-lookup"><span data-stu-id="b6822-142">At this point, the Echo Adapter should be available to consuming applications.</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="b6822-143">后续步骤</span><span class="sxs-lookup"><span data-stu-id="b6822-143">Next Steps</span></span>  
 <span data-ttu-id="b6822-144">本教程中已完成。</span><span class="sxs-lookup"><span data-stu-id="b6822-144">This tutorial is complete.</span></span> <span data-ttu-id="b6822-145">如果你想要在.NET 项目中测试 Echo 适配器的功能，请参阅[教程 2： 使用 Echo 适配器通过.NET](../../adapters-and-accelerators/wcf-lob-adapter-sdk/tutorial-2-consume-the-echo-adapter-from-net.md)。</span><span class="sxs-lookup"><span data-stu-id="b6822-145">If you want to test Echo Adapter functionality in a .NET project, see [Tutorial 2: Consume the Echo Adapter from .NET](../../adapters-and-accelerators/wcf-lob-adapter-sdk/tutorial-2-consume-the-echo-adapter-from-net.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b6822-146">请参阅</span><span class="sxs-lookup"><span data-stu-id="b6822-146">See Also</span></span>  
 <span data-ttu-id="b6822-147">[步骤 8： 实现 Echo 适配器的同步入站处理程序](../../adapters-and-accelerators/wcf-lob-adapter-sdk/step-8-implement-the-synchronous-inbound-handler-for-the-echo-adapter.md) </span><span class="sxs-lookup"><span data-stu-id="b6822-147">[Step 8: Implement the Synchronous Inbound Handler for the Echo Adapter](../../adapters-and-accelerators/wcf-lob-adapter-sdk/step-8-implement-the-synchronous-inbound-handler-for-the-echo-adapter.md) </span></span>  
 [<span data-ttu-id="b6822-148">教程 2：从 .NET 使用 Echo 适配器</span><span class="sxs-lookup"><span data-stu-id="b6822-148">Tutorial 2: Consume the Echo Adapter from .NET</span></span>](../../adapters-and-accelerators/wcf-lob-adapter-sdk/tutorial-2-consume-the-echo-adapter-from-net.md)