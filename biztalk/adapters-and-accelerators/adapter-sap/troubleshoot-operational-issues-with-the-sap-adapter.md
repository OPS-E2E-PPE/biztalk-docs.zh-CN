---
title: 使用 BizTalk 中的 SAP 适配器进行的操作问题故障排除 |Microsoft 文档
description: 常见错误、 问题和解决方法与 mySAP 适配器 BizTalk 适配器包 (BAP) 中
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: bb0f005b-7548-478b-8243-69e07c29d02c
caps.latest.revision: 32
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f98a4f7b9ed0a504c3adc245916ca9d39af7a7fe
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/28/2017
ms.locfileid: "25967507"
---
# <a name="troubleshoot-operational-issues-with-the-sap-adapter"></a><span data-ttu-id="34d0e-103">与 SAP 适配器排除操作问题</span><span class="sxs-lookup"><span data-stu-id="34d0e-103">Troubleshoot Operational Issues with the SAP adapter</span></span>
<span data-ttu-id="34d0e-104">本部分讨论如何使用故障排除方法来解决操作使用时可能遇到的错误[!INCLUDE[adaptersap](../../includes/adaptersap-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="34d0e-104">This section discusses using troubleshooting techniques to resolve operational errors that you might encounter when using [!INCLUDE[adaptersap](../../includes/adaptersap-md.md)].</span></span>  
  
### <a name="enable-tracing"></a><span data-ttu-id="34d0e-105">启用跟踪</span><span class="sxs-lookup"><span data-stu-id="34d0e-105">Enable tracing</span></span>  
 <span data-ttu-id="34d0e-106">有关跟踪中的支持信息[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]，请参阅[诊断跟踪和消息日志记录为 SAP 适配器](../../adapters-and-accelerators/adapter-sap/diagnostic-tracing-and-message-logging-for-the-sap-adapter.md)。</span><span class="sxs-lookup"><span data-stu-id="34d0e-106">For information about tracing support in the [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)], see [Diagnostic Tracing and Message Logging for the SAP adapter](../../adapters-and-accelerators/adapter-sap/diagnostic-tracing-and-message-logging-for-the-sap-adapter.md).</span></span>  
  
##  <a name="client_dll"></a><span data-ttu-id="34d0e-107">加载绑定时出错</span><span class="sxs-lookup"><span data-stu-id="34d0e-107">Error loading the binding</span></span>  
 <span data-ttu-id="34d0e-108">**问题**</span><span class="sxs-lookup"><span data-stu-id="34d0e-108">**Problem**</span></span>  
  
 <span data-ttu-id="34d0e-109">当你尝试启动[!INCLUDE[addadapterservreflong](../../includes/addadapterservreflong-md.md)]或[!INCLUDE[consumeadapterservlong](../../includes/consumeadapterservlong-md.md)]，GUI 将报告以下错误：</span><span class="sxs-lookup"><span data-stu-id="34d0e-109">When you try to start the [!INCLUDE[addadapterservreflong](../../includes/addadapterservreflong-md.md)]or the [!INCLUDE[consumeadapterservlong](../../includes/consumeadapterservlong-md.md)], the GUI gives the following error:</span></span>  
  
```  
There was an error loading the binding, <binding name>, from your system configuration.  
ConfigurationErrorsException: Exception has been thrown by the target of an invocation.  
```  
  
 <span data-ttu-id="34d0e-110">**可能的原因**</span><span class="sxs-lookup"><span data-stu-id="34d0e-110">**Cause**</span></span>  
  
 <span data-ttu-id="34d0e-111">当你启动[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]或[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]，[!INCLUDE[firstref_btsWinCommFoundation](../../includes/firstref-btswincommfoundation-md.md)]加载所有已安装适配器的适配器绑定。</span><span class="sxs-lookup"><span data-stu-id="34d0e-111">When you start the [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)] or the [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)], [!INCLUDE[firstref_btsWinCommFoundation](../../includes/firstref-btswincommfoundation-md.md)] loads the adapter bindings for all the installed adapters.</span></span> <span data-ttu-id="34d0e-112">反过来，适配器绑定都依赖于企业应用程序的特定客户端软件。</span><span class="sxs-lookup"><span data-stu-id="34d0e-112">In turn, the adapter bindings are dependent on the specific client software for the enterprise application.</span></span> <span data-ttu-id="34d0e-113">你可能会遇到此问题的一个或两个原因如下：</span><span class="sxs-lookup"><span data-stu-id="34d0e-113">You might face this issue for one or both of the following reasons:</span></span>  
  
-   <span data-ttu-id="34d0e-114">在安装适配器的计算机上未安装所需的 LOB 客户端软件。</span><span class="sxs-lookup"><span data-stu-id="34d0e-114">The required LOB client software is not installed on the computer where you installed the adapter.</span></span>  
  
-   <span data-ttu-id="34d0e-115">未将适配器安装中包含的所有适配器的典型或完全安装[!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="34d0e-115">You did a Typical or Complete installation of the adapter, which installs all the adapters contained in the [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)].</span></span> <span data-ttu-id="34d0e-116">但是，可能只有一个企业应用程序安装 LOB 客户端库。</span><span class="sxs-lookup"><span data-stu-id="34d0e-116">However, the LOB client libraries might be installed for only one enterprise application.</span></span> <span data-ttu-id="34d0e-117">因此，GUI 无法加载其他适配器的绑定。</span><span class="sxs-lookup"><span data-stu-id="34d0e-117">As a result, the GUI fails to load the bindings for the other adapters.</span></span>  
  
 <span data-ttu-id="34d0e-118">**解决方法**</span><span class="sxs-lookup"><span data-stu-id="34d0e-118">**Resolution**</span></span>  
  
-   <span data-ttu-id="34d0e-119">请确保执行适配器安装需要适配器的自定义安装。</span><span class="sxs-lookup"><span data-stu-id="34d0e-119">Make sure you do a Custom installation of the adapters to install only the adapter you need.</span></span>  
  
-   <span data-ttu-id="34d0e-120">请确保你安装的计算机上安装了所需的 LOB 客户端版本[!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="34d0e-120">Make sure the required LOB client versions are installed on the computer where you installed the [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)].</span></span> <span data-ttu-id="34d0e-121">[支持 LOB 系统](https://social.technet.microsoft.com/wiki/contents/articles/17631.biztalk-server-supported-line-of-business-lob-and-enterprise-systems.aspx)列出支持的版本。</span><span class="sxs-lookup"><span data-stu-id="34d0e-121">[Supported LOB systems](https://social.technet.microsoft.com/wiki/contents/articles/17631.biztalk-server-supported-line-of-business-lob-and-enterprise-systems.aspx) lists the supported versions.</span></span> <span data-ttu-id="34d0e-122">[!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)]还需要某些 Dll 与 SAP 系统之间的接口。</span><span class="sxs-lookup"><span data-stu-id="34d0e-122">The [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)] also requires certain DLLs to interface with the SAP system.</span></span> <span data-ttu-id="34d0e-123">有关适配器所需的 Dll 的详细信息，请参阅[用于 SAP 的数据提供程序安装自定义 Rfc](../../adapters-and-accelerators/adapter-sap/install-custom-rfcs-for-the-data-provider-for-sap.md)。</span><span class="sxs-lookup"><span data-stu-id="34d0e-123">For more information about the DLLs required by the adapter, see [Install Custom RFCs for the Data Provider for SAP](../../adapters-and-accelerators/adapter-sap/install-custom-rfcs-for-the-data-provider-for-sap.md).</span></span>
  
##  <a name="BKMK_SAPDisplay"></a><span data-ttu-id="34d0e-124">SAP 适配器是 BizTalk 管理控制台中缺少</span><span class="sxs-lookup"><span data-stu-id="34d0e-124">The SAP adapter is missing in BizTalk Administration console</span></span>  
 <span data-ttu-id="34d0e-125">**问题**</span><span class="sxs-lookup"><span data-stu-id="34d0e-125">**Problem**</span></span>  
  
<span data-ttu-id="34d0e-126">[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]附带[!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)]未显示在列表中的 BizTalk Server 管理控制台中的适配器。</span><span class="sxs-lookup"><span data-stu-id="34d0e-126">The [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] included with [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)] does not show up in the list of adapters in the BizTalk Server Administration console.</span></span>  
  
 <span data-ttu-id="34d0e-127">**可能的原因**</span><span class="sxs-lookup"><span data-stu-id="34d0e-127">**Cause**</span></span>  
  
 <span data-ttu-id="34d0e-128">[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]是 WCF 自定义绑定。</span><span class="sxs-lookup"><span data-stu-id="34d0e-128">The [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] is a WCF custom binding.</span></span> <span data-ttu-id="34d0e-129">因此，尽管[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理控制台显示[!INCLUDE[wcfadapter_short](../../includes/wcfadapter-short-md.md)]，它不会显示 WCF 自定义绑定，并因此，不会显示基于 WCF 的[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="34d0e-129">So, although the [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] Administration console displays the [!INCLUDE[wcfadapter_short](../../includes/wcfadapter-short-md.md)], it does not display the WCF custom bindings and hence, does not display the WCF-based [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)].</span></span>  
  
 <span data-ttu-id="34d0e-130">**解决方法**</span><span class="sxs-lookup"><span data-stu-id="34d0e-130">**Resolution**</span></span>  
  
 <span data-ttu-id="34d0e-131">你可以显式添加[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]到[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理控制台中所述的步骤[将 SAP 适配器添加到 BizTalk Server 管理控制台](../../adapters-and-accelerators/adapter-sap/add-the-sap-adapter-to-biztalk-server-administration-console.md)。</span><span class="sxs-lookup"><span data-stu-id="34d0e-131">You can explicitly add the [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] to the [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] Administration console by following the steps mentioned in [Add the SAP Adapter to BizTalk Server Administration Console](../../adapters-and-accelerators/adapter-sap/add-the-sap-adapter-to-biztalk-server-administration-console.md).</span></span>  
  
##  <a name="BKMK_SAPConnOpen"></a><span data-ttu-id="34d0e-132">Dll 缺少打开与 SAP 的连接时出错</span><span class="sxs-lookup"><span data-stu-id="34d0e-132">DLLs are missing error opening a connection to SAP</span></span>  
 <span data-ttu-id="34d0e-133">**问题**</span><span class="sxs-lookup"><span data-stu-id="34d0e-133">**Problem**</span></span>  
  
 <span data-ttu-id="34d0e-134">当你尝试打开到 SAP 系统使用的连接[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]，在 SAP 系统中，会出现一个对话框告知某些 Dll 的缺失。</span><span class="sxs-lookup"><span data-stu-id="34d0e-134">When you try to open a connection to the SAP system using the [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)], a dialog box appears in the SAP system, informing that some DLLs are missing.</span></span>  
  
 <span data-ttu-id="34d0e-135">**可能的原因**</span><span class="sxs-lookup"><span data-stu-id="34d0e-135">**Cause**</span></span>  
  
 <span data-ttu-id="34d0e-136">[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] Librfc32u.dll 用于建立与 SAP 系统的连接。</span><span class="sxs-lookup"><span data-stu-id="34d0e-136">The [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] uses librfc32u.dll to establish a connection with the SAP system.</span></span> <span data-ttu-id="34d0e-137">Librfc32u.dll，反过来，需要一组 Dll 才能正常。</span><span class="sxs-lookup"><span data-stu-id="34d0e-137">The librfc32u.dll, in turn, requires a set of DLLs to function.</span></span> <span data-ttu-id="34d0e-138">如果这些支持 Dll 不会添加到 PATH 变量的计算机上出现此错误其中[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]安装。</span><span class="sxs-lookup"><span data-stu-id="34d0e-138">You get this error if these supporting DLLs are not added to the PATH variable on the computer where the [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] is installed.</span></span>  
  
 <span data-ttu-id="34d0e-139">**解决方法**</span><span class="sxs-lookup"><span data-stu-id="34d0e-139">**Resolution**</span></span>  
  
 <span data-ttu-id="34d0e-140">请参阅表来为解决此问题提供[中加载的适配器绑定错误](#client_dll)问题。</span><span class="sxs-lookup"><span data-stu-id="34d0e-140">Refer to the table provided as a resolution to the [Error in loading the adapter bindings](#client_dll) issue.</span></span> <span data-ttu-id="34d0e-141">表列出了与 SAP 系统使用连接所需的支持 Dll [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="34d0e-141">The table lists the supporting DLLs required to interface with the SAP system using the [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)].</span></span>  
  
##  <a name="BKMK_SAPXmlRetrieve"></a><span data-ttu-id="34d0e-142">具有多个 65,536 节点检索 XML 时出错</span><span class="sxs-lookup"><span data-stu-id="34d0e-142">Error retrieving XML with more than 65,536 nodes</span></span>  
 <span data-ttu-id="34d0e-143">**问题**</span><span class="sxs-lookup"><span data-stu-id="34d0e-143">**Problem**</span></span>  
  
 <span data-ttu-id="34d0e-144">适配器将检索具有多个 65,536 节点的 XML 输出时报告以下错误。</span><span class="sxs-lookup"><span data-stu-id="34d0e-144">The adapter gives the following error while retrieving XML output that has more than 65,536 nodes.</span></span>  
  
```  
Maximum number of items that can be serialized or deserialized in an object graph is '65536'.  
Change the object graph or increase the MaxItemsInObjectGraph quota.  
```  
  
 <span data-ttu-id="34d0e-145">**可能的原因**</span><span class="sxs-lookup"><span data-stu-id="34d0e-145">**Cause**</span></span>  
  
 <span data-ttu-id="34d0e-146">适配器不能序列化和反序列化具有多个 65,536 项的对象。</span><span class="sxs-lookup"><span data-stu-id="34d0e-146">The adapter cannot serialize and deserialize an object with more than 65,536 items.</span></span>  
  
 <span data-ttu-id="34d0e-147">**解决方法**</span><span class="sxs-lookup"><span data-stu-id="34d0e-147">**Resolution**</span></span>  
  
 <span data-ttu-id="34d0e-148">可以通过设置来解决此问题`maxItemsInObjectGraph`参数在以下两种方法之一：</span><span class="sxs-lookup"><span data-stu-id="34d0e-148">You can fix this issue by setting the `maxItemsInObjectGraph` parameter in either of the following two ways:</span></span>  
  
-   <span data-ttu-id="34d0e-149">将此参数设置通过更改`maxItemsInObjectGraph`中的参数`ServiceBehavior`服务类中的属性。</span><span class="sxs-lookup"><span data-stu-id="34d0e-149">Set this parameter by changing the `maxItemsInObjectGraph` parameter in the `ServiceBehavior` attribute on your service class.</span></span>  
  
-   <span data-ttu-id="34d0e-150">将以下代码添加到你的应用程序的 app.config 文件。</span><span class="sxs-lookup"><span data-stu-id="34d0e-150">Add the following to your application's app.config file.</span></span>  
  
    ```  
    <behaviors>  
      <endpointBehaviors>  
        <behavior name="NewBehavior">  
          <dataContractSerializer maxItemsInObjectGraph="65536000" />  
        </behavior>  
      </endpointBehaviors>  
    </behaviors>  
    ```  
  
 <span data-ttu-id="34d0e-151">示例 app.config 将如下所示。</span><span class="sxs-lookup"><span data-stu-id="34d0e-151">A sample app.config will look like the following.</span></span>  
  
```  
<?xml version="1.0" encoding="utf-8"?>  
<configuration>  
  <system.serviceModel>  
    <behaviors>  
      <endpointBehaviors>  
        <behavior name="NewBehavior">  
         <dataContractSerializer maxItemsInObjectGraph="65536000" />  
        </behavior>  
      </endpointBehaviors>  
    </behaviors>  
    <client>  
      <endpoint   behaviorConfiguration="NewBehavior" binding="sapBinding"  
       contract="IOutboundContract" name="sap_ICalculator" />  
    </client>  
  </system.serviceModel>  
</configuration>  
```  
  
##  <a name="BKMK_SAPConnURI"></a><span data-ttu-id="34d0e-152">在 BizTalk Server 中输入 WCF 自定义端口的连接 URI 的错误</span><span class="sxs-lookup"><span data-stu-id="34d0e-152">Error entering a connection URI for a WCF-Custom port in BizTalk Server</span></span>  
 <span data-ttu-id="34d0e-153">**问题**</span><span class="sxs-lookup"><span data-stu-id="34d0e-153">**Problem**</span></span>  
  
 [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]<span data-ttu-id="34d0e-154">指定连接 URI 以连接到 SAP 系统时，则报告以下错误。</span><span class="sxs-lookup"><span data-stu-id="34d0e-154"> gives the following error when you specify a connection URI to connect to the SAP system.</span></span>  
  
```  
Error saving properties.  
(System.ArgumentException) The specified address is invalid.  
(System.ArgumentException) Invalid address;  
"<connection URI>" is not a well-formed absolute uri.  
```  
  
 <span data-ttu-id="34d0e-155">**可能的原因**</span><span class="sxs-lookup"><span data-stu-id="34d0e-155">**Cause**</span></span>  
  
 <span data-ttu-id="34d0e-156">连接 URI 不符合标准的编码格式。</span><span class="sxs-lookup"><span data-stu-id="34d0e-156">The connection URI does not adhere to the standard encoding format.</span></span> <span data-ttu-id="34d0e-157">例如，参数的值可能包含一个空格。</span><span class="sxs-lookup"><span data-stu-id="34d0e-157">For example, the value for a parameter might contain a space.</span></span>  
  
 <span data-ttu-id="34d0e-158">**解决方法**</span><span class="sxs-lookup"><span data-stu-id="34d0e-158">**Resolution**</span></span>  
  
 <span data-ttu-id="34d0e-159">请确保你指定的 URI 符合标准的编码格式的连接。</span><span class="sxs-lookup"><span data-stu-id="34d0e-159">Make sure the connection URI you specify adheres to the standard encoding format.</span></span> <span data-ttu-id="34d0e-160">例如，必须通过"%20"替换为空格。</span><span class="sxs-lookup"><span data-stu-id="34d0e-160">For example, a blank space must be replaced by "%20".</span></span>  
  
##  <a name="BKMK_SAPOperate"></a><span data-ttu-id="34d0e-161">System.ArgumentNullException 上 SAP 的操作出错</span><span class="sxs-lookup"><span data-stu-id="34d0e-161">System.ArgumentNullException error while completing an operation on SAP</span></span>  
 <span data-ttu-id="34d0e-162">**问题**</span><span class="sxs-lookup"><span data-stu-id="34d0e-162">**Problem**</span></span>  
  
 <span data-ttu-id="34d0e-163">适配器执行针对 SAP 系统使用的任何操作时将报告以下错误[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="34d0e-163">The adapter gives the following error when performing any operation on the SAP system using [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)].</span></span>  
  
```  
System.ArgumentNullException: Value cannot be null.  
```  
  
 <span data-ttu-id="34d0e-164">**可能的原因**</span><span class="sxs-lookup"><span data-stu-id="34d0e-164">**Cause**</span></span>  
  
 <span data-ttu-id="34d0e-165">未指定消息的 WCF 操作。</span><span class="sxs-lookup"><span data-stu-id="34d0e-165">The WCF action for the message is not specified.</span></span> <span data-ttu-id="34d0e-166">WCF 需要为每个操作，在 LOB 应用程序上执行的操作会告知适配器指定的 SOAP 操作。</span><span class="sxs-lookup"><span data-stu-id="34d0e-166">WCF requires a SOAP action to be specified for every operation, which informs the adapter about the operation to be performed on the LOB application.</span></span>  
  
 <span data-ttu-id="34d0e-167">**解决方法**</span><span class="sxs-lookup"><span data-stu-id="34d0e-167">**Resolution**</span></span>  
  
 <span data-ttu-id="34d0e-168">指定的 SOAP 操作中发送端口或 BizTalk 业务流程中的消息上下文属性。</span><span class="sxs-lookup"><span data-stu-id="34d0e-168">Specify the SOAP action in the send port or as a message context property in a BizTalk orchestration.</span></span> <span data-ttu-id="34d0e-169">有关说明，请参阅[配置 SAP 系统的 SOAP 操作](../../adapters-and-accelerators/adapter-sap/configure-the-soap-action-for-the-sap-system.md)。</span><span class="sxs-lookup"><span data-stu-id="34d0e-169">For instructions, see [Configure the SOAP action for the SAP system](../../adapters-and-accelerators/adapter-sap/configure-the-soap-action-for-the-sap-system.md).</span></span> <span data-ttu-id="34d0e-170">请参阅[消息和消息架构](messages-and-message-schemas-for-biztalk-adapter-for-mysap-business-suite.md)若要查看的每个操作的操作的列表。</span><span class="sxs-lookup"><span data-stu-id="34d0e-170">See [Messages and message schemas](messages-and-message-schemas-for-biztalk-adapter-for-mysap-business-suite.md) to see a list of actions for each operation.</span></span>  
  
##  <a name="BKMK_SAPXmlParsing"></a><span data-ttu-id="34d0e-171">由于指定的操作中不正确的操作名称 XmlReaderParsingException</span><span class="sxs-lookup"><span data-stu-id="34d0e-171">XmlReaderParsingException due to incorrect operation name in the specified action</span></span>  
 <span data-ttu-id="34d0e-172">**问题**</span><span class="sxs-lookup"><span data-stu-id="34d0e-172">**Problem**</span></span>  
  
 <span data-ttu-id="34d0e-173">将消息发送到 SAP 系统时，BizTalk Server 管理控制台提供了以下错误：</span><span class="sxs-lookup"><span data-stu-id="34d0e-173">The BizTalk Server Administration Console gives the following error when sending messages to an SAP system:</span></span>  
  
```  
Microsoft.ServiceModel.Channels.Common.XmlReaderParsingException: Invalid argument:  
<BtsActionMapping xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xmlns:xsd="http://www.w3.org/2001/XMLSchema">  
  <Operation Name="<operation_name>" Action="<action>" />  
</BtsActionMapping>  
```  
  
 <span data-ttu-id="34d0e-174">**可能的原因**</span><span class="sxs-lookup"><span data-stu-id="34d0e-174">**Cause**</span></span>  
  
 <span data-ttu-id="34d0e-175">如果通过导入创建的端口绑定文件中配置 WCF 自定义端口[!INCLUDE[consumeadapterservlong](../../includes/consumeadapterservlong-md.md)]，采用以下格式指定端口中的操作：</span><span class="sxs-lookup"><span data-stu-id="34d0e-175">If you configure a WCF-Custom port by importing the port binding file created by the [!INCLUDE[consumeadapterservlong](../../includes/consumeadapterservlong-md.md)], the action in the port is specified in the following format:</span></span>  
  
```  
<BtsActionMapping>  
  <Operation Name="Op1" Action="http://MyService/Svc/Op1" />  
</BtsActionMapping>  
```  
  
 <span data-ttu-id="34d0e-176">在以上格式中，操作名称受生成架构时选择该操作。</span><span class="sxs-lookup"><span data-stu-id="34d0e-176">In the above format, the operation name is governed by the operation you chose while generating the schema.</span></span> <span data-ttu-id="34d0e-177">例如，如果 RFC_CUSTOMER_GET 生成架构，则操作中的操作名称将"RFC_CUSTOMER_GET"。</span><span class="sxs-lookup"><span data-stu-id="34d0e-177">For example, if you generated schema for RFC_CUSTOMER_GET, the operation name in the action will be "RFC_CUSTOMER_GET".</span></span> <span data-ttu-id="34d0e-178">但是中的逻辑端口的操作名称创建在 BizTalk 业务流程中[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]可能不同。</span><span class="sxs-lookup"><span data-stu-id="34d0e-178">However, the operation name in the logical port created in the BizTalk orchestration in [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)] might be different.</span></span>  
  
 <span data-ttu-id="34d0e-179">**解决方法**</span><span class="sxs-lookup"><span data-stu-id="34d0e-179">**Resolution**</span></span>  
  
 <span data-ttu-id="34d0e-180">请确保操作名称在这两个逻辑端口 (在 BizTalk 业务流程中[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]) 和 （在 BizTalk Server 管理控制台） 的物理端口都相同。</span><span class="sxs-lookup"><span data-stu-id="34d0e-180">Make sure the operation names in both the logical port (in the BizTalk orchestration in [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]) and the physical port (in BizTalk Server Administration Console) are same.</span></span>  
  
##  <a name="BKMK_SAPHundredCons"></a><span data-ttu-id="34d0e-181">打开与 SAP 超过 100 个连接时出错</span><span class="sxs-lookup"><span data-stu-id="34d0e-181">Error opening more than 100 connections to SAP</span></span>  
 <span data-ttu-id="34d0e-182">**问题**</span><span class="sxs-lookup"><span data-stu-id="34d0e-182">**Problem**</span></span>  
  
 <span data-ttu-id="34d0e-183">打开超过 100 个连接到 SAP 系统时，该适配器将引发以下异常。</span><span class="sxs-lookup"><span data-stu-id="34d0e-183">The adapter throws the following exception when opening more than 100 connections to the SAP system.</span></span>  
  
```  
Microsoft.ServiceModel.Channels.Common.ConnectionException: ErrorCode=RFC_OK. ErrorGroup=RFC_ERROR_COMMUNICATION. SapErrorMessage=Connect to SAP gateway failed  
Connect_PM  GWHOST=<gw_host>, GWSERV=<gw_serv>, SYSNR=<sys_number>  
LOCATION    CPIC (TCP/IP) on local host with Unicode  
ERROR       max no of 100 conversations exceeded  
```  
  
 <span data-ttu-id="34d0e-184">**可能的原因**</span><span class="sxs-lookup"><span data-stu-id="34d0e-184">**Cause**</span></span>  
  
 <span data-ttu-id="34d0e-185">默认情况下，SAP 不启用超过 100 个连接到系统。</span><span class="sxs-lookup"><span data-stu-id="34d0e-185">By default, SAP does not enable more than 100 connections into the system.</span></span>  
  
 <span data-ttu-id="34d0e-186">**解决方法**</span><span class="sxs-lookup"><span data-stu-id="34d0e-186">**Resolution**</span></span>  
  
 <span data-ttu-id="34d0e-187">若要增加最大连接数，必须已安装并将其设置为数字值的 SAP 客户端库的计算机上创建一个环境变量。</span><span class="sxs-lookup"><span data-stu-id="34d0e-187">To increase the maximum number of connections, you must create an environment variable on the computer that has the SAP client libraries installed and set it to a numeric value.</span></span> <span data-ttu-id="34d0e-188">为此环境变量指定的值是最大可以成为 SAP 系统的连接数。</span><span class="sxs-lookup"><span data-stu-id="34d0e-188">The value you specify for this environment variable is the maximum number of connections that can be made into the SAP system.</span></span> <span data-ttu-id="34d0e-189">创建环境变量具有以下详细信息：</span><span class="sxs-lookup"><span data-stu-id="34d0e-189">Create the environment variable with the following details:</span></span>  
  
-   <span data-ttu-id="34d0e-190">**变量名称**: CPIC_MAX_CONV</span><span class="sxs-lookup"><span data-stu-id="34d0e-190">**Variable name**: CPIC_MAX_CONV</span></span>  
  
-   <span data-ttu-id="34d0e-191">**变量值**： 任何正数值。</span><span class="sxs-lookup"><span data-stu-id="34d0e-191">**Variable value**: any positive numeric value.</span></span> <span data-ttu-id="34d0e-192">例如，如果要启用 200 连接到 SAP 系统，可以指定的值设为 200。</span><span class="sxs-lookup"><span data-stu-id="34d0e-192">For example, to enable 200 connections into the SAP system, specify the value as 200.</span></span>  
  
 <span data-ttu-id="34d0e-193">有关创建环境变量的说明，请参阅"如何对 Windows 2000 中创建系统变量"在[http://go.microsoft.com/fwlink/?LinkId=95020](http://go.microsoft.com/fwlink/?LinkId=95020)。</span><span class="sxs-lookup"><span data-stu-id="34d0e-193">For instructions on creating an environment variable, see "How To Create System Variables in Windows 2000" at [http://go.microsoft.com/fwlink/?LinkId=95020](http://go.microsoft.com/fwlink/?LinkId=95020).</span></span>  
  
##  <a name="BKMK_SAPIDOCMetadata"></a><span data-ttu-id="34d0e-194">生成时出现错误或检索到的 Idoc 的元数据</span><span class="sxs-lookup"><span data-stu-id="34d0e-194">Error generating or retrieving metadata for IDOCs</span></span>  
 <span data-ttu-id="34d0e-195">**问题**</span><span class="sxs-lookup"><span data-stu-id="34d0e-195">**Problem**</span></span>  
  
 <span data-ttu-id="34d0e-196">生成的元数据时**接收**操作中的 SAP 系统，idoc[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]将报告以下错误。</span><span class="sxs-lookup"><span data-stu-id="34d0e-196">While generating metadata for the **Receive** operation for an IDOC in an SAP system, the [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] gives the following error.</span></span>  
  
```  
Error while retrieving or generating the WSDL.  
Adapter message: Details: ErrorCode=RFC_EXCEPTION.  
ErrorGroup=RFC_ERROR_APPLICATION_EXCEPTION. SapErrorMessage= OBJECT_UNKNOWN.  
AdapterErrorMessage=Error returned by RfcCallReceiveEx while calling RFC: IDOCTYPE_READ_COMPLETE.  
```  
  
 <span data-ttu-id="34d0e-197">**可能的原因**</span><span class="sxs-lookup"><span data-stu-id="34d0e-197">**Cause**</span></span>  
  
 <span data-ttu-id="34d0e-198">[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] IDOCTYPE_READ_COMPLETE RFC 用于检索的元数据**接收**IDOC 的操作。</span><span class="sxs-lookup"><span data-stu-id="34d0e-198">The [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] uses the IDOCTYPE_READ_COMPLETE RFC to retrieve the metadata for the **Receive** operation for an IDOC.</span></span> <span data-ttu-id="34d0e-199">调用此 RFC SAP 系统中需要特定的用户权限。</span><span class="sxs-lookup"><span data-stu-id="34d0e-199">Invoking this RFC requires specific user permissions in the SAP system.</span></span> <span data-ttu-id="34d0e-200">若要生成元数据，如果你已连接到 SAP 系统使用的凭据没有权限来调用 IDOCTYPE_READ_COMPLETE RFC，[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]将会出错。</span><span class="sxs-lookup"><span data-stu-id="34d0e-200">To generate metadata, if you have connected to the SAP system using a credential that does not have permission to invoke the IDOCTYPE_READ_COMPLETE RFC, the [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] gives an error.</span></span>  
  
 <span data-ttu-id="34d0e-201">**解决方法**</span><span class="sxs-lookup"><span data-stu-id="34d0e-201">**Resolution**</span></span>  
  
 <span data-ttu-id="34d0e-202">登录到 SAP GUI 使用已为适配器使用的相同凭据。</span><span class="sxs-lookup"><span data-stu-id="34d0e-202">Log in to the SAP GUI using the same credentials you had used for the adapter.</span></span> <span data-ttu-id="34d0e-203">导航到事务 SE37，并输入 RFC 作为 IDOCTYPE_READ_COMPLETE 执行的名称。</span><span class="sxs-lookup"><span data-stu-id="34d0e-203">Navigate to transaction SE37, and enter the name of the RFC to execute as IDOCTYPE_READ_COMPLETE.</span></span>  
  
 <span data-ttu-id="34d0e-204">为输入参数 PI_IDOCTYP 和 PI_CIMTYP，输入对应于自定义的 IDoc 的值。</span><span class="sxs-lookup"><span data-stu-id="34d0e-204">For the input parameters PI_IDOCTYP and PI_CIMTYP, enter the values corresponding to the custom IDoc.</span></span> <span data-ttu-id="34d0e-205">对于 PI_VERSION 和 PI_RELEASE 参数，为所选适配器元数据 UI 中输入相同的值。</span><span class="sxs-lookup"><span data-stu-id="34d0e-205">For the parameters PI_VERSION and PI_RELEASE, enter the same values as being chosen in the Adapter Metadata UI.</span></span> <span data-ttu-id="34d0e-206">然后，按 F8 来执行。</span><span class="sxs-lookup"><span data-stu-id="34d0e-206">And, press F8 to execute.</span></span>  
  
 <span data-ttu-id="34d0e-207">您应获取作为什么适配器接收，有关问题的详细信息相同的异常。</span><span class="sxs-lookup"><span data-stu-id="34d0e-207">You should get the same exception as what the adapter receives, with more information about the issue.</span></span>  
  
 <span data-ttu-id="34d0e-208">如果仍无法解决此问题，生成的架构**ReceiveIdoc**操作而不是**接收**操作。</span><span class="sxs-lookup"><span data-stu-id="34d0e-208">If you are still not able to resolve the issue, generate a schema for the **ReceiveIdoc** operation instead of the **Receive** operation.</span></span> <span data-ttu-id="34d0e-209">在这种情况下，SAP 适配器不使用 IDOCTYPE_READ_COMPLETE，且不引发任何错误。</span><span class="sxs-lookup"><span data-stu-id="34d0e-209">In this case, the SAP adapter does not use IDOCTYPE_READ_COMPLETE, and does not throw any error.</span></span>  
  
##  <a name="BKMK_SAPIDOCReceive"></a><span data-ttu-id="34d0e-210">错误发送或接收已取消释放段的 Idoc</span><span class="sxs-lookup"><span data-stu-id="34d0e-210">Error sending or receiving IDOCs that have unreleased segments</span></span>  
 <span data-ttu-id="34d0e-211">**问题**</span><span class="sxs-lookup"><span data-stu-id="34d0e-211">**Problem**</span></span>  
  
 <span data-ttu-id="34d0e-212">[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]发送到的 Idoc 时提供 XmlReaderParsingException (使用**发送**操作) 或接收到的 Idoc (使用**接收**操作)，已取消释放段。</span><span class="sxs-lookup"><span data-stu-id="34d0e-212">The [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] gives an XmlReaderParsingException while sending IDOCs (using **Send** operation) or receiving IDOCs (using **Receive** operation) that have unreleased segments.</span></span>  
  
 <span data-ttu-id="34d0e-213">**可能的原因**</span><span class="sxs-lookup"><span data-stu-id="34d0e-213">**Cause**</span></span>  
  
 <span data-ttu-id="34d0e-214">Idoc 被构成的段。</span><span class="sxs-lookup"><span data-stu-id="34d0e-214">IDOCs are constituted of segments.</span></span> <span data-ttu-id="34d0e-215">生成元数据，时[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]检索 SAP 系统中存在的所有发布的段。</span><span class="sxs-lookup"><span data-stu-id="34d0e-215">While generating metadata, the [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] retrieves all the released segments that are present in the SAP system.</span></span> <span data-ttu-id="34d0e-216">但是，当适配器客户端使用元数据来执行的操作，如接收 IDOC，[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]提供 XmlReaderParsingException。</span><span class="sxs-lookup"><span data-stu-id="34d0e-216">However, when the adapter client uses the metadata to perform an operation such as receiving an IDOC, the [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] gives an XmlReaderParsingException.</span></span> <span data-ttu-id="34d0e-217">因为收到的 IDOC 时，SAP 系统可能会发送某些未发布的段，为其元数据不生成适配器，将发生这种情况。</span><span class="sxs-lookup"><span data-stu-id="34d0e-217">This occurs because when the IDOC is received, the SAP system might have sent some unreleased segments as well, the metadata for which was not generated by the adapter.</span></span>  
  
 <span data-ttu-id="34d0e-218">**解决方法**</span><span class="sxs-lookup"><span data-stu-id="34d0e-218">**Resolution**</span></span>  
  
 <span data-ttu-id="34d0e-219">执行以下任一操作：</span><span class="sxs-lookup"><span data-stu-id="34d0e-219">Do any of the following:</span></span>  
  
-   <span data-ttu-id="34d0e-220">通过应用相应的修补程序未释放的段的 SAP 系统进行升级。</span><span class="sxs-lookup"><span data-stu-id="34d0e-220">Upgrade your SAP system by applying appropriate patches for the unreleased segments.</span></span>  
  
-   <span data-ttu-id="34d0e-221">使用**SendIdoc**或**ReceiveIdoc**操作发送和接收到的 Idoc 分别。</span><span class="sxs-lookup"><span data-stu-id="34d0e-221">Use **SendIdoc** or **ReceiveIdoc** operations to send and receive IDOCs respectively.</span></span> <span data-ttu-id="34d0e-222">有关这些操作的详细信息，请参阅[SAP 中的 Idoc 上的操作](../../adapters-and-accelerators/adapter-sap/operations-on-idocs-in-sap.md)。</span><span class="sxs-lookup"><span data-stu-id="34d0e-222">For more information about these operations, see [Operations on IDOCs in SAP](../../adapters-and-accelerators/adapter-sap/operations-on-idocs-in-sap.md).</span></span>  
  
##  <a name="BKMK_SAPIDOCSend"></a><span data-ttu-id="34d0e-223">将平面文件 Idoc 发送到 SAP 使用 SAP FilePort 接收到的错误</span><span class="sxs-lookup"><span data-stu-id="34d0e-223">Error sending flat-file IDOCs to SAP that were received using the SAP FilePort</span></span>  
 <span data-ttu-id="34d0e-224">**问题**</span><span class="sxs-lookup"><span data-stu-id="34d0e-224">**Problem**</span></span>  
  
 <span data-ttu-id="34d0e-225">如果你尝试发送 (使用**发送**操作) 到 SAP 系统使用 SAP FilePort 生成平面文件 IDOC，BizTalk 业务流程中的平面文件分析器将失败，将 flatf 文件转换为 XML 格式，从而失败IDOD**发送**操作。</span><span class="sxs-lookup"><span data-stu-id="34d0e-225">If you try to send (using **Send** operation) a flat-file IDOC to an SAP system that was generated using an SAP FilePort, the flat-file parser in the BizTalk orchestration fails to convert the flatf-file to an XML format, thereby failing the IDOD **Send** operation.</span></span>  
  
 <span data-ttu-id="34d0e-226">**可能的原因**</span><span class="sxs-lookup"><span data-stu-id="34d0e-226">**Cause**</span></span>  
  
 <span data-ttu-id="34d0e-227">当 SAP 系统生成使用 FilePort 的 IDOC 时，修剪关闭段的末尾的所有空格。</span><span class="sxs-lookup"><span data-stu-id="34d0e-227">When the SAP system generates an IDOC using a FilePort, it trims off all the empty spaces at the end of a segment.</span></span> <span data-ttu-id="34d0e-228">但是，平面文件分析器要求存在才可成功将平面文件转换为 XML 的段中的最后一个字段的数据。</span><span class="sxs-lookup"><span data-stu-id="34d0e-228">However, the flat-file parser expects the data of the last field in the segment to be present to successfully convert the flat-file to XML.</span></span> <span data-ttu-id="34d0e-229">因为空空间不存在的段中，平面文件分析器将无法分析为 XML 的平面文件。</span><span class="sxs-lookup"><span data-stu-id="34d0e-229">Because the empty spaces are not present in the segment, the flat-file parser fails to parse the flat-file to XML.</span></span>  
  
 <span data-ttu-id="34d0e-230">**解决方法**</span><span class="sxs-lookup"><span data-stu-id="34d0e-230">**Resolution**</span></span>  
  
 <span data-ttu-id="34d0e-231">对于使用 SAP FilePort 生成此类平面文件 Idoc，使用**SendIdoc**操作相反。</span><span class="sxs-lookup"><span data-stu-id="34d0e-231">For such flat-file IDOCs generated using the SAP FilePort, use the **SendIdoc** operation instead.</span></span> <span data-ttu-id="34d0e-232">有关此操作的详细信息，请参阅[SAP 中的 Idoc 上的操作](../../adapters-and-accelerators/adapter-sap/operations-on-idocs-in-sap.md)。</span><span class="sxs-lookup"><span data-stu-id="34d0e-232">For more information about this operation, see [Operations on IDOCs in SAP](../../adapters-and-accelerators/adapter-sap/operations-on-idocs-in-sap.md).</span></span>  
  
##  <a name="BKMK_SAPRecIDOCCompat"></a><span data-ttu-id="34d0e-233">错误从 SAP 接收到的 Idoc，如果 EnableBizTalkCompatibilityMode 属性设置为 true</span><span class="sxs-lookup"><span data-stu-id="34d0e-233">Error receiving IDOCs from SAP if EnableBizTalkCompatibilityMode property is set to true</span></span>  
 <span data-ttu-id="34d0e-234">**问题**</span><span class="sxs-lookup"><span data-stu-id="34d0e-234">**Problem**</span></span>  
  
 <span data-ttu-id="34d0e-235">在接收与 IDOC 时遇到以下异常，则**EnableBizTalkCompatibilityMode**绑定属性设置为 true:</span><span class="sxs-lookup"><span data-stu-id="34d0e-235">The following exception is encountered while receiving an IDOC with the **EnableBizTalkCompatibilityMode** binding property set to true:</span></span>  
  
```  
System.Exception: Loading property information list by namespace failed or property not found in the list. Verify that the schema is deployed properly.  
```  
  
 <span data-ttu-id="34d0e-236">**可能的原因**</span><span class="sxs-lookup"><span data-stu-id="34d0e-236">**Cause**</span></span>  
  
 <span data-ttu-id="34d0e-237">如果绑定属性**EnableBizTalkCompatibilityMode**设置为**true**，必须添加 BizTalk 属性架构 DLL 为[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]作为 BizTalk 应用程序中，即，资源在其中部署你的项目的应用程序。</span><span class="sxs-lookup"><span data-stu-id="34d0e-237">If the binding property **EnableBizTalkCompatibilityMode** is set to **true**, you must add the BizTalk property schema DLL for the [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] as a resource in your BizTalk application, that is, the application in which your project is deployed.</span></span>  
  
 <span data-ttu-id="34d0e-238">**解决方法**</span><span class="sxs-lookup"><span data-stu-id="34d0e-238">**Resolution**</span></span>  
  
 <span data-ttu-id="34d0e-239">名称的 BizTalk 属性架构[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]是*Microsoft.Adapters.SAP.BiztalkPropertySchema.dll*。</span><span class="sxs-lookup"><span data-stu-id="34d0e-239">The name for the BizTalk property schema for the [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] is *Microsoft.Adapters.SAP.BiztalkPropertySchema.dll*.</span></span> <span data-ttu-id="34d0e-240">这由安装[!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)]设置下\<安装驱动器\>: \程序 Files\Microsoft BizTalk 适配器 Pack\bin。</span><span class="sxs-lookup"><span data-stu-id="34d0e-240">This is installed by the [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)] setup under \<installation drive\>:\ Program Files\Microsoft BizTalk Adapter Pack\bin.</span></span> <span data-ttu-id="34d0e-241">执行以下任务来为你的 BizTalk 应用程序中的资源添加此程序集。</span><span class="sxs-lookup"><span data-stu-id="34d0e-241">Perform the following tasks to add this assembly as a resource in your BizTalk application.</span></span>  
  
#### <a name="add-an-assembly-as-a-resource-in-biztalk-application"></a><span data-ttu-id="34d0e-242">将程序集添加为 BizTalk 应用程序中的资源</span><span class="sxs-lookup"><span data-stu-id="34d0e-242">Add an assembly as a resource in BizTalk application</span></span>  
  
1.  <span data-ttu-id="34d0e-243">启动[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理控制台。</span><span class="sxs-lookup"><span data-stu-id="34d0e-243">Start the [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] Administration console.</span></span>  
  
2.  <span data-ttu-id="34d0e-244">在控制台树中，展开**BizTalk 组**，展开**应用程序**，然后你想要添加 BizTalk 程序集与应用程序。</span><span class="sxs-lookup"><span data-stu-id="34d0e-244">In the console tree, expand **BizTalk Group**, expand **Applications**, and then the application to which you want to add a BizTalk assembly.</span></span>  
  
3.  <span data-ttu-id="34d0e-245">展开**应用程序**和你想要添加 BizTalk 程序集的应用程序。</span><span class="sxs-lookup"><span data-stu-id="34d0e-245">Expand **Applications** and the application to which you want to add a BizTalk assembly.</span></span>  
  
4.  <span data-ttu-id="34d0e-246">右键单击**资源**，指向**添加**，然后单击**BizTalk 程序集**。</span><span class="sxs-lookup"><span data-stu-id="34d0e-246">Right-click **Resources**, point to **Add**, and then click **BizTalk Assemblies**.</span></span>  
  
5.  <span data-ttu-id="34d0e-247">单击**添加**，导航到包含 BizTalk 程序集文件的文件夹，选择 BizTalk 程序集文件，，然后单击**打开**。</span><span class="sxs-lookup"><span data-stu-id="34d0e-247">Click **Add**, navigate to the folder containing the BizTalk assembly file, select the BizTalk assembly file, and then click **Open**.</span></span>  
  
6.  <span data-ttu-id="34d0e-248">在**选项**，指定安装到 GAC 中，BizTalk 程序集的选项，然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="34d0e-248">In **Options**, specify the options for installing the BizTalk assembly to the GAC, and then click **OK**.</span></span>  
  
##  <a name="BKMK_SAPIDOCValidate"></a><span data-ttu-id="34d0e-249">中从某个 SAP 系统接收到的 Idoc 时验证错误</span><span class="sxs-lookup"><span data-stu-id="34d0e-249">Error in validation while receiving IDOCs from an SAP system</span></span>  
 <span data-ttu-id="34d0e-250">**问题**</span><span class="sxs-lookup"><span data-stu-id="34d0e-250">**Problem**</span></span>  
  
 <span data-ttu-id="34d0e-251">从 SAP 系统收到的 IDOC 未通过验证并显示如下错误：</span><span class="sxs-lookup"><span data-stu-id="34d0e-251">An IDOC received from an SAP system fails validation with an error similar to the following:</span></span>  
  
```  
There was a failure executing the receive pipeline: "Microsoft.BizTalk.DefaultPipelines.XMLReceive, Microsoft.BizTalk.DefaultPipelines, Version=3.0.1.0, Culture=neutral, PublicKeyToken=<token>"  
Source: "Pipeline " Receive Port: "ReceiveIdoc" URI: "<connection uri>"  
Reason: The document failed to validate because of the following error:  
"The 'http://Microsoft.LobServices.Sap/2007/03/Types/Idoc/3/CREMAS03//620:TAXBS' element has an invalid value according to its data type."  
```  
  
 <span data-ttu-id="34d0e-252">**可能的原因**</span><span class="sxs-lookup"><span data-stu-id="34d0e-252">**Cause**</span></span>  
  
 <span data-ttu-id="34d0e-253">用于接收 IDOC 生成的元数据包含可为特定的列作为接收操作的一部分接收的允许值。</span><span class="sxs-lookup"><span data-stu-id="34d0e-253">The metadata generated for receiving an IDOC contains the permissible values that can be received for a particular column as part of the receive operation.</span></span> <span data-ttu-id="34d0e-254">这些值公开为生成的元数据中的枚举。</span><span class="sxs-lookup"><span data-stu-id="34d0e-254">These values are exposed as enumeration in the generated metadata.</span></span> <span data-ttu-id="34d0e-255">但是，实际收到的 IDOC 时，收到的值可能不同于枚举值。</span><span class="sxs-lookup"><span data-stu-id="34d0e-255">However, when the IDOC is actually received, the value received could be different from the enumerated values.</span></span> <span data-ttu-id="34d0e-256">因此验证值时，接收操作将失败。</span><span class="sxs-lookup"><span data-stu-id="34d0e-256">Hence the receive operation fails while validating the values.</span></span> <span data-ttu-id="34d0e-257">例如，在上面的错误消息验证失败，TAXBS 列。</span><span class="sxs-lookup"><span data-stu-id="34d0e-257">For example, in the above error message validation fails for the TAXBS column.</span></span>  
  
 <span data-ttu-id="34d0e-258">**解决方法**</span><span class="sxs-lookup"><span data-stu-id="34d0e-258">**Resolution**</span></span>  
  
 <span data-ttu-id="34d0e-259">你必须手动编辑 （对于 BizTalk 项目） 的架构或客户端代理中的枚举 （对于.NET 项目使用 WCF 服务模型） 以包括从 SAP 系统收到的值。</span><span class="sxs-lookup"><span data-stu-id="34d0e-259">You must manually edit the enumeration in schema (for BizTalk projects) or the client proxy (for .NET projects using WCF service model) to include the value received from the SAP system.</span></span>  
  
##  <a name="BKMK_SAPFFIDOC"></a><span data-ttu-id="34d0e-260">平面文件 Idoc 之前和之后将转换为 XML，不相同</span><span class="sxs-lookup"><span data-stu-id="34d0e-260">Flat-file IDOCs, before and after converting to XML, are not identical</span></span>  
 <span data-ttu-id="34d0e-261">**问题**</span><span class="sxs-lookup"><span data-stu-id="34d0e-261">**Problem**</span></span>  
  
 <span data-ttu-id="34d0e-262">如果你使用平面文件分析器来将平面文件 IDOC 转换为 XML 使用架构，然后将 XML 转换回通过管道使用架构的平面文件 IDOC，两个平面文件 Idoc 不相同。</span><span class="sxs-lookup"><span data-stu-id="34d0e-262">If you use a flat file parser to convert a flat-file IDOC to an XML using the schema, and then convert the XML back to a flat-file IDOC through a pipeline using the schema, the two flat-file IDOCs are not identical.</span></span>  
  
 <span data-ttu-id="34d0e-263">**可能的原因**</span><span class="sxs-lookup"><span data-stu-id="34d0e-263">**Cause**</span></span>  
  
 <span data-ttu-id="34d0e-264">当从平面文件 IDOC 生成 XML，平面文件分析器不会生成具有空白值的 XML 节点。</span><span class="sxs-lookup"><span data-stu-id="34d0e-264">When generating the XML from a flat-file IDOC, the flat file parser does not generate the XML nodes with blank values.</span></span> <span data-ttu-id="34d0e-265">当此 XML 转换回平面文件时，从 XML 缺少的节点不会反映在平面文件 IDOC。</span><span class="sxs-lookup"><span data-stu-id="34d0e-265">When this XML is converted back to a flat-file, the nodes missing from the XML are not reflected in the flat-file IDOC.</span></span> <span data-ttu-id="34d0e-266">因此平面文件 Idoc 不相同。</span><span class="sxs-lookup"><span data-stu-id="34d0e-266">Hence the flat-file IDOCs are not identical.</span></span>  
  
 <span data-ttu-id="34d0e-267">**解决方法**</span><span class="sxs-lookup"><span data-stu-id="34d0e-267">**Resolution**</span></span>  
  
 <span data-ttu-id="34d0e-268">用于将平面文件转换为 XML，反之亦然，在"发送"接收"节点定义中，架构中执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="34d0e-268">In the schema used to convert the flat-file to XML and vice-versa, within the "Send" or "Receive" node definition, do the following:</span></span>  
  
1.  <span data-ttu-id="34d0e-269">设置**suppress_empty_nodes**属性**false**并设置**generate_empty_nodes**属性**true**。</span><span class="sxs-lookup"><span data-stu-id="34d0e-269">Set the **suppress_empty_nodes** property to **false** and set the **generate_empty_nodes** property to **true**.</span></span> <span data-ttu-id="34d0e-270">默认情况下， **suppress_empty_nodes**属性设置为**true**和**generate_empty_nodes**属性设置为**false**，和因此所有空节点不会反映在 XML 中。</span><span class="sxs-lookup"><span data-stu-id="34d0e-270">By default, the **suppress_empty_nodes** property is set to **true** and the **generate_empty_nodes** property is set to **false**, and hence all empty nodes are not reflected in the XML.</span></span>  
  
2.  <span data-ttu-id="34d0e-271">平面文件可能包含额外回车符末尾。</span><span class="sxs-lookup"><span data-stu-id="34d0e-271">The flat-file may contain an extra carriage return at the end.</span></span> <span data-ttu-id="34d0e-272">你可以设置**suppress_trailing_delimiters**属性**是**若要避免此额外的回车。</span><span class="sxs-lookup"><span data-stu-id="34d0e-272">You can set the **suppress_trailing_delimiters** property to **Yes** to avoid this extra carriage return.</span></span> <span data-ttu-id="34d0e-273">此属性还公开为**禁止显示尾随分隔符**属性，如果你打开中的架构[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="34d0e-273">This property is also exposed as the **Suppress Trailing Delimiters** property if you open the schema in [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)].</span></span>  
  
##  <a name="BKMK_SAPAction"></a><span data-ttu-id="34d0e-274">不正确使用使用绑定文件创建的物理端口的操作错误</span><span class="sxs-lookup"><span data-stu-id="34d0e-274">Incorrect Action error using a physical port creating with a binding file</span></span>  
 <span data-ttu-id="34d0e-275">**问题**</span><span class="sxs-lookup"><span data-stu-id="34d0e-275">**Problem**</span></span>  
  
 <span data-ttu-id="34d0e-276">在使用后[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]若要生成对 SAP 系统的特定操作的架构外, 接程序还会创建端口绑定文件。</span><span class="sxs-lookup"><span data-stu-id="34d0e-276">After you use the [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)] to generate schema for a specific operation on the SAP system, the add-in also creates a port binding file.</span></span> <span data-ttu-id="34d0e-277">可以导入此文件使用绑定的[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]BizTalk Server 中创建的物理端口的管理控制台。</span><span class="sxs-lookup"><span data-stu-id="34d0e-277">You can import this binding file using the [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] Administration console to create physical ports in BizTalk Server.</span></span> <span data-ttu-id="34d0e-278">但是，当消息发送到 SAP 系统使用此类端口时，该适配器将无法了解在端口上指定的操作，并提供了类似于以下错误：</span><span class="sxs-lookup"><span data-stu-id="34d0e-278">However, when you send messages to the SAP system using such ports, the adapter fails to understand the action specified on the port and gives an error similar to the following:</span></span>  
  
```  
Microsoft.ServiceModel.Channels.Common.UnsupportedOperationException: Incorrect Action   
<BtsActionMapping xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xmlns:xsd="http://www.w3.org/2001/XMLSchema">  
  <Operation Name="<op_name>" Action="<action>" />  
</BtsActionMapping>. Correct the specified Action, or refer to the documentation on the allowed formats for the Actions.  
```  
  
 <span data-ttu-id="34d0e-279">**可能的原因**</span><span class="sxs-lookup"><span data-stu-id="34d0e-279">**Cause**</span></span>  
  
 <span data-ttu-id="34d0e-280">在创建逻辑端口 BizTalk 业务流程中时，指定这些端口上的操作的某些名称，或只需使用如 Operation_1、 Operation_2 等的默认名称。但是，在生成的绑定文件[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]，操作名称是为其生成元数据操作的名称相同。</span><span class="sxs-lookup"><span data-stu-id="34d0e-280">When you create logical ports in a BizTalk orchestration, you specify certain names for the operations on those ports or you just use the default names like Operation_1, Operation_2, etc. However, in the binding file generated by the [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)], the operation name is same as the name of the operation for which you generate metadata.</span></span> <span data-ttu-id="34d0e-281">例如，如果您为 RFC_CUSTOMER_GET 生成元数据，操作将设置为以下：</span><span class="sxs-lookup"><span data-stu-id="34d0e-281">For example, if you generate metadata for RFC_CUSTOMER_GET, the action will be set to the following:</span></span>  
  
```  
<Operation Name="RFC_CUSTOMER_GET" Action="http://Microsoft.LobServices.Sap/2007/03/Rfc/RFC_CUSTOMER_GET" />  
```  
  
 <span data-ttu-id="34d0e-282">当你导入的绑定文件时，物理端口设置相同的操作。</span><span class="sxs-lookup"><span data-stu-id="34d0e-282">When you import the binding file, the same action is set on physical port.</span></span> <span data-ttu-id="34d0e-283">因此，逻辑端口 （Operation_1、 Operation_2 等） 上的操作名称与上的物理端口，从而导致错误的操作中指定的操作名称不匹配。</span><span class="sxs-lookup"><span data-stu-id="34d0e-283">So, the operation names on the logical port (Operation_1, Operation_2, etc.) do not match the operation names specified in the action on the physical port, resulting in an error.</span></span>  
  
 <span data-ttu-id="34d0e-284">**解决方法**</span><span class="sxs-lookup"><span data-stu-id="34d0e-284">**Resolution**</span></span>  
  
 <span data-ttu-id="34d0e-285">请确保逻辑端口中的操作名称指定为中的物理端口的操作的一部分的操作名称相同。</span><span class="sxs-lookup"><span data-stu-id="34d0e-285">Make sure the operation name in the logical port is the same as the operation name specified as part of the action in the physical port.</span></span> <span data-ttu-id="34d0e-286">执行以下操作之一：</span><span class="sxs-lookup"><span data-stu-id="34d0e-286">Do one of the following:</span></span>  
  
-   <span data-ttu-id="34d0e-287">对为其生成元数据，例如 RFC_CUSTOMER_GET 操作从 Operation_1 等更改 BizTalk 业务流程中的逻辑端口中的操作名称。</span><span class="sxs-lookup"><span data-stu-id="34d0e-287">Change the operation name in the logical port in BizTalk orchestration from Operation_1, etc. to the operation for which you generate metadata, for example RFC_CUSTOMER_GET.</span></span>  
  
-   <span data-ttu-id="34d0e-288">将中的物理端口上的操作的操作名称更改为中的逻辑端口的操作名称。</span><span class="sxs-lookup"><span data-stu-id="34d0e-288">Change the operation name in the action on the physical port to the operation name in the logical port.</span></span> <span data-ttu-id="34d0e-289">例如，你无法更改中类似于下面的物理端口的操作：</span><span class="sxs-lookup"><span data-stu-id="34d0e-289">For example, you could change the action in the physical port to resemble the following:</span></span>  
  
    ```  
    <Operation Name="Operation_1" Action="http://Microsoft.LobServices.Sap/2007/03/Rfc/RFC_CUSTOMER_GET" />  
    ```  
  
##  <a name="BKMK_SAPTableParams"></a><span data-ttu-id="34d0e-290">响应消息上 SAP 运行一个操作并不包含任何表参数</span><span class="sxs-lookup"><span data-stu-id="34d0e-290">The response message for an operation ran on SAP does not contain any table parameters</span></span>  
 <span data-ttu-id="34d0e-291">**可能的原因**</span><span class="sxs-lookup"><span data-stu-id="34d0e-291">**Cause**</span></span>  
  
 <span data-ttu-id="34d0e-292">如果你使用[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]执行对 SAP 系统的操作中返回大量的表，并且每个表具有大量的记录，将搜索大型数据集从 SAP 系统作为响应消息的一部分返回。</span><span class="sxs-lookup"><span data-stu-id="34d0e-292">If you use the [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] to execute an operation on the SAP system that returns a large number of tables, and each table has a large number of records, that will amount to a large dataset being returned as part of the response message from the SAP system.</span></span> <span data-ttu-id="34d0e-293">因此，默认情况下，[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]不返回任何表参数作为响应消息的一部分。</span><span class="sxs-lookup"><span data-stu-id="34d0e-293">So, by default, the [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] does not return any table parameters as part of the response message.</span></span>  
  
 <span data-ttu-id="34d0e-294">**解决方法**</span><span class="sxs-lookup"><span data-stu-id="34d0e-294">**Resolution**</span></span>  
  
 <span data-ttu-id="34d0e-295">你可以请求所需的表[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]作为响应一部分返回。</span><span class="sxs-lookup"><span data-stu-id="34d0e-295">You can request the tables that you want [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] to return as part of the response.</span></span> <span data-ttu-id="34d0e-296">你可以做到这一点作为请求消息发送到 SAP 系统的一部分来提供一个空表参数。</span><span class="sxs-lookup"><span data-stu-id="34d0e-296">You can do so by providing an empty table parameter as part of the request message that you send to the SAP system.</span></span> <span data-ttu-id="34d0e-297">例如， `<table_parameter_name />`。</span><span class="sxs-lookup"><span data-stu-id="34d0e-297">For example, `<table_parameter_name />`.</span></span>  
  
##  <a name="BKMK_SAPIncorrectCreds"></a><span data-ttu-id="34d0e-298">适配器客户端不接收来自 SAP 响应</span><span class="sxs-lookup"><span data-stu-id="34d0e-298">Adapter Clients do not receive the response from SAP</span></span>
 <span data-ttu-id="34d0e-299">**问题**</span><span class="sxs-lookup"><span data-stu-id="34d0e-299">**Problem**</span></span>  
  
 <span data-ttu-id="34d0e-300">使用具有适配器时[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]，如果在 WCF 自定义的凭据将发送端口不正确，不会处理请求消息。</span><span class="sxs-lookup"><span data-stu-id="34d0e-300">When using the adapters with [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)], if the credentials on the WCF-custom send port are incorrect, the request messages are not processed.</span></span> <span data-ttu-id="34d0e-301">指定正确的凭据后，将消息发送到 SAP 系统，并收到的响应。</span><span class="sxs-lookup"><span data-stu-id="34d0e-301">After you specify the correct credentials, the message is sent to the SAP system and a response is received.</span></span> <span data-ttu-id="34d0e-302">但是，响应消息不可用到的输出端口。</span><span class="sxs-lookup"><span data-stu-id="34d0e-302">However, the response message is not available to the out port.</span></span>  
  
 <span data-ttu-id="34d0e-303">**解决方法**</span><span class="sxs-lookup"><span data-stu-id="34d0e-303">**Resolution**</span></span>  
  
 <span data-ttu-id="34d0e-304">重新启动 BizTalk 主机实例。</span><span class="sxs-lookup"><span data-stu-id="34d0e-304">Restart the BizTalk host instance.</span></span>  
  
##  <a name="BKMK_SAPInboundConn"></a><span data-ttu-id="34d0e-305">接收来自 SAP 服务器的入站的消息的连接问题</span><span class="sxs-lookup"><span data-stu-id="34d0e-305">Connectivity issues receiving an inbound message from the SAP server</span></span>  
 <span data-ttu-id="34d0e-306">**问题**</span><span class="sxs-lookup"><span data-stu-id="34d0e-306">**Problem**</span></span>  
  
 <span data-ttu-id="34d0e-307">你将收到以下错误仅在接收来自使用 WCF 自定义的 SAP 服务器的入站的消息接收端口[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="34d0e-307">You get the following error only while receiving an inbound message from the SAP server using a WCF-Custom receive port for the [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)].</span></span>  
  
```  
The Messaging Engine failed to add a receive location "<location_name>" with URL "<connection URI>" to the adapter "WCF-Custom".  
Reason: "Microsoft.Adapters.SAP.RFCException: Details: ErrorCode=RFC_OK. ErrorGroup=RFC_ERROR_COMMUNICATION. SapErrorMessage=Connect to SAP gateway failed  
Connect_PM  TPNAME=<name>, GWHOST=<host>, GWSERV=<server>  
```  
  
 <span data-ttu-id="34d0e-308">但是，你将能够成功地将消息发送到 SAP 系统使用 WCF 自定义发送端口。</span><span class="sxs-lookup"><span data-stu-id="34d0e-308">However, you are successfully able to send messages to the SAP system using a WCF-Custom send port.</span></span>  
  
 <span data-ttu-id="34d0e-309">**解决方法**</span><span class="sxs-lookup"><span data-stu-id="34d0e-309">**Resolution**</span></span>  
  
 <span data-ttu-id="34d0e-310">对于你运行适配器客户端，并且尝试再次接收入站的消息的同一计算机上安装 SAP GUI。</span><span class="sxs-lookup"><span data-stu-id="34d0e-310">Install the SAP GUI on the same computer where you are running the adapter client and try receiving the inbound message again.</span></span> <span data-ttu-id="34d0e-311">有关如何安装 SAP GUI 的详细信息，请参阅 SAP 文档。</span><span class="sxs-lookup"><span data-stu-id="34d0e-311">For more information about how to install the SAP GUI, refer to SAP documentation.</span></span>  
  
##  <a name="BKMK_SAPRootNode"></a><span data-ttu-id="34d0e-312">与 RootNode TypeName BizTalk 项目中的错误</span><span class="sxs-lookup"><span data-stu-id="34d0e-312">Error with RootNode TypeName in BizTalk Projects</span></span>  
 <span data-ttu-id="34d0e-313">**问题**</span><span class="sxs-lookup"><span data-stu-id="34d0e-313">**Problem**</span></span>  
  
 <span data-ttu-id="34d0e-314">在 BizTalk 项目中[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]，如果从架构生成[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]包含无效字符或保留的字**RootNode TypeName**属性，编译项目时将出现以下错误:</span><span class="sxs-lookup"><span data-stu-id="34d0e-314">In a BizTalk project in [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)], if the schemas generated from the [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)] contains invalid characters or reserved words for the **RootNode TypeName** property, the following error will occur while compiling the project:</span></span>  
  
```  
Node <node reference> - Specify a valid .NET type name for this root node.  
The current .NET type name of this root node is invalid (it is a reserved BizTalk Keyword or is an invalid C# identifier).  
```  
  
 <span data-ttu-id="34d0e-315">**解决方法**</span><span class="sxs-lookup"><span data-stu-id="34d0e-315">**Resolution**</span></span>  
  
1.  <span data-ttu-id="34d0e-316">右键单击该错误并选择中引用的 rood 节点**属性**。</span><span class="sxs-lookup"><span data-stu-id="34d0e-316">Right-click the rood node referenced in the error and select **Properties**.</span></span>  
  
2.  <span data-ttu-id="34d0e-317">有关**RootNode TypeName**属性，删除任何非法字符或保留字，例如，圆点 （.）。</span><span class="sxs-lookup"><span data-stu-id="34d0e-317">For the **RootNode TypeName** property, remove any illegal characters or reserved words, for example, dot (.).</span></span>  
  
##  <a name="BKMK_SAPVS2008"></a><span data-ttu-id="34d0e-318">使用 Visual Studio 中的适配器时出现的无效的绑定警告</span><span class="sxs-lookup"><span data-stu-id="34d0e-318">Invalid binding warning when using the adapter in Visual Studio</span></span>  
 <span data-ttu-id="34d0e-319">**问题**</span><span class="sxs-lookup"><span data-stu-id="34d0e-319">**Problem**</span></span>  
  
 <span data-ttu-id="34d0e-320">当你使用该适配器在 Visual Studio 中创建应用程序并打开生成的适配器的配置文件 (app.config) 时，你将看到类似于以下警告：</span><span class="sxs-lookup"><span data-stu-id="34d0e-320">When you use the adapter to create an application in Visual Studio and you open the configuration file (app.config) generated by the adapter, you see a warning similar to the following:</span></span>  
  
```  
The element 'bindings' has invalid child element 'sapBinding'. List of possible elements expected: 'basicHttpBinding, customBinding, ...  
```  
  
 <span data-ttu-id="34d0e-321">**可能的原因**</span><span class="sxs-lookup"><span data-stu-id="34d0e-321">**Cause**</span></span>  
  
 <span data-ttu-id="34d0e-322">由于会出现此警告[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]绑定， `sapBinding`，不标准绑定随[!INCLUDE[firstref_btsWinCommFoundation](../../includes/firstref-btswincommfoundation-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="34d0e-322">This warning appears because the [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] binding, `sapBinding`, is not a standard binding shipped with the [!INCLUDE[firstref_btsWinCommFoundation](../../includes/firstref-btswincommfoundation-md.md)].</span></span>  
  
 <span data-ttu-id="34d0e-323">**解决方法**</span><span class="sxs-lookup"><span data-stu-id="34d0e-323">**Resolution**</span></span>  
  
 <span data-ttu-id="34d0e-324">可以安全地忽略此警告。</span><span class="sxs-lookup"><span data-stu-id="34d0e-324">You can safely ignore this warning.</span></span>  
  
##  <a name="BKMK_SAPSimilarSchema"></a><span data-ttu-id="34d0e-325">BizTalk Server 中的 XLANG 异常</span><span class="sxs-lookup"><span data-stu-id="34d0e-325">XLANG exception in BizTalk Server</span></span>
 <span data-ttu-id="34d0e-326">**问题**</span><span class="sxs-lookup"><span data-stu-id="34d0e-326">**Problem**</span></span>  
  
 <span data-ttu-id="34d0e-327">BizTalk Server 引发 XLANG 异常或异常指出应用程序找不到文档规范，因为多个架构匹配的消息类型。</span><span class="sxs-lookup"><span data-stu-id="34d0e-327">BizTalk Server throws an XLANG exception or an exception stating that the application cannot locate the document specification because multiple schemas matched the message type.</span></span>  
  
 <span data-ttu-id="34d0e-328">**可能的原因**</span><span class="sxs-lookup"><span data-stu-id="34d0e-328">**Cause**</span></span>  
  
 <span data-ttu-id="34d0e-329">由于以下任一发生这种情况：</span><span class="sxs-lookup"><span data-stu-id="34d0e-329">This happens because of either of the following:</span></span>  
  
-   <span data-ttu-id="34d0e-330">在你生成多个架构的泛型的操作 （如 SendIdoc 和 ReceiveIdoc） 在 BizTalk Server 项目中，将其部署到 BizTalk Server 应用程序，，然后运行应用程序执行 SAP 系统上的相应操作。</span><span class="sxs-lookup"><span data-stu-id="34d0e-330">You have generated more than one schema of a generic operation (such as SendIdoc and ReceiveIdoc) in a BizTalk Server project, deployed it to a BizTalk Server application, and then ran the application to perform respective operations on an SAP system.</span></span> <span data-ttu-id="34d0e-331">由于架构是公用的冲突之间没有部署 BizTalk Server 应用程序中的架构。</span><span class="sxs-lookup"><span data-stu-id="34d0e-331">Because the schemas are common, there is a conflict between the schemas that are deployed in the BizTalk Server application.</span></span>  
  
-   <span data-ttu-id="34d0e-332">如果多个项目，已经为每个 BizTalk Server 项目生成泛型操作架构，请部署到单独上相同的 BizTalk Server 应用程序托管，，然后运行应用程序或应用程序即可执行相应的每个项目SAP 系统上的操作。</span><span class="sxs-lookup"><span data-stu-id="34d0e-332">In case of multiple projects, you have generated a generic operation schema for each of the BizTalk Server projects, deployed each project to a separate BizTalk Server application on the same host, and then ran an application or applications to perform respective operations on an SAP system.</span></span> <span data-ttu-id="34d0e-333">因为架构和程序集都可访问 BizTalk Server 中的应用程序，各种 BizTalk Server 应用程序和程序集下部署的常见架构之间存在不冲突。</span><span class="sxs-lookup"><span data-stu-id="34d0e-333">Because the schemas and assemblies are accessible across the applications in BizTalk Server, there is a conflict between the common schemas deployed under various BizTalk Server applications and assemblies.</span></span>  
  
 <span data-ttu-id="34d0e-334">**解决方法**</span><span class="sxs-lookup"><span data-stu-id="34d0e-334">**Resolution**</span></span>  
  
 <span data-ttu-id="34d0e-335">BizTalk Server 应用程序使用单个泛型操作架构文件。</span><span class="sxs-lookup"><span data-stu-id="34d0e-335">Use a single generic operation schema file for a BizTalk Server application.</span></span> <span data-ttu-id="34d0e-336">如果你需要在同一主机上的多个 BizTalk Server 应用程序中使用泛型操作架构，创建包含单个泛型操作架构中的应用程序，然后使用 BizTalk Server 中的所有其他应用程序中的泛型操作架构。</span><span class="sxs-lookup"><span data-stu-id="34d0e-336">If you need to use a generic operation schema in multiple BizTalk Server applications on the same host, create an application containing a single generic operation schema, and then use the generic operation schema from all other applications in BizTalk Server.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="34d0e-337">另请参阅</span><span class="sxs-lookup"><span data-stu-id="34d0e-337">See Also</span></span>  
[<span data-ttu-id="34d0e-338">故障排除 SAP 适配器</span><span class="sxs-lookup"><span data-stu-id="34d0e-338">Troubleshoot the SAP adapter</span></span>](../../adapters-and-accelerators/adapter-sap/troubleshoot-the-sap-adapter.md)