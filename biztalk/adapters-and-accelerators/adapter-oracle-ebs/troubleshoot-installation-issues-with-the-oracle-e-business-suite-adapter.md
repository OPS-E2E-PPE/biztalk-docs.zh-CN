---
title: "解决安装问题与 Oracle E-business Suite 适配器 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 09b3af20-ab87-44e8-8ded-c19432552be7
caps.latest.revision: "15"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 387ca48954fc075e696a8d3b093fbc9f1b5d7259
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="troubleshoot-installation-issues-with-the-oracle-e-business-suite-adapter"></a><span data-ttu-id="f17ee-102">与 Oracle E-business Suite 适配器解决安装问题</span><span class="sxs-lookup"><span data-stu-id="f17ee-102">Troubleshoot Installation Issues with the Oracle E-Business Suite adapter</span></span>
<span data-ttu-id="f17ee-103">安装 Microsoft[!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)]复制产品二进制文件的计算机上并注册每个适配器的绑定。</span><span class="sxs-lookup"><span data-stu-id="f17ee-103">Installation of the Microsoft [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)] copies the product binaries on the computer and registers the bindings for each adapter.</span></span> <span data-ttu-id="f17ee-104">本部分讨论如何使用故障排除方法来解决安装错误。</span><span class="sxs-lookup"><span data-stu-id="f17ee-104">This section discusses using troubleshooting techniques to resolve installation errors.</span></span>  
  
## <a name="logging-messages-for-setup-actions"></a><span data-ttu-id="f17ee-105">安装程序操作的日志记录消息</span><span class="sxs-lookup"><span data-stu-id="f17ee-105">Logging Messages for Setup Actions</span></span>  
 <span data-ttu-id="f17ee-106">[!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)]安装程序执行安装的标准任务[!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="f17ee-106">The [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)] setup program performs the standard task of installing the [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)].</span></span> <span data-ttu-id="f17ee-107">此外，安装程序还执行某些自定义操作，例如注册的适配器绑定。</span><span class="sxs-lookup"><span data-stu-id="f17ee-107">Additionally, the setup also performs certain custom actions such as registering the adapter bindings.</span></span> <span data-ttu-id="f17ee-108">可以记录这两个标准以及自定义操作的安装程序将执行的消息。</span><span class="sxs-lookup"><span data-stu-id="f17ee-108">You can log messages for both the standard as well as custom actions that the setup performs.</span></span>  
  
-   <span data-ttu-id="f17ee-109">[!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)]安装程序将安装使用 MSI 的适配器特定的文件。</span><span class="sxs-lookup"><span data-stu-id="f17ee-109">The [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)] setup installs the adapter-specific files using an MSI.</span></span> <span data-ttu-id="f17ee-110">因此，安装程序的日志记录是标准的 MSI 日志记录。</span><span class="sxs-lookup"><span data-stu-id="f17ee-110">Therefore, the logging for the setup is the standard MSI logging.</span></span> <span data-ttu-id="f17ee-111">[Windows 安装程序日志记录](https://msdn.microsoft.com/library/windows/desktop/aa372847.aspx)提供更多详细信息。</span><span class="sxs-lookup"><span data-stu-id="f17ee-111">[Windows Installer Logging](https://msdn.microsoft.com/library/windows/desktop/aa372847.aspx) provides more details.</span></span> 
  
-   <span data-ttu-id="f17ee-112">安装程序执行的自定义操作的所有日志都位于 %temp%\adaptersetup.log。</span><span class="sxs-lookup"><span data-stu-id="f17ee-112">All logs for the custom actions that the setup program performs are available at %TEMP%\adaptersetup.log.</span></span> <span data-ttu-id="f17ee-113">如果跟踪日志文件失败，跟踪也会出现在事件日志。</span><span class="sxs-lookup"><span data-stu-id="f17ee-113">If the tracing to the log file fails, the traces are also available in the event log.</span></span>  
  
## <a name="known-issues"></a><span data-ttu-id="f17ee-114">已知问题</span><span class="sxs-lookup"><span data-stu-id="f17ee-114">Known Issues</span></span>  
 <span data-ttu-id="f17ee-115">以下是在安装时可能遇到的最常见错误[!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)]，以及其可能的原因和解决方法。</span><span class="sxs-lookup"><span data-stu-id="f17ee-115">The following are the most common errors you might encounter when installing the [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)], along with their probable cause and resolution.</span></span>  
  
  
  
###  <span data-ttu-id="f17ee-116"><a name="BKMK_OraAppBinding"></a>安装程序无法注册适配器绑定</span><span class="sxs-lookup"><span data-stu-id="f17ee-116"><a name="BKMK_OraAppBinding"></a> Setup fails to register adapter bindings</span></span>  
 <span data-ttu-id="f17ee-117">**问题**</span><span class="sxs-lookup"><span data-stu-id="f17ee-117">**Problem**</span></span>  
  
 <span data-ttu-id="f17ee-118">Microsoft[!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)]安装向导无法注册的适配器绑定，但将继续执行适配器安装。</span><span class="sxs-lookup"><span data-stu-id="f17ee-118">The Microsoft [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)] setup wizard fails to register the adapter bindings, but proceeds with the adapter installation.</span></span>  
  
 <span data-ttu-id="f17ee-119">**可能的原因**</span><span class="sxs-lookup"><span data-stu-id="f17ee-119">**Cause**</span></span>  
  
 <span data-ttu-id="f17ee-120">这可能会由于存在问题导致[!INCLUDE[firstref_btsWinCommFoundation](../../includes/firstref-btswincommfoundation-md.md)]安装，[!INCLUDE[afproductnamelong](../../includes/afproductnamelong-md.md)]安装或被损坏的 machine.config 文件。</span><span class="sxs-lookup"><span data-stu-id="f17ee-120">This might result due to problems with [!INCLUDE[firstref_btsWinCommFoundation](../../includes/firstref-btswincommfoundation-md.md)] installation, [!INCLUDE[afproductnamelong](../../includes/afproductnamelong-md.md)] installation, or the machine.config file being corrupt.</span></span> <span data-ttu-id="f17ee-121">适配器绑定写入到 machine.config 文件中。</span><span class="sxs-lookup"><span data-stu-id="f17ee-121">The adapter bindings are written to the machine.config file.</span></span>  
  
 <span data-ttu-id="f17ee-122">**解决方法**</span><span class="sxs-lookup"><span data-stu-id="f17ee-122">**Resolution**</span></span>  
  
 <span data-ttu-id="f17ee-123">你应该手动注册[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]绑定。</span><span class="sxs-lookup"><span data-stu-id="f17ee-123">You should manually register the [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] binding.</span></span>  
  
##### <a name="to-register-the-adapter-binding"></a><span data-ttu-id="f17ee-124">若要注册的适配器绑定</span><span class="sxs-lookup"><span data-stu-id="f17ee-124">To register the adapter binding</span></span>  
  
1.  <span data-ttu-id="f17ee-125">导航到计算机上的 machine.config 文件。</span><span class="sxs-lookup"><span data-stu-id="f17ee-125">Navigate to the machine.config file on the computer.</span></span> <span data-ttu-id="f17ee-126">例如，在 32 位平台上，machine.config 位于下\<系统驱动器 >: \WINDOWS\Microsoft.NET\Framework\\< 版本\>\CONFIG。</span><span class="sxs-lookup"><span data-stu-id="f17ee-126">For example, on a 32-bit platform, the machine.config is available under \<system drive>:\WINDOWS\Microsoft.NET\Framework\\<version\>\CONFIG.</span></span>  
  
     <span data-ttu-id="f17ee-127">在此路径中， \<*版本*> 是.NET Framework 的版本。</span><span class="sxs-lookup"><span data-stu-id="f17ee-127">In this path, \<*version*> is the version of the .NET Framework.</span></span>  
  
2.  <span data-ttu-id="f17ee-128">通过使用文本编辑器中打开该文件。</span><span class="sxs-lookup"><span data-stu-id="f17ee-128">Open the file by using a text editor.</span></span>  
  
3.  <span data-ttu-id="f17ee-129">若要注册[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]绑定：</span><span class="sxs-lookup"><span data-stu-id="f17ee-129">To register the [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] binding:</span></span>  
  
    1.  <span data-ttu-id="f17ee-130">搜索的元素"的 system.serviceModel"和其下添加以下：</span><span class="sxs-lookup"><span data-stu-id="f17ee-130">Search for the element "system.serviceModel" and add the following under it:</span></span>  
  
        ```  
        <client>  
          <endpoint binding="oracleEBSBinding" contract="IMetadataExchange" name="oracleebs" />  
        </client>  
        ```  
  
    2.  <span data-ttu-id="f17ee-131">搜索"bindingElementExtensions"system.serviceModel\extensions 下的元素。</span><span class="sxs-lookup"><span data-stu-id="f17ee-131">Search for the element "bindingElementExtensions" under system.serviceModel\extensions.</span></span>  
  
    3.  <span data-ttu-id="f17ee-132">查找缺失[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]绑定。</span><span class="sxs-lookup"><span data-stu-id="f17ee-132">Look for the missing [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] binding.</span></span> <span data-ttu-id="f17ee-133">添加以下节"bindingElementExtensions"节点下。</span><span class="sxs-lookup"><span data-stu-id="f17ee-133">Add the following section under the "bindingElementExtensions" node.</span></span>  
  
         <span data-ttu-id="f17ee-134">有关[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]，添加：</span><span class="sxs-lookup"><span data-stu-id="f17ee-134">For [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)], add:</span></span>  
  
        ```  
        <add name="oracleEBSAdapter" type="Microsoft.Adapters.OracleEBS.OracleEBSBindingElementExtensionElement, Microsoft.Adapters.OracleEBS, Version=<version>, Culture=neutral, PublicKeyToken=<public key>" />  
        ```  
  
    4.  <span data-ttu-id="f17ee-135">搜索"bindingExtensions"system.serviceModel\extensions 下的元素。</span><span class="sxs-lookup"><span data-stu-id="f17ee-135">Search for the element "bindingExtensions" under system.serviceModel\extensions.</span></span>  
  
    5.  <span data-ttu-id="f17ee-136">查找缺失[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]绑定。</span><span class="sxs-lookup"><span data-stu-id="f17ee-136">Look for the missing [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] binding.</span></span> <span data-ttu-id="f17ee-137">添加以下节"bindingExtensions"节点下。</span><span class="sxs-lookup"><span data-stu-id="f17ee-137">Add the following section under the "bindingExtensions" node.</span></span>  
  
         <span data-ttu-id="f17ee-138">有关[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]，添加：</span><span class="sxs-lookup"><span data-stu-id="f17ee-138">For [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)], add:</span></span>  
  
        ```  
        <add name="oracleEBSBinding" type="Microsoft.Adapters.OracleEBS.OracleEBSBindingCollectionElement, Microsoft.Adapters.OracleEBS, Version=<version>, Culture=neutral, PublicKeyToken=<public key>" />  
        ```  
  
    > [!NOTE]
    >  <span data-ttu-id="f17ee-139">有关如何确定公用密钥和版本的信息，请参阅[确定的公钥和版本](#BKMK_PubKey)。</span><span class="sxs-lookup"><span data-stu-id="f17ee-139">For information about how to determine the public key and the version, see [Determining the Public Key and Version](#BKMK_PubKey).</span></span>  
  
4.  <span data-ttu-id="f17ee-140">保存并关闭 machine.config 文件。</span><span class="sxs-lookup"><span data-stu-id="f17ee-140">Save and close the machine.config file.</span></span>  
  
####  <span data-ttu-id="f17ee-141"><a name="BKMK_PubKey"></a>确定的公钥和版本</span><span class="sxs-lookup"><span data-stu-id="f17ee-141"><a name="BKMK_PubKey"></a> Determining the Public Key and Version</span></span>  
 <span data-ttu-id="f17ee-142">执行以下步骤来确定的公钥[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="f17ee-142">Perform the following steps to determine the public key for [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)].</span></span>  
  
###### <a name="to-determine-the-public-key"></a><span data-ttu-id="f17ee-143">若要确定的公钥</span><span class="sxs-lookup"><span data-stu-id="f17ee-143">To determine the public key</span></span>  
  
1.  <span data-ttu-id="f17ee-144">导航到 Windows 目录中，通常 C:\WINDOWS\assembly。</span><span class="sxs-lookup"><span data-stu-id="f17ee-144">Navigate to the Windows directory, typically C:\WINDOWS\assembly.</span></span>  
  
2.  <span data-ttu-id="f17ee-145">右键单击对其需的公钥和版本，且然后选择该 DLL**属性**。</span><span class="sxs-lookup"><span data-stu-id="f17ee-145">Right-click the DLL for which you want the public key and the version, and then select **Properties**.</span></span> <span data-ttu-id="f17ee-146">下表列出的 DLL 的名称[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="f17ee-146">The following table lists the name of the DLL for [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)].</span></span>  
  
    |<span data-ttu-id="f17ee-147">适配器</span><span class="sxs-lookup"><span data-stu-id="f17ee-147">Adapter</span></span>|<span data-ttu-id="f17ee-148">DLL 的名称</span><span class="sxs-lookup"><span data-stu-id="f17ee-148">Name of the DLL</span></span>|  
    |-------------|---------------------|  
    |[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]|<span data-ttu-id="f17ee-149">Microsoft.Adapters.OracleEBS</span><span class="sxs-lookup"><span data-stu-id="f17ee-149">Microsoft.Adapters.OracleEBS</span></span>|  
  
3.  <span data-ttu-id="f17ee-150">上**常规**选项卡上，针对值**Public Key Token**标签指定 DLL 的公共密钥。</span><span class="sxs-lookup"><span data-stu-id="f17ee-150">On the **General** tab, the value against the **Public Key Token** label specifies the public key for the DLL.</span></span> <span data-ttu-id="f17ee-151">同样，针对值**版本**标签指定的 dll 的版本号。</span><span class="sxs-lookup"><span data-stu-id="f17ee-151">Similarly, value against the **Version** label specifies the version number for the DLL.</span></span>  
  
4.  <span data-ttu-id="f17ee-152">复制公钥，，然后单击**取消**。</span><span class="sxs-lookup"><span data-stu-id="f17ee-152">Copy the public key, and then click **Cancel**.</span></span>  
  
###  <span data-ttu-id="f17ee-153"><a name="BKMK_ConsumeOraApp"></a>在 64 位安装上使用使用适配器服务外接程序或添加适配器服务引用插件时出错</span><span class="sxs-lookup"><span data-stu-id="f17ee-153"><a name="BKMK_ConsumeOraApp"></a> Error while using the Consume Adapter Service add-in or Add Adapter Service Reference plug-in on a 64-bit installation</span></span>  
 <span data-ttu-id="f17ee-154">**问题**</span><span class="sxs-lookup"><span data-stu-id="f17ee-154">**Problem**</span></span>  
  
 <span data-ttu-id="f17ee-155">使用[!INCLUDE[addadapterservreflong](../../includes/addadapterservreflong-md.md)]或[!INCLUDE[consumeadapterservlong](../../includes/consumeadapterservlong-md.md)]从[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]运行的 64 位版本的 64 位计算机上[!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)]会导致以下错误：</span><span class="sxs-lookup"><span data-stu-id="f17ee-155">Using the [!INCLUDE[addadapterservreflong](../../includes/addadapterservreflong-md.md)] or the [!INCLUDE[consumeadapterservlong](../../includes/consumeadapterservlong-md.md)] from [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)] on a 64-bit computer running 64-bit version of the [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)] results in the following error:</span></span>  
  
```  
No valid adapters are installed on this machine  
```  
  
 <span data-ttu-id="f17ee-156">**可能的原因**</span><span class="sxs-lookup"><span data-stu-id="f17ee-156">**Cause**</span></span>  
  
 <span data-ttu-id="f17ee-157">[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]是 WCF 自定义绑定，它在 machine.config 文件中的 System.ServiceModel 下注册。</span><span class="sxs-lookup"><span data-stu-id="f17ee-157">The [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] is a WCF custom binding, which is registered under System.ServiceModel in the machine.config file.</span></span> <span data-ttu-id="f17ee-158">64 位平台都有两个 machine.config 文件，其中一个 32 位应用程序使用，另一个 64 位应用程序使用。</span><span class="sxs-lookup"><span data-stu-id="f17ee-158">A 64-bit platform has two machine.config files, one used by the 32-bit applications and the other used by the 64-bit applications.</span></span> <span data-ttu-id="f17ee-159">因此，在安装 64 位版本的[!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)]，安装向导在 64 位版本的 machine.config 文件中注册绑定。</span><span class="sxs-lookup"><span data-stu-id="f17ee-159">So, when you install the 64-bit version of the [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)], the setup wizard registers the bindings in the 64-bit version of the machine.config file.</span></span> <span data-ttu-id="f17ee-160">但是，[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]作为 32 位进程运行，因此启动[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]从[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]，插件检查 machine.config 文件的 32 位版本中的绑定和失败为错误。</span><span class="sxs-lookup"><span data-stu-id="f17ee-160">However, [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)] runs as a 32-bit process and hence when you launch the [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)] from [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)], the plug-in checks for the bindings in the 32-bit version of the machine.config file and fails giving an error.</span></span>  
  
 <span data-ttu-id="f17ee-161">**解决方法**</span><span class="sxs-lookup"><span data-stu-id="f17ee-161">**Resolution**</span></span>  
  
-   <span data-ttu-id="f17ee-162">安装的 32 位和 64 位版本[!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)]在 64 位[!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]安装。</span><span class="sxs-lookup"><span data-stu-id="f17ee-162">Install both the 32-bit and 64-bit versions of the [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)] on a 64-bit [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)] installation.</span></span>  
  
    > [!IMPORTANT]
    >  <span data-ttu-id="f17ee-163">你必须只有 64 位[!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]安装。</span><span class="sxs-lookup"><span data-stu-id="f17ee-163">You must only have a 64-bit [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)] installation.</span></span> <span data-ttu-id="f17ee-164">通过并行安装 32 位和 64 位[!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]不支持在一台计算机上。</span><span class="sxs-lookup"><span data-stu-id="f17ee-164">Side-by-side installation of 32-bit and 64-bit [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)] on a single computer is not supported.</span></span>  
  
-   <span data-ttu-id="f17ee-165">安装修补程序集 11.1.0.7 的 Oracle 客户端 11.1.0.6 Oracle 数据访问组件的 32 位和 64 位版本。</span><span class="sxs-lookup"><span data-stu-id="f17ee-165">Install both the 32-bit and 64-bit versions of the Oracle Data Access Components for Oracle Client 11.1.0.6 with Patch Set 11.1.0.7.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="f17ee-166">若要确保你的应用程序与 ODP.NET 的最新版本，你必须具有"策略 Dll"在计算机上安装并在 GAC 中注册。</span><span class="sxs-lookup"><span data-stu-id="f17ee-166">To make sure your application works with the most recent version of ODP.NET, you must have the "policy DLLs" installed on the computer and registered in the GAC.</span></span> <span data-ttu-id="f17ee-167">有关详细信息，请参阅"Oracle 数据提供程序的.NET 常见问题"在[http://go.microsoft.com/fwlink/p/?LinkId=92834](http://go.microsoft.com/fwlink/p/?LinkId=92834)。</span><span class="sxs-lookup"><span data-stu-id="f17ee-167">For more information, see "Oracle Data Provider for .NET FAQ" at [http://go.microsoft.com/fwlink/p/?LinkId=92834](http://go.microsoft.com/fwlink/p/?LinkId=92834).</span></span>  
  
###  <span data-ttu-id="f17ee-168"><a name="BKMK_OraAppInvalidBinding"></a>在 BizTalk Server 管理控制台中配置 Oracle E-business Suite 适配器的端口，在 64 位安装上时的无效的绑定错误</span><span class="sxs-lookup"><span data-stu-id="f17ee-168"><a name="BKMK_OraAppInvalidBinding"></a> Invalid binding error while configuring Oracle E-Business Suite adapter ports in BizTalk Server Administration Console on a 64-bit installation</span></span>  
 <span data-ttu-id="f17ee-169">**问题**</span><span class="sxs-lookup"><span data-stu-id="f17ee-169">**Problem**</span></span>  
  
 <span data-ttu-id="f17ee-170">当你尝试配置中的适配器的端口[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理控制台中，你将收到以下错误：</span><span class="sxs-lookup"><span data-stu-id="f17ee-170">When you try to configure a port for the adapter in [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] Administration console, you get the following error:</span></span>  
  
```  
"Unable to create binding configuration element for editing. Check the values of the BindingType and BindingConfiguration properties.  
(Microsoft.Biztalk.Adapter.Wcf.Converters.CreateBindingException) Unable to get binding type for binding extension "oracleEBSBinding".  
Verify the binding extension is registered in machine.config."  
```  
  
 <span data-ttu-id="f17ee-171">**可能的原因**</span><span class="sxs-lookup"><span data-stu-id="f17ee-171">**Cause**</span></span>  
  
 <span data-ttu-id="f17ee-172">[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]是 WCF 自定义绑定，它在 machine.config 文件中的 System.ServiceModel 下注册。</span><span class="sxs-lookup"><span data-stu-id="f17ee-172">The [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] is a WCF custom binding, which is registered under System.ServiceModel in the machine.config file.</span></span> <span data-ttu-id="f17ee-173">64 位平台都有两个 machine.config 文件，其中一个 32 位应用程序使用，另一个 64 位应用程序使用。</span><span class="sxs-lookup"><span data-stu-id="f17ee-173">A 64-bit platform has two machine.config files, one used by the 32-bit applications and the other used by the 64-bit applications.</span></span> <span data-ttu-id="f17ee-174">因此，在安装 64 位版本的[!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)]，安装向导在 64 位版本的 machine.config 文件中注册绑定。</span><span class="sxs-lookup"><span data-stu-id="f17ee-174">So, when you install the 64-bit version of the [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)], the setup wizard registers the bindings in the 64-bit version of the machine.config file.</span></span> <span data-ttu-id="f17ee-175">但是，[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]作为 32 位进程运行的管理控制台，因此当你配置为适配器的端口时，它检查 machine.config 文件的 32 位版本中的绑定无法提供错误。</span><span class="sxs-lookup"><span data-stu-id="f17ee-175">However, [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] Administration console runs as a 32-bit process and hence when you configure a port for the adapter, it checks for the bindings in the 32-bit version of the machine.config file and fails giving an error.</span></span>  
  
 <span data-ttu-id="f17ee-176">**解决方法**</span><span class="sxs-lookup"><span data-stu-id="f17ee-176">**Resolution**</span></span>  
  
-   <span data-ttu-id="f17ee-177">安装的 32 位和 64 位版本[!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)]在 64 位[!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]安装。</span><span class="sxs-lookup"><span data-stu-id="f17ee-177">Install both the 32-bit and 64-bit versions of the [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)] on a 64-bit [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)] installation.</span></span>  
  
    > [!IMPORTANT]
    >  <span data-ttu-id="f17ee-178">你必须只有 64 位[!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]安装。</span><span class="sxs-lookup"><span data-stu-id="f17ee-178">You must only have a 64-bit [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)] installation.</span></span> <span data-ttu-id="f17ee-179">通过并行安装 32 位和 64 位[!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]不支持在一台计算机上。</span><span class="sxs-lookup"><span data-stu-id="f17ee-179">Side-by-side installation of 32-bit and 64-bit [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)] on a single computer is not supported.</span></span>  
  
-   <span data-ttu-id="f17ee-180">安装修补程序集 11.1.0.7 的 Oracle 客户端 11.1.0.6 Oracle 数据访问组件的 32 位和 64 位版本。</span><span class="sxs-lookup"><span data-stu-id="f17ee-180">Install both the 32-bit and 64-bit versions of the Oracle Data Access Components for Oracle Client 11.1.0.6 with Patch Set 11.1.0.7.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="f17ee-181">若要确保你的应用程序与 ODP.NET 的最新版本，你必须具有"策略 Dll"在计算机上安装并在 GAC 中注册。</span><span class="sxs-lookup"><span data-stu-id="f17ee-181">To make sure your application works with the most recent version of ODP.NET, you must have the "policy DLLs" installed on the computer and registered in the GAC.</span></span> <span data-ttu-id="f17ee-182">有关详细信息，请参阅"Oracle 数据提供程序的.NET 常见问题"在[http://go.microsoft.com/fwlink/p/?LinkId=92834](http://go.microsoft.com/fwlink/p/?LinkId=92834)。</span><span class="sxs-lookup"><span data-stu-id="f17ee-182">For more information, see "Oracle Data Provider for .NET FAQ" at [http://go.microsoft.com/fwlink/p/?LinkId=92834](http://go.microsoft.com/fwlink/p/?LinkId=92834).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f17ee-183">另请参阅</span><span class="sxs-lookup"><span data-stu-id="f17ee-183">See Also</span></span>  
[<span data-ttu-id="f17ee-184">故障排除 Oracle EBS 适配器</span><span class="sxs-lookup"><span data-stu-id="f17ee-184">Troubleshooting the Oracle EBS adapter</span></span>](../../adapters-and-accelerators/adapter-oracle-ebs/troubleshooting-the-oracle-ebs-adapter.md)