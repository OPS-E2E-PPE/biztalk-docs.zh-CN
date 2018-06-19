---
title: 使用 BizTalk 中的 Siebel 适配器进行的操作问题故障排除 |Microsoft 文档
description: 常见的问题和解决方法为 Siebel 适配器 BizTalk 适配器包 (BAP) 中
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 74d152d9-9893-4f93-894a-350bae8be7bd
caps.latest.revision: 22
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 1ff6e36afd7cecc967069fd3ecf5414c6afdb014
ms.sourcegitcommit: 3fc338e52d5dbca2c3ea1685a2faafc7582fe23a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/01/2017
ms.locfileid: "26009630"
---
# <a name="troubleshoot-operational-issues-with-the-siebel-adapter"></a><span data-ttu-id="66561-103">与 Siebel 适配器排除操作问题</span><span class="sxs-lookup"><span data-stu-id="66561-103">Troubleshoot Operational Issues with the Siebel adapter</span></span>
<span data-ttu-id="66561-104">本部分提供有关操作问题的信息使用时可能遇到的一个集中的位置[!INCLUDE[adaptersiebel](../../includes/adaptersiebel-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="66561-104">This section provides a centralized location for information about operational issues you might encounter when using the [!INCLUDE[adaptersiebel](../../includes/adaptersiebel-md.md)].</span></span>  
  
## <a name="enabling-tracing"></a><span data-ttu-id="66561-105">启用跟踪</span><span class="sxs-lookup"><span data-stu-id="66561-105">Enabling Tracing</span></span>  
 <span data-ttu-id="66561-106">有关跟踪中的支持信息[!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]，请参阅[诊断跟踪和消息日志记录为 Siebel 适配器](../../adapters-and-accelerators/adapter-siebel/diagnostic-tracing-and-message-logging-for-the-siebel-adapter.md)。</span><span class="sxs-lookup"><span data-stu-id="66561-106">For information about tracing support in the [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)], see [Diagnostic Tracing and Message Logging for the Siebel adapter](../../adapters-and-accelerators/adapter-siebel/diagnostic-tracing-and-message-logging-for-the-siebel-adapter.md).</span></span>  
  
## <a name="known-issues"></a><span data-ttu-id="66561-107">已知问题</span><span class="sxs-lookup"><span data-stu-id="66561-107">Known Issues</span></span>  
 <span data-ttu-id="66561-108">以下是一些问题和建议的解决方案使用时，你可能会遇到[!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="66561-108">The following are some issues and recommended solutions that you might encounter while using the [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)].</span></span>  
  
  
###  <a name="BKMK_SiebelBindingError"></a><span data-ttu-id="66561-109">在加载适配器绑定错误</span><span class="sxs-lookup"><span data-stu-id="66561-109">Error in loading the adapter bindings</span></span>  
 <span data-ttu-id="66561-110">**问题**</span><span class="sxs-lookup"><span data-stu-id="66561-110">**Problem**</span></span>  
  
 <span data-ttu-id="66561-111">当你尝试启动[!INCLUDE[addadapterservreflong](../../includes/addadapterservreflong-md.md)]或[!INCLUDE[consumeadapterservlong](../../includes/consumeadapterservlong-md.md)]，GUI 将报告以下错误：</span><span class="sxs-lookup"><span data-stu-id="66561-111">When you try to start the [!INCLUDE[addadapterservreflong](../../includes/addadapterservreflong-md.md)] or the [!INCLUDE[consumeadapterservlong](../../includes/consumeadapterservlong-md.md)], the GUI gives the following error:</span></span>  
  
```  
There was an error loading the binding, <binding name>, from your system configuration.  
ConfigurationErrorsException: Exception has been thrown by the target of an invocation.  
```  
  
 <span data-ttu-id="66561-112">**可能的原因**</span><span class="sxs-lookup"><span data-stu-id="66561-112">**Cause**</span></span>  
  
 <span data-ttu-id="66561-113">当你启动[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]或[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]，WCF 加载所有已安装适配器的适配器绑定。</span><span class="sxs-lookup"><span data-stu-id="66561-113">When you start the [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)] or the [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)], WCF loads the adapter bindings for all the installed adapters.</span></span> <span data-ttu-id="66561-114">反过来，适配器绑定都依赖于特定的企业应用程序客户端软件。</span><span class="sxs-lookup"><span data-stu-id="66561-114">In turn, the adapter bindings are dependent on the specific enterprise application client software.</span></span> <span data-ttu-id="66561-115">因此，您会受到此问题的一个或两个原因如下：</span><span class="sxs-lookup"><span data-stu-id="66561-115">So, you could face this issue for one or both of the following reasons:</span></span>  
  
-   <span data-ttu-id="66561-116">在安装适配器的计算机上未安装所需的 LOB 客户端软件。</span><span class="sxs-lookup"><span data-stu-id="66561-116">The required LOB client software is not installed on the computer where you installed the adapter.</span></span>  
  
-   <span data-ttu-id="66561-117">未将适配器安装中的所有适配器的"典型"或"完成"安装[!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="66561-117">You did a "Typical" or "Complete" installation of the adapter, which installs all the adapters in the [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)].</span></span> <span data-ttu-id="66561-118">但是，可能只有一个企业应用程序安装的客户端库。</span><span class="sxs-lookup"><span data-stu-id="66561-118">However, the client libraries might be installed for only one enterprise application.</span></span> <span data-ttu-id="66561-119">因此，GUI 无法加载其他适配器的绑定。</span><span class="sxs-lookup"><span data-stu-id="66561-119">As a result, the GUI fails to load the bindings for the other adapters.</span></span>  
  
 <span data-ttu-id="66561-120">**解决方法**</span><span class="sxs-lookup"><span data-stu-id="66561-120">**Resolution**</span></span>  
  
-   <span data-ttu-id="66561-121">请确保在你安装的计算机上安装了必需的客户端版本[!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="66561-121">Make sure the required client versions are installed on the computer where you installed the [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)].</span></span>  
  
-   <span data-ttu-id="66561-122">请确保执行适配器安装需要适配器的自定义安装。</span><span class="sxs-lookup"><span data-stu-id="66561-122">Make sure you do a custom installation of the adapters to install only the adapter you need.</span></span>  
  
###  <a name="BKMK_SiebelDispAdap"></a><span data-ttu-id="66561-123">Siebel 适配器不会显示在列表中在 BizTalk Server 管理控制台中的适配器</span><span class="sxs-lookup"><span data-stu-id="66561-123">The Siebel adapter does not display in the list of adapters in BizTalk Server Administration console</span></span>  
 <span data-ttu-id="66561-124">**问题**</span><span class="sxs-lookup"><span data-stu-id="66561-124">**Problem**</span></span>  
  
 <span data-ttu-id="66561-125">与不同的是较早版本附带的适配器[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]、[!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]所附带[!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)]未显示在列表中的 BizTalk Server 管理控制台中的适配器。</span><span class="sxs-lookup"><span data-stu-id="66561-125">Unlike the earlier version of the adapters that shipped with [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)], the [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)] that shipped with [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)] does not show up in the list of adapters in the BizTalk Server Administration console.</span></span>  
  
 <span data-ttu-id="66561-126">**可能的原因**</span><span class="sxs-lookup"><span data-stu-id="66561-126">**Cause**</span></span>  
  
 <span data-ttu-id="66561-127">最新[!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]是 WCF 自定义绑定。</span><span class="sxs-lookup"><span data-stu-id="66561-127">The latest [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)] is a WCF custom binding.</span></span> <span data-ttu-id="66561-128">因此，尽管[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理控制台显示[!INCLUDE[wcfadapter_short](../../includes/wcfadapter-short-md.md)]，它不会显示 WCF 自定义绑定，并因此，不会显示基于 WCF 的[!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="66561-128">So, although the [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] Administration console displays the [!INCLUDE[wcfadapter_short](../../includes/wcfadapter-short-md.md)], it does not display the WCF custom bindings and hence, does not display the WCF-based [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)].</span></span>  
  
 <span data-ttu-id="66561-129">**解决方法**</span><span class="sxs-lookup"><span data-stu-id="66561-129">**Resolution**</span></span>  
  
 <span data-ttu-id="66561-130">你可以显式添加[!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]到[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理控制台中所述的步骤[将 Siebel 适配器添加到 BizTalk Server 管理控制台](../../adapters-and-accelerators/adapter-siebel/add-the-siebel-adapter-to-biztalk-server-administration-console.md)。</span><span class="sxs-lookup"><span data-stu-id="66561-130">You can explicitly add the [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)] to the [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] Administration console by following the steps mentioned in [Add the Siebel Adapter to BizTalk Server Administration Console](../../adapters-and-accelerators/adapter-siebel/add-the-siebel-adapter-to-biztalk-server-administration-console.md).</span></span>  
  
###  <a name="BKMK_SiebelConnecting"></a><span data-ttu-id="66561-131">连接到 Siebel 系统时出错</span><span class="sxs-lookup"><span data-stu-id="66561-131">Error while connecting to the Siebel system</span></span>  
 <span data-ttu-id="66561-132">**问题**</span><span class="sxs-lookup"><span data-stu-id="66561-132">**Problem**</span></span>  
  
 <span data-ttu-id="66561-133">[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]或[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]当你尝试连接到 Siebel 系统时将报告以下错误：</span><span class="sxs-lookup"><span data-stu-id="66561-133">The [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)] or the [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)] gives the following error when you try to connect to the Siebel system:</span></span>  
  
```  
Connecting to the system LOB has failed. Retrieving the COM class factory for component with CLSID {ID} failed due to the following error: 80040154  
```  
  
 <span data-ttu-id="66561-134">**可能的原因**</span><span class="sxs-lookup"><span data-stu-id="66561-134">**Cause**</span></span>  
  
 <span data-ttu-id="66561-135">计算机上可能未安装 Siebel Web 客户端。</span><span class="sxs-lookup"><span data-stu-id="66561-135">The Siebel Web client might not be installed on the computer.</span></span>  
  
 <span data-ttu-id="66561-136">**解决方法**</span><span class="sxs-lookup"><span data-stu-id="66561-136">**Resolution**</span></span>  
  
 <span data-ttu-id="66561-137">请确保在计算机上安装 Siebel Web 客户端的受支持的版本。</span><span class="sxs-lookup"><span data-stu-id="66561-137">Make sure the supported version of the Siebel Web client is installed on the computer.</span></span> <span data-ttu-id="66561-138">请参阅安装指南以支持的客户端和的 Siebel server 版本。</span><span class="sxs-lookup"><span data-stu-id="66561-138">Refer to the installation guide for supported client and server versions for Siebel.</span></span> <span data-ttu-id="66561-139">安装指南位于\<系统驱动器\>: files\microsoft [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)]\Documents。</span><span class="sxs-lookup"><span data-stu-id="66561-139">The installation guide is available at \<system drive\>:\Program Files\Microsoft [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)]\Documents.</span></span>  
  
###  <a name="BKMK_SiebelXMLRetrieve"></a><span data-ttu-id="66561-140">具有多个 65536 节点检索 Xml 时的错误</span><span class="sxs-lookup"><span data-stu-id="66561-140">Error while retrieving XMLs with more than 65536 nodes</span></span>  
 <span data-ttu-id="66561-141">**问题**</span><span class="sxs-lookup"><span data-stu-id="66561-141">**Problem**</span></span>  
  
 <span data-ttu-id="66561-142">适配器将检索具有多个 65536 节点的 XML 输出时报告以下错误。</span><span class="sxs-lookup"><span data-stu-id="66561-142">The adapter gives the following error while retrieving XML output that has more than 65536 nodes.</span></span>  
  
```  
Maximum number of items that can be serialized or deserialized in an object graph is '65536'.  
Change the object graph or increase the MaxItemsInObjectGraph quota.  
```  
  
 <span data-ttu-id="66561-143">**可能的原因**</span><span class="sxs-lookup"><span data-stu-id="66561-143">**Cause**</span></span>  
  
 <span data-ttu-id="66561-144">适配器不能序列化和反序列化具有多个 65536 的项的对象。</span><span class="sxs-lookup"><span data-stu-id="66561-144">The adapter cannot serialize and deserialize an object with more than 65536 items.</span></span>  
  
 <span data-ttu-id="66561-145">**解决方法**</span><span class="sxs-lookup"><span data-stu-id="66561-145">**Resolution**</span></span>  
  
 <span data-ttu-id="66561-146">可以通过设置来解决此问题`maxItemsInObjectGraph`参数。</span><span class="sxs-lookup"><span data-stu-id="66561-146">You can fix this issue by setting the `maxItemsInObjectGraph` parameter.</span></span> <span data-ttu-id="66561-147">可在任何以下两种方式将其设置：</span><span class="sxs-lookup"><span data-stu-id="66561-147">You can set this in any of the following two ways:</span></span>  
  
-   <span data-ttu-id="66561-148">将此参数设置通过更改`maxItemsInObjectGraph`中的参数`ServiceBehavior`服务类中的属性。</span><span class="sxs-lookup"><span data-stu-id="66561-148">Set this parameter by changing the `maxItemsInObjectGraph` parameter in the `ServiceBehavior` attribute on your service class.</span></span>  
  
-   <span data-ttu-id="66561-149">将以下代码添加到你的应用程序的 app.config 文件。</span><span class="sxs-lookup"><span data-stu-id="66561-149">Add the following to your application's app.config file.</span></span>  
  
    ```  
    <behaviors>  
      <endpointBehaviors>  
        <behavior name="NewBehavior">  
          <dataContractSerializer maxItemsInObjectGraph="65536000" />  
        </behavior>  
      </endpointBehaviors>  
    </behaviors>  
    ```  
  
 <span data-ttu-id="66561-150">示例 app.config 将如下所示：</span><span class="sxs-lookup"><span data-stu-id="66561-150">A sample app.config will look like:</span></span>  
  
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
      <endpoint   behaviorConfiguration="NewBehavior" binding="siebelBinding"  
       contract="IOutboundContract" name="siebel_ICalculator" />  
    </client>  
  </system.serviceModel>  
</configuration>  
```  
  
###  <a name="BKMK_SiebelConnURI"></a><span data-ttu-id="66561-151">在 BizTalk 中指定的 WCF 自定义端口的连接 URI 时出错</span><span class="sxs-lookup"><span data-stu-id="66561-151">Error while specifying a connection URI for a WCF-Custom port in BizTalk</span></span>  
 <span data-ttu-id="66561-152">**问题**</span><span class="sxs-lookup"><span data-stu-id="66561-152">**Problem**</span></span>  
  
 [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]<span data-ttu-id="66561-153">指定连接 URI 以连接到 Siebel 系统时，则报告以下错误。</span><span class="sxs-lookup"><span data-stu-id="66561-153"> gives the following error when you specify a connection URI to connect to the Siebel system.</span></span>  
  
```  
Error saving properties.  
(System.ArgumentException) The specified address is invalid.  
(System.ArgumentException) Invalid address;  
"<connection URI>" is not a well-formed absolute uri.  
```  
  
 <span data-ttu-id="66561-154">**可能的原因**</span><span class="sxs-lookup"><span data-stu-id="66561-154">**Cause**</span></span>  
  
 <span data-ttu-id="66561-155">连接 URI 不符合标准的编码格式。</span><span class="sxs-lookup"><span data-stu-id="66561-155">The connection URI does not adhere to the standard encoding format.</span></span> <span data-ttu-id="66561-156">例如，参数的值可能包含一个空格。</span><span class="sxs-lookup"><span data-stu-id="66561-156">For example, the value for a parameter might contain a space.</span></span>  
  
 <span data-ttu-id="66561-157">**解决方法**</span><span class="sxs-lookup"><span data-stu-id="66561-157">**Resolution**</span></span>  
  
 <span data-ttu-id="66561-158">请确保你指定的 URI 符合标准的编码格式的连接。</span><span class="sxs-lookup"><span data-stu-id="66561-158">Make sure the connection URI you specify adheres to the standard encoding format.</span></span> <span data-ttu-id="66561-159">例如，必须通过"%20"替换为空格。</span><span class="sxs-lookup"><span data-stu-id="66561-159">For example, a blank space must be replaced by "%20".</span></span>  
  
###  <a name="BKMK_SiebelPerfOps"></a><span data-ttu-id="66561-160">执行 Siebel 系统上的操作时出错</span><span class="sxs-lookup"><span data-stu-id="66561-160">Error while performing operation on the Siebel system</span></span>  
 <span data-ttu-id="66561-161">**问题**</span><span class="sxs-lookup"><span data-stu-id="66561-161">**Problem**</span></span>  
  
 <span data-ttu-id="66561-162">适配器执行针对 Siebel 系统使用的任何操作时将报告以下错误[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="66561-162">The adapter gives the following error when performing any operation on the Siebel system using [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)].</span></span>  
  
-   <span data-ttu-id="66561-163">**BizTalk server**</span><span class="sxs-lookup"><span data-stu-id="66561-163">**For BizTalk Server**</span></span>  
  
    ```  
    System.ArgumentNullException: Value cannot be null.  
    ```  
  
 <span data-ttu-id="66561-164">**可能的原因**</span><span class="sxs-lookup"><span data-stu-id="66561-164">**Cause**</span></span>  
  
 <span data-ttu-id="66561-165">未指定消息的 WCF 操作。</span><span class="sxs-lookup"><span data-stu-id="66561-165">The WCF action for the message is not specified.</span></span> <span data-ttu-id="66561-166">WCF 需要为每个操作，在 LOB 应用程序上执行的操作会告知适配器指定的 SOAP 操作。</span><span class="sxs-lookup"><span data-stu-id="66561-166">WCF requires a SOAP action to be specified for every operation, which informs the adapter about the operation to be performed on the LOB application.</span></span>  
  
 <span data-ttu-id="66561-167">**解决方法**</span><span class="sxs-lookup"><span data-stu-id="66561-167">**Resolution**</span></span>  
  
 <span data-ttu-id="66561-168">指定的 SOAP 操作中发送端口或 BizTalk 业务流程中的消息上下文属性。</span><span class="sxs-lookup"><span data-stu-id="66561-168">Specify the SOAP action in the send port or as a message context property in a BizTalk orchestration.</span></span> <span data-ttu-id="66561-169">有关说明，请参阅[配置用于 Siebel 的 SOAP 操作](../../adapters-and-accelerators/adapter-siebel/configure-the-soap-action-for-siebel.md)。</span><span class="sxs-lookup"><span data-stu-id="66561-169">For instructions, see [Configure the SOAP action for Siebel](../../adapters-and-accelerators/adapter-siebel/configure-the-soap-action-for-siebel.md).</span></span> <span data-ttu-id="66561-170">请参阅[消息和消息架构](messages-and-message-schemas-for-siebel-adapter-in-biztalk.md)有关每个操作的操作的列表。</span><span class="sxs-lookup"><span data-stu-id="66561-170">See [Messages and message schemas](messages-and-message-schemas-for-siebel-adapter-in-biztalk.md) for a list of actions for each operation.</span></span>  
  
###  <a name="BKMK_SiebelXmlParsing"></a><span data-ttu-id="66561-171">由于指定的操作中的不正确的操作名称 XmlReaderParsingException</span><span class="sxs-lookup"><span data-stu-id="66561-171">XmlReaderParsingException due to an incorrect operation name in the specified action</span></span>  
 <span data-ttu-id="66561-172">**问题**</span><span class="sxs-lookup"><span data-stu-id="66561-172">**Problem**</span></span>  
  
 <span data-ttu-id="66561-173">将消息发送到 Siebel 系统时，BizTalk Server 管理控制台提供了以下错误：</span><span class="sxs-lookup"><span data-stu-id="66561-173">The BizTalk Server Administration console gives the following error when sending messages to a Siebel system:</span></span>  
  
```  
Microsoft.ServiceModel.Channels.Common.XmlReaderParsingException: Invalid argument:  
<BtsActionMapping xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xmlns:xsd="http://www.w3.org/2001/XMLSchema">  
  <Operation Name="<operation_name>" Action="<action>" />  
</BtsActionMapping>  
```  
  
 <span data-ttu-id="66561-174">**可能的原因**</span><span class="sxs-lookup"><span data-stu-id="66561-174">**Cause**</span></span>  
  
 <span data-ttu-id="66561-175">如果通过导入创建的端口绑定文件中配置 WCF 自定义端口[!INCLUDE[consumeadapterservlong](../../includes/consumeadapterservlong-md.md)]，采用以下格式指定端口中的操作：</span><span class="sxs-lookup"><span data-stu-id="66561-175">If you configure a WCF-Custom port by importing the port binding file created by the [!INCLUDE[consumeadapterservlong](../../includes/consumeadapterservlong-md.md)], the action in the port is specified in the following format:</span></span>  
  
```  
<BtsActionMapping>  
  <Operation Name="Op1" Action="http://MyService/Svc/Op1" />  
</BtsActionMapping>  
```  
  
 <span data-ttu-id="66561-176">在前面的格式中，操作名称受生成架构时选择该操作。</span><span class="sxs-lookup"><span data-stu-id="66561-176">In the preceding format, the operation name is governed by the operation you chose while generating the schema.</span></span> <span data-ttu-id="66561-177">例如，如果你生成 Siebel 在业务组件上的查询操作的架构，则操作中的操作名称将"查询"。</span><span class="sxs-lookup"><span data-stu-id="66561-177">For example, if you generated schema for a Query operation on a Siebel business component, the operation name in the action will be "Query".</span></span> <span data-ttu-id="66561-178">但是中的逻辑端口的操作名称创建在 BizTalk 业务流程中[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]可能不同。</span><span class="sxs-lookup"><span data-stu-id="66561-178">However, the operation name in the logical port created in the BizTalk orchestration in [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)] might be different.</span></span>  
  
 <span data-ttu-id="66561-179">**解决方法**</span><span class="sxs-lookup"><span data-stu-id="66561-179">**Resolution**</span></span>  
  
 <span data-ttu-id="66561-180">请确保操作名称在这两个逻辑端口 (在 BizTalk 业务流程中[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]) 和 （在 BizTalk Server 管理控制台） 的物理端口相同。</span><span class="sxs-lookup"><span data-stu-id="66561-180">Make sure the operation names in both the logical port (in the BizTalk orchestration in [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]) and the physical port (in BizTalk Server Administration console) are the same.</span></span>  
  
###  <a name="BKMK_SiebelTerminate"></a><span data-ttu-id="66561-181">使用在 Siebel 适配器的应用程序不会终止</span><span class="sxs-lookup"><span data-stu-id="66561-181">Application using the Siebel adapter does not terminate</span></span>  
 <span data-ttu-id="66561-182">**问题**</span><span class="sxs-lookup"><span data-stu-id="66561-182">**Problem**</span></span>  
  
 <span data-ttu-id="66561-183">使用的应用程序[!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]与 Siebel 7.5 版客户端不会终止。</span><span class="sxs-lookup"><span data-stu-id="66561-183">An application that uses the [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)] with Siebel client version 7.5 does not terminate.</span></span>  
  
 <span data-ttu-id="66561-184">**可能的原因**</span><span class="sxs-lookup"><span data-stu-id="66561-184">**Cause**</span></span>  
  
 <span data-ttu-id="66561-185">这是因为 Siebel 客户端问题其中过程不会终止时从 Siebel 服务器注销。</span><span class="sxs-lookup"><span data-stu-id="66561-185">This is because of a Siebel client issue where the process does not terminate when logging off from a Siebel server.</span></span>  
  
 <span data-ttu-id="66561-186">**解决方法**</span><span class="sxs-lookup"><span data-stu-id="66561-186">**Resolution**</span></span>  
  
 <span data-ttu-id="66561-187">请确保你具有 7.5.3.17 为 Siebel 服务器，以及快速修复 QF0H05 安装的修补程序。</span><span class="sxs-lookup"><span data-stu-id="66561-187">Make sure you have the patch 7.5.3.17 installed for the Siebel server, along with the quick fix QF0H05.</span></span>  
  
###  <a name="BKMK_SiebelHang"></a><span data-ttu-id="66561-188">Siebel 服务器重新启动，则可能会挂起 Siebel 适配器</span><span class="sxs-lookup"><span data-stu-id="66561-188">Siebel adapter may hang if the Siebel server is restarted</span></span>  
 <span data-ttu-id="66561-189">**问题**</span><span class="sxs-lookup"><span data-stu-id="66561-189">**Problem**</span></span>  
  
 <span data-ttu-id="66561-190">如果 Siebel 服务器重新启动时[!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]将消息发送到使用 Siebel 服务器，[!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]可能会挂起。</span><span class="sxs-lookup"><span data-stu-id="66561-190">If the Siebel server is restarted while the [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)] is sending a message to the Siebel server using, the [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)] may hang.</span></span>  
  
 <span data-ttu-id="66561-191">**解决方法**</span><span class="sxs-lookup"><span data-stu-id="66561-191">**Resolution**</span></span>  
  
 <span data-ttu-id="66561-192">重新启动 BizTalk 应用程序主机实例。</span><span class="sxs-lookup"><span data-stu-id="66561-192">Restart the BizTalk application host instance.</span></span> <span data-ttu-id="66561-193">若要这样做从[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理控制台中的，在控制台树中展开**BizTalk 组**，展开**平台设置**，然后单击**主机实例**。</span><span class="sxs-lookup"><span data-stu-id="66561-193">To do so from the [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] Administration console, in the console tree expand **BizTalk Group**, expand **Platform Settings**, and then click **Host Instances**.</span></span> <span data-ttu-id="66561-194">从右窗格中，右键单击主机名称，然后选择**重新启动**。</span><span class="sxs-lookup"><span data-stu-id="66561-194">From the right pane, right-click the host name, and then select **Restart**.</span></span>  
  
###  <a name="BKMK_SiebelAction"></a><span data-ttu-id="66561-195">适配器无法识别的物理端口上的操作，即使使用适配器服务外接程序生成的绑定文件用于创建端口</span><span class="sxs-lookup"><span data-stu-id="66561-195">The adapter does not recognize the action on the physical port even though you use the binding file generated by the Consume Adapter Service add-in to create the ports</span></span>  
 <span data-ttu-id="66561-196">**问题**</span><span class="sxs-lookup"><span data-stu-id="66561-196">**Problem**</span></span>  
  
 <span data-ttu-id="66561-197">在使用后[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]若要生成 Siebel 系统上的特定操作的架构外, 接程序还会创建端口绑定文件。</span><span class="sxs-lookup"><span data-stu-id="66561-197">After you use the [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)] to generate schema for a specific operation on the Siebel system, the add-in also creates a port binding file.</span></span> <span data-ttu-id="66561-198">可以导入此文件使用绑定的[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]BizTalk Server 中创建的物理端口的管理控制台。</span><span class="sxs-lookup"><span data-stu-id="66561-198">You can import this binding file using the [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] Administration console to create physical ports in BizTalk Server.</span></span> <span data-ttu-id="66561-199">但是，当消息发送到 Siebel 系统使用此类端口时，该适配器将无法了解在端口上指定的操作，并提供了类似于以下错误：</span><span class="sxs-lookup"><span data-stu-id="66561-199">However, when you send messages to the Siebel system using such ports, the adapter fails to understand the action specified on the port and gives an error similar to the following:</span></span>  
  
```  
Microsoft.ServiceModel.Channels.Common.UnsupportedOperationException: Incorrect Action   
<BtsActionMapping xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xmlns:xsd="http://www.w3.org/2001/XMLSchema">  
  <Operation Name="<op_name>" Action="<action>" />  
</BtsActionMapping>. Correct the specified Action, or refer to the documentation on the allowed formats for the Actions.  
```  
  
 <span data-ttu-id="66561-200">**可能的原因**</span><span class="sxs-lookup"><span data-stu-id="66561-200">**Cause**</span></span>  
  
 <span data-ttu-id="66561-201">在创建逻辑端口 BizTalk 业务流程中时，指定这些端口上的操作的某些名称，或只需使用如 Operation_1、 Operation_2 等的默认名称。但是，在生成的绑定文件[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]，操作名称是为其生成元数据操作的名称相同。</span><span class="sxs-lookup"><span data-stu-id="66561-201">When you create logical ports in a BizTalk orchestration, you specify certain names for the operations on those ports or you just use the default names like Operation_1, Operation_2, etc. However, in the binding file generated by the [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)], the operation name is same as the name of the operation for which you generate metadata.</span></span> <span data-ttu-id="66561-202">例如，如果你生成帐户在业务组件上的插入操作的元数据，操作将设置为以下：</span><span class="sxs-lookup"><span data-stu-id="66561-202">For example, if you generate metadata for Insert operation on the Account business component, the action will be set to the following:</span></span>  
  
```  
<Operation Name="Insert" Action="http://Microsoft.LobServices.Siebel/2007/03/BusinessObjects/Account/Account/Insert" />  
```  
  
 <span data-ttu-id="66561-203">当你导入的绑定文件时，物理端口设置相同的操作。</span><span class="sxs-lookup"><span data-stu-id="66561-203">When you import the binding file, the same action is set on physical port.</span></span> <span data-ttu-id="66561-204">因此，逻辑端口 （Operation_1、 Operation_2 等） 上的操作名称与上的物理端口，从而导致错误的操作中指定的操作名称不匹配。</span><span class="sxs-lookup"><span data-stu-id="66561-204">So, the operation names on the logical port (Operation_1, Operation_2, etc.) do not match the operation names specified in the action on the physical port, resulting in an error.</span></span>  
  
 <span data-ttu-id="66561-205">**解决方法**</span><span class="sxs-lookup"><span data-stu-id="66561-205">**Resolution**</span></span>  
  
 <span data-ttu-id="66561-206">请确保逻辑端口中的操作名称指定为中的物理端口的操作的一部分的操作名称相同。</span><span class="sxs-lookup"><span data-stu-id="66561-206">Make sure the operation name in the logical port is the same as the operation name specified as part of the action in the physical port.</span></span> <span data-ttu-id="66561-207">执行以下操作之一：</span><span class="sxs-lookup"><span data-stu-id="66561-207">Do one of the following:</span></span>  
  
-   <span data-ttu-id="66561-208">对为其生成元数据，例如插入操作从 Operation_1 等更改 BizTalk 业务流程中的逻辑端口中的操作名称。</span><span class="sxs-lookup"><span data-stu-id="66561-208">Change the operation name in the logical port in BizTalk orchestration from Operation_1, etc. to the operation for which you generate metadata, for example Insert.</span></span>  
  
-   <span data-ttu-id="66561-209">将中的物理端口上的操作的操作名称更改为中的逻辑端口的操作名称。</span><span class="sxs-lookup"><span data-stu-id="66561-209">Change the operation name in the action on the physical port to the operation name in the logical port.</span></span> <span data-ttu-id="66561-210">例如，你无法更改中类似于下面的物理端口的操作：</span><span class="sxs-lookup"><span data-stu-id="66561-210">For example, you could change the action in the physical port to resemble the following:</span></span>  
  
    ```  
    <Operation Name="Operation_1" Action="http://Microsoft.LobServices.Siebel/2007/03/BusinessObjects/Account/Account/Insert" />  
    ```  
  
###  <a name="BKMK_SiebelXMLEncode"></a><span data-ttu-id="66561-211">Siebel 适配器不处理使用名称中的 XML 编码字符串的 Siebel 对象</span><span class="sxs-lookup"><span data-stu-id="66561-211">Siebel adapter does not handle Siebel objects with XML encoded strings in the name</span></span>  
 <span data-ttu-id="66561-212">**问题**</span><span class="sxs-lookup"><span data-stu-id="66561-212">**Problem**</span></span>  
  
 <span data-ttu-id="66561-213">[!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]无法执行涉及其名称中包含编码的 XML 字符串的 Siebel 对象 （业务对象、 业务组件、 业务服务、 选择列表、 方法、 字段、 自变量、 等） 的操作。</span><span class="sxs-lookup"><span data-stu-id="66561-213">The [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)] cannot perform operations involving Siebel objects (business objects, business components, business services, picklist, methods, fields, arguments, etc) that have XML encoded strings in their name.</span></span> <span data-ttu-id="66561-214">例如，[!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]将不能调用具有名称 Time_x0020_Stamp 的业务服务方法。</span><span class="sxs-lookup"><span data-stu-id="66561-214">For example, the [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)] will not be able to invoke a business service method with the name Time_x0020_Stamp.</span></span>  
  
 <span data-ttu-id="66561-215">**解决方法**</span><span class="sxs-lookup"><span data-stu-id="66561-215">**Resolution**</span></span>  
  
 <span data-ttu-id="66561-216">请确保 Siebel 对象不包含其名称中编码的 XML 字符串。</span><span class="sxs-lookup"><span data-stu-id="66561-216">Make sure the Siebel objects do not contain XML encoded strings in their name.</span></span>  
  
###  <a name="BKMK_SiebelRootNode"></a><span data-ttu-id="66561-217">与 RootNode TypeName BizTalk 项目中的错误</span><span class="sxs-lookup"><span data-stu-id="66561-217">Error with RootNode TypeName in BizTalk Projects</span></span>  
 <span data-ttu-id="66561-218">**问题**</span><span class="sxs-lookup"><span data-stu-id="66561-218">**Problem**</span></span>  
  
 <span data-ttu-id="66561-219">在 BizTalk 项目中[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]，如果从架构生成[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]包含无效字符或保留的字**RootNode TypeName**属性，编译项目时将出现以下错误:</span><span class="sxs-lookup"><span data-stu-id="66561-219">In a BizTalk project in [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)], if the schemas generated from the [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)] contains invalid characters or reserved words for the **RootNode TypeName** property, the following error will occur while compiling the project:</span></span>  
  
```  
Node <node reference> - Specify a valid .NET type name for this root node.  
The current .NET type name of this root node is invalid (it is a reserved BizTalk Keyword or is an invalid C# identifier).  
```  
  
 <span data-ttu-id="66561-220">**解决方法**</span><span class="sxs-lookup"><span data-stu-id="66561-220">**Resolution**</span></span>  
  
1.  <span data-ttu-id="66561-221">右键单击该错误并选择中引用的 rood 节点**属性**。</span><span class="sxs-lookup"><span data-stu-id="66561-221">Right-click the rood node referenced in the error and select **Properties**.</span></span>  
  
2.  <span data-ttu-id="66561-222">有关**RootNode TypeName**属性，删除任何非法字符或保留字，例如，圆点 （.）。</span><span class="sxs-lookup"><span data-stu-id="66561-222">For the **RootNode TypeName** property, remove any illegal characters or reserved words, for example, dot (.).</span></span>  
  
###  <a name="BKMK_SiebelVS2008"></a><span data-ttu-id="66561-223">使用 Visual Studio 中的适配器时出现的无效的绑定警告</span><span class="sxs-lookup"><span data-stu-id="66561-223">Invalid binding warning when using the adapter in Visual Studio</span></span>  
 <span data-ttu-id="66561-224">**问题**</span><span class="sxs-lookup"><span data-stu-id="66561-224">**Problem**</span></span>  
  
 <span data-ttu-id="66561-225">当你使用该适配器在 Visual Studio 中创建应用程序并打开生成的适配器的配置文件 (app.config) 时，你将看到类似于以下警告：</span><span class="sxs-lookup"><span data-stu-id="66561-225">When you use the adapter to create an application in Visual Studio and you open the configuration file (app.config) generated by the adapter, you see a warning similar to the following:</span></span>  
  
```  
The element 'bindings' has invalid child element 'siebelBinding'. List of possible elements expected: 'basicHttpBinding, customBinding, ...  
```  
  
 <span data-ttu-id="66561-226">**可能的原因**</span><span class="sxs-lookup"><span data-stu-id="66561-226">**Cause**</span></span>  
  
 <span data-ttu-id="66561-227">由于会出现此警告[!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]绑定， `siebelBinding`，不标准绑定随[!INCLUDE[firstref_btsWinCommFoundation](../../includes/firstref-btswincommfoundation-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="66561-227">This warning appears because the [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)] binding, `siebelBinding`, is not a standard binding shipped with the [!INCLUDE[firstref_btsWinCommFoundation](../../includes/firstref-btswincommfoundation-md.md)].</span></span>  
  
 <span data-ttu-id="66561-228">**解决方法**</span><span class="sxs-lookup"><span data-stu-id="66561-228">**Resolution**</span></span>  
  
 <span data-ttu-id="66561-229">可以安全地忽略此警告。</span><span class="sxs-lookup"><span data-stu-id="66561-229">You can safely ignore this warning.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="66561-230">另请参阅</span><span class="sxs-lookup"><span data-stu-id="66561-230">See Also</span></span>  
[<span data-ttu-id="66561-231">解决在 Siebel 适配器</span><span class="sxs-lookup"><span data-stu-id="66561-231">Troubleshoot the Siebel adapter</span></span>](../../adapters-and-accelerators/adapter-siebel/troubleshoot-the-siebel-adapter.md)