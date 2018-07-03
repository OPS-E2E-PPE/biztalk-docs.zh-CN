---
title: 使用 BizTalk 中的 SAP 适配器进行的操作问题故障排除 |Microsoft Docs
description: 常见错误、 问题和解决方法与 mySAP 适配器在 BizTalk 适配器包 (BAP)
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
ms.openlocfilehash: 1c137b60c9c9a8c354baf39b91349e0836c94b91
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36998270"
---
# <a name="troubleshoot-operational-issues-with-the-sap-adapter"></a><span data-ttu-id="b5d03-103">使用 SAP 适配器进行的操作问题故障排除</span><span class="sxs-lookup"><span data-stu-id="b5d03-103">Troubleshoot Operational Issues with the SAP adapter</span></span>
<span data-ttu-id="b5d03-104">本部分讨论如何使用故障排除技术来解决操作使用时可能遇到的错误[!INCLUDE[adaptersap](../../includes/adaptersap-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="b5d03-104">This section discusses using troubleshooting techniques to resolve operational errors that you might encounter when using [!INCLUDE[adaptersap](../../includes/adaptersap-md.md)].</span></span>  
  
### <a name="enable-tracing"></a><span data-ttu-id="b5d03-105">启用跟踪</span><span class="sxs-lookup"><span data-stu-id="b5d03-105">Enable tracing</span></span>  
 <span data-ttu-id="b5d03-106">有关跟踪中的支持信息[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]，请参阅[诊断跟踪和消息日志记录 SAP 适配器的](../../adapters-and-accelerators/adapter-sap/diagnostic-tracing-and-message-logging-for-the-sap-adapter.md)。</span><span class="sxs-lookup"><span data-stu-id="b5d03-106">For information about tracing support in the [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)], see [Diagnostic Tracing and Message Logging for the SAP adapter](../../adapters-and-accelerators/adapter-sap/diagnostic-tracing-and-message-logging-for-the-sap-adapter.md).</span></span>  
  
##  <a name="client_dll"></a> <span data-ttu-id="b5d03-107">加载绑定时出错</span><span class="sxs-lookup"><span data-stu-id="b5d03-107">Error loading the binding</span></span>  
 <span data-ttu-id="b5d03-108">**问题**</span><span class="sxs-lookup"><span data-stu-id="b5d03-108">**Problem**</span></span>  
  
 <span data-ttu-id="b5d03-109">当您尝试启动[!INCLUDE[addadapterservreflong](../../includes/addadapterservreflong-md.md)]或[!INCLUDE[consumeadapterservlong](../../includes/consumeadapterservlong-md.md)]，GUI 将报告以下错误：</span><span class="sxs-lookup"><span data-stu-id="b5d03-109">When you try to start the [!INCLUDE[addadapterservreflong](../../includes/addadapterservreflong-md.md)]or the [!INCLUDE[consumeadapterservlong](../../includes/consumeadapterservlong-md.md)], the GUI gives the following error:</span></span>  
  
```  
There was an error loading the binding, <binding name>, from your system configuration.  
ConfigurationErrorsException: Exception has been thrown by the target of an invocation.  
```  
  
 <span data-ttu-id="b5d03-110">**原因**</span><span class="sxs-lookup"><span data-stu-id="b5d03-110">**Cause**</span></span>  
  
 <span data-ttu-id="b5d03-111">当您启动[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]或[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]，[!INCLUDE[firstref_btsWinCommFoundation](../../includes/firstref-btswincommfoundation-md.md)]加载所有已安装的适配器的适配器绑定。</span><span class="sxs-lookup"><span data-stu-id="b5d03-111">When you start the [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)] or the [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)], [!INCLUDE[firstref_btsWinCommFoundation](../../includes/firstref-btswincommfoundation-md.md)] loads the adapter bindings for all the installed adapters.</span></span> <span data-ttu-id="b5d03-112">反过来，适配器绑定都依赖于企业应用程序特定的客户端软件。</span><span class="sxs-lookup"><span data-stu-id="b5d03-112">In turn, the adapter bindings are dependent on the specific client software for the enterprise application.</span></span> <span data-ttu-id="b5d03-113">您可能会遇到此问题的一个或两个原因如下：</span><span class="sxs-lookup"><span data-stu-id="b5d03-113">You might face this issue for one or both of the following reasons:</span></span>  
  
- <span data-ttu-id="b5d03-114">在安装该适配器的计算机上未安装所需的 LOB 客户端软件。</span><span class="sxs-lookup"><span data-stu-id="b5d03-114">The required LOB client software is not installed on the computer where you installed the adapter.</span></span>  
  
- <span data-ttu-id="b5d03-115">未将适配器安装中包含的所有适配器的典型或完全安装[!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="b5d03-115">You did a Typical or Complete installation of the adapter, which installs all the adapters contained in the [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)].</span></span> <span data-ttu-id="b5d03-116">但是，可能只有一个企业应用程序安装 LOB 客户端库。</span><span class="sxs-lookup"><span data-stu-id="b5d03-116">However, the LOB client libraries might be installed for only one enterprise application.</span></span> <span data-ttu-id="b5d03-117">因此，在 GUI 无法加载其他适配器的绑定。</span><span class="sxs-lookup"><span data-stu-id="b5d03-117">As a result, the GUI fails to load the bindings for the other adapters.</span></span>  
  
  <span data-ttu-id="b5d03-118">**解决方法**</span><span class="sxs-lookup"><span data-stu-id="b5d03-118">**Resolution**</span></span>  
  
- <span data-ttu-id="b5d03-119">请确保执行要安装仅需要的适配器的适配器的自定义安装。</span><span class="sxs-lookup"><span data-stu-id="b5d03-119">Make sure you do a Custom installation of the adapters to install only the adapter you need.</span></span>  
  
- <span data-ttu-id="b5d03-120">请确保你安装的计算机上安装了所需的 LOB 客户端版本[!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="b5d03-120">Make sure the required LOB client versions are installed on the computer where you installed the [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)].</span></span> <span data-ttu-id="b5d03-121">[支持 LOB 系统](https://social.technet.microsoft.com/wiki/contents/articles/17631.biztalk-server-supported-line-of-business-lob-and-enterprise-systems.aspx)列出了受支持的版本。</span><span class="sxs-lookup"><span data-stu-id="b5d03-121">[Supported LOB systems](https://social.technet.microsoft.com/wiki/contents/articles/17631.biztalk-server-supported-line-of-business-lob-and-enterprise-systems.aspx) lists the supported versions.</span></span> <span data-ttu-id="b5d03-122">[!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)]还要求某些 Dll，以便与 SAP 系统进行交互。</span><span class="sxs-lookup"><span data-stu-id="b5d03-122">The [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)] also requires certain DLLs to interface with the SAP system.</span></span> <span data-ttu-id="b5d03-123">有关适配器所必需的 Dll 的详细信息，请参阅[适用于 SAP 数据提供程序安装自定义 Rfc](../../adapters-and-accelerators/adapter-sap/install-custom-rfcs-for-the-data-provider-for-sap.md)。</span><span class="sxs-lookup"><span data-stu-id="b5d03-123">For more information about the DLLs required by the adapter, see [Install Custom RFCs for the Data Provider for SAP](../../adapters-and-accelerators/adapter-sap/install-custom-rfcs-for-the-data-provider-for-sap.md).</span></span>
  
##  <a name="BKMK_SAPDisplay"></a> <span data-ttu-id="b5d03-124">SAP 适配器缺少 BizTalk 管理控制台中</span><span class="sxs-lookup"><span data-stu-id="b5d03-124">The SAP adapter is missing in BizTalk Administration console</span></span>  
 <span data-ttu-id="b5d03-125">**问题**</span><span class="sxs-lookup"><span data-stu-id="b5d03-125">**Problem**</span></span>  
  
<span data-ttu-id="b5d03-126">[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]附带[!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)]未显示在 BizTalk Server 管理控制台中的适配器列表中。</span><span class="sxs-lookup"><span data-stu-id="b5d03-126">The [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] included with [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)] does not show up in the list of adapters in the BizTalk Server Administration console.</span></span>  
  
 <span data-ttu-id="b5d03-127">**原因**</span><span class="sxs-lookup"><span data-stu-id="b5d03-127">**Cause**</span></span>  
  
 <span data-ttu-id="b5d03-128">[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]是 WCF 自定义绑定。</span><span class="sxs-lookup"><span data-stu-id="b5d03-128">The [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] is a WCF custom binding.</span></span> <span data-ttu-id="b5d03-129">因此，尽管[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理控制台中显示[!INCLUDE[wcfadapter_short](../../includes/wcfadapter-short-md.md)]，它不会显示 WCF 自定义绑定，因此，不会显示基于 WCF 的[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="b5d03-129">So, although the [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] Administration console displays the [!INCLUDE[wcfadapter_short](../../includes/wcfadapter-short-md.md)], it does not display the WCF custom bindings and hence, does not display the WCF-based [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)].</span></span>  
  
 <span data-ttu-id="b5d03-130">**解决方法**</span><span class="sxs-lookup"><span data-stu-id="b5d03-130">**Resolution**</span></span>  
  
 <span data-ttu-id="b5d03-131">您可以显式添加[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]到[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理控制台中所述的步骤[将 SAP 适配器添加到 BizTalk Server 管理控制台](../../adapters-and-accelerators/adapter-sap/add-the-sap-adapter-to-biztalk-server-administration-console.md)。</span><span class="sxs-lookup"><span data-stu-id="b5d03-131">You can explicitly add the [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] to the [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] Administration console by following the steps mentioned in [Add the SAP Adapter to BizTalk Server Administration Console](../../adapters-and-accelerators/adapter-sap/add-the-sap-adapter-to-biztalk-server-administration-console.md).</span></span>  
  
##  <a name="BKMK_SAPConnOpen"></a> <span data-ttu-id="b5d03-132">Dll 缺少打开与 SAP 的连接时出错</span><span class="sxs-lookup"><span data-stu-id="b5d03-132">DLLs are missing error opening a connection to SAP</span></span>  
 <span data-ttu-id="b5d03-133">**问题**</span><span class="sxs-lookup"><span data-stu-id="b5d03-133">**Problem**</span></span>  
  
 <span data-ttu-id="b5d03-134">当您尝试打开连接到 SAP 系统使用[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]，在 SAP 系统中，会出现一个对话框，在某些 Dll 丢失了通知。</span><span class="sxs-lookup"><span data-stu-id="b5d03-134">When you try to open a connection to the SAP system using the [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)], a dialog box appears in the SAP system, informing that some DLLs are missing.</span></span>  
  
 <span data-ttu-id="b5d03-135">**原因**</span><span class="sxs-lookup"><span data-stu-id="b5d03-135">**Cause**</span></span>  
  
 <span data-ttu-id="b5d03-136">[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] Librfc32u.dll 用于建立与 SAP 系统的连接。</span><span class="sxs-lookup"><span data-stu-id="b5d03-136">The [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] uses librfc32u.dll to establish a connection with the SAP system.</span></span> <span data-ttu-id="b5d03-137">Librfc32u.dll，反过来，需要一的组 Dll 才能正常。</span><span class="sxs-lookup"><span data-stu-id="b5d03-137">The librfc32u.dll, in turn, requires a set of DLLs to function.</span></span> <span data-ttu-id="b5d03-138">如果这些支持 Dll 不会添加到 PATH 变量的计算机上收到此错误在其中[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]安装。</span><span class="sxs-lookup"><span data-stu-id="b5d03-138">You get this error if these supporting DLLs are not added to the PATH variable on the computer where the [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] is installed.</span></span>  
  
 <span data-ttu-id="b5d03-139">**解决方法**</span><span class="sxs-lookup"><span data-stu-id="b5d03-139">**Resolution**</span></span>  
  
 <span data-ttu-id="b5d03-140">请参阅表来为解决此问题提供[加载适配器绑定时出错](#client_dll)问题。</span><span class="sxs-lookup"><span data-stu-id="b5d03-140">Refer to the table provided as a resolution to the [Error in loading the adapter bindings](#client_dll) issue.</span></span> <span data-ttu-id="b5d03-141">此表列出了与 SAP 系统使用所需的支持 Dll [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="b5d03-141">The table lists the supporting DLLs required to interface with the SAP system using the [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)].</span></span>  
  
##  <a name="BKMK_SAPXmlRetrieve"></a> <span data-ttu-id="b5d03-142">检索与 65536 个以上节点的 XML 时出错</span><span class="sxs-lookup"><span data-stu-id="b5d03-142">Error retrieving XML with more than 65,536 nodes</span></span>  
 <span data-ttu-id="b5d03-143">**问题**</span><span class="sxs-lookup"><span data-stu-id="b5d03-143">**Problem**</span></span>  
  
 <span data-ttu-id="b5d03-144">检索具有 65536 个以上节点的 XML 输出时，适配器将报告以下错误。</span><span class="sxs-lookup"><span data-stu-id="b5d03-144">The adapter gives the following error while retrieving XML output that has more than 65,536 nodes.</span></span>  
  
```  
Maximum number of items that can be serialized or deserialized in an object graph is '65536'.  
Change the object graph or increase the MaxItemsInObjectGraph quota.  
```  
  
 <span data-ttu-id="b5d03-145">**原因**</span><span class="sxs-lookup"><span data-stu-id="b5d03-145">**Cause**</span></span>  
  
 <span data-ttu-id="b5d03-146">适配器不能序列化和反序列化具有多个 65,536 项的对象。</span><span class="sxs-lookup"><span data-stu-id="b5d03-146">The adapter cannot serialize and deserialize an object with more than 65,536 items.</span></span>  
  
 <span data-ttu-id="b5d03-147">**解决方法**</span><span class="sxs-lookup"><span data-stu-id="b5d03-147">**Resolution**</span></span>  
  
 <span data-ttu-id="b5d03-148">可以通过设置来解决此问题`maxItemsInObjectGraph`中通过以下两种方式的参数：</span><span class="sxs-lookup"><span data-stu-id="b5d03-148">You can fix this issue by setting the `maxItemsInObjectGraph` parameter in either of the following two ways:</span></span>  
  
- <span data-ttu-id="b5d03-149">将此参数设置通过更改`maxItemsInObjectGraph`中的参数`ServiceBehavior`服务类中的属性。</span><span class="sxs-lookup"><span data-stu-id="b5d03-149">Set this parameter by changing the `maxItemsInObjectGraph` parameter in the `ServiceBehavior` attribute on your service class.</span></span>  
  
- <span data-ttu-id="b5d03-150">以下代码添加到应用程序的 app.config 文件。</span><span class="sxs-lookup"><span data-stu-id="b5d03-150">Add the following to your application's app.config file.</span></span>  
  
  ```  
  <behaviors>  
    <endpointBehaviors>  
      <behavior name="NewBehavior">  
        <dataContractSerializer maxItemsInObjectGraph="65536000" />  
      </behavior>  
    </endpointBehaviors>  
  </behaviors>  
  ```  
  
  <span data-ttu-id="b5d03-151">示例 app.config 看起来如下所示。</span><span class="sxs-lookup"><span data-stu-id="b5d03-151">A sample app.config will look like the following.</span></span>  
  
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
  
##  <a name="BKMK_SAPConnURI"></a> <span data-ttu-id="b5d03-152">错误输入 BizTalk Server 中的 WCF 自定义端口的连接 URI</span><span class="sxs-lookup"><span data-stu-id="b5d03-152">Error entering a connection URI for a WCF-Custom port in BizTalk Server</span></span>  
 <span data-ttu-id="b5d03-153">**问题**</span><span class="sxs-lookup"><span data-stu-id="b5d03-153">**Problem**</span></span>  
  
 [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]<span data-ttu-id="b5d03-154"> 在指定连接 URI 连接到 SAP 系统时出现以下错误。</span><span class="sxs-lookup"><span data-stu-id="b5d03-154"> gives the following error when you specify a connection URI to connect to the SAP system.</span></span>  
  
```  
Error saving properties.  
(System.ArgumentException) The specified address is invalid.  
(System.ArgumentException) Invalid address;  
"<connection URI>" is not a well-formed absolute uri.  
```  
  
 <span data-ttu-id="b5d03-155">**原因**</span><span class="sxs-lookup"><span data-stu-id="b5d03-155">**Cause**</span></span>  
  
 <span data-ttu-id="b5d03-156">连接 URI 不符合标准的编码格式。</span><span class="sxs-lookup"><span data-stu-id="b5d03-156">The connection URI does not adhere to the standard encoding format.</span></span> <span data-ttu-id="b5d03-157">例如，某个参数的值可能包含一个空格。</span><span class="sxs-lookup"><span data-stu-id="b5d03-157">For example, the value for a parameter might contain a space.</span></span>  
  
 <span data-ttu-id="b5d03-158">**解决方法**</span><span class="sxs-lookup"><span data-stu-id="b5d03-158">**Resolution**</span></span>  
  
 <span data-ttu-id="b5d03-159">请确保你指定的 URI 遵循标准编码格式的连接。</span><span class="sxs-lookup"><span data-stu-id="b5d03-159">Make sure the connection URI you specify adheres to the standard encoding format.</span></span> <span data-ttu-id="b5d03-160">例如，必须通过"%20"替换为空格。</span><span class="sxs-lookup"><span data-stu-id="b5d03-160">For example, a blank space must be replaced by "%20".</span></span>  
  
##  <a name="BKMK_SAPOperate"></a> <span data-ttu-id="b5d03-161">System.ArgumentNullException 上 SAP 的操作出错</span><span class="sxs-lookup"><span data-stu-id="b5d03-161">System.ArgumentNullException error while completing an operation on SAP</span></span>  
 <span data-ttu-id="b5d03-162">**问题**</span><span class="sxs-lookup"><span data-stu-id="b5d03-162">**Problem**</span></span>  
  
 <span data-ttu-id="b5d03-163">对 SAP 系统使用执行任何操作时，适配器将报告以下错误[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="b5d03-163">The adapter gives the following error when performing any operation on the SAP system using [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)].</span></span>  
  
```  
System.ArgumentNullException: Value cannot be null.  
```  
  
 <span data-ttu-id="b5d03-164">**原因**</span><span class="sxs-lookup"><span data-stu-id="b5d03-164">**Cause**</span></span>  
  
 <span data-ttu-id="b5d03-165">未指定消息的 WCF 操作。</span><span class="sxs-lookup"><span data-stu-id="b5d03-165">The WCF action for the message is not specified.</span></span> <span data-ttu-id="b5d03-166">WCF 需要用于为每个操作，向适配器通知上的 LOB 应用程序执行的操作指定的 SOAP 操作。</span><span class="sxs-lookup"><span data-stu-id="b5d03-166">WCF requires a SOAP action to be specified for every operation, which informs the adapter about the operation to be performed on the LOB application.</span></span>  
  
 <span data-ttu-id="b5d03-167">**解决方法**</span><span class="sxs-lookup"><span data-stu-id="b5d03-167">**Resolution**</span></span>  
  
 <span data-ttu-id="b5d03-168">在发送端口或为 BizTalk 业务流程的消息上下文属性指定的 SOAP 操作。</span><span class="sxs-lookup"><span data-stu-id="b5d03-168">Specify the SOAP action in the send port or as a message context property in a BizTalk orchestration.</span></span> <span data-ttu-id="b5d03-169">有关说明，请参阅[配置用于 SAP 系统的 SOAP 操作](../../adapters-and-accelerators/adapter-sap/configure-the-soap-action-for-the-sap-system.md)。</span><span class="sxs-lookup"><span data-stu-id="b5d03-169">For instructions, see [Configure the SOAP action for the SAP system](../../adapters-and-accelerators/adapter-sap/configure-the-soap-action-for-the-sap-system.md).</span></span> <span data-ttu-id="b5d03-170">请参阅[消息和消息架构](messages-and-message-schemas-for-biztalk-adapter-for-mysap-business-suite.md)若要查看每个操作的操作的列表。</span><span class="sxs-lookup"><span data-stu-id="b5d03-170">See [Messages and message schemas](messages-and-message-schemas-for-biztalk-adapter-for-mysap-business-suite.md) to see a list of actions for each operation.</span></span>  
  
##  <a name="BKMK_SAPXmlParsing"></a> <span data-ttu-id="b5d03-171">由于不正确的操作名称中指定的操作的 XmlReaderParsingException</span><span class="sxs-lookup"><span data-stu-id="b5d03-171">XmlReaderParsingException due to incorrect operation name in the specified action</span></span>  
 <span data-ttu-id="b5d03-172">**问题**</span><span class="sxs-lookup"><span data-stu-id="b5d03-172">**Problem**</span></span>  
  
 <span data-ttu-id="b5d03-173">将消息发送到 SAP 系统时，BizTalk Server 管理控制台将报告以下错误：</span><span class="sxs-lookup"><span data-stu-id="b5d03-173">The BizTalk Server Administration Console gives the following error when sending messages to an SAP system:</span></span>  
  
```  
Microsoft.ServiceModel.Channels.Common.XmlReaderParsingException: Invalid argument:  
<BtsActionMapping xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xmlns:xsd="http://www.w3.org/2001/XMLSchema">  
  <Operation Name="<operation_name>" Action="<action>" />  
</BtsActionMapping>  
```  
  
 <span data-ttu-id="b5d03-174">**原因**</span><span class="sxs-lookup"><span data-stu-id="b5d03-174">**Cause**</span></span>  
  
 <span data-ttu-id="b5d03-175">如果通过导入创建的端口绑定文件配置 WCF 自定义端口[!INCLUDE[consumeadapterservlong](../../includes/consumeadapterservlong-md.md)]，采用以下格式指定端口中的操作：</span><span class="sxs-lookup"><span data-stu-id="b5d03-175">If you configure a WCF-Custom port by importing the port binding file created by the [!INCLUDE[consumeadapterservlong](../../includes/consumeadapterservlong-md.md)], the action in the port is specified in the following format:</span></span>  
  
```  
<BtsActionMapping>  
  <Operation Name="Op1" Action="http://MyService/Svc/Op1" />  
</BtsActionMapping>  
```  
  
 <span data-ttu-id="b5d03-176">在上述格式中，操作名称受生成架构时选择该操作。</span><span class="sxs-lookup"><span data-stu-id="b5d03-176">In the above format, the operation name is governed by the operation you chose while generating the schema.</span></span> <span data-ttu-id="b5d03-177">例如，如果 RFC_CUSTOMER_GET 生成架构，操作名称的操作中将"RFC_CUSTOMER_GET"。</span><span class="sxs-lookup"><span data-stu-id="b5d03-177">For example, if you generated schema for RFC_CUSTOMER_GET, the operation name in the action will be "RFC_CUSTOMER_GET".</span></span> <span data-ttu-id="b5d03-178">但是中的逻辑端口的操作名称创建在 BizTalk 业务流程中[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]可能不同。</span><span class="sxs-lookup"><span data-stu-id="b5d03-178">However, the operation name in the logical port created in the BizTalk orchestration in [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)] might be different.</span></span>  
  
 <span data-ttu-id="b5d03-179">**解决方法**</span><span class="sxs-lookup"><span data-stu-id="b5d03-179">**Resolution**</span></span>  
  
 <span data-ttu-id="b5d03-180">请确保操作名称的两个逻辑端口 (在 BizTalk 业务流程中[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]) 和 （在 BizTalk Server 管理控制台） 的物理端口相同。</span><span class="sxs-lookup"><span data-stu-id="b5d03-180">Make sure the operation names in both the logical port (in the BizTalk orchestration in [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]) and the physical port (in BizTalk Server Administration Console) are same.</span></span>  
  
##  <a name="BKMK_SAPHundredCons"></a> <span data-ttu-id="b5d03-181">打开与 SAP 超过 100 个连接时出错</span><span class="sxs-lookup"><span data-stu-id="b5d03-181">Error opening more than 100 connections to SAP</span></span>  
 <span data-ttu-id="b5d03-182">**问题**</span><span class="sxs-lookup"><span data-stu-id="b5d03-182">**Problem**</span></span>  
  
 <span data-ttu-id="b5d03-183">打开到 SAP 系统的 100 多个连接时，适配器将引发以下异常。</span><span class="sxs-lookup"><span data-stu-id="b5d03-183">The adapter throws the following exception when opening more than 100 connections to the SAP system.</span></span>  
  
```  
Microsoft.ServiceModel.Channels.Common.ConnectionException: ErrorCode=RFC_OK. ErrorGroup=RFC_ERROR_COMMUNICATION. SapErrorMessage=Connect to SAP gateway failed  
Connect_PM  GWHOST=<gw_host>, GWSERV=<gw_serv>, SYSNR=<sys_number>  
LOCATION    CPIC (TCP/IP) on local host with Unicode  
ERROR       max no of 100 conversations exceeded  
```  
  
 <span data-ttu-id="b5d03-184">**原因**</span><span class="sxs-lookup"><span data-stu-id="b5d03-184">**Cause**</span></span>  
  
 <span data-ttu-id="b5d03-185">默认情况下，SAP 不会启用超过 100 个连接到系统。</span><span class="sxs-lookup"><span data-stu-id="b5d03-185">By default, SAP does not enable more than 100 connections into the system.</span></span>  
  
 <span data-ttu-id="b5d03-186">**解决方法**</span><span class="sxs-lookup"><span data-stu-id="b5d03-186">**Resolution**</span></span>  
  
 <span data-ttu-id="b5d03-187">若要增加最大连接数，必须已安装并将其设置为数字值的 SAP 客户端库的计算机上创建一个环境变量。</span><span class="sxs-lookup"><span data-stu-id="b5d03-187">To increase the maximum number of connections, you must create an environment variable on the computer that has the SAP client libraries installed and set it to a numeric value.</span></span> <span data-ttu-id="b5d03-188">为此环境变量指定的值是最大可为 SAP 系统的连接数。</span><span class="sxs-lookup"><span data-stu-id="b5d03-188">The value you specify for this environment variable is the maximum number of connections that can be made into the SAP system.</span></span> <span data-ttu-id="b5d03-189">使用以下详细信息创建环境变量：</span><span class="sxs-lookup"><span data-stu-id="b5d03-189">Create the environment variable with the following details:</span></span>  
  
- <span data-ttu-id="b5d03-190">**变量名称**: CPIC_MAX_CONV</span><span class="sxs-lookup"><span data-stu-id="b5d03-190">**Variable name**: CPIC_MAX_CONV</span></span>  
  
- <span data-ttu-id="b5d03-191">**变量值**： 任何正的数字值。</span><span class="sxs-lookup"><span data-stu-id="b5d03-191">**Variable value**: any positive numeric value.</span></span> <span data-ttu-id="b5d03-192">例如，如果要启用 200 个连接到 SAP 系统，可以指定值设为 200。</span><span class="sxs-lookup"><span data-stu-id="b5d03-192">For example, to enable 200 connections into the SAP system, specify the value as 200.</span></span>  
  
  <span data-ttu-id="b5d03-193">创建一个环境变量的说明，请参阅"如何在 Windows 2000 中创建系统变量"处[ http://go.microsoft.com/fwlink/?LinkId=95020 ](http://go.microsoft.com/fwlink/?LinkId=95020)。</span><span class="sxs-lookup"><span data-stu-id="b5d03-193">For instructions on creating an environment variable, see "How To Create System Variables in Windows 2000" at [http://go.microsoft.com/fwlink/?LinkId=95020](http://go.microsoft.com/fwlink/?LinkId=95020).</span></span>  
  
##  <a name="BKMK_SAPIDOCMetadata"></a> <span data-ttu-id="b5d03-194">生成时出现错误或检索 Idoc 的元数据</span><span class="sxs-lookup"><span data-stu-id="b5d03-194">Error generating or retrieving metadata for IDOCs</span></span>  
 <span data-ttu-id="b5d03-195">**问题**</span><span class="sxs-lookup"><span data-stu-id="b5d03-195">**Problem**</span></span>  
  
 <span data-ttu-id="b5d03-196">生成的元数据时**接收**SAP 系统中的 IDOC 的操作[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]时出现以下错误。</span><span class="sxs-lookup"><span data-stu-id="b5d03-196">While generating metadata for the **Receive** operation for an IDOC in an SAP system, the [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] gives the following error.</span></span>  
  
```  
Error while retrieving or generating the WSDL.  
Adapter message: Details: ErrorCode=RFC_EXCEPTION.  
ErrorGroup=RFC_ERROR_APPLICATION_EXCEPTION. SapErrorMessage= OBJECT_UNKNOWN.  
AdapterErrorMessage=Error returned by RfcCallReceiveEx while calling RFC: IDOCTYPE_READ_COMPLETE.  
```  
  
 <span data-ttu-id="b5d03-197">**原因**</span><span class="sxs-lookup"><span data-stu-id="b5d03-197">**Cause**</span></span>  
  
 <span data-ttu-id="b5d03-198">[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] IDOCTYPE_READ_COMPLETE RFC 用于检索的元数据**接收**IDOC 的操作。</span><span class="sxs-lookup"><span data-stu-id="b5d03-198">The [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] uses the IDOCTYPE_READ_COMPLETE RFC to retrieve the metadata for the **Receive** operation for an IDOC.</span></span> <span data-ttu-id="b5d03-199">调用此 RFC 要求 SAP 系统中的特定用户的权限。</span><span class="sxs-lookup"><span data-stu-id="b5d03-199">Invoking this RFC requires specific user permissions in the SAP system.</span></span> <span data-ttu-id="b5d03-200">若要生成的元数据，如果已连接到 SAP 系统使用的凭据，没有权限来调用 IDOCTYPE_READ_COMPLETE RFC[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]会出错。</span><span class="sxs-lookup"><span data-stu-id="b5d03-200">To generate metadata, if you have connected to the SAP system using a credential that does not have permission to invoke the IDOCTYPE_READ_COMPLETE RFC, the [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] gives an error.</span></span>  
  
 <span data-ttu-id="b5d03-201">**解决方法**</span><span class="sxs-lookup"><span data-stu-id="b5d03-201">**Resolution**</span></span>  
  
 <span data-ttu-id="b5d03-202">登录到 SAP GUI 使用相同的凭据必须用于该适配器。</span><span class="sxs-lookup"><span data-stu-id="b5d03-202">Log in to the SAP GUI using the same credentials you had used for the adapter.</span></span> <span data-ttu-id="b5d03-203">导航到事务 SE37，并输入 RFC IDOCTYPE_READ_COMPLETE 作为执行的名称。</span><span class="sxs-lookup"><span data-stu-id="b5d03-203">Navigate to transaction SE37, and enter the name of the RFC to execute as IDOCTYPE_READ_COMPLETE.</span></span>  
  
 <span data-ttu-id="b5d03-204">PI_IDOCTYP 和 PI_CIMTYP 的输入参数，请输入对应于自定义 IDoc 的值。</span><span class="sxs-lookup"><span data-stu-id="b5d03-204">For the input parameters PI_IDOCTYP and PI_CIMTYP, enter the values corresponding to the custom IDoc.</span></span> <span data-ttu-id="b5d03-205">对于 PI_VERSION 和 PI_RELEASE 参数，为所选适配器元数据 UI 中输入相同的值。</span><span class="sxs-lookup"><span data-stu-id="b5d03-205">For the parameters PI_VERSION and PI_RELEASE, enter the same values as being chosen in the Adapter Metadata UI.</span></span> <span data-ttu-id="b5d03-206">然后，按 F8 来执行。</span><span class="sxs-lookup"><span data-stu-id="b5d03-206">And, press F8 to execute.</span></span>  
  
 <span data-ttu-id="b5d03-207">应收到相同的错误什么适配器接收时，有关该问题的详细信息。</span><span class="sxs-lookup"><span data-stu-id="b5d03-207">You should get the same exception as what the adapter receives, with more information about the issue.</span></span>  
  
 <span data-ttu-id="b5d03-208">如果仍然无法解决此问题，生成的架构**ReceiveIdoc**而不是操作**接收**操作。</span><span class="sxs-lookup"><span data-stu-id="b5d03-208">If you are still not able to resolve the issue, generate a schema for the **ReceiveIdoc** operation instead of the **Receive** operation.</span></span> <span data-ttu-id="b5d03-209">在这种情况下，SAP 适配器不使用 IDOCTYPE_READ_COMPLETE，并且不会引发任何错误。</span><span class="sxs-lookup"><span data-stu-id="b5d03-209">In this case, the SAP adapter does not use IDOCTYPE_READ_COMPLETE, and does not throw any error.</span></span>  
  
##  <a name="BKMK_SAPIDOCReceive"></a> <span data-ttu-id="b5d03-210">错误发送或接收具有取消释放段的 Idoc</span><span class="sxs-lookup"><span data-stu-id="b5d03-210">Error sending or receiving IDOCs that have unreleased segments</span></span>  
 <span data-ttu-id="b5d03-211">**问题**</span><span class="sxs-lookup"><span data-stu-id="b5d03-211">**Problem**</span></span>  
  
 <span data-ttu-id="b5d03-212">[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]发送 Idoc 时提供 XmlReaderParsingException (使用**发送**操作) 或接收 Idoc (使用**接收**操作)，已取消释放段。</span><span class="sxs-lookup"><span data-stu-id="b5d03-212">The [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] gives an XmlReaderParsingException while sending IDOCs (using **Send** operation) or receiving IDOCs (using **Receive** operation) that have unreleased segments.</span></span>  
  
 <span data-ttu-id="b5d03-213">**原因**</span><span class="sxs-lookup"><span data-stu-id="b5d03-213">**Cause**</span></span>  
  
 <span data-ttu-id="b5d03-214">Idoc 被构成的段。</span><span class="sxs-lookup"><span data-stu-id="b5d03-214">IDOCs are constituted of segments.</span></span> <span data-ttu-id="b5d03-215">生成元数据时[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]检索 SAP 系统中存在的所有已发布的段。</span><span class="sxs-lookup"><span data-stu-id="b5d03-215">While generating metadata, the [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] retrieves all the released segments that are present in the SAP system.</span></span> <span data-ttu-id="b5d03-216">但是，当适配器客户端使用的元数据执行操作接收 IDOC，例如[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]提供 XmlReaderParsingException。</span><span class="sxs-lookup"><span data-stu-id="b5d03-216">However, when the adapter client uses the metadata to perform an operation such as receiving an IDOC, the [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] gives an XmlReaderParsingException.</span></span> <span data-ttu-id="b5d03-217">这是因为 SAP 系统收到的 IDOC 后，可能发送某些未发布的段，适配器未生成其元数据。</span><span class="sxs-lookup"><span data-stu-id="b5d03-217">This occurs because when the IDOC is received, the SAP system might have sent some unreleased segments as well, the metadata for which was not generated by the adapter.</span></span>  
  
 <span data-ttu-id="b5d03-218">**解决方法**</span><span class="sxs-lookup"><span data-stu-id="b5d03-218">**Resolution**</span></span>  
  
 <span data-ttu-id="b5d03-219">执行以下任一操作：</span><span class="sxs-lookup"><span data-stu-id="b5d03-219">Do any of the following:</span></span>  
  
-   <span data-ttu-id="b5d03-220">将 SAP 系统升级通过应用相应的修补程序未发布段。</span><span class="sxs-lookup"><span data-stu-id="b5d03-220">Upgrade your SAP system by applying appropriate patches for the unreleased segments.</span></span>  
  
-   <span data-ttu-id="b5d03-221">使用**SendIdoc**或**ReceiveIdoc**操作来发送和接收 Idoc 分别。</span><span class="sxs-lookup"><span data-stu-id="b5d03-221">Use **SendIdoc** or **ReceiveIdoc** operations to send and receive IDOCs respectively.</span></span> <span data-ttu-id="b5d03-222">有关这些操作的详细信息，请参阅[sap 的 Idoc 的操作](../../adapters-and-accelerators/adapter-sap/operations-on-idocs-in-sap.md)。</span><span class="sxs-lookup"><span data-stu-id="b5d03-222">For more information about these operations, see [Operations on IDOCs in SAP](../../adapters-and-accelerators/adapter-sap/operations-on-idocs-in-sap.md).</span></span>  
  
##  <a name="BKMK_SAPIDOCSend"></a> <span data-ttu-id="b5d03-223">将平面文件 Idoc 发送到 SAP 使用 SAP FilePort 接收到的错误</span><span class="sxs-lookup"><span data-stu-id="b5d03-223">Error sending flat-file IDOCs to SAP that were received using the SAP FilePort</span></span>  
 <span data-ttu-id="b5d03-224">**问题**</span><span class="sxs-lookup"><span data-stu-id="b5d03-224">**Problem**</span></span>  
  
 <span data-ttu-id="b5d03-225">如果您尝试发送 (使用**发送**操作) 到 SAP 系统，使用 SAP FilePort 生成平面文件 IDOC，BizTalk 业务流程中的平面文件分析器无法 flatf 文件转换为 XML 格式，从而失败IDOD**发送**操作。</span><span class="sxs-lookup"><span data-stu-id="b5d03-225">If you try to send (using **Send** operation) a flat-file IDOC to an SAP system that was generated using an SAP FilePort, the flat-file parser in the BizTalk orchestration fails to convert the flatf-file to an XML format, thereby failing the IDOD **Send** operation.</span></span>  
  
 <span data-ttu-id="b5d03-226">**原因**</span><span class="sxs-lookup"><span data-stu-id="b5d03-226">**Cause**</span></span>  
  
 <span data-ttu-id="b5d03-227">当 SAP 系统生成使用 FilePort IDOC 时，修剪关闭一个段末尾的所有空白空间。</span><span class="sxs-lookup"><span data-stu-id="b5d03-227">When the SAP system generates an IDOC using a FilePort, it trims off all the empty spaces at the end of a segment.</span></span> <span data-ttu-id="b5d03-228">但是，平面文件分析器要求存在才可成功地将平面文件转换为 XML 的段中的最后一个字段的数据。</span><span class="sxs-lookup"><span data-stu-id="b5d03-228">However, the flat-file parser expects the data of the last field in the segment to be present to successfully convert the flat-file to XML.</span></span> <span data-ttu-id="b5d03-229">因为空空间不存在的段中，平面文件分析器无法分析为 XML 的平面文件。</span><span class="sxs-lookup"><span data-stu-id="b5d03-229">Because the empty spaces are not present in the segment, the flat-file parser fails to parse the flat-file to XML.</span></span>  
  
 <span data-ttu-id="b5d03-230">**解决方法**</span><span class="sxs-lookup"><span data-stu-id="b5d03-230">**Resolution**</span></span>  
  
 <span data-ttu-id="b5d03-231">对于使用 SAP FilePort 生成此类平面文件 Idoc，使用**SendIdoc**操作相反。</span><span class="sxs-lookup"><span data-stu-id="b5d03-231">For such flat-file IDOCs generated using the SAP FilePort, use the **SendIdoc** operation instead.</span></span> <span data-ttu-id="b5d03-232">有关此操作的详细信息，请参阅[sap 的 Idoc 的操作](../../adapters-and-accelerators/adapter-sap/operations-on-idocs-in-sap.md)。</span><span class="sxs-lookup"><span data-stu-id="b5d03-232">For more information about this operation, see [Operations on IDOCs in SAP](../../adapters-and-accelerators/adapter-sap/operations-on-idocs-in-sap.md).</span></span>  
  
##  <a name="BKMK_SAPRecIDOCCompat"></a> <span data-ttu-id="b5d03-233">错误从 SAP 接收 Idoc，如果 EnableBizTalkCompatibilityMode 属性设置为 true</span><span class="sxs-lookup"><span data-stu-id="b5d03-233">Error receiving IDOCs from SAP if EnableBizTalkCompatibilityMode property is set to true</span></span>  
 <span data-ttu-id="b5d03-234">**问题**</span><span class="sxs-lookup"><span data-stu-id="b5d03-234">**Problem**</span></span>  
  
 <span data-ttu-id="b5d03-235">接收与 IDOC 时遇到以下异常**EnableBizTalkCompatibilityMode**绑定属性设置为 true:</span><span class="sxs-lookup"><span data-stu-id="b5d03-235">The following exception is encountered while receiving an IDOC with the **EnableBizTalkCompatibilityMode** binding property set to true:</span></span>  
  
```  
System.Exception: Loading property information list by namespace failed or property not found in the list. Verify that the schema is deployed properly.  
```  
  
 <span data-ttu-id="b5d03-236">**原因**</span><span class="sxs-lookup"><span data-stu-id="b5d03-236">**Cause**</span></span>  
  
 <span data-ttu-id="b5d03-237">如果绑定属性**EnableBizTalkCompatibilityMode**设置为**true**，你必须将 BizTalk 属性架构 DLL 添加为[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]为 BizTalk 应用程序，即中的资源在其中部署你的项目的应用程序。</span><span class="sxs-lookup"><span data-stu-id="b5d03-237">If the binding property **EnableBizTalkCompatibilityMode** is set to **true**, you must add the BizTalk property schema DLL for the [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] as a resource in your BizTalk application, that is, the application in which your project is deployed.</span></span>  
  
 <span data-ttu-id="b5d03-238">**解决方法**</span><span class="sxs-lookup"><span data-stu-id="b5d03-238">**Resolution**</span></span>  
  
 <span data-ttu-id="b5d03-239">BizTalk 属性架构的名称[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]是*Microsoft.Adapters.SAP.BiztalkPropertySchema.dll*。</span><span class="sxs-lookup"><span data-stu-id="b5d03-239">The name for the BizTalk property schema for the [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] is *Microsoft.Adapters.SAP.BiztalkPropertySchema.dll*.</span></span> <span data-ttu-id="b5d03-240">此情况下安装[!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)]设置下\<安装驱动器\>: \Program Files\Microsoft BizTalk 适配器 Pack\bin。</span><span class="sxs-lookup"><span data-stu-id="b5d03-240">This is installed by the [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)] setup under \<installation drive\>:\ Program Files\Microsoft BizTalk Adapter Pack\bin.</span></span> <span data-ttu-id="b5d03-241">执行以下任务来添加此程序集作为 BizTalk 应用程序中的资源。</span><span class="sxs-lookup"><span data-stu-id="b5d03-241">Perform the following tasks to add this assembly as a resource in your BizTalk application.</span></span>  
  
#### <a name="add-an-assembly-as-a-resource-in-biztalk-application"></a><span data-ttu-id="b5d03-242">将程序集添加为 BizTalk 应用程序中的资源</span><span class="sxs-lookup"><span data-stu-id="b5d03-242">Add an assembly as a resource in BizTalk application</span></span>  
  
1. <span data-ttu-id="b5d03-243">启动[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理控制台。</span><span class="sxs-lookup"><span data-stu-id="b5d03-243">Start the [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] Administration console.</span></span>  
  
2. <span data-ttu-id="b5d03-244">在控制台树中，展开**BizTalk 组**，展开**应用程序**，，然后你想要添加 BizTalk 程序集的应用程序。</span><span class="sxs-lookup"><span data-stu-id="b5d03-244">In the console tree, expand **BizTalk Group**, expand **Applications**, and then the application to which you want to add a BizTalk assembly.</span></span>  
  
3. <span data-ttu-id="b5d03-245">展开**应用程序**和你想要添加 BizTalk 程序集的应用程序。</span><span class="sxs-lookup"><span data-stu-id="b5d03-245">Expand **Applications** and the application to which you want to add a BizTalk assembly.</span></span>  
  
4. <span data-ttu-id="b5d03-246">右键单击**资源**，依次指向**添加**，然后单击**BizTalk 程序集**。</span><span class="sxs-lookup"><span data-stu-id="b5d03-246">Right-click **Resources**, point to **Add**, and then click **BizTalk Assemblies**.</span></span>  
  
5. <span data-ttu-id="b5d03-247">单击**外**，导航到包含 BizTalk 程序集文件的文件夹中，选择 BizTalk 程序集文件，然后单击**打开**。</span><span class="sxs-lookup"><span data-stu-id="b5d03-247">Click **Add**, navigate to the folder containing the BizTalk assembly file, select the BizTalk assembly file, and then click **Open**.</span></span>  
  
6. <span data-ttu-id="b5d03-248">在中**选项**，为 BizTalk 程序集安装到 GAC 中，指定选项，然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="b5d03-248">In **Options**, specify the options for installing the BizTalk assembly to the GAC, and then click **OK**.</span></span>  
  
##  <a name="BKMK_SAPIDOCValidate"></a> <span data-ttu-id="b5d03-249">中从 SAP 系统接收 Idoc 时的验证错误</span><span class="sxs-lookup"><span data-stu-id="b5d03-249">Error in validation while receiving IDOCs from an SAP system</span></span>  
 <span data-ttu-id="b5d03-250">**问题**</span><span class="sxs-lookup"><span data-stu-id="b5d03-250">**Problem**</span></span>  
  
 <span data-ttu-id="b5d03-251">从 SAP 系统接收 IDOC 未能通过验证，类似于以下错误：</span><span class="sxs-lookup"><span data-stu-id="b5d03-251">An IDOC received from an SAP system fails validation with an error similar to the following:</span></span>  
  
```  
There was a failure executing the receive pipeline: "Microsoft.BizTalk.DefaultPipelines.XMLReceive, Microsoft.BizTalk.DefaultPipelines, Version=3.0.1.0, Culture=neutral, PublicKeyToken=<token>"  
Source: "Pipeline " Receive Port: "ReceiveIdoc" URI: "<connection uri>"  
Reason: The document failed to validate because of the following error:  
"The 'http://Microsoft.LobServices.Sap/2007/03/Types/Idoc/3/CREMAS03//620:TAXBS' element has an invalid value according to its data type."  
```  
  
 <span data-ttu-id="b5d03-252">**原因**</span><span class="sxs-lookup"><span data-stu-id="b5d03-252">**Cause**</span></span>  
  
 <span data-ttu-id="b5d03-253">生成用于接收 IDOC 的元数据包含接收操作的一部分接收特定列的允许值。</span><span class="sxs-lookup"><span data-stu-id="b5d03-253">The metadata generated for receiving an IDOC contains the permissible values that can be received for a particular column as part of the receive operation.</span></span> <span data-ttu-id="b5d03-254">这些值公开为生成的元数据中的枚举。</span><span class="sxs-lookup"><span data-stu-id="b5d03-254">These values are exposed as enumeration in the generated metadata.</span></span> <span data-ttu-id="b5d03-255">但是，当实际收到 IDOC 时，收到的值可能不同于枚举值。</span><span class="sxs-lookup"><span data-stu-id="b5d03-255">However, when the IDOC is actually received, the value received could be different from the enumerated values.</span></span> <span data-ttu-id="b5d03-256">因此，接收操作失败时验证的值。</span><span class="sxs-lookup"><span data-stu-id="b5d03-256">Hence the receive operation fails while validating the values.</span></span> <span data-ttu-id="b5d03-257">例如，在上述错误消息的验证失败 TAXBS 列。</span><span class="sxs-lookup"><span data-stu-id="b5d03-257">For example, in the above error message validation fails for the TAXBS column.</span></span>  
  
 <span data-ttu-id="b5d03-258">**解决方法**</span><span class="sxs-lookup"><span data-stu-id="b5d03-258">**Resolution**</span></span>  
  
 <span data-ttu-id="b5d03-259">您必须手动编辑架构 （对于 BizTalk 项目） 或客户端代理中的枚举 （对于.NET 项目使用 WCF 服务模型） 包含 SAP 系统从收到的值。</span><span class="sxs-lookup"><span data-stu-id="b5d03-259">You must manually edit the enumeration in schema (for BizTalk projects) or the client proxy (for .NET projects using WCF service model) to include the value received from the SAP system.</span></span>  
  
##  <a name="BKMK_SAPFFIDOC"></a> <span data-ttu-id="b5d03-260">平面文件 Idoc 转换为 XML，前后不完全相同</span><span class="sxs-lookup"><span data-stu-id="b5d03-260">Flat-file IDOCs, before and after converting to XML, are not identical</span></span>  
 <span data-ttu-id="b5d03-261">**问题**</span><span class="sxs-lookup"><span data-stu-id="b5d03-261">**Problem**</span></span>  
  
 <span data-ttu-id="b5d03-262">如果使用平面文件分析器将平面文件 IDOC 转换为使用该架构的 XML，然后将 XML 转换回通过管道使用的架构的平面文件 IDOC，则两个平面文件 Idoc 不相同。</span><span class="sxs-lookup"><span data-stu-id="b5d03-262">If you use a flat file parser to convert a flat-file IDOC to an XML using the schema, and then convert the XML back to a flat-file IDOC through a pipeline using the schema, the two flat-file IDOCs are not identical.</span></span>  
  
 <span data-ttu-id="b5d03-263">**原因**</span><span class="sxs-lookup"><span data-stu-id="b5d03-263">**Cause**</span></span>  
  
 <span data-ttu-id="b5d03-264">当从平面文件 IDOC 生成 XML，平面文件分析器不会生成具有空白值的 XML 节点。</span><span class="sxs-lookup"><span data-stu-id="b5d03-264">When generating the XML from a flat-file IDOC, the flat file parser does not generate the XML nodes with blank values.</span></span> <span data-ttu-id="b5d03-265">当此 XML 转换回平面文件时，XML 中缺少的节点不会反映在平面文件 IDOC。</span><span class="sxs-lookup"><span data-stu-id="b5d03-265">When this XML is converted back to a flat-file, the nodes missing from the XML are not reflected in the flat-file IDOC.</span></span> <span data-ttu-id="b5d03-266">因此平面文件 Idoc 不相同。</span><span class="sxs-lookup"><span data-stu-id="b5d03-266">Hence the flat-file IDOCs are not identical.</span></span>  
  
 <span data-ttu-id="b5d03-267">**解决方法**</span><span class="sxs-lookup"><span data-stu-id="b5d03-267">**Resolution**</span></span>  
  
 <span data-ttu-id="b5d03-268">用于将平面文件转换为 XML，反之亦然，在"发送"接收"节点定义中，在架构中执行以下步骤：</span><span class="sxs-lookup"><span data-stu-id="b5d03-268">In the schema used to convert the flat-file to XML and vice-versa, within the "Send" or "Receive" node definition, do the following:</span></span>  
  
1. <span data-ttu-id="b5d03-269">设置**suppress_empty_nodes**属性设置为**false**并设置**generate_empty_nodes**属性设置为**true**。</span><span class="sxs-lookup"><span data-stu-id="b5d03-269">Set the **suppress_empty_nodes** property to **false** and set the **generate_empty_nodes** property to **true**.</span></span> <span data-ttu-id="b5d03-270">默认情况下**suppress_empty_nodes**属性设置为**true**并**generate_empty_nodes**属性设置为**false**，和因此所有空节点不会反映在 XML 中。</span><span class="sxs-lookup"><span data-stu-id="b5d03-270">By default, the **suppress_empty_nodes** property is set to **true** and the **generate_empty_nodes** property is set to **false**, and hence all empty nodes are not reflected in the XML.</span></span>  
  
2. <span data-ttu-id="b5d03-271">平面文件可能包含额外回车符结尾。</span><span class="sxs-lookup"><span data-stu-id="b5d03-271">The flat-file may contain an extra carriage return at the end.</span></span> <span data-ttu-id="b5d03-272">可以设置**suppress_trailing_delimiters**属性设置为**是**若要避免此额外的回车。</span><span class="sxs-lookup"><span data-stu-id="b5d03-272">You can set the **suppress_trailing_delimiters** property to **Yes** to avoid this extra carriage return.</span></span> <span data-ttu-id="b5d03-273">为该属性还公开**取消尾部分隔符**属性，如果您打开中的架构[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="b5d03-273">This property is also exposed as the **Suppress Trailing Delimiters** property if you open the schema in [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)].</span></span>  
  
##  <a name="BKMK_SAPAction"></a> <span data-ttu-id="b5d03-274">使用绑定文件一起创建的物理端口不正确的操作错误</span><span class="sxs-lookup"><span data-stu-id="b5d03-274">Incorrect Action error using a physical port creating with a binding file</span></span>  
 <span data-ttu-id="b5d03-275">**问题**</span><span class="sxs-lookup"><span data-stu-id="b5d03-275">**Problem**</span></span>  
  
 <span data-ttu-id="b5d03-276">在使用后[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]若要生成上的 SAP 系统的特定操作的架构外, 接程序还会创建端口绑定文件。</span><span class="sxs-lookup"><span data-stu-id="b5d03-276">After you use the [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)] to generate schema for a specific operation on the SAP system, the add-in also creates a port binding file.</span></span> <span data-ttu-id="b5d03-277">您可以导入此文件使用绑定[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理控制台，可在 BizTalk Server 中创建物理端口。</span><span class="sxs-lookup"><span data-stu-id="b5d03-277">You can import this binding file using the [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] Administration console to create physical ports in BizTalk Server.</span></span> <span data-ttu-id="b5d03-278">但是时将消息发送到 SAP 系统使用此类端口时，, 适配器将无法理解的端口上指定的操作，并提供了类似于以下的错误：</span><span class="sxs-lookup"><span data-stu-id="b5d03-278">However, when you send messages to the SAP system using such ports, the adapter fails to understand the action specified on the port and gives an error similar to the following:</span></span>  
  
```  
Microsoft.ServiceModel.Channels.Common.UnsupportedOperationException: Incorrect Action   
<BtsActionMapping xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xmlns:xsd="http://www.w3.org/2001/XMLSchema">  
  <Operation Name="<op_name>" Action="<action>" />  
</BtsActionMapping>. Correct the specified Action, or refer to the documentation on the allowed formats for the Actions.  
```  
  
 <span data-ttu-id="b5d03-279">**原因**</span><span class="sxs-lookup"><span data-stu-id="b5d03-279">**Cause**</span></span>  
  
 <span data-ttu-id="b5d03-280">BizTalk 业务流程中创建逻辑端口时，指定这些端口上操作某些名称，或只需使用默认名称，例如 Operation_1、 Operation_2，等等。但是，在生成的绑定文件[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]，操作名称是与为其生成元数据的操作的名称相同。</span><span class="sxs-lookup"><span data-stu-id="b5d03-280">When you create logical ports in a BizTalk orchestration, you specify certain names for the operations on those ports or you just use the default names like Operation_1, Operation_2, etc. However, in the binding file generated by the [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)], the operation name is same as the name of the operation for which you generate metadata.</span></span> <span data-ttu-id="b5d03-281">例如，如果您为 RFC_CUSTOMER_GET 生成元数据，操作将设置为以下：</span><span class="sxs-lookup"><span data-stu-id="b5d03-281">For example, if you generate metadata for RFC_CUSTOMER_GET, the action will be set to the following:</span></span>  
  
```  
<Operation Name="RFC_CUSTOMER_GET" Action="http://Microsoft.LobServices.Sap/2007/03/Rfc/RFC_CUSTOMER_GET" />  
```  
  
 <span data-ttu-id="b5d03-282">导入绑定文件时，物理端口上设置相同的操作。</span><span class="sxs-lookup"><span data-stu-id="b5d03-282">When you import the binding file, the same action is set on physical port.</span></span> <span data-ttu-id="b5d03-283">因此，逻辑端口 （Operation_1、 Operation_2 等） 上的操作名称与物理端口，从而导致错误的操作中指定的操作名称不匹配。</span><span class="sxs-lookup"><span data-stu-id="b5d03-283">So, the operation names on the logical port (Operation_1, Operation_2, etc.) do not match the operation names specified in the action on the physical port, resulting in an error.</span></span>  
  
 <span data-ttu-id="b5d03-284">**解决方法**</span><span class="sxs-lookup"><span data-stu-id="b5d03-284">**Resolution**</span></span>  
  
 <span data-ttu-id="b5d03-285">请确保逻辑端口中的操作名称中的物理端口的操作中指定的操作名称相同。</span><span class="sxs-lookup"><span data-stu-id="b5d03-285">Make sure the operation name in the logical port is the same as the operation name specified as part of the action in the physical port.</span></span> <span data-ttu-id="b5d03-286">执行以下操作之一：</span><span class="sxs-lookup"><span data-stu-id="b5d03-286">Do one of the following:</span></span>  
  
-   <span data-ttu-id="b5d03-287">对为其生成元数据，例如 RFC_CUSTOMER_GET 操作从 Operation_1 等更改 BizTalk 业务流程中的逻辑端口中的操作名称。</span><span class="sxs-lookup"><span data-stu-id="b5d03-287">Change the operation name in the logical port in BizTalk orchestration from Operation_1, etc. to the operation for which you generate metadata, for example RFC_CUSTOMER_GET.</span></span>  
  
-   <span data-ttu-id="b5d03-288">将物理端口上的操作中的操作名称更改为中的逻辑端口的操作名称。</span><span class="sxs-lookup"><span data-stu-id="b5d03-288">Change the operation name in the action on the physical port to the operation name in the logical port.</span></span> <span data-ttu-id="b5d03-289">例如，可以更改为类似于以下的物理端口中的操作：</span><span class="sxs-lookup"><span data-stu-id="b5d03-289">For example, you could change the action in the physical port to resemble the following:</span></span>  
  
    ```  
    <Operation Name="Operation_1" Action="http://Microsoft.LobServices.Sap/2007/03/Rfc/RFC_CUSTOMER_GET" />  
    ```  
  
##  <a name="BKMK_SAPTableParams"></a> <span data-ttu-id="b5d03-290">响应消息的操作在 SAP 上运行不包含任何表参数</span><span class="sxs-lookup"><span data-stu-id="b5d03-290">The response message for an operation ran on SAP does not contain any table parameters</span></span>  
 <span data-ttu-id="b5d03-291">**原因**</span><span class="sxs-lookup"><span data-stu-id="b5d03-291">**Cause**</span></span>  
  
 <span data-ttu-id="b5d03-292">如果使用[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]地执行对 SAP 系统的操作返回大量的表，每个表包含大量的记录，那将搜索到 SAP 系统从返回的响应消息的一部分的大型数据集。</span><span class="sxs-lookup"><span data-stu-id="b5d03-292">If you use the [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] to execute an operation on the SAP system that returns a large number of tables, and each table has a large number of records, that will amount to a large dataset being returned as part of the response message from the SAP system.</span></span> <span data-ttu-id="b5d03-293">因此，默认情况下，[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]不返回任何表参数作为响应消息的一部分。</span><span class="sxs-lookup"><span data-stu-id="b5d03-293">So, by default, the [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] does not return any table parameters as part of the response message.</span></span>  
  
 <span data-ttu-id="b5d03-294">**解决方法**</span><span class="sxs-lookup"><span data-stu-id="b5d03-294">**Resolution**</span></span>  
  
 <span data-ttu-id="b5d03-295">你可以请求所需的表[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]作为响应一部分返回。</span><span class="sxs-lookup"><span data-stu-id="b5d03-295">You can request the tables that you want [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] to return as part of the response.</span></span> <span data-ttu-id="b5d03-296">就可以做到的请求消息发送到 SAP 系统的一部分提供一个空表参数。</span><span class="sxs-lookup"><span data-stu-id="b5d03-296">You can do so by providing an empty table parameter as part of the request message that you send to the SAP system.</span></span> <span data-ttu-id="b5d03-297">例如， `<table_parameter_name />`。</span><span class="sxs-lookup"><span data-stu-id="b5d03-297">For example, `<table_parameter_name />`.</span></span>  
  
##  <a name="BKMK_SAPIncorrectCreds"></a> <span data-ttu-id="b5d03-298">适配器客户端不从 SAP 接收响应</span><span class="sxs-lookup"><span data-stu-id="b5d03-298">Adapter Clients do not receive the response from SAP</span></span>
 <span data-ttu-id="b5d03-299">**问题**</span><span class="sxs-lookup"><span data-stu-id="b5d03-299">**Problem**</span></span>  
  
 <span data-ttu-id="b5d03-300">使用与适配器时[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]，如果在 WCF 自定义的凭据将发送端口不正确，不会处理请求消息。</span><span class="sxs-lookup"><span data-stu-id="b5d03-300">When using the adapters with [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)], if the credentials on the WCF-custom send port are incorrect, the request messages are not processed.</span></span> <span data-ttu-id="b5d03-301">指定正确的凭据后，将消息发送到 SAP 系统，并收到的响应。</span><span class="sxs-lookup"><span data-stu-id="b5d03-301">After you specify the correct credentials, the message is sent to the SAP system and a response is received.</span></span> <span data-ttu-id="b5d03-302">但是，响应消息不是输出连接到可用的。</span><span class="sxs-lookup"><span data-stu-id="b5d03-302">However, the response message is not available to the out port.</span></span>  
  
 <span data-ttu-id="b5d03-303">**解决方法**</span><span class="sxs-lookup"><span data-stu-id="b5d03-303">**Resolution**</span></span>  
  
 <span data-ttu-id="b5d03-304">重新启动 BizTalk 主机实例。</span><span class="sxs-lookup"><span data-stu-id="b5d03-304">Restart the BizTalk host instance.</span></span>  
  
##  <a name="BKMK_SAPInboundConn"></a> <span data-ttu-id="b5d03-305">接收来自 SAP 服务器的入站的消息的连接问题</span><span class="sxs-lookup"><span data-stu-id="b5d03-305">Connectivity issues receiving an inbound message from the SAP server</span></span>  
 <span data-ttu-id="b5d03-306">**问题**</span><span class="sxs-lookup"><span data-stu-id="b5d03-306">**Problem**</span></span>  
  
 <span data-ttu-id="b5d03-307">获取仅在接收来自使用 WCF 自定义在 SAP 服务器的入站的消息的接收端口时出现以下错误[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="b5d03-307">You get the following error only while receiving an inbound message from the SAP server using a WCF-Custom receive port for the [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)].</span></span>  
  
```  
The Messaging Engine failed to add a receive location "<location_name>" with URL "<connection URI>" to the adapter "WCF-Custom".  
Reason: "Microsoft.Adapters.SAP.RFCException: Details: ErrorCode=RFC_OK. ErrorGroup=RFC_ERROR_COMMUNICATION. SapErrorMessage=Connect to SAP gateway failed  
Connect_PM  TPNAME=<name>, GWHOST=<host>, GWSERV=<server>  
```  
  
 <span data-ttu-id="b5d03-308">但是，你将能够成功地将消息发送到 SAP 系统使用 Wcf-custom 发送端口。</span><span class="sxs-lookup"><span data-stu-id="b5d03-308">However, you are successfully able to send messages to the SAP system using a WCF-Custom send port.</span></span>  
  
 <span data-ttu-id="b5d03-309">**解决方法**</span><span class="sxs-lookup"><span data-stu-id="b5d03-309">**Resolution**</span></span>  
  
 <span data-ttu-id="b5d03-310">在其中运行适配器客户端，并且在尝试再次接收的入站的消息的同一计算机上安装 SAP GUI。</span><span class="sxs-lookup"><span data-stu-id="b5d03-310">Install the SAP GUI on the same computer where you are running the adapter client and try receiving the inbound message again.</span></span> <span data-ttu-id="b5d03-311">有关如何安装 SAP GUI 的详细信息，请参阅 SAP 文档。</span><span class="sxs-lookup"><span data-stu-id="b5d03-311">For more information about how to install the SAP GUI, refer to SAP documentation.</span></span>  
  
##  <a name="BKMK_SAPRootNode"></a> <span data-ttu-id="b5d03-312">使用 BizTalk 项目中的 RootNode TypeName 错误</span><span class="sxs-lookup"><span data-stu-id="b5d03-312">Error with RootNode TypeName in BizTalk Projects</span></span>  
 <span data-ttu-id="b5d03-313">**问题**</span><span class="sxs-lookup"><span data-stu-id="b5d03-313">**Problem**</span></span>  
  
 <span data-ttu-id="b5d03-314">中的 BizTalk 项目中[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]，则从架构生成[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]包含无效的字符或保留的字**RootNode TypeName**属性，编译项目时将发生以下错误:</span><span class="sxs-lookup"><span data-stu-id="b5d03-314">In a BizTalk project in [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)], if the schemas generated from the [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)] contains invalid characters or reserved words for the **RootNode TypeName** property, the following error will occur while compiling the project:</span></span>  
  
```  
Node <node reference> - Specify a valid .NET type name for this root node.  
The current .NET type name of this root node is invalid (it is a reserved BizTalk Keyword or is an invalid C# identifier).  
```  
  
 <span data-ttu-id="b5d03-315">**解决方法**</span><span class="sxs-lookup"><span data-stu-id="b5d03-315">**Resolution**</span></span>  
  
1.  <span data-ttu-id="b5d03-316">右键单击该错误，然后选择中引用的 rood 这样节点**属性**。</span><span class="sxs-lookup"><span data-stu-id="b5d03-316">Right-click the rood node referenced in the error and select **Properties**.</span></span>  
  
2.  <span data-ttu-id="b5d03-317">有关**RootNode TypeName**属性，删除任何非法字符或保留字，例如，点 （.）。</span><span class="sxs-lookup"><span data-stu-id="b5d03-317">For the **RootNode TypeName** property, remove any illegal characters or reserved words, for example, dot (.).</span></span>  
  
##  <a name="BKMK_SAPVS2008"></a> <span data-ttu-id="b5d03-318">无效的绑定时出现的警告在 Visual Studio 中使用适配器</span><span class="sxs-lookup"><span data-stu-id="b5d03-318">Invalid binding warning when using the adapter in Visual Studio</span></span>  
 <span data-ttu-id="b5d03-319">**问题**</span><span class="sxs-lookup"><span data-stu-id="b5d03-319">**Problem**</span></span>  
  
 <span data-ttu-id="b5d03-320">当适配器用于在 Visual Studio 中创建应用程序并打开由适配器生成的配置文件 (app.config) 时，您会看到类似于下面的警告：</span><span class="sxs-lookup"><span data-stu-id="b5d03-320">When you use the adapter to create an application in Visual Studio and you open the configuration file (app.config) generated by the adapter, you see a warning similar to the following:</span></span>  
  
```  
The element 'bindings' has invalid child element 'sapBinding'. List of possible elements expected: 'basicHttpBinding, customBinding, ...  
```  
  
 <span data-ttu-id="b5d03-321">**原因**</span><span class="sxs-lookup"><span data-stu-id="b5d03-321">**Cause**</span></span>  
  
 <span data-ttu-id="b5d03-322">会出现此警告[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]绑定， `sapBinding`，不标准绑定随附于[!INCLUDE[firstref_btsWinCommFoundation](../../includes/firstref-btswincommfoundation-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="b5d03-322">This warning appears because the [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] binding, `sapBinding`, is not a standard binding shipped with the [!INCLUDE[firstref_btsWinCommFoundation](../../includes/firstref-btswincommfoundation-md.md)].</span></span>  
  
 <span data-ttu-id="b5d03-323">**解决方法**</span><span class="sxs-lookup"><span data-stu-id="b5d03-323">**Resolution**</span></span>  
  
 <span data-ttu-id="b5d03-324">可以安全地忽略此警告。</span><span class="sxs-lookup"><span data-stu-id="b5d03-324">You can safely ignore this warning.</span></span>  
  
##  <a name="BKMK_SAPSimilarSchema"></a> <span data-ttu-id="b5d03-325">在 BizTalk Server 中的 XLANG 异常</span><span class="sxs-lookup"><span data-stu-id="b5d03-325">XLANG exception in BizTalk Server</span></span>
 <span data-ttu-id="b5d03-326">**问题**</span><span class="sxs-lookup"><span data-stu-id="b5d03-326">**Problem**</span></span>  
  
 <span data-ttu-id="b5d03-327">BizTalk Server 将引发异常，表明该应用程序找不到文档规范，因为多个架构匹配的消息类型或 XLANG 异常。</span><span class="sxs-lookup"><span data-stu-id="b5d03-327">BizTalk Server throws an XLANG exception or an exception stating that the application cannot locate the document specification because multiple schemas matched the message type.</span></span>  
  
 <span data-ttu-id="b5d03-328">**原因**</span><span class="sxs-lookup"><span data-stu-id="b5d03-328">**Cause**</span></span>  
  
 <span data-ttu-id="b5d03-329">由于以下任一发生这种情况：</span><span class="sxs-lookup"><span data-stu-id="b5d03-329">This happens because of either of the following:</span></span>  
  
- <span data-ttu-id="b5d03-330">已生成多个架构在 BizTalk Server 项目中，一个泛型操作 （例如 SendIdoc 和 ReceiveIdoc） 部署到 BizTalk Server 应用程序，然后运行应用程序来执行 SAP 系统上的相应操作。</span><span class="sxs-lookup"><span data-stu-id="b5d03-330">You have generated more than one schema of a generic operation (such as SendIdoc and ReceiveIdoc) in a BizTalk Server project, deployed it to a BizTalk Server application, and then ran the application to perform respective operations on an SAP system.</span></span> <span data-ttu-id="b5d03-331">架构是公用的因为冲突之间没有 BizTalk Server 应用程序中部署的架构。</span><span class="sxs-lookup"><span data-stu-id="b5d03-331">Because the schemas are common, there is a conflict between the schemas that are deployed in the BizTalk Server application.</span></span>  
  
- <span data-ttu-id="b5d03-332">如果多个项目，您为每个 BizTalk Server 项目生成泛型操作架构，部署到单独的同一个 BizTalk Server 应用程序托管，，然后运行应用程序或应用程序即可执行相应的每个项目对 SAP 系统的操作。</span><span class="sxs-lookup"><span data-stu-id="b5d03-332">In case of multiple projects, you have generated a generic operation schema for each of the BizTalk Server projects, deployed each project to a separate BizTalk Server application on the same host, and then ran an application or applications to perform respective operations on an SAP system.</span></span> <span data-ttu-id="b5d03-333">因为架构和程序集都是可访问 BizTalk Server 中的应用程序，则冲突之间常见的架构部署在各种 BizTalk Server 应用程序和程序集。</span><span class="sxs-lookup"><span data-stu-id="b5d03-333">Because the schemas and assemblies are accessible across the applications in BizTalk Server, there is a conflict between the common schemas deployed under various BizTalk Server applications and assemblies.</span></span>  
  
  <span data-ttu-id="b5d03-334">**解决方法**</span><span class="sxs-lookup"><span data-stu-id="b5d03-334">**Resolution**</span></span>  
  
  <span data-ttu-id="b5d03-335">BizTalk Server 应用程序使用单个泛型操作架构文件。</span><span class="sxs-lookup"><span data-stu-id="b5d03-335">Use a single generic operation schema file for a BizTalk Server application.</span></span> <span data-ttu-id="b5d03-336">如果需要在同一主机上的多个 BizTalk Server 应用程序中使用泛型操作架构，创建包含单个泛型操作架构的应用程序，然后使用 BizTalk Server 中的所有其他应用程序中的泛型操作架构。</span><span class="sxs-lookup"><span data-stu-id="b5d03-336">If you need to use a generic operation schema in multiple BizTalk Server applications on the same host, create an application containing a single generic operation schema, and then use the generic operation schema from all other applications in BizTalk Server.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b5d03-337">请参阅</span><span class="sxs-lookup"><span data-stu-id="b5d03-337">See Also</span></span>  
[<span data-ttu-id="b5d03-338">SAP 适配器疑难解答</span><span class="sxs-lookup"><span data-stu-id="b5d03-338">Troubleshoot the SAP adapter</span></span>](../../adapters-and-accelerators/adapter-sap/troubleshoot-the-sap-adapter.md)