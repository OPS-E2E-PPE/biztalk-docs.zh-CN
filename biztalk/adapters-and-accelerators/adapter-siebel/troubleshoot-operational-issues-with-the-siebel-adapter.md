---
title: 使用 Siebel 适配器在 BizTalk 中进行的操作问题故障排除 |Microsoft Docs
description: 常见的问题和 Siebel 适配器的 BizTalk 适配器包 (BAP) 中的解决方法
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
ms.openlocfilehash: 5d17e325465ce5aa575a6d499aa6b8bf73e07696
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36978934"
---
# <a name="troubleshoot-operational-issues-with-the-siebel-adapter"></a><span data-ttu-id="d1ded-103">使用 Siebel 适配器进行的操作问题故障排除</span><span class="sxs-lookup"><span data-stu-id="d1ded-103">Troubleshoot Operational Issues with the Siebel adapter</span></span>
<span data-ttu-id="d1ded-104">本部分提供有关操作问题的信息使用时可能遇到的一个集中的位置[!INCLUDE[adaptersiebel](../../includes/adaptersiebel-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="d1ded-104">This section provides a centralized location for information about operational issues you might encounter when using the [!INCLUDE[adaptersiebel](../../includes/adaptersiebel-md.md)].</span></span>  
  
## <a name="enabling-tracing"></a><span data-ttu-id="d1ded-105">启用跟踪</span><span class="sxs-lookup"><span data-stu-id="d1ded-105">Enabling Tracing</span></span>  
 <span data-ttu-id="d1ded-106">有关跟踪中的支持信息[!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]，请参阅[诊断跟踪和消息日志记录 Siebel 适配器的](../../adapters-and-accelerators/adapter-siebel/diagnostic-tracing-and-message-logging-for-the-siebel-adapter.md)。</span><span class="sxs-lookup"><span data-stu-id="d1ded-106">For information about tracing support in the [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)], see [Diagnostic Tracing and Message Logging for the Siebel adapter](../../adapters-and-accelerators/adapter-siebel/diagnostic-tracing-and-message-logging-for-the-siebel-adapter.md).</span></span>  
  
## <a name="known-issues"></a><span data-ttu-id="d1ded-107">已知问题</span><span class="sxs-lookup"><span data-stu-id="d1ded-107">Known Issues</span></span>  
 <span data-ttu-id="d1ded-108">以下是一些问题和建议的解决方案使用时可能遇到[!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="d1ded-108">The following are some issues and recommended solutions that you might encounter while using the [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)].</span></span>  
  
  
###  <a name="BKMK_SiebelBindingError"></a> <span data-ttu-id="d1ded-109">加载适配器绑定时出错</span><span class="sxs-lookup"><span data-stu-id="d1ded-109">Error in loading the adapter bindings</span></span>  
 <span data-ttu-id="d1ded-110">**问题**</span><span class="sxs-lookup"><span data-stu-id="d1ded-110">**Problem**</span></span>  
  
 <span data-ttu-id="d1ded-111">当您尝试启动[!INCLUDE[addadapterservreflong](../../includes/addadapterservreflong-md.md)]或[!INCLUDE[consumeadapterservlong](../../includes/consumeadapterservlong-md.md)]，GUI 将报告以下错误：</span><span class="sxs-lookup"><span data-stu-id="d1ded-111">When you try to start the [!INCLUDE[addadapterservreflong](../../includes/addadapterservreflong-md.md)] or the [!INCLUDE[consumeadapterservlong](../../includes/consumeadapterservlong-md.md)], the GUI gives the following error:</span></span>  
  
```  
There was an error loading the binding, <binding name>, from your system configuration.  
ConfigurationErrorsException: Exception has been thrown by the target of an invocation.  
```  
  
 <span data-ttu-id="d1ded-112">**原因**</span><span class="sxs-lookup"><span data-stu-id="d1ded-112">**Cause**</span></span>  
  
 <span data-ttu-id="d1ded-113">当您启动[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]或[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]，WCF 将加载所有已安装的适配器的适配器绑定。</span><span class="sxs-lookup"><span data-stu-id="d1ded-113">When you start the [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)] or the [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)], WCF loads the adapter bindings for all the installed adapters.</span></span> <span data-ttu-id="d1ded-114">反过来，适配器绑定都依赖于特定企业应用程序客户端软件。</span><span class="sxs-lookup"><span data-stu-id="d1ded-114">In turn, the adapter bindings are dependent on the specific enterprise application client software.</span></span> <span data-ttu-id="d1ded-115">因此，可能会遇到此问题的一个或两个原因如下：</span><span class="sxs-lookup"><span data-stu-id="d1ded-115">So, you could face this issue for one or both of the following reasons:</span></span>  
  
- <span data-ttu-id="d1ded-116">在安装该适配器的计算机上未安装所需的 LOB 客户端软件。</span><span class="sxs-lookup"><span data-stu-id="d1ded-116">The required LOB client software is not installed on the computer where you installed the adapter.</span></span>  
  
- <span data-ttu-id="d1ded-117">未将适配器安装中的所有适配器的"典型"或"完全"安装[!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="d1ded-117">You did a "Typical" or "Complete" installation of the adapter, which installs all the adapters in the [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)].</span></span> <span data-ttu-id="d1ded-118">但是，可能只有一个企业应用程序安装的客户端库。</span><span class="sxs-lookup"><span data-stu-id="d1ded-118">However, the client libraries might be installed for only one enterprise application.</span></span> <span data-ttu-id="d1ded-119">因此，在 GUI 无法加载其他适配器的绑定。</span><span class="sxs-lookup"><span data-stu-id="d1ded-119">As a result, the GUI fails to load the bindings for the other adapters.</span></span>  
  
  <span data-ttu-id="d1ded-120">**解决方法**</span><span class="sxs-lookup"><span data-stu-id="d1ded-120">**Resolution**</span></span>  
  
- <span data-ttu-id="d1ded-121">请确保在您安装的计算机上安装了必需的客户端版本[!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="d1ded-121">Make sure the required client versions are installed on the computer where you installed the [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)].</span></span>  
  
- <span data-ttu-id="d1ded-122">请确保执行要安装仅需要的适配器的适配器的自定义安装。</span><span class="sxs-lookup"><span data-stu-id="d1ded-122">Make sure you do a custom installation of the adapters to install only the adapter you need.</span></span>  
  
###  <a name="BKMK_SiebelDispAdap"></a> <span data-ttu-id="d1ded-123">Siebel 适配器不会显示在 BizTalk Server 管理控制台中的适配器列表中</span><span class="sxs-lookup"><span data-stu-id="d1ded-123">The Siebel adapter does not display in the list of adapters in BizTalk Server Administration console</span></span>  
 <span data-ttu-id="d1ded-124">**问题**</span><span class="sxs-lookup"><span data-stu-id="d1ded-124">**Problem**</span></span>  
  
 <span data-ttu-id="d1ded-125">与早期版本附带的适配器的不同[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]，则[!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]附带[!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)]未显示在 BizTalk Server 管理控制台中的适配器列表中。</span><span class="sxs-lookup"><span data-stu-id="d1ded-125">Unlike the earlier version of the adapters that shipped with [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)], the [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)] that shipped with [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)] does not show up in the list of adapters in the BizTalk Server Administration console.</span></span>  
  
 <span data-ttu-id="d1ded-126">**原因**</span><span class="sxs-lookup"><span data-stu-id="d1ded-126">**Cause**</span></span>  
  
 <span data-ttu-id="d1ded-127">最新[!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]是 WCF 自定义绑定。</span><span class="sxs-lookup"><span data-stu-id="d1ded-127">The latest [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)] is a WCF custom binding.</span></span> <span data-ttu-id="d1ded-128">因此，尽管[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理控制台中显示[!INCLUDE[wcfadapter_short](../../includes/wcfadapter-short-md.md)]，它不会显示 WCF 自定义绑定，因此，不会显示基于 WCF 的[!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="d1ded-128">So, although the [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] Administration console displays the [!INCLUDE[wcfadapter_short](../../includes/wcfadapter-short-md.md)], it does not display the WCF custom bindings and hence, does not display the WCF-based [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)].</span></span>  
  
 <span data-ttu-id="d1ded-129">**解决方法**</span><span class="sxs-lookup"><span data-stu-id="d1ded-129">**Resolution**</span></span>  
  
 <span data-ttu-id="d1ded-130">您可以显式添加[!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]到[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理控制台中所述的步骤[将 Siebel 适配器添加到 BizTalk Server 管理控制台](../../adapters-and-accelerators/adapter-siebel/add-the-siebel-adapter-to-biztalk-server-administration-console.md)。</span><span class="sxs-lookup"><span data-stu-id="d1ded-130">You can explicitly add the [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)] to the [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] Administration console by following the steps mentioned in [Add the Siebel Adapter to BizTalk Server Administration Console](../../adapters-and-accelerators/adapter-siebel/add-the-siebel-adapter-to-biztalk-server-administration-console.md).</span></span>  
  
###  <a name="BKMK_SiebelConnecting"></a> <span data-ttu-id="d1ded-131">连接到 Siebel 系统时出错</span><span class="sxs-lookup"><span data-stu-id="d1ded-131">Error while connecting to the Siebel system</span></span>  
 <span data-ttu-id="d1ded-132">**问题**</span><span class="sxs-lookup"><span data-stu-id="d1ded-132">**Problem**</span></span>  
  
 <span data-ttu-id="d1ded-133">[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]或[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]时尝试连接到 Siebel 系统时出现以下错误：</span><span class="sxs-lookup"><span data-stu-id="d1ded-133">The [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)] or the [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)] gives the following error when you try to connect to the Siebel system:</span></span>  
  
```  
Connecting to the system LOB has failed. Retrieving the COM class factory for component with CLSID {ID} failed due to the following error: 80040154  
```  
  
 <span data-ttu-id="d1ded-134">**原因**</span><span class="sxs-lookup"><span data-stu-id="d1ded-134">**Cause**</span></span>  
  
 <span data-ttu-id="d1ded-135">不可能在计算机上安装 Siebel Web 客户端。</span><span class="sxs-lookup"><span data-stu-id="d1ded-135">The Siebel Web client might not be installed on the computer.</span></span>  
  
 <span data-ttu-id="d1ded-136">**解决方法**</span><span class="sxs-lookup"><span data-stu-id="d1ded-136">**Resolution**</span></span>  
  
 <span data-ttu-id="d1ded-137">请确保在计算机上安装的 Siebel Web 客户端的受支持的版本。</span><span class="sxs-lookup"><span data-stu-id="d1ded-137">Make sure the supported version of the Siebel Web client is installed on the computer.</span></span> <span data-ttu-id="d1ded-138">请参阅支持的客户端的安装指南和用于 Siebel 的服务器版本。</span><span class="sxs-lookup"><span data-stu-id="d1ded-138">Refer to the installation guide for supported client and server versions for Siebel.</span></span> <span data-ttu-id="d1ded-139">安装指南位于\<系统驱动器\>: \Program Files\Microsoft [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)]\Documents。</span><span class="sxs-lookup"><span data-stu-id="d1ded-139">The installation guide is available at \<system drive\>:\Program Files\Microsoft [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)]\Documents.</span></span>  
  
###  <a name="BKMK_SiebelXMLRetrieve"></a> <span data-ttu-id="d1ded-140">具有多个 65536 节点检索 Xml 时出错</span><span class="sxs-lookup"><span data-stu-id="d1ded-140">Error while retrieving XMLs with more than 65536 nodes</span></span>  
 <span data-ttu-id="d1ded-141">**问题**</span><span class="sxs-lookup"><span data-stu-id="d1ded-141">**Problem**</span></span>  
  
 <span data-ttu-id="d1ded-142">检索具有超过 65536 节点的 XML 输出时，适配器将报告以下错误。</span><span class="sxs-lookup"><span data-stu-id="d1ded-142">The adapter gives the following error while retrieving XML output that has more than 65536 nodes.</span></span>  
  
```  
Maximum number of items that can be serialized or deserialized in an object graph is '65536'.  
Change the object graph or increase the MaxItemsInObjectGraph quota.  
```  
  
 <span data-ttu-id="d1ded-143">**原因**</span><span class="sxs-lookup"><span data-stu-id="d1ded-143">**Cause**</span></span>  
  
 <span data-ttu-id="d1ded-144">适配器不能序列化和反序列化具有多个 65536 的项的对象。</span><span class="sxs-lookup"><span data-stu-id="d1ded-144">The adapter cannot serialize and deserialize an object with more than 65536 items.</span></span>  
  
 <span data-ttu-id="d1ded-145">**解决方法**</span><span class="sxs-lookup"><span data-stu-id="d1ded-145">**Resolution**</span></span>  
  
 <span data-ttu-id="d1ded-146">可以通过设置来解决此问题`maxItemsInObjectGraph`参数。</span><span class="sxs-lookup"><span data-stu-id="d1ded-146">You can fix this issue by setting the `maxItemsInObjectGraph` parameter.</span></span> <span data-ttu-id="d1ded-147">可以在任何以下两种方式设置此：</span><span class="sxs-lookup"><span data-stu-id="d1ded-147">You can set this in any of the following two ways:</span></span>  
  
- <span data-ttu-id="d1ded-148">将此参数设置通过更改`maxItemsInObjectGraph`中的参数`ServiceBehavior`服务类中的属性。</span><span class="sxs-lookup"><span data-stu-id="d1ded-148">Set this parameter by changing the `maxItemsInObjectGraph` parameter in the `ServiceBehavior` attribute on your service class.</span></span>  
  
- <span data-ttu-id="d1ded-149">以下代码添加到应用程序的 app.config 文件。</span><span class="sxs-lookup"><span data-stu-id="d1ded-149">Add the following to your application's app.config file.</span></span>  
  
  ```  
  <behaviors>  
    <endpointBehaviors>  
      <behavior name="NewBehavior">  
        <dataContractSerializer maxItemsInObjectGraph="65536000" />  
      </behavior>  
    </endpointBehaviors>  
  </behaviors>  
  ```  
  
  <span data-ttu-id="d1ded-150">示例 app.config 将如下所示：</span><span class="sxs-lookup"><span data-stu-id="d1ded-150">A sample app.config will look like:</span></span>  
  
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
  
###  <a name="BKMK_SiebelConnURI"></a> <span data-ttu-id="d1ded-151">在 BizTalk 中指定的 WCF 自定义端口的连接 URI 时出错</span><span class="sxs-lookup"><span data-stu-id="d1ded-151">Error while specifying a connection URI for a WCF-Custom port in BizTalk</span></span>  
 <span data-ttu-id="d1ded-152">**问题**</span><span class="sxs-lookup"><span data-stu-id="d1ded-152">**Problem**</span></span>  
  
 [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]<span data-ttu-id="d1ded-153"> 在指定连接 URI 连接到 Siebel 系统时出现以下错误。</span><span class="sxs-lookup"><span data-stu-id="d1ded-153"> gives the following error when you specify a connection URI to connect to the Siebel system.</span></span>  
  
```  
Error saving properties.  
(System.ArgumentException) The specified address is invalid.  
(System.ArgumentException) Invalid address;  
"<connection URI>" is not a well-formed absolute uri.  
```  
  
 <span data-ttu-id="d1ded-154">**原因**</span><span class="sxs-lookup"><span data-stu-id="d1ded-154">**Cause**</span></span>  
  
 <span data-ttu-id="d1ded-155">连接 URI 不符合标准的编码格式。</span><span class="sxs-lookup"><span data-stu-id="d1ded-155">The connection URI does not adhere to the standard encoding format.</span></span> <span data-ttu-id="d1ded-156">例如，某个参数的值可能包含一个空格。</span><span class="sxs-lookup"><span data-stu-id="d1ded-156">For example, the value for a parameter might contain a space.</span></span>  
  
 <span data-ttu-id="d1ded-157">**解决方法**</span><span class="sxs-lookup"><span data-stu-id="d1ded-157">**Resolution**</span></span>  
  
 <span data-ttu-id="d1ded-158">请确保你指定的 URI 遵循标准编码格式的连接。</span><span class="sxs-lookup"><span data-stu-id="d1ded-158">Make sure the connection URI you specify adheres to the standard encoding format.</span></span> <span data-ttu-id="d1ded-159">例如，必须通过"%20"替换为空格。</span><span class="sxs-lookup"><span data-stu-id="d1ded-159">For example, a blank space must be replaced by "%20".</span></span>  
  
###  <a name="BKMK_SiebelPerfOps"></a> <span data-ttu-id="d1ded-160">Siebel 系统上执行操作时出错</span><span class="sxs-lookup"><span data-stu-id="d1ded-160">Error while performing operation on the Siebel system</span></span>  
 <span data-ttu-id="d1ded-161">**问题**</span><span class="sxs-lookup"><span data-stu-id="d1ded-161">**Problem**</span></span>  
  
 <span data-ttu-id="d1ded-162">执行对 Siebel 系统使用的任何操作时，适配器将报告以下错误[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="d1ded-162">The adapter gives the following error when performing any operation on the Siebel system using [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)].</span></span>  
  
- <span data-ttu-id="d1ded-163">**为 BizTalk Server**</span><span class="sxs-lookup"><span data-stu-id="d1ded-163">**For BizTalk Server**</span></span>  
  
  ```  
  System.ArgumentNullException: Value cannot be null.  
  ```  
  
  <span data-ttu-id="d1ded-164">**原因**</span><span class="sxs-lookup"><span data-stu-id="d1ded-164">**Cause**</span></span>  
  
  <span data-ttu-id="d1ded-165">未指定消息的 WCF 操作。</span><span class="sxs-lookup"><span data-stu-id="d1ded-165">The WCF action for the message is not specified.</span></span> <span data-ttu-id="d1ded-166">WCF 需要用于为每个操作，向适配器通知上的 LOB 应用程序执行的操作指定的 SOAP 操作。</span><span class="sxs-lookup"><span data-stu-id="d1ded-166">WCF requires a SOAP action to be specified for every operation, which informs the adapter about the operation to be performed on the LOB application.</span></span>  
  
  <span data-ttu-id="d1ded-167">**解决方法**</span><span class="sxs-lookup"><span data-stu-id="d1ded-167">**Resolution**</span></span>  
  
  <span data-ttu-id="d1ded-168">在发送端口或为 BizTalk 业务流程的消息上下文属性指定的 SOAP 操作。</span><span class="sxs-lookup"><span data-stu-id="d1ded-168">Specify the SOAP action in the send port or as a message context property in a BizTalk orchestration.</span></span> <span data-ttu-id="d1ded-169">有关说明，请参阅[配置用于 Siebel 的 SOAP 操作](../../adapters-and-accelerators/adapter-siebel/configure-the-soap-action-for-siebel.md)。</span><span class="sxs-lookup"><span data-stu-id="d1ded-169">For instructions, see [Configure the SOAP action for Siebel](../../adapters-and-accelerators/adapter-siebel/configure-the-soap-action-for-siebel.md).</span></span> <span data-ttu-id="d1ded-170">请参阅[消息和消息架构](messages-and-message-schemas-for-siebel-adapter-in-biztalk.md)有关每个操作的操作的列表。</span><span class="sxs-lookup"><span data-stu-id="d1ded-170">See [Messages and message schemas](messages-and-message-schemas-for-siebel-adapter-in-biztalk.md) for a list of actions for each operation.</span></span>  
  
###  <a name="BKMK_SiebelXmlParsing"></a> <span data-ttu-id="d1ded-171">由于指定的操作中的不正确的操作名称 XmlReaderParsingException</span><span class="sxs-lookup"><span data-stu-id="d1ded-171">XmlReaderParsingException due to an incorrect operation name in the specified action</span></span>  
 <span data-ttu-id="d1ded-172">**问题**</span><span class="sxs-lookup"><span data-stu-id="d1ded-172">**Problem**</span></span>  
  
 <span data-ttu-id="d1ded-173">将消息发送到 Siebel 系统时，BizTalk Server 管理控制台将报告以下错误：</span><span class="sxs-lookup"><span data-stu-id="d1ded-173">The BizTalk Server Administration console gives the following error when sending messages to a Siebel system:</span></span>  
  
```  
Microsoft.ServiceModel.Channels.Common.XmlReaderParsingException: Invalid argument:  
<BtsActionMapping xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xmlns:xsd="http://www.w3.org/2001/XMLSchema">  
  <Operation Name="<operation_name>" Action="<action>" />  
</BtsActionMapping>  
```  
  
 <span data-ttu-id="d1ded-174">**原因**</span><span class="sxs-lookup"><span data-stu-id="d1ded-174">**Cause**</span></span>  
  
 <span data-ttu-id="d1ded-175">如果通过导入创建的端口绑定文件配置 WCF 自定义端口[!INCLUDE[consumeadapterservlong](../../includes/consumeadapterservlong-md.md)]，采用以下格式指定端口中的操作：</span><span class="sxs-lookup"><span data-stu-id="d1ded-175">If you configure a WCF-Custom port by importing the port binding file created by the [!INCLUDE[consumeadapterservlong](../../includes/consumeadapterservlong-md.md)], the action in the port is specified in the following format:</span></span>  
  
```  
<BtsActionMapping>  
  <Operation Name="Op1" Action="http://MyService/Svc/Op1" />  
</BtsActionMapping>  
```  
  
 <span data-ttu-id="d1ded-176">在前面的格式，操作名称受生成架构时选择该操作。</span><span class="sxs-lookup"><span data-stu-id="d1ded-176">In the preceding format, the operation name is governed by the operation you chose while generating the schema.</span></span> <span data-ttu-id="d1ded-177">例如，如果生成一个 Siebel 业务组件上的查询操作的架构，则操作中的操作名称将是"查询"。</span><span class="sxs-lookup"><span data-stu-id="d1ded-177">For example, if you generated schema for a Query operation on a Siebel business component, the operation name in the action will be "Query".</span></span> <span data-ttu-id="d1ded-178">但是中的逻辑端口的操作名称创建在 BizTalk 业务流程中[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]可能不同。</span><span class="sxs-lookup"><span data-stu-id="d1ded-178">However, the operation name in the logical port created in the BizTalk orchestration in [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)] might be different.</span></span>  
  
 <span data-ttu-id="d1ded-179">**解决方法**</span><span class="sxs-lookup"><span data-stu-id="d1ded-179">**Resolution**</span></span>  
  
 <span data-ttu-id="d1ded-180">请确保操作名称的两个逻辑端口 (在 BizTalk 业务流程中[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]) 和 （在 BizTalk Server 管理控制台） 的物理端口相同。</span><span class="sxs-lookup"><span data-stu-id="d1ded-180">Make sure the operation names in both the logical port (in the BizTalk orchestration in [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]) and the physical port (in BizTalk Server Administration console) are the same.</span></span>  
  
###  <a name="BKMK_SiebelTerminate"></a> <span data-ttu-id="d1ded-181">使用 Siebel 适配器的应用程序不会终止</span><span class="sxs-lookup"><span data-stu-id="d1ded-181">Application using the Siebel adapter does not terminate</span></span>  
 <span data-ttu-id="d1ded-182">**问题**</span><span class="sxs-lookup"><span data-stu-id="d1ded-182">**Problem**</span></span>  
  
 <span data-ttu-id="d1ded-183">使用的应用程序[!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]与 Siebel 7.5 版客户端不会终止。</span><span class="sxs-lookup"><span data-stu-id="d1ded-183">An application that uses the [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)] with Siebel client version 7.5 does not terminate.</span></span>  
  
 <span data-ttu-id="d1ded-184">**原因**</span><span class="sxs-lookup"><span data-stu-id="d1ded-184">**Cause**</span></span>  
  
 <span data-ttu-id="d1ded-185">这是因为 Siebel 客户端问题的过程不会终止时从 Siebel 服务器注销。</span><span class="sxs-lookup"><span data-stu-id="d1ded-185">This is because of a Siebel client issue where the process does not terminate when logging off from a Siebel server.</span></span>  
  
 <span data-ttu-id="d1ded-186">**解决方法**</span><span class="sxs-lookup"><span data-stu-id="d1ded-186">**Resolution**</span></span>  
  
 <span data-ttu-id="d1ded-187">请确保你已 7.5.3.17 Siebel 服务器，以及快速修复 QF0H05 安装了修补程序。</span><span class="sxs-lookup"><span data-stu-id="d1ded-187">Make sure you have the patch 7.5.3.17 installed for the Siebel server, along with the quick fix QF0H05.</span></span>  
  
###  <a name="BKMK_SiebelHang"></a> <span data-ttu-id="d1ded-188">Siebel 服务器重新启动，则可能会挂起 Siebel 适配器</span><span class="sxs-lookup"><span data-stu-id="d1ded-188">Siebel adapter may hang if the Siebel server is restarted</span></span>  
 <span data-ttu-id="d1ded-189">**问题**</span><span class="sxs-lookup"><span data-stu-id="d1ded-189">**Problem**</span></span>  
  
 <span data-ttu-id="d1ded-190">如果 Siebel 服务器将重启时[!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]将一条消息发送到 Siebel 服务器使用，[!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]可能会挂起。</span><span class="sxs-lookup"><span data-stu-id="d1ded-190">If the Siebel server is restarted while the [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)] is sending a message to the Siebel server using, the [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)] may hang.</span></span>  
  
 <span data-ttu-id="d1ded-191">**解决方法**</span><span class="sxs-lookup"><span data-stu-id="d1ded-191">**Resolution**</span></span>  
  
 <span data-ttu-id="d1ded-192">重新启动 BizTalk 应用程序主机实例。</span><span class="sxs-lookup"><span data-stu-id="d1ded-192">Restart the BizTalk application host instance.</span></span> <span data-ttu-id="d1ded-193">若要执行此操作从[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理控制台中的，在控制台树中展开**BizTalk 组**，展开**平台设置**，然后单击**主机实例**。</span><span class="sxs-lookup"><span data-stu-id="d1ded-193">To do so from the [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] Administration console, in the console tree expand **BizTalk Group**, expand **Platform Settings**, and then click **Host Instances**.</span></span> <span data-ttu-id="d1ded-194">从右窗格中，右键单击主机名称，然后选择**重新启动**。</span><span class="sxs-lookup"><span data-stu-id="d1ded-194">From the right pane, right-click the host name, and then select **Restart**.</span></span>  
  
###  <a name="BKMK_SiebelAction"></a> <span data-ttu-id="d1ded-195">适配器不识别物理端口上的操作，即使由使用适配器服务加载项生成的绑定文件用于创建端口</span><span class="sxs-lookup"><span data-stu-id="d1ded-195">The adapter does not recognize the action on the physical port even though you use the binding file generated by the Consume Adapter Service add-in to create the ports</span></span>  
 <span data-ttu-id="d1ded-196">**问题**</span><span class="sxs-lookup"><span data-stu-id="d1ded-196">**Problem**</span></span>  
  
 <span data-ttu-id="d1ded-197">在使用后[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]若要生成上的 Siebel 系统的特定操作的架构外, 接程序还会创建端口绑定文件。</span><span class="sxs-lookup"><span data-stu-id="d1ded-197">After you use the [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)] to generate schema for a specific operation on the Siebel system, the add-in also creates a port binding file.</span></span> <span data-ttu-id="d1ded-198">您可以导入此文件使用绑定[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理控制台，可在 BizTalk Server 中创建物理端口。</span><span class="sxs-lookup"><span data-stu-id="d1ded-198">You can import this binding file using the [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] Administration console to create physical ports in BizTalk Server.</span></span> <span data-ttu-id="d1ded-199">但是时将消息发送到 Siebel 系统使用此类端口时，, 适配器将无法理解的端口上指定的操作，并提供了类似于以下的错误：</span><span class="sxs-lookup"><span data-stu-id="d1ded-199">However, when you send messages to the Siebel system using such ports, the adapter fails to understand the action specified on the port and gives an error similar to the following:</span></span>  
  
```  
Microsoft.ServiceModel.Channels.Common.UnsupportedOperationException: Incorrect Action   
<BtsActionMapping xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xmlns:xsd="http://www.w3.org/2001/XMLSchema">  
  <Operation Name="<op_name>" Action="<action>" />  
</BtsActionMapping>. Correct the specified Action, or refer to the documentation on the allowed formats for the Actions.  
```  
  
 <span data-ttu-id="d1ded-200">**原因**</span><span class="sxs-lookup"><span data-stu-id="d1ded-200">**Cause**</span></span>  
  
 <span data-ttu-id="d1ded-201">BizTalk 业务流程中创建逻辑端口时，指定这些端口上操作某些名称，或只需使用默认名称，例如 Operation_1、 Operation_2，等等。但是，在生成的绑定文件[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]，操作名称是与为其生成元数据的操作的名称相同。</span><span class="sxs-lookup"><span data-stu-id="d1ded-201">When you create logical ports in a BizTalk orchestration, you specify certain names for the operations on those ports or you just use the default names like Operation_1, Operation_2, etc. However, in the binding file generated by the [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)], the operation name is same as the name of the operation for which you generate metadata.</span></span> <span data-ttu-id="d1ded-202">例如，如果您生成帐户业务组件上的插入操作的元数据，操作将设置为以下：</span><span class="sxs-lookup"><span data-stu-id="d1ded-202">For example, if you generate metadata for Insert operation on the Account business component, the action will be set to the following:</span></span>  
  
```  
<Operation Name="Insert" Action="http://Microsoft.LobServices.Siebel/2007/03/BusinessObjects/Account/Account/Insert" />  
```  
  
 <span data-ttu-id="d1ded-203">导入绑定文件时，物理端口上设置相同的操作。</span><span class="sxs-lookup"><span data-stu-id="d1ded-203">When you import the binding file, the same action is set on physical port.</span></span> <span data-ttu-id="d1ded-204">因此，逻辑端口 （Operation_1、 Operation_2 等） 上的操作名称与物理端口，从而导致错误的操作中指定的操作名称不匹配。</span><span class="sxs-lookup"><span data-stu-id="d1ded-204">So, the operation names on the logical port (Operation_1, Operation_2, etc.) do not match the operation names specified in the action on the physical port, resulting in an error.</span></span>  
  
 <span data-ttu-id="d1ded-205">**解决方法**</span><span class="sxs-lookup"><span data-stu-id="d1ded-205">**Resolution**</span></span>  
  
 <span data-ttu-id="d1ded-206">请确保逻辑端口中的操作名称中的物理端口的操作中指定的操作名称相同。</span><span class="sxs-lookup"><span data-stu-id="d1ded-206">Make sure the operation name in the logical port is the same as the operation name specified as part of the action in the physical port.</span></span> <span data-ttu-id="d1ded-207">执行以下操作之一：</span><span class="sxs-lookup"><span data-stu-id="d1ded-207">Do one of the following:</span></span>  
  
-   <span data-ttu-id="d1ded-208">对为其生成元数据，例如 Insert 操作从 Operation_1 等更改 BizTalk 业务流程中的逻辑端口中的操作名称。</span><span class="sxs-lookup"><span data-stu-id="d1ded-208">Change the operation name in the logical port in BizTalk orchestration from Operation_1, etc. to the operation for which you generate metadata, for example Insert.</span></span>  
  
-   <span data-ttu-id="d1ded-209">将物理端口上的操作中的操作名称更改为中的逻辑端口的操作名称。</span><span class="sxs-lookup"><span data-stu-id="d1ded-209">Change the operation name in the action on the physical port to the operation name in the logical port.</span></span> <span data-ttu-id="d1ded-210">例如，可以更改为类似于以下的物理端口中的操作：</span><span class="sxs-lookup"><span data-stu-id="d1ded-210">For example, you could change the action in the physical port to resemble the following:</span></span>  
  
    ```  
    <Operation Name="Operation_1" Action="http://Microsoft.LobServices.Siebel/2007/03/BusinessObjects/Account/Account/Insert" />  
    ```  
  
###  <a name="BKMK_SiebelXMLEncode"></a> <span data-ttu-id="d1ded-211">Siebel 适配器不会处理与在名称中编码的 XML 字符串的 Siebel 对象</span><span class="sxs-lookup"><span data-stu-id="d1ded-211">Siebel adapter does not handle Siebel objects with XML encoded strings in the name</span></span>  
 <span data-ttu-id="d1ded-212">**问题**</span><span class="sxs-lookup"><span data-stu-id="d1ded-212">**Problem**</span></span>  
  
 <span data-ttu-id="d1ded-213">[!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]无法执行涉及 Siebel 对象 （业务对象、 业务组件、 业务服务、 选择列表、 方法、 字段、 参数等） 的名称中包含编码的 XML 字符串的操作。</span><span class="sxs-lookup"><span data-stu-id="d1ded-213">The [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)] cannot perform operations involving Siebel objects (business objects, business components, business services, picklist, methods, fields, arguments, etc) that have XML encoded strings in their name.</span></span> <span data-ttu-id="d1ded-214">例如，[!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]将不能调用具有名称 Time_x0020_Stamp 的业务服务方法。</span><span class="sxs-lookup"><span data-stu-id="d1ded-214">For example, the [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)] will not be able to invoke a business service method with the name Time_x0020_Stamp.</span></span>  
  
 <span data-ttu-id="d1ded-215">**解决方法**</span><span class="sxs-lookup"><span data-stu-id="d1ded-215">**Resolution**</span></span>  
  
 <span data-ttu-id="d1ded-216">请确保 Siebel 对象不包含其名称中编码的 XML 字符串。</span><span class="sxs-lookup"><span data-stu-id="d1ded-216">Make sure the Siebel objects do not contain XML encoded strings in their name.</span></span>  
  
###  <a name="BKMK_SiebelRootNode"></a> <span data-ttu-id="d1ded-217">使用 BizTalk 项目中的 RootNode TypeName 错误</span><span class="sxs-lookup"><span data-stu-id="d1ded-217">Error with RootNode TypeName in BizTalk Projects</span></span>  
 <span data-ttu-id="d1ded-218">**问题**</span><span class="sxs-lookup"><span data-stu-id="d1ded-218">**Problem**</span></span>  
  
 <span data-ttu-id="d1ded-219">中的 BizTalk 项目中[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]，则从架构生成[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]包含无效的字符或保留的字**RootNode TypeName**属性，编译项目时将发生以下错误:</span><span class="sxs-lookup"><span data-stu-id="d1ded-219">In a BizTalk project in [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)], if the schemas generated from the [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)] contains invalid characters or reserved words for the **RootNode TypeName** property, the following error will occur while compiling the project:</span></span>  
  
```  
Node <node reference> - Specify a valid .NET type name for this root node.  
The current .NET type name of this root node is invalid (it is a reserved BizTalk Keyword or is an invalid C# identifier).  
```  
  
 <span data-ttu-id="d1ded-220">**解决方法**</span><span class="sxs-lookup"><span data-stu-id="d1ded-220">**Resolution**</span></span>  
  
1.  <span data-ttu-id="d1ded-221">右键单击该错误，然后选择中引用的 rood 这样节点**属性**。</span><span class="sxs-lookup"><span data-stu-id="d1ded-221">Right-click the rood node referenced in the error and select **Properties**.</span></span>  
  
2.  <span data-ttu-id="d1ded-222">有关**RootNode TypeName**属性，删除任何非法字符或保留字，例如，点 （.）。</span><span class="sxs-lookup"><span data-stu-id="d1ded-222">For the **RootNode TypeName** property, remove any illegal characters or reserved words, for example, dot (.).</span></span>  
  
###  <a name="BKMK_SiebelVS2008"></a> <span data-ttu-id="d1ded-223">无效的绑定时出现的警告在 Visual Studio 中使用适配器</span><span class="sxs-lookup"><span data-stu-id="d1ded-223">Invalid binding warning when using the adapter in Visual Studio</span></span>  
 <span data-ttu-id="d1ded-224">**问题**</span><span class="sxs-lookup"><span data-stu-id="d1ded-224">**Problem**</span></span>  
  
 <span data-ttu-id="d1ded-225">当适配器用于在 Visual Studio 中创建应用程序并打开由适配器生成的配置文件 (app.config) 时，您会看到类似于下面的警告：</span><span class="sxs-lookup"><span data-stu-id="d1ded-225">When you use the adapter to create an application in Visual Studio and you open the configuration file (app.config) generated by the adapter, you see a warning similar to the following:</span></span>  
  
```  
The element 'bindings' has invalid child element 'siebelBinding'. List of possible elements expected: 'basicHttpBinding, customBinding, ...  
```  
  
 <span data-ttu-id="d1ded-226">**原因**</span><span class="sxs-lookup"><span data-stu-id="d1ded-226">**Cause**</span></span>  
  
 <span data-ttu-id="d1ded-227">会出现此警告[!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]绑定， `siebelBinding`，不标准绑定随附于[!INCLUDE[firstref_btsWinCommFoundation](../../includes/firstref-btswincommfoundation-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="d1ded-227">This warning appears because the [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)] binding, `siebelBinding`, is not a standard binding shipped with the [!INCLUDE[firstref_btsWinCommFoundation](../../includes/firstref-btswincommfoundation-md.md)].</span></span>  
  
 <span data-ttu-id="d1ded-228">**解决方法**</span><span class="sxs-lookup"><span data-stu-id="d1ded-228">**Resolution**</span></span>  
  
 <span data-ttu-id="d1ded-229">可以安全地忽略此警告。</span><span class="sxs-lookup"><span data-stu-id="d1ded-229">You can safely ignore this warning.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d1ded-230">请参阅</span><span class="sxs-lookup"><span data-stu-id="d1ded-230">See Also</span></span>  
[<span data-ttu-id="d1ded-231">Siebel 适配器疑难解答</span><span class="sxs-lookup"><span data-stu-id="d1ded-231">Troubleshoot the Siebel adapter</span></span>](../../adapters-and-accelerators/adapter-siebel/troubleshoot-the-siebel-adapter.md)