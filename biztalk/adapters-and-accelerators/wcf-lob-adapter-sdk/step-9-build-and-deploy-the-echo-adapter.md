---
title: "步骤 9： 生成并部署 Echo 适配器 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 1ead10ab-1acf-47c5-ad16-dc6938601906
caps.latest.revision: "13"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: cec35363cca2f20b38e8a2ecf8bdaf36306f6554
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="step-9-build-and-deploy-the-echo-adapter"></a><span data-ttu-id="29110-102">步骤 9： 生成并部署 Echo 适配器</span><span class="sxs-lookup"><span data-stu-id="29110-102">Step 9: Build and Deploy the Echo Adapter</span></span>
<span data-ttu-id="29110-103">![步骤 9 9](../../adapters-and-accelerators/wcf-lob-adapter-sdk/media/step-9of9.gif "Step_9of9")</span><span class="sxs-lookup"><span data-stu-id="29110-103">![Step 9 of 9](../../adapters-and-accelerators/wcf-lob-adapter-sdk/media/step-9of9.gif "Step_9of9")</span></span>  
  
 <span data-ttu-id="29110-104">**完成时间：** 10 分钟</span><span class="sxs-lookup"><span data-stu-id="29110-104">**Time to complete:** 10 minutes</span></span>  
  
 <span data-ttu-id="29110-105">在此步骤中，你将执行部署 Echo 适配器所需的任务。</span><span class="sxs-lookup"><span data-stu-id="29110-105">In this step, you will perform the tasks necessary to deploy the Echo Adapter.</span></span> <span data-ttu-id="29110-106">这包括如下：</span><span class="sxs-lookup"><span data-stu-id="29110-106">This involves all of the following:</span></span>  
  
-   <span data-ttu-id="29110-107">创建一个强名称文件并将其分配给 Echo 适配器程序集</span><span class="sxs-lookup"><span data-stu-id="29110-107">Create a strong name file and assign it to the Echo Adapter assembly</span></span>  
  
-   <span data-ttu-id="29110-108">生成 Echo 适配器</span><span class="sxs-lookup"><span data-stu-id="29110-108">Build the Echo Adapter</span></span>  
  
-   <span data-ttu-id="29110-109">发布到 GAC 的程序集</span><span class="sxs-lookup"><span data-stu-id="29110-109">Publish the assembly into the GAC</span></span>  
  
-   <span data-ttu-id="29110-110">注册的 Echo 适配器[!INCLUDE[firstref_btsWinCommFoundation](../../includes/firstref-btswincommfoundation-md.md)]</span><span class="sxs-lookup"><span data-stu-id="29110-110">Register the Echo Adapter with the [!INCLUDE[firstref_btsWinCommFoundation](../../includes/firstref-btswincommfoundation-md.md)]</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="29110-111">先决条件</span><span class="sxs-lookup"><span data-stu-id="29110-111">Prerequisites</span></span>  
 <span data-ttu-id="29110-112">若要成功完成此步骤，你应熟悉强名称的文件和 gac。</span><span class="sxs-lookup"><span data-stu-id="29110-112">To successfully complete this step, you should be familiar with strong name files and the GAC.</span></span> <span data-ttu-id="29110-113">基本了解[!INCLUDE[firstref_btsWinCommFoundation](../../includes/firstref-btswincommfoundation-md.md)]配置是有用的但并不是必需。</span><span class="sxs-lookup"><span data-stu-id="29110-113">A basic understanding of [!INCLUDE[firstref_btsWinCommFoundation](../../includes/firstref-btswincommfoundation-md.md)] configuration is helpful but not required.</span></span>  
  
### <a name="to-assign-a-strong-name-to-your-assembly"></a><span data-ttu-id="29110-114">指定程序集的强名称</span><span class="sxs-lookup"><span data-stu-id="29110-114">To assign a strong name to your assembly</span></span>  
  
1.  <span data-ttu-id="29110-115">在解决方案资源管理器，右键单击**EchoAdapter**项目，，然后单击**属性**。</span><span class="sxs-lookup"><span data-stu-id="29110-115">In Solution Explorer, right-click the **EchoAdapter** project, and then click **Properties**.</span></span>  
  
2.  <span data-ttu-id="29110-116">在 EchoAdapter 属性页对话框中，选择**签名**从左窗格。</span><span class="sxs-lookup"><span data-stu-id="29110-116">In the EchoAdapter Property Pages dialog box, select **Signing** from the left pane.</span></span>  
  
3.  <span data-ttu-id="29110-117">单击**对程序集签名**选项卡。</span><span class="sxs-lookup"><span data-stu-id="29110-117">Click the **Sign the assembly** tab.</span></span>  
  
4.  <span data-ttu-id="29110-118">选择**\<新建 … >**强名称的文件。</span><span class="sxs-lookup"><span data-stu-id="29110-118">Choose **\<new…>** for the strong name file.</span></span> <span data-ttu-id="29110-119">当系统提示输入文件的名称，键入**EchoAdapter.snk**，取消保护选择密钥文件使用密码选项，然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="29110-119">When prompted for a file name, type **EchoAdapter.snk**,deselect the protect my key file with a password option, then click **OK**.</span></span>  
  
5.  <span data-ttu-id="29110-120">单击**应用程序**选项卡。</span><span class="sxs-lookup"><span data-stu-id="29110-120">Click the **Application** tab.</span></span>  
  
6.  <span data-ttu-id="29110-121">程序集名称更改为**Microsoft.Adapters.Samples.EchoV2**。</span><span class="sxs-lookup"><span data-stu-id="29110-121">Change the assembly name to **Microsoft.Adapters.Samples.EchoV2**.</span></span>  
  
7.  <span data-ttu-id="29110-122">单击**文件**在 Visual Studio 菜单然后选择**保存所有**。</span><span class="sxs-lookup"><span data-stu-id="29110-122">Click **File** on the Visual Studio menu then choose **Save All**.</span></span>  
  
### <a name="to-build-and-deploy-echo-adapter"></a><span data-ttu-id="29110-123">若要生成和部署 Echo 适配器</span><span class="sxs-lookup"><span data-stu-id="29110-123">To build and deploy Echo Adapter</span></span>  
  
1.  <span data-ttu-id="29110-124">在解决方案资源管理器，右键单击**EchoAdapter**项目，，然后单击**生成**。</span><span class="sxs-lookup"><span data-stu-id="29110-124">In Solution Explorer, right-click the **EchoAdapter** project, and then click **Build**.</span></span> <span data-ttu-id="29110-125">如果生成未成功，则修复任何错误，并请尝试重新生成 Echo 适配器。</span><span class="sxs-lookup"><span data-stu-id="29110-125">If the build does not succeed, fix any errors and try rebuilding the Echo Adapter.</span></span>  
  
2.  <span data-ttu-id="29110-126">打开 Visual Studio 命令提示符。</span><span class="sxs-lookup"><span data-stu-id="29110-126">Open a Visual Studio command prompt.</span></span>  
  
3.  <span data-ttu-id="29110-127">键入下列命令：</span><span class="sxs-lookup"><span data-stu-id="29110-127">Type the following command:</span></span>  
  
     <span data-ttu-id="29110-128">**gacutil.exe /if"\<**  *路径 assembly\Microsoft.Adapters.Samples.EchoV2.dll* **>"**</span><span class="sxs-lookup"><span data-stu-id="29110-128">**gacutil.exe /if "\<** *path to assembly\Microsoft.Adapters.Samples.EchoV2.dll* **>"**</span></span>  
  
     <span data-ttu-id="29110-129">此命令将程序集安装到 GAC，覆盖任何具有相同程序集名称的现有程序集。</span><span class="sxs-lookup"><span data-stu-id="29110-129">This installs the assembly to the GAC, overwriting any existing assembly that has the same assembly name.</span></span>  
  
### <a name="to-register-the-echo-adapter-with-windows-communication-foundation"></a><span data-ttu-id="29110-130">若要注册 Windows Communication Foundation Echo 适配器</span><span class="sxs-lookup"><span data-stu-id="29110-130">To register the Echo Adapter with Windows Communication Foundation</span></span>  
  
1.  <span data-ttu-id="29110-131">编辑位于 Microsoft .NET 配置文件夹中的 machine.config 文件。</span><span class="sxs-lookup"><span data-stu-id="29110-131">Edit the machine.config file located in the Microsoft .NET configuration folder.</span></span> <span data-ttu-id="29110-132">若要执行此操作，请单击**启动**，单击**运行**，类型**记事本\<Windows 安装路径 > \Microsoft.NET\Framework\\< 版本\>\CONFIG\machine.config**，然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="29110-132">To do this, click **Start**, click **Run**, type **notepad \<Windows install path>\Microsoft.NET\Framework\\<version\>\CONFIG\machine.config**, and then click **OK**.</span></span>  
  
2.  <span data-ttu-id="29110-133">更新 machine.config 文件。</span><span class="sxs-lookup"><span data-stu-id="29110-133">Update the machine.config file.</span></span> <span data-ttu-id="29110-134">如果你 machine.config 不包含 system.serviceModel 部分，在末尾的配置文件，但在结束根标记之前添加以下部分。</span><span class="sxs-lookup"><span data-stu-id="29110-134">If your machine.config does not contain a system.serviceModel section, add the following section at the end of the configuration file but before the closing root tag.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="29110-135">将替换适配器的信息的版本、 区域性、 公钥标记和其他特定于程序集的信息。</span><span class="sxs-lookup"><span data-stu-id="29110-135">Replace the version, culture, public key token and other assembly-specific information with your adapter's information.</span></span>  
  
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
  
     - <span data-ttu-id="29110-136">或 -</span><span class="sxs-lookup"><span data-stu-id="29110-136">OR -</span></span>  
  
     <span data-ttu-id="29110-137">如果你 machine.config 包含 system.serviceModel 部分，确定哪些元素缺少，并将其添加。</span><span class="sxs-lookup"><span data-stu-id="29110-137">If your machine.config contains a system.serviceModel section, determine which elements are missing and add them.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="29110-138">将替换适配器的信息的版本、 区域性、 公钥标记和其他特定于程序集的信息。</span><span class="sxs-lookup"><span data-stu-id="29110-138">Replace the version, culture, public key token and other assembly-specific information with your adapter's information.</span></span>  
  
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
  
3.  <span data-ttu-id="29110-139">保存 machine.config 文件。</span><span class="sxs-lookup"><span data-stu-id="29110-139">Save the machine.config file.</span></span>  
  
## <a name="what-did-i-just-do"></a><span data-ttu-id="29110-140">未我只需做什么？</span><span class="sxs-lookup"><span data-stu-id="29110-140">What Did I Just Do?</span></span>  
 <span data-ttu-id="29110-141">在此 Echo 适配器本教程的最后一步，你将添加到 Echo 适配器的强名称、 生成和部署适配器，然后修改 Machine.config，包括有关适配器的信息。</span><span class="sxs-lookup"><span data-stu-id="29110-141">In this final step of the Echo Adapter tutorial, you added a strong name to the Echo Adapter, built and deployed the adapter, then modified Machine.config to include information about the adapter.</span></span> <span data-ttu-id="29110-142">此时，Echo 适配器应可供消费应用程序。</span><span class="sxs-lookup"><span data-stu-id="29110-142">At this point, the Echo Adapter should be available to consuming applications.</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="29110-143">后续步骤</span><span class="sxs-lookup"><span data-stu-id="29110-143">Next Steps</span></span>  
 <span data-ttu-id="29110-144">本教程已完成。</span><span class="sxs-lookup"><span data-stu-id="29110-144">This tutorial is complete.</span></span> <span data-ttu-id="29110-145">如果你想要测试的.NET 项目中的 Echo 适配器的功能，请参阅[教程 2： 使用.NET Echo 适配器](../../adapters-and-accelerators/wcf-lob-adapter-sdk/tutorial-2-consume-the-echo-adapter-from-net.md)。</span><span class="sxs-lookup"><span data-stu-id="29110-145">If you want to test Echo Adapter functionality in a .NET project, see [Tutorial 2: Consume the Echo Adapter from .NET](../../adapters-and-accelerators/wcf-lob-adapter-sdk/tutorial-2-consume-the-echo-adapter-from-net.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="29110-146">另请参阅</span><span class="sxs-lookup"><span data-stu-id="29110-146">See Also</span></span>  
 <span data-ttu-id="29110-147">[步骤 8： 为 Echo 适配器实现同步的入站处理程序](../../adapters-and-accelerators/wcf-lob-adapter-sdk/step-8-implement-the-synchronous-inbound-handler-for-the-echo-adapter.md) </span><span class="sxs-lookup"><span data-stu-id="29110-147">[Step 8: Implement the Synchronous Inbound Handler for the Echo Adapter](../../adapters-and-accelerators/wcf-lob-adapter-sdk/step-8-implement-the-synchronous-inbound-handler-for-the-echo-adapter.md) </span></span>  
 [<span data-ttu-id="29110-148">教程 2： 使用.NET Echo 适配器</span><span class="sxs-lookup"><span data-stu-id="29110-148">Tutorial 2: Consume the Echo Adapter from .NET</span></span>](../../adapters-and-accelerators/wcf-lob-adapter-sdk/tutorial-2-consume-the-echo-adapter-from-net.md)