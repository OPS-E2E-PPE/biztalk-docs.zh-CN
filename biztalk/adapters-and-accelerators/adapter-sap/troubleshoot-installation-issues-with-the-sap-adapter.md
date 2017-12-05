---
title: "与 SAP 适配器解决安装问题 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- troubleshooting, installation
- installation, troubleshooting
ms.assetid: fdfdaf44-c32d-43a5-998d-02032c0b9211
caps.latest.revision: "15"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: dc33d5d15ef876e18a5a17fa33944dd7d1b36461
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/28/2017
---
# <a name="troubleshoot-installation-issues-with-the-sap-adapter"></a><span data-ttu-id="64764-102">与 SAP 适配器解决安装问题</span><span class="sxs-lookup"><span data-stu-id="64764-102">Troubleshoot Installation Issues with the SAP adapter</span></span>
<span data-ttu-id="64764-103">安装 Microsoft[!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)]复制产品二进制文件的计算机上并注册每个适配器的绑定。</span><span class="sxs-lookup"><span data-stu-id="64764-103">Installation of the Microsoft [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)] copies the product binaries on the computer and registers the bindings for each adapter.</span></span> <span data-ttu-id="64764-104">本部分讨论故障排除方法来解决安装错误。</span><span class="sxs-lookup"><span data-stu-id="64764-104">This section discusses troubleshooting techniques to resolve installation errors.</span></span>  
  
## <a name="logging-messages-for-setup-actions"></a><span data-ttu-id="64764-105">安装程序操作的日志记录消息</span><span class="sxs-lookup"><span data-stu-id="64764-105">Logging Messages for Setup Actions</span></span>  
 <span data-ttu-id="64764-106">[!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)]安装程序执行安装的标准任务[!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="64764-106">The [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)] setup program performs the standard task of installing the [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)].</span></span> <span data-ttu-id="64764-107">此外，安装程序还执行某些自定义操作，例如注册的适配器绑定。</span><span class="sxs-lookup"><span data-stu-id="64764-107">Additionally, the setup also performs certain custom actions such as registering the adapter bindings.</span></span> <span data-ttu-id="64764-108">可以记录这两个标准以及自定义操作的安装程序将执行的消息。</span><span class="sxs-lookup"><span data-stu-id="64764-108">You can log messages for both the standard as well as custom actions that the setup performs.</span></span>  
  
-   <span data-ttu-id="64764-109">[!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)]安装程序将安装使用 MSI 的适配器特定文件。</span><span class="sxs-lookup"><span data-stu-id="64764-109">The [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)] setup installs the adapter specific files using an MSI.</span></span> <span data-ttu-id="64764-110">因此，安装程序的日志记录是标准的 MSI 日志记录。</span><span class="sxs-lookup"><span data-stu-id="64764-110">Hence, the logging for the setup is the standard MSI logging.</span></span>  
  
-   <span data-ttu-id="64764-111">安装程序执行的自定义操作的日志位于 %temp%\adaptersetup.log。</span><span class="sxs-lookup"><span data-stu-id="64764-111">Logs for the custom actions that the setup program performs are available at %TEMP%\adaptersetup.log.</span></span> <span data-ttu-id="64764-112">如果跟踪日志文件失败，跟踪也会出现在事件日志。</span><span class="sxs-lookup"><span data-stu-id="64764-112">If the tracing to the log file fails, the traces are also available in the event log.</span></span>  
  
##  <a name="BKMK_SAPSetupBinding"></a><span data-ttu-id="64764-113">安装程序无法注册适配器绑定或数据访问接口</span><span class="sxs-lookup"><span data-stu-id="64764-113">Setup fails to register adapter bindings or data providers</span></span>  
 <span data-ttu-id="64764-114">**问题**</span><span class="sxs-lookup"><span data-stu-id="64764-114">**Problem**</span></span>  
  
 <span data-ttu-id="64764-115">Microsoft[!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)]安装向导无法注册的适配器绑定或[!INCLUDE[adoprovidersaplong](../../includes/adoprovidersaplong-md.md)]，但与适配器安装继续进行。</span><span class="sxs-lookup"><span data-stu-id="64764-115">The Microsoft [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)] setup wizard fails to register the adapter bindings or the [!INCLUDE[adoprovidersaplong](../../includes/adoprovidersaplong-md.md)], but proceeds with the adapter installation.</span></span>  
  
 <span data-ttu-id="64764-116">**可能的原因**</span><span class="sxs-lookup"><span data-stu-id="64764-116">**Cause**</span></span>  
  
 <span data-ttu-id="64764-117">这可能会由于存在问题导致[!INCLUDE[firstref_btsWinCommFoundation](../../includes/firstref-btswincommfoundation-md.md)]安装，[!INCLUDE[afproductnamelong](../../includes/afproductnamelong-md.md)]安装或被损坏的 machine.config 文件。</span><span class="sxs-lookup"><span data-stu-id="64764-117">This might result due to problems with [!INCLUDE[firstref_btsWinCommFoundation](../../includes/firstref-btswincommfoundation-md.md)] installation, [!INCLUDE[afproductnamelong](../../includes/afproductnamelong-md.md)] installation, or the machine.config file being corrupt.</span></span> <span data-ttu-id="64764-118">适配器绑定写入到 machine.config 文件中。</span><span class="sxs-lookup"><span data-stu-id="64764-118">The adapter bindings are written to the machine.config file.</span></span>  
  
 <span data-ttu-id="64764-119">**解决方法**</span><span class="sxs-lookup"><span data-stu-id="64764-119">**Resolution**</span></span>  
  
 <span data-ttu-id="64764-120">你应该手动注册[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]绑定或[!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="64764-120">You should manually register the [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] binding or the [!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)].</span></span>  
  
### <a name="register-the-adapter-bindings-or-the-data-provider"></a><span data-ttu-id="64764-121">注册的适配器绑定或数据提供程序</span><span class="sxs-lookup"><span data-stu-id="64764-121">Register the adapter bindings or the data provider</span></span>  
  
1.  <span data-ttu-id="64764-122">导航到计算机上的 machine.config 文件。</span><span class="sxs-lookup"><span data-stu-id="64764-122">Navigate to the machine.config file on the computer.</span></span> <span data-ttu-id="64764-123">例如，在 32 位平台上，machine.config 位于下\<系统驱动器\>: \WINDOWS\Microsoft.NET\Framework\\< 版本\>\CONFIG。</span><span class="sxs-lookup"><span data-stu-id="64764-123">For example, on a 32-bit platform, the machine.config is available under \<system drive\>:\WINDOWS\Microsoft.NET\Framework\\<version\>\CONFIG.</span></span>  
  
     <span data-ttu-id="64764-124">在此路径中，\<版本\>是.NET Framework 的版本。</span><span class="sxs-lookup"><span data-stu-id="64764-124">In this path, \<version\> is the version of the .NET Framework.</span></span>  
  
2.  <span data-ttu-id="64764-125">打开使用文本编辑器的文件。</span><span class="sxs-lookup"><span data-stu-id="64764-125">Open the file using a text editor.</span></span>  
  
3.  <span data-ttu-id="64764-126">若要注册[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]绑定：</span><span class="sxs-lookup"><span data-stu-id="64764-126">To register the [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] binding:</span></span>  
  
    1.  <span data-ttu-id="64764-127">搜索的元素"的 system.serviceModel"和其下添加以下：</span><span class="sxs-lookup"><span data-stu-id="64764-127">Search for the element "system.serviceModel" and add the following under it:</span></span>  
  
        ```  
        <client>  
          <endpoint binding="sapBinding" contract="IMetadataExchange" name="sap" />  
        </client>  
        ```  
  
    2.  <span data-ttu-id="64764-128">搜索"bindingElementExtensions"system.serviceModel\extensions 下的元素。</span><span class="sxs-lookup"><span data-stu-id="64764-128">Search for the element "bindingElementExtensions" under system.serviceModel\extensions.</span></span>  
  
    3.  <span data-ttu-id="64764-129">查找缺失[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]绑定。</span><span class="sxs-lookup"><span data-stu-id="64764-129">Look for the missing [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] binding.</span></span> <span data-ttu-id="64764-130">添加以下节"bindingElementExtensions"节点下。</span><span class="sxs-lookup"><span data-stu-id="64764-130">Add the following section under the "bindingElementExtensions" node.</span></span>  
  
         <span data-ttu-id="64764-131">有关[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]，添加：</span><span class="sxs-lookup"><span data-stu-id="64764-131">For [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)], add:</span></span>  
  
        ```  
        <add name="sapAdapter" type="Microsoft.Adapters.SAP.SAPAdapterExtensionElement,Microsoft.Adapters.SAP, Version=<version>, Culture=neutral, PublicKeyToken=<public key>" />  
        ```  
  
    4.  <span data-ttu-id="64764-132">搜索"bindingExtensions"system.serviceModel\extensions 下的元素。</span><span class="sxs-lookup"><span data-stu-id="64764-132">Search for the element "bindingExtensions" under system.serviceModel\extensions.</span></span>  
  
    5.  <span data-ttu-id="64764-133">查找缺失[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]绑定。</span><span class="sxs-lookup"><span data-stu-id="64764-133">Look for the missing [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] binding.</span></span> <span data-ttu-id="64764-134">添加以下节"bindingExtensions"节点下。</span><span class="sxs-lookup"><span data-stu-id="64764-134">Add the following section under the "bindingExtensions" node.</span></span>  
  
         <span data-ttu-id="64764-135">有关[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]，添加：</span><span class="sxs-lookup"><span data-stu-id="64764-135">For [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)], add:</span></span>  
  
        ```  
        <add name="sapBinding" type="Microsoft.Adapters.SAP.SAPAdapterBindingSection,Microsoft.Adapters.SAP, Version=<version>, Culture=neutral, PublicKeyToken=<public key>" />  
        ```  
  
        > [!NOTE]
        >  <span data-ttu-id="64764-136">有关如何确定的公钥的信息，请参阅[确定的公钥和版本](#BKMK_PubKey)。</span><span class="sxs-lookup"><span data-stu-id="64764-136">For information about how to determine the public key, see [Determining the Public Key and Version](#BKMK_PubKey).</span></span>  
  
4.  <span data-ttu-id="64764-137">若要注册[!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)]:</span><span class="sxs-lookup"><span data-stu-id="64764-137">To register the [!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)]:</span></span>  
  
    1.  <span data-ttu-id="64764-138">搜索"system.data"节点下的元素"DbProviderFactories"。</span><span class="sxs-lookup"><span data-stu-id="64764-138">Search for the element "DbProviderFactories" under the "system.data" node.</span></span>  
  
    2.  <span data-ttu-id="64764-139">查找缺失[!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="64764-139">Look for the missing [!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)].</span></span> <span data-ttu-id="64764-140">添加以下节"DbProviderFactories"节点下。</span><span class="sxs-lookup"><span data-stu-id="64764-140">Add the following section under the "DbProviderFactories" node.</span></span>  
  
         <span data-ttu-id="64764-141">有关[!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)]，添加：</span><span class="sxs-lookup"><span data-stu-id="64764-141">For [!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)], add:</span></span>  
  
        ```  
        <add name="SAPClient Data Provider" invariant="Microsoft.Data.SAPClient" description=".NET Framework Data Provider for mySAP Business Suite" type="Microsoft.Data.SAPClient.SAPClientFactory,Microsoft.Data.SAPClient, Version=<version>, Culture=neutral, PublicKeyToken=<public key>" />  
        ```  
  
5.  <span data-ttu-id="64764-142">保存并关闭 machine.config 文件。</span><span class="sxs-lookup"><span data-stu-id="64764-142">Save and close the machine.config file.</span></span>  
  
###  <a name="BKMK_PubKey"></a><span data-ttu-id="64764-143">确定的公钥和版本</span><span class="sxs-lookup"><span data-stu-id="64764-143">Determining the Public Key and Version</span></span>  
 <span data-ttu-id="64764-144">执行以下步骤来确定的公钥[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]或[!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="64764-144">Perform the following steps to determine the public key for [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] or [!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)].</span></span>  
  
1.  <span data-ttu-id="64764-145">导航到 Windows 目录中，通常 C:\WINDOWS\assembly。</span><span class="sxs-lookup"><span data-stu-id="64764-145">Navigate to the Windows directory, typically C:\WINDOWS\assembly.</span></span>  
  
2.  <span data-ttu-id="64764-146">右键单击该 DLL 为其您希望将公钥，，然后选择**属性**。</span><span class="sxs-lookup"><span data-stu-id="64764-146">Right-click the DLL for which you want the public key, and then select **Properties**.</span></span> <span data-ttu-id="64764-147">下表列出的 Dll 的名称[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]和[!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="64764-147">The following table lists the name of the DLLs for [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] and [!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)].</span></span>  
  
    |<span data-ttu-id="64764-148">适配器/数据提供程序</span><span class="sxs-lookup"><span data-stu-id="64764-148">Adapter/Data Provider</span></span>|<span data-ttu-id="64764-149">DLL 的名称</span><span class="sxs-lookup"><span data-stu-id="64764-149">Name of the DLL</span></span>|  
    |----------------------------|---------------------|  
    |[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]|<span data-ttu-id="64764-150">Microsoft.Adapters.SAP</span><span class="sxs-lookup"><span data-stu-id="64764-150">Microsoft.Adapters.SAP</span></span>|  
    |[!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)]|<span data-ttu-id="64764-151">Microsoft.Data.SAPClient</span><span class="sxs-lookup"><span data-stu-id="64764-151">Microsoft.Data.SAPClient</span></span>|  
  
3.  <span data-ttu-id="64764-152">上**常规**选项卡上，针对值**Public Key Token**标签指定 DLL 的公共密钥。</span><span class="sxs-lookup"><span data-stu-id="64764-152">On the **General** tab, the value against the **Public Key Token** label specifies the public key for the DLL.</span></span> <span data-ttu-id="64764-153">同样，针对值**版本**标签指定的 dll 的版本号。</span><span class="sxs-lookup"><span data-stu-id="64764-153">Similarly, value against the **Version** label specifies the version number for the DLL.</span></span>  
  
4.  <span data-ttu-id="64764-154">复制公钥，，然后单击**取消**。</span><span class="sxs-lookup"><span data-stu-id="64764-154">Copy the public key, and then click **Cancel**.</span></span>  
  
##  <a name="BKMK_SAPConsumeBinding"></a><span data-ttu-id="64764-155">没有有效的适配器是安装的错误</span><span class="sxs-lookup"><span data-stu-id="64764-155">No valid adapters are installed error</span></span>

 <span data-ttu-id="64764-156">**问题**</span><span class="sxs-lookup"><span data-stu-id="64764-156">**Problem**</span></span>  
  
 <span data-ttu-id="64764-157">使用[!INCLUDE[addadapterservreflong](../../includes/addadapterservreflong-md.md)]或[!INCLUDE[consumeadapterservlong](../../includes/consumeadapterservlong-md.md)]从[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]运行的 64 位版本的 64 位计算机上[!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)]会导致以下错误：</span><span class="sxs-lookup"><span data-stu-id="64764-157">Using the [!INCLUDE[addadapterservreflong](../../includes/addadapterservreflong-md.md)] or the [!INCLUDE[consumeadapterservlong](../../includes/consumeadapterservlong-md.md)] from [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)] on a 64-bit computer running 64-bit version of the [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)] results in the following error:</span></span>  
  
```  
No valid adapters are installed on this machine  
```  
  
 <span data-ttu-id="64764-158">**可能的原因**</span><span class="sxs-lookup"><span data-stu-id="64764-158">**Cause**</span></span>  
  
 <span data-ttu-id="64764-159">[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]是 WCF 自定义绑定，它在 machine.config 文件中的 System.ServiceModel 下注册。</span><span class="sxs-lookup"><span data-stu-id="64764-159">The [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] is a WCF custom binding, which is registered under System.ServiceModel in the machine.config file.</span></span> <span data-ttu-id="64764-160">64 位平台都有两个 machine.config 文件，其中一个 32 位应用程序使用，另一个 64 位应用程序使用。</span><span class="sxs-lookup"><span data-stu-id="64764-160">A 64-bit platform has two machine.config files, one used by the 32-bit applications and the other used by the 64-bit applications.</span></span> <span data-ttu-id="64764-161">因此，在安装 64 位版本的[!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)]，安装向导在 64 位版本的 machine.config 文件中注册绑定。</span><span class="sxs-lookup"><span data-stu-id="64764-161">So, when you install the 64-bit version of the [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)], the setup wizard registers the bindings in the 64-bit version of the machine.config file.</span></span> <span data-ttu-id="64764-162">但是，[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]作为 32 位进程运行，因此启动[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]从[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]，插件检查 machine.config 文件的 32 位版本中的绑定和失败为错误。</span><span class="sxs-lookup"><span data-stu-id="64764-162">However, [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)] runs as a 32-bit process and hence when you launch the [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)] from [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)], the plug-in checks for the bindings in the 32-bit version of the machine.config file and fails giving an error.</span></span>  
  
 <span data-ttu-id="64764-163">**解决方法**</span><span class="sxs-lookup"><span data-stu-id="64764-163">**Resolution**</span></span>  
  
-   <span data-ttu-id="64764-164">安装的 32 位和 64 位版本[!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)]在 64 位[!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]安装。</span><span class="sxs-lookup"><span data-stu-id="64764-164">Install both the 32-bit and 64-bit versions of the [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)] on a 64-bit [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)] installation.</span></span>  
  
    > [!IMPORTANT]
    >  <span data-ttu-id="64764-165">你必须只有 64 位[!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]安装。</span><span class="sxs-lookup"><span data-stu-id="64764-165">You must only have a 64-bit [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)] installation.</span></span> <span data-ttu-id="64764-166">通过并行安装 32 位和 64 位[!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]不支持在一台计算机上。</span><span class="sxs-lookup"><span data-stu-id="64764-166">Side-by-side installation of 32-bit and 64-bit [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)] on a single computer is not supported.</span></span>  
  
-   <span data-ttu-id="64764-167">添加这两个 32 位和 64 位版本的客户端 Dll [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] （如 librfc32u.dll) 到 PATH 变量。</span><span class="sxs-lookup"><span data-stu-id="64764-167">Add both the 32-bit and 64-bit versions of the client DLLs for the [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] (such as librfc32u.dll) to the PATH variable.</span></span> <span data-ttu-id="64764-168">Dll 的 32 位版本必须添加到 C:\Windows\SysWow64 文件夹中。</span><span class="sxs-lookup"><span data-stu-id="64764-168">The 32-bit version of the DLLs must be added to C:\Windows\SysWow64 folder.</span></span> <span data-ttu-id="64764-169">Dll 的 64 位版本必须添加到 C:\Windows\System32 文件夹中。</span><span class="sxs-lookup"><span data-stu-id="64764-169">The 64-bit version of the DLLs must be added to C:\Windows\System32 folder.</span></span>  
  
    > [!IMPORTANT]
    >  <span data-ttu-id="64764-170">如果在具有 64 位操作系统的计算机上运行 （32 或 64 位） 的适配器，并且使用适配器来编写应用程序，则应标记到适配器相同类型 （32 或 64 位） 应用程序。</span><span class="sxs-lookup"><span data-stu-id="64764-170">If the adapter (32 or 64-bit) is running on a computer that has a 64-bit operating system, and you are using the adapter to write an application, you should mark the application to the same type (32 or 64-bit) as the adapter.</span></span> <span data-ttu-id="64764-171">此外，RFC SDK （32 或 64 位） 的版本必须是适配器的相同的版本 （32 或 64 位）。</span><span class="sxs-lookup"><span data-stu-id="64764-171">Also, the version of the RFC SDK (32 or 64-bit) must be same as the version of the adapter (32 or 64-bit).</span></span>  
    >   
    >  <span data-ttu-id="64764-172">例如，如果在具有 64 位操作系统的计算机上运行的 32 位适配器，适配器客户端应用程序必须标记为 32 位。</span><span class="sxs-lookup"><span data-stu-id="64764-172">For example, if a 32-bit adapter is running on a computer with a 64-bit operating system, the adapter client application must be marked as 32-bit.</span></span>  
  
     <span data-ttu-id="64764-173">有关 SAP 客户端 Dll 的详细信息，请参阅[用于 SAP 的数据提供程序安装自定义 Rfc](../../adapters-and-accelerators/adapter-sap/install-custom-rfcs-for-the-data-provider-for-sap.md)。</span><span class="sxs-lookup"><span data-stu-id="64764-173">For more information about the SAP client DLLs, see [Install Custom RFCs for the Data Provider for SAP](../../adapters-and-accelerators/adapter-sap/install-custom-rfcs-for-the-data-provider-for-sap.md).</span></span>  
  
##  <a name="BKMK_SAPInvalidBinding"></a><span data-ttu-id="64764-174">配置 SAP 适配器端口时无效的绑定错误</span><span class="sxs-lookup"><span data-stu-id="64764-174">Invalid binding error while configuring SAP adapter ports</span></span>  
 <span data-ttu-id="64764-175">**问题**</span><span class="sxs-lookup"><span data-stu-id="64764-175">**Problem**</span></span>  
  
 <span data-ttu-id="64764-176">当你尝试配置中的适配器的端口[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理控制台中，你将收到以下错误：</span><span class="sxs-lookup"><span data-stu-id="64764-176">When you try to configure a port for the adapter in [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] Administration console, you get the following error:</span></span>  
  
```  
"Unable to create binding configuration element for editing. Check the values of the BindingType and BindingConfiguration properties.  
(Microsoft.Biztalk.Adapter.Wcf.Converters.CreateBindingException) Unable to get binding type for binding extension "sapBinding".  
Verify the binding extension is registered in machine.config."  
```  
  
 <span data-ttu-id="64764-177">**可能的原因**</span><span class="sxs-lookup"><span data-stu-id="64764-177">**Cause**</span></span>  
  
 <span data-ttu-id="64764-178">[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]是 WCF 自定义绑定，它在 machine.config 文件中的 System.ServiceModel 下注册。</span><span class="sxs-lookup"><span data-stu-id="64764-178">The [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] is a WCF custom binding, which is registered under System.ServiceModel in the machine.config file.</span></span> <span data-ttu-id="64764-179">64 位平台都有两个 machine.config 文件，其中一个 32 位应用程序使用，另一个 64 位应用程序使用。</span><span class="sxs-lookup"><span data-stu-id="64764-179">A 64-bit platform has two machine.config files, one used by the 32-bit applications and the other used by the 64-bit applications.</span></span> <span data-ttu-id="64764-180">因此，在安装 64 位版本的[!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)]，安装向导在 64 位版本的 machine.config 文件中注册绑定。</span><span class="sxs-lookup"><span data-stu-id="64764-180">So, when you install the 64-bit version of the [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)], the setup wizard registers the bindings in the 64-bit version of the machine.config file.</span></span> <span data-ttu-id="64764-181">但是，[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]作为 32 位进程运行的管理控制台，因此当你配置为适配器的端口时，它检查 machine.config 文件的 32 位版本中的绑定无法提供错误。</span><span class="sxs-lookup"><span data-stu-id="64764-181">However, [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] Administration console runs as a 32-bit process and hence when you configure a port for the adapter, it checks for the bindings in the 32-bit version of the machine.config file and fails giving an error.</span></span>  
  
 <span data-ttu-id="64764-182">**解决方法**</span><span class="sxs-lookup"><span data-stu-id="64764-182">**Resolution**</span></span>  
  
-   <span data-ttu-id="64764-183">安装的 32 位和 64 位版本[!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)]在 64 位[!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]安装。</span><span class="sxs-lookup"><span data-stu-id="64764-183">Install both the 32-bit and 64-bit versions of the [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)] on a 64-bit [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)] installation.</span></span>  
  
    > [!IMPORTANT]
    >  <span data-ttu-id="64764-184">你必须只有 64 位[!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]安装。</span><span class="sxs-lookup"><span data-stu-id="64764-184">You must only have a 64-bit [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)] installation.</span></span> <span data-ttu-id="64764-185">通过并行安装 32 位和 64 位[!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]不支持在一台计算机上。</span><span class="sxs-lookup"><span data-stu-id="64764-185">Side-by-side installation of 32-bit and 64-bit [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)] on a single computer is not supported.</span></span>  
  
-   <span data-ttu-id="64764-186">添加这两个 32 位和 64 位版本的客户端 Dll [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] （如 librfc32u.dll) 到 PATH 变量。</span><span class="sxs-lookup"><span data-stu-id="64764-186">Add both the 32-bit and 64-bit versions of the client DLLs for the [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] (such as librfc32u.dll) to the PATH variable.</span></span> <span data-ttu-id="64764-187">Dll 的 32 位版本必须添加到 C:\Windows\SysWow64 文件夹中。</span><span class="sxs-lookup"><span data-stu-id="64764-187">The 32-bit version of the DLLs must be added to C:\Windows\SysWow64 folder.</span></span> <span data-ttu-id="64764-188">Dll 的 64 位版本必须添加到 C:\Windows\System32 文件夹中。</span><span class="sxs-lookup"><span data-stu-id="64764-188">The 64-bit version of the DLLs must be added to C:\Windows\System32 folder.</span></span>  
  
    > [!IMPORTANT]
    >  <span data-ttu-id="64764-189">如果在具有 64 位操作系统的计算机上运行 （32 或 64 位） 的适配器，并且使用适配器来编写应用程序，则应标记到适配器相同类型 （32 或 64 位） 应用程序。</span><span class="sxs-lookup"><span data-stu-id="64764-189">If the adapter (32 or 64-bit) is running on a computer that has a 64-bit operating system, and you are using the adapter to write an application, you should mark the application to the same type (32 or 64-bit) as the adapter.</span></span> <span data-ttu-id="64764-190">此外，RFC SDK （32 或 64 位） 的版本必须是适配器的相同的版本 （32 或 64 位）。</span><span class="sxs-lookup"><span data-stu-id="64764-190">Also, the version of the RFC SDK (32 or 64-bit) must be same as the version of the adapter (32 or 64-bit).</span></span>  
    >   
    >  <span data-ttu-id="64764-191">例如，如果在具有 64 位操作系统的计算机上运行的 32 位适配器，适配器客户端应用程序必须标记为 32 位。</span><span class="sxs-lookup"><span data-stu-id="64764-191">For example, if a 32-bit adapter is running on a computer with a 64-bit operating system, the adapter client application must be marked as 32-bit.</span></span>  
  
     <span data-ttu-id="64764-192">有关 SAP 客户端 Dll 的详细信息，请参阅[用于 SAP 的数据提供程序安装自定义 Rfc](../../adapters-and-accelerators/adapter-sap/install-custom-rfcs-for-the-data-provider-for-sap.md)。</span><span class="sxs-lookup"><span data-stu-id="64764-192">For more information about the SAP client DLLs, see [Install Custom RFCs for the Data Provider for SAP](../../adapters-and-accelerators/adapter-sap/install-custom-rfcs-for-the-data-provider-for-sap.md).</span></span>
  
## <a name="see-also"></a><span data-ttu-id="64764-193">另请参阅</span><span class="sxs-lookup"><span data-stu-id="64764-193">See Also</span></span>  
[<span data-ttu-id="64764-194">故障排除 SAP 适配器</span><span class="sxs-lookup"><span data-stu-id="64764-194">Troubleshoot the SAP adapter</span></span>](../../adapters-and-accelerators/adapter-sap/troubleshoot-the-sap-adapter.md)