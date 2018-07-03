---
title: '使用 Siebel 适配器进行故障排除安装问题: |Microsoft Docs'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- troubleshooting, installation
- installation, troubleshooting
ms.assetid: f9f066d9-37b6-4a18-9f60-d0931ea91a18
caps.latest.revision: 11
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ed3fab4973950b70a49efc90e1bc947561e602c6
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36983494"
---
# <a name="troubleshoot-installation-issues-with-the-siebel-adapter"></a><span data-ttu-id="e73fd-102">使用 Siebel 适配器进行故障排除安装问题：</span><span class="sxs-lookup"><span data-stu-id="e73fd-102">Troubleshoot Installation Issues with the Siebel adapter</span></span>
<span data-ttu-id="e73fd-103">Microsoft[!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)]安装将复制的计算机上的产品二进制文件并注册每个适配器的绑定。</span><span class="sxs-lookup"><span data-stu-id="e73fd-103">The Microsoft [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)] installation copies the product binaries on the computer and registers the bindings for each adapter.</span></span> <span data-ttu-id="e73fd-104">本部分讨论故障排除技术来解决安装错误。</span><span class="sxs-lookup"><span data-stu-id="e73fd-104">This section discusses troubleshooting techniques to resolve installation errors.</span></span>  

## <a name="setup-logging"></a><span data-ttu-id="e73fd-105">安装程序日志记录</span><span class="sxs-lookup"><span data-stu-id="e73fd-105">Setup Logging</span></span>  
 <span data-ttu-id="e73fd-106">[!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)]的安装程序进行安装的标准任务[!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="e73fd-106">The [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)] setup program performs the standard task of installing the [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)].</span></span> <span data-ttu-id="e73fd-107">此外，安装程序还执行某些自定义操作，例如注册适配器绑定。</span><span class="sxs-lookup"><span data-stu-id="e73fd-107">Additionally, the setup also performs certain custom actions such as registering the adapter bindings.</span></span> <span data-ttu-id="e73fd-108">你可以记录执行的安装程序的这两个标准以及自定义操作的消息。</span><span class="sxs-lookup"><span data-stu-id="e73fd-108">You can log messages for both the standard as well as custom actions performed by the setup.</span></span>  

- <span data-ttu-id="e73fd-109">[!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)]安装程序将安装使用 MSI 的适配器特定文件。</span><span class="sxs-lookup"><span data-stu-id="e73fd-109">The [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)] setup installs the adapter specific files using an MSI.</span></span> <span data-ttu-id="e73fd-110">因此，安装程序的日志记录将是标准的 MSI 日志记录。</span><span class="sxs-lookup"><span data-stu-id="e73fd-110">Hence, the logging for the setup will be the standard MSI logging.</span></span>  

- <span data-ttu-id="e73fd-111">安装程序执行的自定义操作的日志位于 %temp%\adaptersetup.log。</span><span class="sxs-lookup"><span data-stu-id="e73fd-111">Logs for the custom actions performed by the setup program are available at %TEMP%\adaptersetup.log.</span></span> <span data-ttu-id="e73fd-112">如果跟踪日志文件失败，跟踪还提供了在事件日志。</span><span class="sxs-lookup"><span data-stu-id="e73fd-112">If the tracing to the log file fails, the traces are also available in the event log.</span></span>  

## <a name="known-issues"></a><span data-ttu-id="e73fd-113">已知问题</span><span class="sxs-lookup"><span data-stu-id="e73fd-113">Known Issues</span></span>  

### <a name="setup-fails-to-register-adapter-bindings"></a><span data-ttu-id="e73fd-114">安装程序无法注册适配器绑定</span><span class="sxs-lookup"><span data-stu-id="e73fd-114">Setup fails to register adapter bindings</span></span>  
 <span data-ttu-id="e73fd-115">**问题**</span><span class="sxs-lookup"><span data-stu-id="e73fd-115">**Problem**</span></span>  

 <span data-ttu-id="e73fd-116">在 Microsoft[!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)]安装向导无法注册[!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]绑定或[!INCLUDE[adoprovidersiebelshort](../../includes/adoprovidersiebelshort-md.md)]，但将继续进行安装适配器。</span><span class="sxs-lookup"><span data-stu-id="e73fd-116">The Microsoft [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)] setup wizard fails to register the [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)] binding or the [!INCLUDE[adoprovidersiebelshort](../../includes/adoprovidersiebelshort-md.md)], but proceeds with the adapter installation.</span></span>  

 <span data-ttu-id="e73fd-117">**原因**</span><span class="sxs-lookup"><span data-stu-id="e73fd-117">**Cause**</span></span>  

 <span data-ttu-id="e73fd-118">这可能会由于 WCF 安装问题而导致[!INCLUDE[afproductnamelong](../../includes/afproductnamelong-md.md)]安装或 machine.config 被损坏。</span><span class="sxs-lookup"><span data-stu-id="e73fd-118">This might result due to problems with WCF installation, [!INCLUDE[afproductnamelong](../../includes/afproductnamelong-md.md)] installation, or the machine.config being corrupt.</span></span> <span data-ttu-id="e73fd-119">适配器绑定写入到 machine.config 文件中。</span><span class="sxs-lookup"><span data-stu-id="e73fd-119">The adapter bindings are written to the machine.config file.</span></span>  

 <span data-ttu-id="e73fd-120">**解决方法**</span><span class="sxs-lookup"><span data-stu-id="e73fd-120">**Resolution**</span></span>  

<span data-ttu-id="e73fd-121">手动注册[!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]绑定和[!INCLUDE[adoprovidersiebelshort](../../includes/adoprovidersiebelshort-md.md)]使用以下步骤：</span><span class="sxs-lookup"><span data-stu-id="e73fd-121">Manually register the [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)] binding and [!INCLUDE[adoprovidersiebelshort](../../includes/adoprovidersiebelshort-md.md)] using the following steps:</span></span> 

1. <span data-ttu-id="e73fd-122">导航到计算机上的 machine.config 文件。</span><span class="sxs-lookup"><span data-stu-id="e73fd-122">Navigate to the machine.config file on the computer.</span></span> <span data-ttu-id="e73fd-123">例如，在 32 位平台上，在 machine.config 位于下\<系统驱动器\>: \WINDOWS\Microsoft.NET\Framework\\< 版本\>\CONFIG。</span><span class="sxs-lookup"><span data-stu-id="e73fd-123">For example, on a 32-bit platform, the machine.config is available under \<system drive\>:\WINDOWS\Microsoft.NET\Framework\\<version\>\CONFIG.</span></span>  

    <span data-ttu-id="e73fd-124">在此路径中，\<版本\>是.NET Framework 的版本。</span><span class="sxs-lookup"><span data-stu-id="e73fd-124">In this path, \<version\> is the version of the .NET Framework.</span></span>  

2. <span data-ttu-id="e73fd-125">打开文件使用文本编辑器。</span><span class="sxs-lookup"><span data-stu-id="e73fd-125">Open the file using a text editor.</span></span>  

3. <span data-ttu-id="e73fd-126">若要注册[!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]绑定：</span><span class="sxs-lookup"><span data-stu-id="e73fd-126">To register the [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)] binding:</span></span>  

   1. <span data-ttu-id="e73fd-127">搜索元素"的 system.serviceModel"并将其下的以下代码添加：</span><span class="sxs-lookup"><span data-stu-id="e73fd-127">Search for the element "system.serviceModel" and add the following under it:</span></span>  

      ```  
      <client>  
        <endpoint binding="siebelBinding" contract="IMetadataExchange" name="siebel" />  
      </client>  
      ```  

   2. <span data-ttu-id="e73fd-128">搜索"bindingElementExtensions"system.serviceModel\extensions 下的元素。</span><span class="sxs-lookup"><span data-stu-id="e73fd-128">Search for the element "bindingElementExtensions" under system.serviceModel\extensions.</span></span>  

   3. <span data-ttu-id="e73fd-129">查找缺失[!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]绑定。</span><span class="sxs-lookup"><span data-stu-id="e73fd-129">Look for the missing [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)] binding.</span></span> <span data-ttu-id="e73fd-130">添加"bindingElementExtensions"节点下的以下部分。</span><span class="sxs-lookup"><span data-stu-id="e73fd-130">Add the following section under the "bindingElementExtensions" node.</span></span>  

       <span data-ttu-id="e73fd-131">有关[!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]，添加：</span><span class="sxs-lookup"><span data-stu-id="e73fd-131">For [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)], add:</span></span>  

      ```  
      <add name="siebelAdapter" type="Microsoft.Adapters.Siebel.SiebelAdapterExtensionElement,Microsoft.Adapters.Siebel, Version=<version>, Culture=neutral, PublicKeyToken=<public key>" />  
      ```  

   4. <span data-ttu-id="e73fd-132">搜索"bindingExtensions"system.serviceModel\extensions 下的元素。</span><span class="sxs-lookup"><span data-stu-id="e73fd-132">Search for the element "bindingExtensions" under system.serviceModel\extensions.</span></span>  

   5. <span data-ttu-id="e73fd-133">查找缺失[!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]绑定。</span><span class="sxs-lookup"><span data-stu-id="e73fd-133">Look for the missing [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)] binding.</span></span> <span data-ttu-id="e73fd-134">添加以下各节"bindingExtensions"节点下。</span><span class="sxs-lookup"><span data-stu-id="e73fd-134">Add the following sections under the "bindingExtensions" node.</span></span>  

       <span data-ttu-id="e73fd-135">有关[!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]，添加：</span><span class="sxs-lookup"><span data-stu-id="e73fd-135">For [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)], add:</span></span>  

      ```  
      <add name="siebelBinding" type="Microsoft.Adapters.Siebel.SiebelAdapterBindingSection,Microsoft.Adapters.Siebel, Version=<version>, Culture=neutral, PublicKeyToken=<public key>" />  
      ```  

      > [!NOTE]
      >  <span data-ttu-id="e73fd-136">有关如何确定的公钥的信息，请参阅[确定公用密钥和版本](#BKMK_PubKey)。</span><span class="sxs-lookup"><span data-stu-id="e73fd-136">For information about how to determine the public key, see [Determining the Public Key and Version](#BKMK_PubKey).</span></span>  

4. <span data-ttu-id="e73fd-137">若要注册[!INCLUDE[adoprovidersiebelshort](../../includes/adoprovidersiebelshort-md.md)]:</span><span class="sxs-lookup"><span data-stu-id="e73fd-137">To register the [!INCLUDE[adoprovidersiebelshort](../../includes/adoprovidersiebelshort-md.md)]:</span></span>  

   1. <span data-ttu-id="e73fd-138">搜索元素 DbProviderFactories system.data 节点下。</span><span class="sxs-lookup"><span data-stu-id="e73fd-138">Search for the element DbProviderFactories under the system.data node.</span></span>  

   2. <span data-ttu-id="e73fd-139">查找缺失[!INCLUDE[adoprovidersiebelshort](../../includes/adoprovidersiebelshort-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="e73fd-139">Look for the missing [!INCLUDE[adoprovidersiebelshort](../../includes/adoprovidersiebelshort-md.md)].</span></span> <span data-ttu-id="e73fd-140">添加 DbProviderFactories 节点下的以下部分。</span><span class="sxs-lookup"><span data-stu-id="e73fd-140">Add the following section under the DbProviderFactories node.</span></span>  

       <span data-ttu-id="e73fd-141">有关[!INCLUDE[adoprovidersiebelshort](../../includes/adoprovidersiebelshort-md.md)]，添加：</span><span class="sxs-lookup"><span data-stu-id="e73fd-141">For [!INCLUDE[adoprovidersiebelshort](../../includes/adoprovidersiebelshort-md.md)], add:</span></span>  

      ```  
      <add name="SiebelClient Data Provider" invariant="Microsoft.Data.SiebelClient"  
          description=".NET Framework Data Provider for Siebel eBusiness Applications"  
          type="Microsoft.Data.SiebelClient.SiebelProviderFactory,Microsoft.Data.SiebelClient, Version=<version>, Culture=neutral, PublicKeyToken=<public key>" />  
      ```  

5. <span data-ttu-id="e73fd-142">保存并关闭 machine.config 文件。</span><span class="sxs-lookup"><span data-stu-id="e73fd-142">Save and close the machine.config file.</span></span>  

####  <a name="BKMK_PubKey"></a> <span data-ttu-id="e73fd-143">确定公用密钥和版本</span><span class="sxs-lookup"><span data-stu-id="e73fd-143">Determining the Public Key and Version</span></span>  
 <span data-ttu-id="e73fd-144">执行以下步骤来确定的公钥[!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]或[!INCLUDE[adoprovidersiebelshort](../../includes/adoprovidersiebelshort-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="e73fd-144">Perform the following steps to determine the public key for [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)] or [!INCLUDE[adoprovidersiebelshort](../../includes/adoprovidersiebelshort-md.md)].</span></span>  

###### <a name="to-determine-the-public-key"></a><span data-ttu-id="e73fd-145">若要确定的公钥</span><span class="sxs-lookup"><span data-stu-id="e73fd-145">To determine the public key</span></span>  

1. <span data-ttu-id="e73fd-146">导航到 Windows 目录，通常 C:\WINDOWS\assembly。</span><span class="sxs-lookup"><span data-stu-id="e73fd-146">Navigate to the Windows directory, typically C:\WINDOWS\assembly.</span></span>  

2. <span data-ttu-id="e73fd-147">右键单击的 DLL 键并选择希望公众**属性**。</span><span class="sxs-lookup"><span data-stu-id="e73fd-147">Right-click the DLL for which you want the public key and select **Properties**.</span></span> <span data-ttu-id="e73fd-148">下表列出了为每个适配器和提供程序 Dll 的名称。</span><span class="sxs-lookup"><span data-stu-id="e73fd-148">The following table lists the name of the DLLs for each adapter and provider.</span></span>  


   |                              <span data-ttu-id="e73fd-149">适配器/ADO 提供程序</span><span class="sxs-lookup"><span data-stu-id="e73fd-149">Adapter/ADO Provider</span></span>                               |       <span data-ttu-id="e73fd-150">DLL 的名称</span><span class="sxs-lookup"><span data-stu-id="e73fd-150">Name of the DLL</span></span>       |
   |---------------------------------------------------------------------------------|-----------------------------|
   |    [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]    |  <span data-ttu-id="e73fd-151">Microsoft.Adapters.Siebel</span><span class="sxs-lookup"><span data-stu-id="e73fd-151">Microsoft.Adapters.Siebel</span></span>  |
   | [!INCLUDE[adoprovidersiebelshort](../../includes/adoprovidersiebelshort-md.md)] | <span data-ttu-id="e73fd-152">Microsoft.Data.SiebelClient</span><span class="sxs-lookup"><span data-stu-id="e73fd-152">Microsoft.Data.SiebelClient</span></span> |


3. <span data-ttu-id="e73fd-153">上**常规**选项卡上，针对值**公钥标记**标签指定 DLL 的公共密钥。</span><span class="sxs-lookup"><span data-stu-id="e73fd-153">On the **General** tab, the value against the **Public Key Token** label specifies the public key for the DLL.</span></span> <span data-ttu-id="e73fd-154">同样，针对值**版本**标签指定 dll 的版本号。</span><span class="sxs-lookup"><span data-stu-id="e73fd-154">Similarly, value against the **Version** label specifies the version number for the DLL.</span></span>  

4. <span data-ttu-id="e73fd-155">复制公钥，，然后单击**取消**。</span><span class="sxs-lookup"><span data-stu-id="e73fd-155">Copy the public key, and then click **Cancel**.</span></span>  

## <a name="see-also"></a><span data-ttu-id="e73fd-156">请参阅</span><span class="sxs-lookup"><span data-stu-id="e73fd-156">See Also</span></span>  
[<span data-ttu-id="e73fd-157">Siebel 适配器疑难解答</span><span class="sxs-lookup"><span data-stu-id="e73fd-157">Troubleshoot the Siebel adapter</span></span>](../../adapters-and-accelerators/adapter-siebel/troubleshoot-the-siebel-adapter.md)