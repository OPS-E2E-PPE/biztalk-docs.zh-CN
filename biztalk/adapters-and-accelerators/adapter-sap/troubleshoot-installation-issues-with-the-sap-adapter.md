---
title: '使用 SAP 适配器进行故障排除安装问题: |Microsoft Docs'
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
ms.assetid: fdfdaf44-c32d-43a5-998d-02032c0b9211
caps.latest.revision: 15
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a72a5e2da055a9e4137e3e8954b72ad32cde40db
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36982726"
---
# <a name="troubleshoot-installation-issues-with-the-sap-adapter"></a><span data-ttu-id="fd8bc-102">使用 SAP 适配器进行故障排除安装问题：</span><span class="sxs-lookup"><span data-stu-id="fd8bc-102">Troubleshoot Installation Issues with the SAP adapter</span></span>
<span data-ttu-id="fd8bc-103">安装 Microsoft[!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)]复制产品二进制文件的计算机上并注册每个适配器的绑定。</span><span class="sxs-lookup"><span data-stu-id="fd8bc-103">Installation of the Microsoft [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)] copies the product binaries on the computer and registers the bindings for each adapter.</span></span> <span data-ttu-id="fd8bc-104">本部分讨论故障排除技术来解决安装错误。</span><span class="sxs-lookup"><span data-stu-id="fd8bc-104">This section discusses troubleshooting techniques to resolve installation errors.</span></span>  

## <a name="logging-messages-for-setup-actions"></a><span data-ttu-id="fd8bc-105">安装程序操作的日志记录消息</span><span class="sxs-lookup"><span data-stu-id="fd8bc-105">Logging Messages for Setup Actions</span></span>  
 <span data-ttu-id="fd8bc-106">[!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)]的安装程序进行安装的标准任务[!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="fd8bc-106">The [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)] setup program performs the standard task of installing the [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)].</span></span> <span data-ttu-id="fd8bc-107">此外，安装程序还执行某些自定义操作，例如注册适配器绑定。</span><span class="sxs-lookup"><span data-stu-id="fd8bc-107">Additionally, the setup also performs certain custom actions such as registering the adapter bindings.</span></span> <span data-ttu-id="fd8bc-108">你可以记录这两个的标准，以及自定义操作安装程序将执行的消息。</span><span class="sxs-lookup"><span data-stu-id="fd8bc-108">You can log messages for both the standard as well as custom actions that the setup performs.</span></span>  

- <span data-ttu-id="fd8bc-109">[!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)]安装程序将安装使用 MSI 的适配器特定文件。</span><span class="sxs-lookup"><span data-stu-id="fd8bc-109">The [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)] setup installs the adapter specific files using an MSI.</span></span> <span data-ttu-id="fd8bc-110">因此，安装程序的日志记录是标准的 MSI 日志记录。</span><span class="sxs-lookup"><span data-stu-id="fd8bc-110">Hence, the logging for the setup is the standard MSI logging.</span></span>  

- <span data-ttu-id="fd8bc-111">安装程序执行的自定义操作的日志位于 %temp%\adaptersetup.log。</span><span class="sxs-lookup"><span data-stu-id="fd8bc-111">Logs for the custom actions that the setup program performs are available at %TEMP%\adaptersetup.log.</span></span> <span data-ttu-id="fd8bc-112">如果跟踪日志文件失败，跟踪还提供了在事件日志。</span><span class="sxs-lookup"><span data-stu-id="fd8bc-112">If the tracing to the log file fails, the traces are also available in the event log.</span></span>  

##  <a name="BKMK_SAPSetupBinding"></a> <span data-ttu-id="fd8bc-113">安装程序无法注册适配器绑定或数据访问接口</span><span class="sxs-lookup"><span data-stu-id="fd8bc-113">Setup fails to register adapter bindings or data providers</span></span>  
 <span data-ttu-id="fd8bc-114">**问题**</span><span class="sxs-lookup"><span data-stu-id="fd8bc-114">**Problem**</span></span>  

 <span data-ttu-id="fd8bc-115">在 Microsoft[!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)]安装向导无法注册适配器绑定或[!INCLUDE[adoprovidersaplong](../../includes/adoprovidersaplong-md.md)]，但将继续进行安装适配器。</span><span class="sxs-lookup"><span data-stu-id="fd8bc-115">The Microsoft [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)] setup wizard fails to register the adapter bindings or the [!INCLUDE[adoprovidersaplong](../../includes/adoprovidersaplong-md.md)], but proceeds with the adapter installation.</span></span>  

 <span data-ttu-id="fd8bc-116">**原因**</span><span class="sxs-lookup"><span data-stu-id="fd8bc-116">**Cause**</span></span>  

 <span data-ttu-id="fd8bc-117">这可能会由于存在问题导致[!INCLUDE[firstref_btsWinCommFoundation](../../includes/firstref-btswincommfoundation-md.md)]安装，[!INCLUDE[afproductnamelong](../../includes/afproductnamelong-md.md)]安装或被损坏的 machine.config 文件。</span><span class="sxs-lookup"><span data-stu-id="fd8bc-117">This might result due to problems with [!INCLUDE[firstref_btsWinCommFoundation](../../includes/firstref-btswincommfoundation-md.md)] installation, [!INCLUDE[afproductnamelong](../../includes/afproductnamelong-md.md)] installation, or the machine.config file being corrupt.</span></span> <span data-ttu-id="fd8bc-118">适配器绑定写入到 machine.config 文件中。</span><span class="sxs-lookup"><span data-stu-id="fd8bc-118">The adapter bindings are written to the machine.config file.</span></span>  

 <span data-ttu-id="fd8bc-119">**解决方法**</span><span class="sxs-lookup"><span data-stu-id="fd8bc-119">**Resolution**</span></span>  

 <span data-ttu-id="fd8bc-120">您应手动注册[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]绑定或[!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="fd8bc-120">You should manually register the [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] binding or the [!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)].</span></span>  

### <a name="register-the-adapter-bindings-or-the-data-provider"></a><span data-ttu-id="fd8bc-121">注册适配器绑定或数据提供程序</span><span class="sxs-lookup"><span data-stu-id="fd8bc-121">Register the adapter bindings or the data provider</span></span>  

1. <span data-ttu-id="fd8bc-122">导航到计算机上的 machine.config 文件。</span><span class="sxs-lookup"><span data-stu-id="fd8bc-122">Navigate to the machine.config file on the computer.</span></span> <span data-ttu-id="fd8bc-123">例如，在 32 位平台上，在 machine.config 位于下\<系统驱动器\>: \WINDOWS\Microsoft.NET\Framework\\< 版本\>\CONFIG。</span><span class="sxs-lookup"><span data-stu-id="fd8bc-123">For example, on a 32-bit platform, the machine.config is available under \<system drive\>:\WINDOWS\Microsoft.NET\Framework\\<version\>\CONFIG.</span></span>  

    <span data-ttu-id="fd8bc-124">在此路径中，\<版本\>是.NET Framework 的版本。</span><span class="sxs-lookup"><span data-stu-id="fd8bc-124">In this path, \<version\> is the version of the .NET Framework.</span></span>  

2. <span data-ttu-id="fd8bc-125">打开文件使用文本编辑器。</span><span class="sxs-lookup"><span data-stu-id="fd8bc-125">Open the file using a text editor.</span></span>  

3. <span data-ttu-id="fd8bc-126">若要注册[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]绑定：</span><span class="sxs-lookup"><span data-stu-id="fd8bc-126">To register the [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] binding:</span></span>  

   1. <span data-ttu-id="fd8bc-127">搜索元素"的 system.serviceModel"并将其下的以下代码添加：</span><span class="sxs-lookup"><span data-stu-id="fd8bc-127">Search for the element "system.serviceModel" and add the following under it:</span></span>  

      ```  
      <client>  
        <endpoint binding="sapBinding" contract="IMetadataExchange" name="sap" />  
      </client>  
      ```  

   2. <span data-ttu-id="fd8bc-128">搜索"bindingElementExtensions"system.serviceModel\extensions 下的元素。</span><span class="sxs-lookup"><span data-stu-id="fd8bc-128">Search for the element "bindingElementExtensions" under system.serviceModel\extensions.</span></span>  

   3. <span data-ttu-id="fd8bc-129">查找缺失[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]绑定。</span><span class="sxs-lookup"><span data-stu-id="fd8bc-129">Look for the missing [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] binding.</span></span> <span data-ttu-id="fd8bc-130">添加"bindingElementExtensions"节点下的以下部分。</span><span class="sxs-lookup"><span data-stu-id="fd8bc-130">Add the following section under the "bindingElementExtensions" node.</span></span>  

       <span data-ttu-id="fd8bc-131">有关[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]，添加：</span><span class="sxs-lookup"><span data-stu-id="fd8bc-131">For [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)], add:</span></span>  

      ```  
      <add name="sapAdapter" type="Microsoft.Adapters.SAP.SAPAdapterExtensionElement,Microsoft.Adapters.SAP, Version=<version>, Culture=neutral, PublicKeyToken=<public key>" />  
      ```  

   4. <span data-ttu-id="fd8bc-132">搜索"bindingExtensions"system.serviceModel\extensions 下的元素。</span><span class="sxs-lookup"><span data-stu-id="fd8bc-132">Search for the element "bindingExtensions" under system.serviceModel\extensions.</span></span>  

   5. <span data-ttu-id="fd8bc-133">查找缺失[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]绑定。</span><span class="sxs-lookup"><span data-stu-id="fd8bc-133">Look for the missing [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] binding.</span></span> <span data-ttu-id="fd8bc-134">添加"bindingExtensions"节点下的以下部分。</span><span class="sxs-lookup"><span data-stu-id="fd8bc-134">Add the following section under the "bindingExtensions" node.</span></span>  

       <span data-ttu-id="fd8bc-135">有关[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]，添加：</span><span class="sxs-lookup"><span data-stu-id="fd8bc-135">For [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)], add:</span></span>  

      ```  
      <add name="sapBinding" type="Microsoft.Adapters.SAP.SAPAdapterBindingSection,Microsoft.Adapters.SAP, Version=<version>, Culture=neutral, PublicKeyToken=<public key>" />  
      ```  

      > [!NOTE]
      >  <span data-ttu-id="fd8bc-136">有关如何确定的公钥的信息，请参阅[确定公用密钥和版本](#BKMK_PubKey)。</span><span class="sxs-lookup"><span data-stu-id="fd8bc-136">For information about how to determine the public key, see [Determining the Public Key and Version](#BKMK_PubKey).</span></span>  

4. <span data-ttu-id="fd8bc-137">若要注册[!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)]:</span><span class="sxs-lookup"><span data-stu-id="fd8bc-137">To register the [!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)]:</span></span>  

   1. <span data-ttu-id="fd8bc-138">搜索"system.data"节点下的元素"DbProviderFactories"。</span><span class="sxs-lookup"><span data-stu-id="fd8bc-138">Search for the element "DbProviderFactories" under the "system.data" node.</span></span>  

   2. <span data-ttu-id="fd8bc-139">查找缺失[!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="fd8bc-139">Look for the missing [!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)].</span></span> <span data-ttu-id="fd8bc-140">添加"DbProviderFactories"节点下的以下部分。</span><span class="sxs-lookup"><span data-stu-id="fd8bc-140">Add the following section under the "DbProviderFactories" node.</span></span>  

       <span data-ttu-id="fd8bc-141">有关[!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)]，添加：</span><span class="sxs-lookup"><span data-stu-id="fd8bc-141">For [!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)], add:</span></span>  

      ```  
      <add name="SAPClient Data Provider" invariant="Microsoft.Data.SAPClient" description=".NET Framework Data Provider for mySAP Business Suite" type="Microsoft.Data.SAPClient.SAPClientFactory,Microsoft.Data.SAPClient, Version=<version>, Culture=neutral, PublicKeyToken=<public key>" />  
      ```  

5. <span data-ttu-id="fd8bc-142">保存并关闭 machine.config 文件。</span><span class="sxs-lookup"><span data-stu-id="fd8bc-142">Save and close the machine.config file.</span></span>  

###  <a name="BKMK_PubKey"></a> <span data-ttu-id="fd8bc-143">确定公用密钥和版本</span><span class="sxs-lookup"><span data-stu-id="fd8bc-143">Determining the Public Key and Version</span></span>  
 <span data-ttu-id="fd8bc-144">执行以下步骤来确定的公钥[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]或[!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="fd8bc-144">Perform the following steps to determine the public key for [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] or [!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)].</span></span>  

1. <span data-ttu-id="fd8bc-145">导航到 Windows 目录，通常 C:\WINDOWS\assembly。</span><span class="sxs-lookup"><span data-stu-id="fd8bc-145">Navigate to the Windows directory, typically C:\WINDOWS\assembly.</span></span>  

2. <span data-ttu-id="fd8bc-146">右键单击的 DLL 为其也希望将公钥，并选择**属性**。</span><span class="sxs-lookup"><span data-stu-id="fd8bc-146">Right-click the DLL for which you want the public key, and then select **Properties**.</span></span> <span data-ttu-id="fd8bc-147">下表列出了为 Dll 的名称[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]和[!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="fd8bc-147">The following table lists the name of the DLLs for [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] and [!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)].</span></span>  


   |                           <span data-ttu-id="fd8bc-148">适配器/数据访问接口</span><span class="sxs-lookup"><span data-stu-id="fd8bc-148">Adapter/Data Provider</span></span>                           |     <span data-ttu-id="fd8bc-149">DLL 的名称</span><span class="sxs-lookup"><span data-stu-id="fd8bc-149">Name of the DLL</span></span>      |
   |---------------------------------------------------------------------------|--------------------------|
   |    [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]    |  <span data-ttu-id="fd8bc-150">Microsoft.Adapters.SAP</span><span class="sxs-lookup"><span data-stu-id="fd8bc-150">Microsoft.Adapters.SAP</span></span>  |
   | [!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)] | <span data-ttu-id="fd8bc-151">Microsoft.Data.SAPClient</span><span class="sxs-lookup"><span data-stu-id="fd8bc-151">Microsoft.Data.SAPClient</span></span> |


3. <span data-ttu-id="fd8bc-152">上**常规**选项卡上，针对值**公钥标记**标签指定 DLL 的公共密钥。</span><span class="sxs-lookup"><span data-stu-id="fd8bc-152">On the **General** tab, the value against the **Public Key Token** label specifies the public key for the DLL.</span></span> <span data-ttu-id="fd8bc-153">同样，针对值**版本**标签指定 dll 的版本号。</span><span class="sxs-lookup"><span data-stu-id="fd8bc-153">Similarly, value against the **Version** label specifies the version number for the DLL.</span></span>  

4. <span data-ttu-id="fd8bc-154">复制公钥，，然后单击**取消**。</span><span class="sxs-lookup"><span data-stu-id="fd8bc-154">Copy the public key, and then click **Cancel**.</span></span>  

##  <a name="BKMK_SAPConsumeBinding"></a> <span data-ttu-id="fd8bc-155">任何有效的适配器不，已安装的错误</span><span class="sxs-lookup"><span data-stu-id="fd8bc-155">No valid adapters are installed error</span></span>

 <span data-ttu-id="fd8bc-156">**问题**</span><span class="sxs-lookup"><span data-stu-id="fd8bc-156">**Problem**</span></span>  

 <span data-ttu-id="fd8bc-157">使用[!INCLUDE[addadapterservreflong](../../includes/addadapterservreflong-md.md)]或[!INCLUDE[consumeadapterservlong](../../includes/consumeadapterservlong-md.md)]从[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]运行的 64 位版本的 64 位计算机上[!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)]会导致以下错误：</span><span class="sxs-lookup"><span data-stu-id="fd8bc-157">Using the [!INCLUDE[addadapterservreflong](../../includes/addadapterservreflong-md.md)] or the [!INCLUDE[consumeadapterservlong](../../includes/consumeadapterservlong-md.md)] from [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)] on a 64-bit computer running 64-bit version of the [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)] results in the following error:</span></span>  

```  
No valid adapters are installed on this machine  
```  

 <span data-ttu-id="fd8bc-158">**原因**</span><span class="sxs-lookup"><span data-stu-id="fd8bc-158">**Cause**</span></span>  

 <span data-ttu-id="fd8bc-159">[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]是 WCF 自定义绑定，后者在 machine.config 文件中的 System.ServiceModel 下注册。</span><span class="sxs-lookup"><span data-stu-id="fd8bc-159">The [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] is a WCF custom binding, which is registered under System.ServiceModel in the machine.config file.</span></span> <span data-ttu-id="fd8bc-160">64 位平台都有两个 machine.config 文件、 一个 32 位应用程序使用，另一个 64 位应用程序使用。</span><span class="sxs-lookup"><span data-stu-id="fd8bc-160">A 64-bit platform has two machine.config files, one used by the 32-bit applications and the other used by the 64-bit applications.</span></span> <span data-ttu-id="fd8bc-161">因此，当你安装 64 位版本的[!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)]，安装向导在 machine.config 文件的 64 位版本中注册绑定。</span><span class="sxs-lookup"><span data-stu-id="fd8bc-161">So, when you install the 64-bit version of the [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)], the setup wizard registers the bindings in the 64-bit version of the machine.config file.</span></span> <span data-ttu-id="fd8bc-162">但是，[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]作为 32 位进程运行，因此启动[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]从[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]，该插件检查 machine.config 文件的 32 位版本中的绑定并失败错误。</span><span class="sxs-lookup"><span data-stu-id="fd8bc-162">However, [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)] runs as a 32-bit process and hence when you launch the [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)] from [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)], the plug-in checks for the bindings in the 32-bit version of the machine.config file and fails giving an error.</span></span>  

 <span data-ttu-id="fd8bc-163">**解决方法**</span><span class="sxs-lookup"><span data-stu-id="fd8bc-163">**Resolution**</span></span>  

- <span data-ttu-id="fd8bc-164">安装的 32 位和 64 位版本[!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)]64 位上[!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]安装。</span><span class="sxs-lookup"><span data-stu-id="fd8bc-164">Install both the 32-bit and 64-bit versions of the [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)] on a 64-bit [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)] installation.</span></span>  

  > [!IMPORTANT]
  >  <span data-ttu-id="fd8bc-165">必须只有 64 位[!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]安装。</span><span class="sxs-lookup"><span data-stu-id="fd8bc-165">You must only have a 64-bit [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)] installation.</span></span> <span data-ttu-id="fd8bc-166">通过并行安装 32 位和 64 位的[!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]不支持在一台计算机上。</span><span class="sxs-lookup"><span data-stu-id="fd8bc-166">Side-by-side installation of 32-bit and 64-bit [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)] on a single computer is not supported.</span></span>  

- <span data-ttu-id="fd8bc-167">添加的客户端 Dll 的 32 位和 64 位版本[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]（如 librfc32u.dll) 到 PATH 变量。</span><span class="sxs-lookup"><span data-stu-id="fd8bc-167">Add both the 32-bit and 64-bit versions of the client DLLs for the [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] (such as librfc32u.dll) to the PATH variable.</span></span> <span data-ttu-id="fd8bc-168">32 位版本的 Dll 必须添加到 C:\Windows\SysWow64 文件夹。</span><span class="sxs-lookup"><span data-stu-id="fd8bc-168">The 32-bit version of the DLLs must be added to C:\Windows\SysWow64 folder.</span></span> <span data-ttu-id="fd8bc-169">Dll 的 64 位版本必须添加到 C:\Windows\System32 文件夹中。</span><span class="sxs-lookup"><span data-stu-id="fd8bc-169">The 64-bit version of the DLLs must be added to C:\Windows\System32 folder.</span></span>  

  > [!IMPORTANT]
  >  <span data-ttu-id="fd8bc-170">如果在具有 64 位操作系统的计算机上运行的适配器 （32 位或 64 位），并且使用适配器来编写应用程序，应将标记作为适配器的相同类型 （32 位或 64 位） 到应用程序。</span><span class="sxs-lookup"><span data-stu-id="fd8bc-170">If the adapter (32 or 64-bit) is running on a computer that has a 64-bit operating system, and you are using the adapter to write an application, you should mark the application to the same type (32 or 64-bit) as the adapter.</span></span> <span data-ttu-id="fd8bc-171">此外，RFC SDK （32 位或 64 位） 的版本必须与适配器 （32 位或 64 位） 的版本相同。</span><span class="sxs-lookup"><span data-stu-id="fd8bc-171">Also, the version of the RFC SDK (32 or 64-bit) must be same as the version of the adapter (32 or 64-bit).</span></span>  
  >   
  >  <span data-ttu-id="fd8bc-172">例如，如果使用 64 位操作系统的计算机上运行 32 位适配器，适配器客户端应用程序必须标记为 32 位。</span><span class="sxs-lookup"><span data-stu-id="fd8bc-172">For example, if a 32-bit adapter is running on a computer with a 64-bit operating system, the adapter client application must be marked as 32-bit.</span></span>  

   <span data-ttu-id="fd8bc-173">有关 SAP 客户端 Dll 的详细信息，请参阅[适用于 SAP 数据提供程序安装自定义 Rfc](../../adapters-and-accelerators/adapter-sap/install-custom-rfcs-for-the-data-provider-for-sap.md)。</span><span class="sxs-lookup"><span data-stu-id="fd8bc-173">For more information about the SAP client DLLs, see [Install Custom RFCs for the Data Provider for SAP](../../adapters-and-accelerators/adapter-sap/install-custom-rfcs-for-the-data-provider-for-sap.md).</span></span>  

##  <a name="BKMK_SAPInvalidBinding"></a> <span data-ttu-id="fd8bc-174">配置 SAP 适配器的端口时无效的绑定错误</span><span class="sxs-lookup"><span data-stu-id="fd8bc-174">Invalid binding error while configuring SAP adapter ports</span></span>  
 <span data-ttu-id="fd8bc-175">**问题**</span><span class="sxs-lookup"><span data-stu-id="fd8bc-175">**Problem**</span></span>  

 <span data-ttu-id="fd8bc-176">当您尝试为中的适配器配置端口[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理控制台中，则会收到以下错误：</span><span class="sxs-lookup"><span data-stu-id="fd8bc-176">When you try to configure a port for the adapter in [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] Administration console, you get the following error:</span></span>  

```  
"Unable to create binding configuration element for editing. Check the values of the BindingType and BindingConfiguration properties.  
(Microsoft.Biztalk.Adapter.Wcf.Converters.CreateBindingException) Unable to get binding type for binding extension "sapBinding".  
Verify the binding extension is registered in machine.config."  
```  

 <span data-ttu-id="fd8bc-177">**原因**</span><span class="sxs-lookup"><span data-stu-id="fd8bc-177">**Cause**</span></span>  

 <span data-ttu-id="fd8bc-178">[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]是 WCF 自定义绑定，后者在 machine.config 文件中的 System.ServiceModel 下注册。</span><span class="sxs-lookup"><span data-stu-id="fd8bc-178">The [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] is a WCF custom binding, which is registered under System.ServiceModel in the machine.config file.</span></span> <span data-ttu-id="fd8bc-179">64 位平台都有两个 machine.config 文件、 一个 32 位应用程序使用，另一个 64 位应用程序使用。</span><span class="sxs-lookup"><span data-stu-id="fd8bc-179">A 64-bit platform has two machine.config files, one used by the 32-bit applications and the other used by the 64-bit applications.</span></span> <span data-ttu-id="fd8bc-180">因此，当你安装 64 位版本的[!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)]，安装向导在 machine.config 文件的 64 位版本中注册绑定。</span><span class="sxs-lookup"><span data-stu-id="fd8bc-180">So, when you install the 64-bit version of the [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)], the setup wizard registers the bindings in the 64-bit version of the machine.config file.</span></span> <span data-ttu-id="fd8bc-181">但是，[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]作为 32 位进程运行管理控制台，因此在配置适配器的端口时，它会检查 32 位版本的 machine.config 文件中的绑定和失败错误。</span><span class="sxs-lookup"><span data-stu-id="fd8bc-181">However, [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] Administration console runs as a 32-bit process and hence when you configure a port for the adapter, it checks for the bindings in the 32-bit version of the machine.config file and fails giving an error.</span></span>  

 <span data-ttu-id="fd8bc-182">**解决方法**</span><span class="sxs-lookup"><span data-stu-id="fd8bc-182">**Resolution**</span></span>  

- <span data-ttu-id="fd8bc-183">安装的 32 位和 64 位版本[!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)]64 位上[!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]安装。</span><span class="sxs-lookup"><span data-stu-id="fd8bc-183">Install both the 32-bit and 64-bit versions of the [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)] on a 64-bit [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)] installation.</span></span>  

  > [!IMPORTANT]
  >  <span data-ttu-id="fd8bc-184">必须只有 64 位[!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]安装。</span><span class="sxs-lookup"><span data-stu-id="fd8bc-184">You must only have a 64-bit [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)] installation.</span></span> <span data-ttu-id="fd8bc-185">通过并行安装 32 位和 64 位的[!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]不支持在一台计算机上。</span><span class="sxs-lookup"><span data-stu-id="fd8bc-185">Side-by-side installation of 32-bit and 64-bit [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)] on a single computer is not supported.</span></span>  

- <span data-ttu-id="fd8bc-186">添加的客户端 Dll 的 32 位和 64 位版本[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]（如 librfc32u.dll) 到 PATH 变量。</span><span class="sxs-lookup"><span data-stu-id="fd8bc-186">Add both the 32-bit and 64-bit versions of the client DLLs for the [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] (such as librfc32u.dll) to the PATH variable.</span></span> <span data-ttu-id="fd8bc-187">32 位版本的 Dll 必须添加到 C:\Windows\SysWow64 文件夹。</span><span class="sxs-lookup"><span data-stu-id="fd8bc-187">The 32-bit version of the DLLs must be added to C:\Windows\SysWow64 folder.</span></span> <span data-ttu-id="fd8bc-188">Dll 的 64 位版本必须添加到 C:\Windows\System32 文件夹中。</span><span class="sxs-lookup"><span data-stu-id="fd8bc-188">The 64-bit version of the DLLs must be added to C:\Windows\System32 folder.</span></span>  

  > [!IMPORTANT]
  >  <span data-ttu-id="fd8bc-189">如果在具有 64 位操作系统的计算机上运行的适配器 （32 位或 64 位），并且使用适配器来编写应用程序，应将标记作为适配器的相同类型 （32 位或 64 位） 到应用程序。</span><span class="sxs-lookup"><span data-stu-id="fd8bc-189">If the adapter (32 or 64-bit) is running on a computer that has a 64-bit operating system, and you are using the adapter to write an application, you should mark the application to the same type (32 or 64-bit) as the adapter.</span></span> <span data-ttu-id="fd8bc-190">此外，RFC SDK （32 位或 64 位） 的版本必须与适配器 （32 位或 64 位） 的版本相同。</span><span class="sxs-lookup"><span data-stu-id="fd8bc-190">Also, the version of the RFC SDK (32 or 64-bit) must be same as the version of the adapter (32 or 64-bit).</span></span>  
  >   
  >  <span data-ttu-id="fd8bc-191">例如，如果使用 64 位操作系统的计算机上运行 32 位适配器，适配器客户端应用程序必须标记为 32 位。</span><span class="sxs-lookup"><span data-stu-id="fd8bc-191">For example, if a 32-bit adapter is running on a computer with a 64-bit operating system, the adapter client application must be marked as 32-bit.</span></span>  

   <span data-ttu-id="fd8bc-192">有关 SAP 客户端 Dll 的详细信息，请参阅[适用于 SAP 数据提供程序安装自定义 Rfc](../../adapters-and-accelerators/adapter-sap/install-custom-rfcs-for-the-data-provider-for-sap.md)。</span><span class="sxs-lookup"><span data-stu-id="fd8bc-192">For more information about the SAP client DLLs, see [Install Custom RFCs for the Data Provider for SAP](../../adapters-and-accelerators/adapter-sap/install-custom-rfcs-for-the-data-provider-for-sap.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="fd8bc-193">请参阅</span><span class="sxs-lookup"><span data-stu-id="fd8bc-193">See Also</span></span>  
[<span data-ttu-id="fd8bc-194">SAP 适配器疑难解答</span><span class="sxs-lookup"><span data-stu-id="fd8bc-194">Troubleshoot the SAP adapter</span></span>](../../adapters-and-accelerators/adapter-sap/troubleshoot-the-sap-adapter.md)