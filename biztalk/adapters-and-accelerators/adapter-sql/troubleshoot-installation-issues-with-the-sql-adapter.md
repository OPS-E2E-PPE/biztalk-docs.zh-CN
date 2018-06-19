---
title: 使用 SQl 适配器进行安装问题故障排除 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 48778158-6064-4731-be72-1af855ebe373
caps.latest.revision: 13
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 3ba1d7e105a1ea09724950f4c0f8b778e45dad46
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/28/2017
ms.locfileid: "25963707"
---
# <a name="troubleshoot-installation-issues-with-the-sql-adapter"></a><span data-ttu-id="126e0-102">解决 SQl 适配器的安装问题</span><span class="sxs-lookup"><span data-stu-id="126e0-102">Troubleshoot Installation Issues with the SQl adapter</span></span>
> [!IMPORTANT]
>  <span data-ttu-id="126e0-103">[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]现作为的一部分[!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)]以及一个单独的适配器。</span><span class="sxs-lookup"><span data-stu-id="126e0-103">The [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] is available as part of the [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)] as well as a separate adapter.</span></span> <span data-ttu-id="126e0-104">如果您正在访问此主题以了解有关安装问题的[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]独立于[!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)]，对所有引用[!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)]安装程序必须将解释为[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]安装程序。</span><span class="sxs-lookup"><span data-stu-id="126e0-104">If you are accessing this topic to know about installation issues with the [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] that is separate from the [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)], all references to the [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)] Setup must be interpreted as [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] Setup.</span></span>  
  
 <span data-ttu-id="126e0-105">安装 Microsoft[!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)]复制产品二进制文件的计算机上并注册每个适配器的绑定。</span><span class="sxs-lookup"><span data-stu-id="126e0-105">Installation of the Microsoft [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)] copies the product binaries on the computer and registers the bindings for each adapter.</span></span> <span data-ttu-id="126e0-106">本部分讨论如何使用故障排除方法来解决安装错误。</span><span class="sxs-lookup"><span data-stu-id="126e0-106">This section discusses using troubleshooting techniques to resolve installation errors.</span></span>  
  
## <a name="logging-messages-for-setup-actions"></a><span data-ttu-id="126e0-107">安装程序操作的日志记录消息</span><span class="sxs-lookup"><span data-stu-id="126e0-107">Logging Messages for Setup Actions</span></span>  
 <span data-ttu-id="126e0-108">[!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)]安装程序执行安装的标准任务[!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="126e0-108">The [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)] setup program performs the standard task of installing the [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)].</span></span> <span data-ttu-id="126e0-109">此外，安装程序还执行某些自定义操作，例如注册的适配器绑定。</span><span class="sxs-lookup"><span data-stu-id="126e0-109">Additionally, the setup also performs certain custom actions such as registering the adapter bindings.</span></span> <span data-ttu-id="126e0-110">可以记录这两个标准以及自定义操作的安装程序将执行的消息。</span><span class="sxs-lookup"><span data-stu-id="126e0-110">You can log messages for both the standard as well as custom actions that the setup performs.</span></span>  
  
-   <span data-ttu-id="126e0-111">[!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)]安装程序将安装使用 MSI 的适配器特定的文件。</span><span class="sxs-lookup"><span data-stu-id="126e0-111">The [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)] setup installs the adapter-specific files using an MSI.</span></span> <span data-ttu-id="126e0-112">因此，安装程序的日志记录是标准的 MSI 日志记录。</span><span class="sxs-lookup"><span data-stu-id="126e0-112">Therefore, the logging for the setup is the standard MSI logging.</span></span>  
  
-   <span data-ttu-id="126e0-113">安装程序执行的自定义操作的所有日志都位于 %temp%\adaptersetup.log。</span><span class="sxs-lookup"><span data-stu-id="126e0-113">All logs for the custom actions that the setup program performs are available at %TEMP%\adaptersetup.log.</span></span> <span data-ttu-id="126e0-114">如果跟踪日志文件失败，跟踪也会出现在事件日志。</span><span class="sxs-lookup"><span data-stu-id="126e0-114">If the tracing to the log file fails, the traces are also available in the event log.</span></span>  
  
## <a name="known-issues"></a><span data-ttu-id="126e0-115">已知问题</span><span class="sxs-lookup"><span data-stu-id="126e0-115">Known Issues</span></span>  
 <span data-ttu-id="126e0-116">以下是在安装时可能遇到的最常见错误[!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)]，以及其可能的原因和解决方法。</span><span class="sxs-lookup"><span data-stu-id="126e0-116">The following are the most common errors you might encounter when installing the [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)], along with their probable cause and resolution.</span></span>  
  
  
  
###  <a name="BKMK_SQLSetupBinding"></a><span data-ttu-id="126e0-117">安装程序无法注册适配器绑定</span><span class="sxs-lookup"><span data-stu-id="126e0-117">Setup fails to register adapter bindings</span></span>  
 <span data-ttu-id="126e0-118">**问题**</span><span class="sxs-lookup"><span data-stu-id="126e0-118">**Problem**</span></span>  
  
 <span data-ttu-id="126e0-119">Microsoft[!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)]安装向导无法注册的适配器绑定，但将继续执行适配器安装。</span><span class="sxs-lookup"><span data-stu-id="126e0-119">The Microsoft [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)] Setup Wizard fails to register the adapter bindings, but proceeds with the adapter installation.</span></span>  
  
 <span data-ttu-id="126e0-120">**可能的原因**</span><span class="sxs-lookup"><span data-stu-id="126e0-120">**Cause**</span></span>  
  
 <span data-ttu-id="126e0-121">这可能会由于存在问题导致[!INCLUDE[firstref_btsWinCommFoundation](../../includes/firstref-btswincommfoundation-md.md)]安装，[!INCLUDE[afproductnamelong](../../includes/afproductnamelong-md.md)]安装或被损坏的 machine.config 文件。</span><span class="sxs-lookup"><span data-stu-id="126e0-121">This might result due to problems with [!INCLUDE[firstref_btsWinCommFoundation](../../includes/firstref-btswincommfoundation-md.md)] installation, [!INCLUDE[afproductnamelong](../../includes/afproductnamelong-md.md)] installation, or the machine.config file being corrupt.</span></span> <span data-ttu-id="126e0-122">适配器绑定写入到 machine.config 文件中。</span><span class="sxs-lookup"><span data-stu-id="126e0-122">The adapter bindings are written to the machine.config file.</span></span>  
  
 <span data-ttu-id="126e0-123">**解决方法**</span><span class="sxs-lookup"><span data-stu-id="126e0-123">**Resolution**</span></span>  
  
 <span data-ttu-id="126e0-124">你应该手动注册[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]绑定。</span><span class="sxs-lookup"><span data-stu-id="126e0-124">You should manually register the [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] binding.</span></span>  
  
##### <a name="to-register-the-adapter-binding"></a><span data-ttu-id="126e0-125">若要注册的适配器绑定</span><span class="sxs-lookup"><span data-stu-id="126e0-125">To register the adapter binding</span></span>  
  
1.  <span data-ttu-id="126e0-126">导航到计算机上的 machine.config 文件。</span><span class="sxs-lookup"><span data-stu-id="126e0-126">Navigate to the machine.config file on the computer.</span></span> <span data-ttu-id="126e0-127">例如，在 32 位平台上，machine.config 位于下\<系统驱动器\>: \WINDOWS\Microsoft.NET\Framework\\< 版本\>\CONFIG。</span><span class="sxs-lookup"><span data-stu-id="126e0-127">For example, on a 32-bit platform, the machine.config is available under \<system drive\>:\WINDOWS\Microsoft.NET\Framework\\<version\>\CONFIG.</span></span>  
  
     <span data-ttu-id="126e0-128">在此路径中，\<版本\>是.NET Framework 的版本。</span><span class="sxs-lookup"><span data-stu-id="126e0-128">In this path, \<version\> is the version of the .NET Framework.</span></span>  
  
2.  <span data-ttu-id="126e0-129">通过使用文本编辑器中打开该文件。</span><span class="sxs-lookup"><span data-stu-id="126e0-129">Open the file by using a text editor.</span></span>  
  
3.  <span data-ttu-id="126e0-130">若要注册[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]绑定：</span><span class="sxs-lookup"><span data-stu-id="126e0-130">To register the [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] binding:</span></span>  
  
    1.  <span data-ttu-id="126e0-131">搜索的元素"的 system.serviceModel"和其下添加以下：</span><span class="sxs-lookup"><span data-stu-id="126e0-131">Search for the element "system.serviceModel" and add the following under it:</span></span>  
  
        ```  
        <client>  
          <endpoint binding="sqlBinding" contract="IMetadataExchange" name="mssql" />  
        </client>  
        ```  
  
    2.  <span data-ttu-id="126e0-132">搜索"bindingElementExtensions"system.serviceModel\extensions 下的元素。</span><span class="sxs-lookup"><span data-stu-id="126e0-132">Search for the element "bindingElementExtensions" under system.serviceModel\extensions.</span></span>  
  
    3.  <span data-ttu-id="126e0-133">查找缺失[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]绑定。</span><span class="sxs-lookup"><span data-stu-id="126e0-133">Look for the missing [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] binding.</span></span> <span data-ttu-id="126e0-134">添加以下节"bindingElementExtensions"节点下。</span><span class="sxs-lookup"><span data-stu-id="126e0-134">Add the following section under the "bindingElementExtensions" node.</span></span>  
  
         <span data-ttu-id="126e0-135">有关[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]，添加：</span><span class="sxs-lookup"><span data-stu-id="126e0-135">For [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)], add:</span></span>  
  
        ```  
        <add name="sqlAdapter" type="Microsoft.Adapters.Sql.SqlAdapterBindingElementExtensionElement,Microsoft.Adapters.Sql, Version=<version>, Culture=neutral, PublicKeyToken=<public key>" />  
        ```  
  
    4.  <span data-ttu-id="126e0-136">搜索"bindingExtensions"system.serviceModel\extensions 下的元素。</span><span class="sxs-lookup"><span data-stu-id="126e0-136">Search for the element "bindingExtensions" under system.serviceModel\extensions.</span></span>  
  
    5.  <span data-ttu-id="126e0-137">查找缺失[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]绑定。</span><span class="sxs-lookup"><span data-stu-id="126e0-137">Look for the missing [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] binding.</span></span> <span data-ttu-id="126e0-138">添加以下节"bindingExtensions"节点下。</span><span class="sxs-lookup"><span data-stu-id="126e0-138">Add the following section under the "bindingExtensions" node.</span></span>  
  
         <span data-ttu-id="126e0-139">有关[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]，添加：</span><span class="sxs-lookup"><span data-stu-id="126e0-139">For [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)], add:</span></span>  
  
        ```  
        <add name="sqlBinding" type="Microsoft.Adapters.Sql.SqlAdapterBindingCollectionElement,Microsoft.Adapters.Sql, Version=<version>, Culture=neutral, PublicKeyToken=<public key>" />  
        ```  
  
    > [!NOTE]
    >  <span data-ttu-id="126e0-140">有关如何确定公用密钥和版本的信息，请参阅[确定的公钥和版本](#BKMK_PubKey)。</span><span class="sxs-lookup"><span data-stu-id="126e0-140">For information about how to determine the public key and the version, see [Determining the Public Key and Version](#BKMK_PubKey).</span></span>  
  
4.  <span data-ttu-id="126e0-141">保存并关闭 machine.config 文件。</span><span class="sxs-lookup"><span data-stu-id="126e0-141">Save and close the machine.config file.</span></span>  
  
####  <a name="BKMK_PubKey"></a><span data-ttu-id="126e0-142">确定的公钥和版本</span><span class="sxs-lookup"><span data-stu-id="126e0-142">Determining the Public Key and Version</span></span>  
 <span data-ttu-id="126e0-143">执行以下步骤来确定的公钥[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="126e0-143">Perform the following steps to determine the public key for [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)].</span></span>  
  
###### <a name="to-determine-the-public-key"></a><span data-ttu-id="126e0-144">若要确定的公钥</span><span class="sxs-lookup"><span data-stu-id="126e0-144">To determine the public key</span></span>  
  
1.  <span data-ttu-id="126e0-145">导航到 Windows 目录中，通常 C:\WINDOWS\assembly。</span><span class="sxs-lookup"><span data-stu-id="126e0-145">Navigate to the Windows directory, typically C:\WINDOWS\assembly.</span></span>  
  
2.  <span data-ttu-id="126e0-146">右键单击对其需的公钥和版本，且然后选择该 DLL**属性**。</span><span class="sxs-lookup"><span data-stu-id="126e0-146">Right-click the DLL for which you want the public key and the version, and then select **Properties**.</span></span> <span data-ttu-id="126e0-147">下表列出的 DLL 的名称[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="126e0-147">The following table lists the name of the DLL for [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)].</span></span>  
  
    |<span data-ttu-id="126e0-148">适配器</span><span class="sxs-lookup"><span data-stu-id="126e0-148">Adapter</span></span>|<span data-ttu-id="126e0-149">DLL 的名称</span><span class="sxs-lookup"><span data-stu-id="126e0-149">Name of the DLL</span></span>|  
    |-------------|---------------------|  
    |[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]|<span data-ttu-id="126e0-150">Microsoft.Adapters.Sql</span><span class="sxs-lookup"><span data-stu-id="126e0-150">Microsoft.Adapters.Sql</span></span>|  
  
3.  <span data-ttu-id="126e0-151">上**常规**选项卡上，针对值**Public Key Token**标签指定 DLL 的公共密钥。</span><span class="sxs-lookup"><span data-stu-id="126e0-151">On the **General** tab, the value against the **Public Key Token** label specifies the public key for the DLL.</span></span> <span data-ttu-id="126e0-152">同样，针对值**版本**标签指定的 dll 的版本号。</span><span class="sxs-lookup"><span data-stu-id="126e0-152">Similarly, value against the **Version** label specifies the version number for the DLL.</span></span>  
  
4.  <span data-ttu-id="126e0-153">复制公钥，，然后单击**取消**。</span><span class="sxs-lookup"><span data-stu-id="126e0-153">Copy the public key, and then click **Cancel**.</span></span>  
  
###  <a name="BKMK_SQLConsumeBinding"></a><span data-ttu-id="126e0-154">在 64 位安装上使用使用适配器服务外接程序或添加适配器服务引用插件时出错</span><span class="sxs-lookup"><span data-stu-id="126e0-154">Error while using the Consume Adapter Service add-in or Add Adapter Service Reference plug-in on a 64-bit installation</span></span>  
 <span data-ttu-id="126e0-155">**问题**</span><span class="sxs-lookup"><span data-stu-id="126e0-155">**Problem**</span></span>  
  
 <span data-ttu-id="126e0-156">使用[!INCLUDE[addadapterservreflong](../../includes/addadapterservreflong-md.md)]或[!INCLUDE[consumeadapterservlong](../../includes/consumeadapterservlong-md.md)]从[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]运行的 64 位版本的 64 位计算机上[!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)]会导致以下错误：</span><span class="sxs-lookup"><span data-stu-id="126e0-156">Using the [!INCLUDE[addadapterservreflong](../../includes/addadapterservreflong-md.md)] or the [!INCLUDE[consumeadapterservlong](../../includes/consumeadapterservlong-md.md)] from [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)] on a 64-bit computer running 64-bit version of the [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)] results in the following error:</span></span>  
  
```  
No valid adapters are installed on this machine  
```  
  
 <span data-ttu-id="126e0-157">**可能的原因**</span><span class="sxs-lookup"><span data-stu-id="126e0-157">**Cause**</span></span>  
  
 <span data-ttu-id="126e0-158">[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]是 WCF 自定义绑定，它在 machine.config 文件中的 System.ServiceModel 下注册。</span><span class="sxs-lookup"><span data-stu-id="126e0-158">The [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] is a WCF custom binding, which is registered under System.ServiceModel in the machine.config file.</span></span> <span data-ttu-id="126e0-159">64 位平台都有两个 machine.config 文件，其中一个 32 位应用程序使用，另一个 64 位应用程序使用。</span><span class="sxs-lookup"><span data-stu-id="126e0-159">A 64-bit platform has two machine.config files, one used by the 32-bit applications and the other used by the 64-bit applications.</span></span> <span data-ttu-id="126e0-160">因此，在安装 64 位版本的[!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)]，安装向导在 64 位版本的 machine.config 文件中注册绑定。</span><span class="sxs-lookup"><span data-stu-id="126e0-160">So, when you install the 64-bit version of the [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)], the setup wizard registers the bindings in the 64-bit version of the machine.config file.</span></span> <span data-ttu-id="126e0-161">但是，[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]作为 32 位进程运行，因此启动[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]从[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]，插件检查 machine.config 文件的 32 位版本中的绑定和失败为错误。</span><span class="sxs-lookup"><span data-stu-id="126e0-161">However, [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)] runs as a 32-bit process and hence when you launch the [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)] from [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)], the plug-in checks for the bindings in the 32-bit version of the machine.config file and fails giving an error.</span></span>  
  
 <span data-ttu-id="126e0-162">**解决方法**</span><span class="sxs-lookup"><span data-stu-id="126e0-162">**Resolution**</span></span>  
  
 <span data-ttu-id="126e0-163">安装的 32 位和 64 位版本[!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)]在 64 位[!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]安装。</span><span class="sxs-lookup"><span data-stu-id="126e0-163">Install both the 32-bit and 64-bit versions of the [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)] on a 64-bit [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)] installation.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="126e0-164">你必须只有 64 位[!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]安装。</span><span class="sxs-lookup"><span data-stu-id="126e0-164">You must only have a 64-bit [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)] installation.</span></span> <span data-ttu-id="126e0-165">通过并行安装 32 位和 64 位[!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]不支持在一台计算机上。</span><span class="sxs-lookup"><span data-stu-id="126e0-165">Side-by-side installation of 32-bit and 64-bit [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)] on a single computer is not supported.</span></span>  
  
###  <a name="BKMK_SQLInvalidBinding"></a><span data-ttu-id="126e0-166">在 BizTalk Server 管理控制台中的 SQL 适配器端口配置在 64 位安装上时的无效的绑定错误</span><span class="sxs-lookup"><span data-stu-id="126e0-166">Invalid binding error while configuring SQL adapter ports in BizTalk Server Administration Console on a 64-bit installation</span></span>  
 <span data-ttu-id="126e0-167">**问题**</span><span class="sxs-lookup"><span data-stu-id="126e0-167">**Problem**</span></span>  
  
 <span data-ttu-id="126e0-168">当你尝试配置中的适配器的端口[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理控制台中，你将收到以下错误：</span><span class="sxs-lookup"><span data-stu-id="126e0-168">When you try to configure a port for the adapter in [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] Administration console, you get the following error:</span></span>  
  
```  
"Unable to create binding configuration element for editing. Check the values of the BindingType and BindingConfiguration properties.  
(Microsoft.Biztalk.Adapter.Wcf.Converters.CreateBindingException) Unable to get binding type for binding extension "sqlBinding".  
Verify the binding extension is registered in machine.config."  
```  
  
 <span data-ttu-id="126e0-169">**可能的原因**</span><span class="sxs-lookup"><span data-stu-id="126e0-169">**Cause**</span></span>  
  
 <span data-ttu-id="126e0-170">[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]是 WCF 自定义绑定，它在 machine.config 文件中的 System.ServiceModel 下注册。</span><span class="sxs-lookup"><span data-stu-id="126e0-170">The [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] is a WCF custom binding, which is registered under System.ServiceModel in the machine.config file.</span></span> <span data-ttu-id="126e0-171">64 位平台都有两个 machine.config 文件，其中一个 32 位应用程序使用，另一个 64 位应用程序使用。</span><span class="sxs-lookup"><span data-stu-id="126e0-171">A 64-bit platform has two machine.config files, one used by the 32-bit applications and the other used by the 64-bit applications.</span></span> <span data-ttu-id="126e0-172">因此，在安装 64 位版本的[!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)]，安装向导在 64 位版本的 machine.config 文件中注册绑定。</span><span class="sxs-lookup"><span data-stu-id="126e0-172">So, when you install the 64-bit version of the [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)], the setup wizard registers the bindings in the 64-bit version of the machine.config file.</span></span> <span data-ttu-id="126e0-173">但是，[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]作为 32 位进程运行的管理控制台，因此当你配置为适配器的端口时，它检查 machine.config 文件的 32 位版本中的绑定无法提供错误。</span><span class="sxs-lookup"><span data-stu-id="126e0-173">However, [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] Administration console runs as a 32-bit process and hence when you configure a port for the adapter, it checks for the bindings in the 32-bit version of the machine.config file and fails giving an error.</span></span>  
  
 <span data-ttu-id="126e0-174">**解决方法**</span><span class="sxs-lookup"><span data-stu-id="126e0-174">**Resolution**</span></span>  
  
 <span data-ttu-id="126e0-175">安装的 32 位和 64 位版本[!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)]在 64 位[!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]安装。</span><span class="sxs-lookup"><span data-stu-id="126e0-175">Install both the 32-bit and 64-bit versions of the [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)] on a 64-bit [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)] installation.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="126e0-176">你必须只有 64 位[!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]安装。</span><span class="sxs-lookup"><span data-stu-id="126e0-176">You must only have a 64-bit [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)] installation.</span></span> <span data-ttu-id="126e0-177">通过并行安装 32 位和 64 位[!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]不支持在一台计算机上。</span><span class="sxs-lookup"><span data-stu-id="126e0-177">Side-by-side installation of 32-bit and 64-bit [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)] on a single computer is not supported.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="126e0-178">另请参阅</span><span class="sxs-lookup"><span data-stu-id="126e0-178">See Also</span></span>  
 [<span data-ttu-id="126e0-179">解决 SQL 适配器</span><span class="sxs-lookup"><span data-stu-id="126e0-179">Troubleshoot the SQL adapter</span></span>](../../adapters-and-accelerators/adapter-sql/troubleshoot-the-sql-adapter.md)