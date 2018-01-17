---
title: "适配器注册文件 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 6750f0ed-4411-4a63-a7fe-f66132cd1e22
caps.latest.revision: "35"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 1c38d00cbaf5d34aa880f5efd1d9e9a59d59c4e0
ms.sourcegitcommit: 3fd1c85d9dc2ce7b77da75a5c2087cc48cfcbe50
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/17/2018
---
# <a name="adapter-registration-file"></a><span data-ttu-id="f5da1-102">适配器注册文件</span><span class="sxs-lookup"><span data-stu-id="f5da1-102">Adapter Registration File</span></span>
<span data-ttu-id="f5da1-103">已成功生成自定义适配器代码后必须将它注册与[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="f5da1-103">After the custom adapter code has been successfully built it must be registered with [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].</span></span> <span data-ttu-id="f5da1-104">可通过使用适当的适配器设置更新注册表来完成此步骤。</span><span class="sxs-lookup"><span data-stu-id="f5da1-104">You do this by updating the registry with the appropriate adapter settings.</span></span> <span data-ttu-id="f5da1-105">你可以手动编写注册表文件，但由于需要输入的信息要求精确且比较复杂，这样做容易出错。</span><span class="sxs-lookup"><span data-stu-id="f5da1-105">You can manually write a registry file, but this is prone to errors due to the preciseness and complexity of the information that you need to enter.</span></span> <span data-ttu-id="f5da1-106">一个更好的办法是运行适配器注册向导。</span><span class="sxs-lookup"><span data-stu-id="f5da1-106">A better decision is to run the Adapter Registry Wizard.</span></span> <span data-ttu-id="f5da1-107">适配器注册向导提供的所有选项与从头创建注册表文件时提供的完全一样，能降低文件中出错的可能性。</span><span class="sxs-lookup"><span data-stu-id="f5da1-107">The Adapter Registry Wizard gives you all the same options as creating a registry file from scratch, and reduces the likelihood of errors in the file.</span></span> <span data-ttu-id="f5da1-108">有关适配器注册表向导的详细信息，请参阅[适配器注册表向导](../core/adapter-registry-wizard.md)。</span><span class="sxs-lookup"><span data-stu-id="f5da1-108">For more information about the Adapter Registry Wizard, see [Adapter Registry Wizard](../core/adapter-registry-wizard.md).</span></span>  
  
 <span data-ttu-id="f5da1-109">StaticAdapterManagement.reg 文件和 DynamicAdapterManagement.reg 文件位于*\<驱动器\>*: files\microsoft BizTalk Server\SDK\Samples\AdaptersDevelopment\File 适配器。</span><span class="sxs-lookup"><span data-stu-id="f5da1-109">The StaticAdapterManagement.reg file and DynamicAdapterManagement.reg file are located at *\<drive\>*:\Program Files\Microsoft BizTalk Server\SDK\Samples\AdaptersDevelopment\File Adapter.</span></span> <span data-ttu-id="f5da1-110">当你运行这些文件之一 (你可以双击它，或右键单击它和选择 **合并**)，它使用注册表中注册了示例文件适配器并将程序集安装到全局程序集缓存。</span><span class="sxs-lookup"><span data-stu-id="f5da1-110">When you run one of these files (you can double-click it or right-click it and and select **Merge**), it registers the sample file adapter with the registry and installs the assembly into the global assembly cache.</span></span> <span data-ttu-id="f5da1-111">若要注册自定义适配器，最好的方法是使用适配器注册向导创建一个新的注册表文件。</span><span class="sxs-lookup"><span data-stu-id="f5da1-111">To register your custom adapter the best option is to create a new registry file by using the Adapter Registry Wizard.</span></span> <span data-ttu-id="f5da1-112">如果自定义静态适配器类似于示例适配器，并且你决定修改现有的注册表文件，请在 StaticAdapterManagement.reg 文件中打开并修改以下属性：</span><span class="sxs-lookup"><span data-stu-id="f5da1-112">If your custom static adapter is similar to the sample adapter, and you decide to modify the existing registry file instead, open and modify the following properties in the StaticAdapterManagement.reg file:</span></span>  
  
-   <span data-ttu-id="f5da1-113">**约束**</span><span class="sxs-lookup"><span data-stu-id="f5da1-113">**Constraints**</span></span>  
  
-   <span data-ttu-id="f5da1-114">**InboundTypeName**</span><span class="sxs-lookup"><span data-stu-id="f5da1-114">**InboundTypeName**</span></span>  
  
-   <span data-ttu-id="f5da1-115">**InboundAssemblyPath**</span><span class="sxs-lookup"><span data-stu-id="f5da1-115">**InboundAssemblyPath**</span></span>  
  
-   <span data-ttu-id="f5da1-116">**OutboundTypeName**</span><span class="sxs-lookup"><span data-stu-id="f5da1-116">**OutboundTypeName**</span></span>  
  
-   <span data-ttu-id="f5da1-117">**OutboundAssemblyPath**</span><span class="sxs-lookup"><span data-stu-id="f5da1-117">**OutboundAssemblyPath**</span></span>  
  
-   <span data-ttu-id="f5da1-118">**AdapterMgmtTypeName**</span><span class="sxs-lookup"><span data-stu-id="f5da1-118">**AdapterMgmtTypeName**</span></span>  
  
-   <span data-ttu-id="f5da1-119">**AdapterMgmtAssemblyPath**</span><span class="sxs-lookup"><span data-stu-id="f5da1-119">**AdapterMgmtAssemblyPath**</span></span>  
  
-   <span data-ttu-id="f5da1-120">**PropertyNameSpace**</span><span class="sxs-lookup"><span data-stu-id="f5da1-120">**PropertyNameSpace**</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="f5da1-121">有关 **OutboundAssemblyPath** 和 **AdapterMgmtAssemblyPath** 我们建议不包括的本地路径，在属性值中，因为配置可能会中断时安装在不同的服务器位置上。</span><span class="sxs-lookup"><span data-stu-id="f5da1-121">For **OutboundAssemblyPath** and **AdapterMgmtAssemblyPath** we recommend that you not include the local path in the property value, because the configuration could break when installed on different server locations.</span></span> <span data-ttu-id="f5da1-122">一个更好的选择是，使用强名称，并在全局程序集缓存中安装它。</span><span class="sxs-lookup"><span data-stu-id="f5da1-122">A better choice is to use a strong name and install it in the global assembly cache.</span></span>  
  
 <span data-ttu-id="f5da1-123">你可以通过两种方式指定实现适配器接收器、适配器发送器和适配器管理的 .NET 类型：</span><span class="sxs-lookup"><span data-stu-id="f5da1-123">You have two options for specifying the .NET type that implements the adapter receiver, adapter transmitter, and adapter management:</span></span>  
  
1.  <span data-ttu-id="f5da1-124">安装到文件夹的适配器，并指定 * TypeName 和 \*AssemblyPath 其中 \*TypeName 是类型。FullName 类和 \*AssemblyPath 是程序集的路径和文件。</span><span class="sxs-lookup"><span data-stu-id="f5da1-124">Install the adapter to a folder and specify *TypeName and \*AssemblyPath where \*TypeName is type.FullName of the class and \*AssemblyPath is the path and file name of the assembly.</span></span>  
  
2.  <span data-ttu-id="f5da1-125">将适配器安装在全局程序集缓存和只需指定 * TypeName 其中 \*TypeName 是类型。类的 AssemblyQualifiedName。</span><span class="sxs-lookup"><span data-stu-id="f5da1-125">Install the adapter in the global assembly cache and specify just *TypeName where \*TypeName is type.AssemblyQualifiedName of the class.</span></span> <span data-ttu-id="f5da1-126">这是建议的选项。</span><span class="sxs-lookup"><span data-stu-id="f5da1-126">This is the recommended option.</span></span>  
  
 <span data-ttu-id="f5da1-127">所有适配器必须包括具有指定 GUID 的注册表项：</span><span class="sxs-lookup"><span data-stu-id="f5da1-127">All adapters must have the following registry keys with the specified GUID:</span></span>  
  
-   <span data-ttu-id="f5da1-128">**实现类别\\{7F46FC3E-3C2C-405B-A47F-8D17942BA8F9}**</span><span class="sxs-lookup"><span data-stu-id="f5da1-128">**Implemented Categories\\{7F46FC3E-3C2C-405B-A47F-8D17942BA8F9}**</span></span>  
  
-   <span data-ttu-id="f5da1-129">**"InboundProtocol_PageProv"="{2DE93EE6-CB01-4007-93E9-C3D71689A281}"**</span><span class="sxs-lookup"><span data-stu-id="f5da1-129">**"InboundProtocol_PageProv"="{2DE93EE6-CB01-4007-93E9-C3D71689A281}"**</span></span>  
  
-   <span data-ttu-id="f5da1-130">**"OutboundProtocol_PageProv"="{2DE93EE6-CB01-4007-93E9-C3D71689A283}"**</span><span class="sxs-lookup"><span data-stu-id="f5da1-130">**"OutboundProtocol_PageProv"="{2DE93EE6-CB01-4007-93E9-C3D71689A283}"**</span></span>  
  
-   <span data-ttu-id="f5da1-131">**"ReceiveLocation_PageProv"="{2DE93EE6-CB01-4007-93E9-C3D71689A280}"**</span><span class="sxs-lookup"><span data-stu-id="f5da1-131">**"ReceiveLocation_PageProv"="{2DE93EE6-CB01-4007-93E9-C3D71689A280}"**</span></span>  
  
-   <span data-ttu-id="f5da1-132">**"TransmitLocation_PageProv"="{2DE93EE6-CB01-4007-93E9-C3D71689A282}"**</span><span class="sxs-lookup"><span data-stu-id="f5da1-132">**"TransmitLocation_PageProv"="{2DE93EE6-CB01-4007-93E9-C3D71689A282}"**</span></span>  
  
 <span data-ttu-id="f5da1-133">基于适配器框架的适配器必须将这些特定的 GUID 用于发送和接收处理程序以及位置属性页。</span><span class="sxs-lookup"><span data-stu-id="f5da1-133">Adapters based on the adapter framework must use these specific GUIDS for send and receive handler and location property pages.</span></span> <span data-ttu-id="f5da1-134">请注意是否适配器是仅限发送的适配器只需要对其进行 **OutboundProtocol_PageProv**和 **TransmitLocation_PageProv**Guid。</span><span class="sxs-lookup"><span data-stu-id="f5da1-134">Note that if an adapter is a send-only adapter it just needs the **OutboundProtocol_PageProv**and **TransmitLocation_PageProv**GUIDs.</span></span> <span data-ttu-id="f5da1-135">与此类似的仅限接收的适配器仅要求 **InboundProtocol_PageProv** 和 **ReceiveLocation_PageProv** Guid。</span><span class="sxs-lookup"><span data-stu-id="f5da1-135">Similarly a receive-only adapter merely requires the **InboundProtocol_PageProv** and **ReceiveLocation_PageProv** GUIDs.</span></span>  
  
 <span data-ttu-id="f5da1-136">以下代码来自 StaticAdapterManagement.reg 文件，DynamicAdapterManagement.reg 文件的代码几乎完全一样。</span><span class="sxs-lookup"><span data-stu-id="f5da1-136">The following code is from the StaticAdapterManagement.reg file, and the code for the DynamicAdapterManagement.reg file is almost identical.</span></span> <span data-ttu-id="f5da1-137">有关每个注册表属性的详细信息，请参阅[注册适配器](../core/registering-an-adapter.md)。</span><span class="sxs-lookup"><span data-stu-id="f5da1-137">For more information about each of the registry properties, see [Registering an Adapter](../core/registering-an-adapter.md).</span></span> <span data-ttu-id="f5da1-138">对注册表文件进行更改后，保存该文件，然后运行它。</span><span class="sxs-lookup"><span data-stu-id="f5da1-138">After making the changes to the registry file, save the file and run it.</span></span>  
  
```  
Windows Registry Editor Version 5.00  
[HKEY_CLASSES_ROOT\CLSID\{62018D08-281A-415b-A6D3-6172E3762867}]  
@="Static DotNetFile Adapter"  
"AppID"="{12A6EBAA-CF68-4B58-B36E-A5A19B22C04E}"  
  
[HKEY_CLASSES_ROOT\CLSID\{62018D08-281A-415b-A6D3-6172E3762867}\BizTalk]  
@="BizTalk"  
"TransportType"="Static DotNetFile"  
"Constraints"=dword:00003C0b  
  
"InboundProtocol_PageProv"="{2DE93EE6-CB01-4007-93E9-C3D71689A281}"  
"OutboundProtocol_PageProv"="{2DE93EE6-CB01-4007-93E9-C3D71689A283}"  
"ReceiveLocation_PageProv"="{2DE93EE6-CB01-4007-93E9-C3D71689A280}"  
"TransmitLocation_PageProv"="{2DE93EE6-CB01-4007-93E9-C3D71689A282}"  
  
"InboundEngineCLSID"="{3D4B599E-2202-4bbb-9FC6-7ACA3906E5DE}"  
"InboundTypeName"="Microsoft.BizTalk.SDKSamples.Adapters.DotNetFileReceiver""InboundAssemblyPath"="C:\\Program Files\\Microsoft BizTalk Server <version>\\SDK\\Samples\\AdaptersDevelopment\\File Adapter\\Runtime\\bin\\Debug\\Microsoft.BizTalk.SDKSamples.Adapters.DotNetFile.Runtime.dll"  
"OutboundEngineCLSID"="{024DB758-AAF9-415e-A121-4AC245DD49EC}"  
"OutboundTypeName"="Microsoft.BizTalk.SDKSamples.Adapters.DotNetFileTransmitter""OutboundAssemblyPath"="C:\\Program Files\\Microsoft BizTalk Server <version>\SDK\\Samples\\AdaptersDevelopment\\File Adapter\\Runtime\\bin\\Debug\\Microsoft.BizTalk.SDKSamples.Adapters.DotNetFile.Runtime.dll""AdapterMgmtTypeName"="Microsoft.BizTalk.SDKSamples.Adapters.Designtime.StaticAdapterManagement""AdapterMgmtAssemblyPath"="C:\\Program Files\\Microsoft BizTalk Server <version>\SDK\\Samples\\AdaptersDevelopment\\File Adapter\\Design Time\\Adapter Management\\bin\\Debug\\Microsoft.BizTalk.SDKSamples.Adapters.DotNetFile.Designtime.dll""PropertyNameSpace"="http://schemas.microsoft.com/BizTalk/2003/SDK_Samples/Messaging/Transports/dotnetfile-properties"  
"AliasesXML"="<AdapterAliasList><AdapterAlias>DotNetFILE://</AdapterAlias></AdapterAliasList>"  
"ReceiveHandlerPropertiesXML"="<CustomProps><AdapterConfig vt=\"8\"/></CustomProps>"  
"SendHandlerPropertiesXML"="<CustomProps><AdapterConfig vt=\"8\"/></CustomProps>"  
"ReceiveLocationPropertiesXML"="<CustomProps><AdapterConfig vt=\"8\"/></CustomProps>"  
"SendLocationPropertiesXML"="<CustomProps><AdapterConfig vt=\"8\"/></CustomProps>"  
[HKEY_CLASSES_ROOT\CLSID\{62018D08-281A-415b-A6D3-6172E3762867}\Implemented Categories]  
[HKEY_CLASSES_ROOT\CLSID\{62018D08-281A-415b-A6D3-6172E3762867}\Implemented Categories\{7F46FC3E-3C2C-405B-A47F-8D17942BA8F9}]  
```  
  
### <a name="to-register-the-static-sample-adapter"></a><span data-ttu-id="f5da1-139">注册静态示例适配器</span><span class="sxs-lookup"><span data-stu-id="f5da1-139">To register the static sample adapter</span></span>  
  
1.  <span data-ttu-id="f5da1-140">使用以下过程运行 SDK 中的文件适配器。</span><span class="sxs-lookup"><span data-stu-id="f5da1-140">Complete the procedure to run the file adapter sample in the SDK.</span></span> <span data-ttu-id="f5da1-141">有关详细信息，请参阅[文件适配器 （BizTalk Server 示例）](../core/file-adapter-biztalk-server-sample.md)。</span><span class="sxs-lookup"><span data-stu-id="f5da1-141">For more information, see [File Adapter (BizTalk Server Sample)](../core/file-adapter-biztalk-server-sample.md).</span></span>  
  
2.  <span data-ttu-id="f5da1-142">单击 **启动**, ，指向 **所有程序**, ，指向 **附件**, ，然后单击 **Windows 资源管理器**。</span><span class="sxs-lookup"><span data-stu-id="f5da1-142">Click **Start**, point to **All Programs**, point to **Accessories**, and then click **Windows Explorer**.</span></span>  
  
3.  <span data-ttu-id="f5da1-143">BizTalk Server 中，导航到安装驱动器，然后导航到 **<**  `drive` **>: files\microsoft** [!INCLUDE[btsBizTalkServer2006r3ui](../includes/btsbiztalkserver2006r3ui-md.md)] **\SDK\Samples\AdaptersUsage\File 适配器**。</span><span class="sxs-lookup"><span data-stu-id="f5da1-143">Navigate to the installation drive for BizTalk Server, and then navigate to **<**`drive`**>:\Program Files\Microsoft** [!INCLUDE[btsBizTalkServer2006r3ui](../includes/btsbiztalkserver2006r3ui-md.md)]**\SDK\Samples\AdaptersUsage\File Adapter**.</span></span>  
  
4.  <span data-ttu-id="f5da1-144">若要将示例适配器添加到注册表中，双击 **StaticAdapterManagement.reg**。(如果你想要向运行注册表中添加动态文件适配器**DynamicAdapterManagement.reg**改为和文件无处不在其他相应的使用。)</span><span class="sxs-lookup"><span data-stu-id="f5da1-144">To add the sample adapter to the registry, double-click **StaticAdapterManagement.reg**. (If you want to add the dynamic file adapter to the registry run **DynamicAdapterManagement.reg** instead and use that file everywhere else as appropriate.)</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="f5da1-145">如果 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 没有安装在计算机的 C 驱动器上，你必须用适当的安装路径修改 StaticAdapterManagement.reg 文件。</span><span class="sxs-lookup"><span data-stu-id="f5da1-145">If [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] is not installed on drive C of your computer, you must modify the StaticAdapterManagement.reg file with the appropriate installation path.</span></span> <span data-ttu-id="f5da1-146">搜索 c︰ 该文件并将其替换为正确的安装驱动器。</span><span class="sxs-lookup"><span data-stu-id="f5da1-146">Search the file for C: and replace it with the correct installation drive.</span></span>  
  
5.  <span data-ttu-id="f5da1-147">在 **注册表编辑器** 对话框中，单击 **是** 以将示例适配器添加到注册表中，然后单击 **确定** 以关闭对话框中，验证的信息已添加到注册表。</span><span class="sxs-lookup"><span data-stu-id="f5da1-147">In the **Registry Editor** dialog box, click **Yes** to add the sample adapter to the registry, and then click **OK** to close the dialog box, verifying that the information was added to the registry.</span></span>  
  
6.  <span data-ttu-id="f5da1-148">若要关闭 Windows 资源管理器，在 **文件** 菜单上，单击 **关闭**。</span><span class="sxs-lookup"><span data-stu-id="f5da1-148">To close Windows Explorer, on the **File** menu, click **Close**.</span></span>  
  
     <span data-ttu-id="f5da1-149">该示例静态适配器现在注册与[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="f5da1-149">The sample static adapter is now registered with [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].</span></span>