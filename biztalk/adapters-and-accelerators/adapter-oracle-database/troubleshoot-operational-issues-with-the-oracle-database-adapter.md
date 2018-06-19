---
title: 排除与 Oracle 数据库适配器的操作问题 |Microsoft 文档
description: 常见的问题和 Oracle 数据库适配器 BizTalk 适配器包 (BAP) 中的解决方法
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 2fb83245-2b6a-48cc-8601-b923bb009a58
caps.latest.revision: 25
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 8ac926a378224e09dce36a52b52c171fb27911b0
ms.sourcegitcommit: 3fc338e52d5dbca2c3ea1685a2faafc7582fe23a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/01/2017
ms.locfileid: "26010102"
---
# <a name="troubleshoot-operational-issues-with-the-oracle-database-adapter"></a><span data-ttu-id="d983a-103">排除与 Oracle 数据库适配器的操作问题</span><span class="sxs-lookup"><span data-stu-id="d983a-103">Troubleshoot operational issues with the Oracle Database adapter</span></span>
<span data-ttu-id="d983a-104">故障排除技术解决你可能会遇到使用的操作错误[!INCLUDE[adapteroracle](../../includes/adapteroracle-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="d983a-104">Troubleshooting techniques to resolve operational errors that you may experience using [!INCLUDE[adapteroracle](../../includes/adapteroracle-md.md)].</span></span>  
  
## <a name="enable-tracing"></a><span data-ttu-id="d983a-105">启用跟踪</span><span class="sxs-lookup"><span data-stu-id="d983a-105">Enable tracing</span></span>  
 <span data-ttu-id="d983a-106">有关跟踪中的支持信息[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]，请参阅[诊断跟踪和消息日志记录为 Oracle 数据库适配器](../../adapters-and-accelerators/adapter-oracle-database/diagnostic-tracing-and-message-logging-for-the-oracle-database-adapter.md)。</span><span class="sxs-lookup"><span data-stu-id="d983a-106">For information about tracing support in the [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)], see [Diagnostic tracing and message logging for the Oracle Database adapter](../../adapters-and-accelerators/adapter-oracle-database/diagnostic-tracing-and-message-logging-for-the-oracle-database-adapter.md).</span></span>  
  
## <a name="known-issues"></a><span data-ttu-id="d983a-107">已知问题</span><span class="sxs-lookup"><span data-stu-id="d983a-107">Known Issues</span></span>  
 <span data-ttu-id="d983a-108">以下是使用时可能遇到的最常见错误[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]，以及其可能的原因和解决方法。</span><span class="sxs-lookup"><span data-stu-id="d983a-108">The following are the most common errors you might encounter when using the [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)], along with their probable cause and resolution.</span></span>   
  
### <a name="BKMK_OraDBLoading"></a><span data-ttu-id="d983a-109">在加载适配器绑定错误</span><span class="sxs-lookup"><span data-stu-id="d983a-109">Error in loading the adapter bindings</span></span>  
 <span data-ttu-id="d983a-110">**问题**</span><span class="sxs-lookup"><span data-stu-id="d983a-110">**Problem**</span></span>  
  
 <span data-ttu-id="d983a-111">当你尝试启动[!INCLUDE[addadapterservreflong](../../includes/addadapterservreflong-md.md)]或[!INCLUDE[consumeadapterservlong](../../includes/consumeadapterservlong-md.md)]，你将收到以下错误：</span><span class="sxs-lookup"><span data-stu-id="d983a-111">When you try to start the [!INCLUDE[addadapterservreflong](../../includes/addadapterservreflong-md.md)] or the [!INCLUDE[consumeadapterservlong](../../includes/consumeadapterservlong-md.md)], you get the following error:</span></span>  
  
```  
There was an error loading the binding, <binding name>, from your system configuration.  
ConfigurationErrorsException: Exception has been thrown by the target of an invocation.  
```  
  
 <span data-ttu-id="d983a-112">**可能的原因**</span><span class="sxs-lookup"><span data-stu-id="d983a-112">**Cause**</span></span>  
  
 <span data-ttu-id="d983a-113">当你尝试启动[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]或[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]，WCF 加载所有已安装适配器的适配器绑定。</span><span class="sxs-lookup"><span data-stu-id="d983a-113">When you try to start the [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)] or the [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)], WCF loads the adapter bindings for all the installed adapters.</span></span> <span data-ttu-id="d983a-114">反过来，适配器绑定都依赖于企业应用程序的特定客户端软件。</span><span class="sxs-lookup"><span data-stu-id="d983a-114">In turn, the adapter bindings are dependent on the specific client software for the enterprise application.</span></span> <span data-ttu-id="d983a-115">你可能会遇到此问题的一个或两个原因如下：</span><span class="sxs-lookup"><span data-stu-id="d983a-115">You might face this issue for one or both of the following reasons:</span></span>  
  
-   <span data-ttu-id="d983a-116">在安装适配器的计算机上未安装所需的 LOB 客户端软件。</span><span class="sxs-lookup"><span data-stu-id="d983a-116">The required LOB client software is not installed on the computer where you installed the adapter.</span></span>  
  
-   <span data-ttu-id="d983a-117">未将适配器安装中包含的所有适配器的典型或完全安装[!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="d983a-117">You did a Typical or Complete installation of the adapter, which installs all the adapters contained in the [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)].</span></span> <span data-ttu-id="d983a-118">但是，可能只有一个企业应用程序安装 LOB 客户端库。</span><span class="sxs-lookup"><span data-stu-id="d983a-118">However, the LOB client libraries might be installed for only one enterprise application.</span></span> <span data-ttu-id="d983a-119">因此，GUI 无法加载其他适配器的绑定。</span><span class="sxs-lookup"><span data-stu-id="d983a-119">As a result, the GUI fails to load the bindings for the other adapters.</span></span>  
  
 <span data-ttu-id="d983a-120">**解决方法**</span><span class="sxs-lookup"><span data-stu-id="d983a-120">**Resolution**</span></span>  
  
-   <span data-ttu-id="d983a-121">请确保在你安装的计算机上安装了所需的 LOB 客户端版本[!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="d983a-121">Make sure that the required LOB client versions are installed on the computer where you installed the [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)].</span></span> <span data-ttu-id="d983a-122">[支持的业务线 (LOB) 和企业系统](https://social.technet.microsoft.com/wiki/contents/articles/17631.biztalk-server-supported-line-of-business-lob-and-enterprise-systems.aspx)列出支持的客户端版本。</span><span class="sxs-lookup"><span data-stu-id="d983a-122">[Supported Line-of-Business (LOB) and Enterprise systems](https://social.technet.microsoft.com/wiki/contents/articles/17631.biztalk-server-supported-line-of-business-lob-and-enterprise-systems.aspx) lists the supported client versions.</span></span>  
  
-   <span data-ttu-id="d983a-123">请确保执行适配器安装需要适配器的自定义安装。</span><span class="sxs-lookup"><span data-stu-id="d983a-123">Make sure you do a custom installation of the adapters to install only the adapter you need.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="d983a-124">若要确保你的应用程序与 ODP.NET 的最新版本，你必须具有"策略 Dll"在计算机上安装并在 GAC 中注册。</span><span class="sxs-lookup"><span data-stu-id="d983a-124">To make sure your application works with the most recent version of ODP.NET, you must have the "policy DLLs" installed on the computer and registered in the GAC.</span></span> <span data-ttu-id="d983a-125">有关详细信息，请参阅[用于.NET 的 Oracle 数据提供程序](http://go.microsoft.com/fwlink/p/?LinkId=92834)Oracle 的网站上。</span><span class="sxs-lookup"><span data-stu-id="d983a-125">For more information, see [Oracle Data Provider for .NET](http://go.microsoft.com/fwlink/p/?LinkId=92834) on Oracle's website.</span></span>  
  
###  <a name="BKMK_OraDBAdapDisplay"></a><span data-ttu-id="d983a-126">Oracle 数据库适配器不会显示在列表中在 BizTalk Server 管理控制台中的适配器</span><span class="sxs-lookup"><span data-stu-id="d983a-126">The Oracle database adapter does not display in the list of adapters in BizTalk Server Administration console</span></span>  
 <span data-ttu-id="d983a-127">**问题**</span><span class="sxs-lookup"><span data-stu-id="d983a-127">**Problem**</span></span>  
  
<span data-ttu-id="d983a-128">[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]与 inlcuded [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)] BizTalk Server 管理控制台中的适配器的列表中未列出。</span><span class="sxs-lookup"><span data-stu-id="d983a-128">The [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] inlcuded with [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)] is not listed in the list of adapters in the BizTalk Server Administration console.</span></span>  
  
 <span data-ttu-id="d983a-129">**可能的原因**</span><span class="sxs-lookup"><span data-stu-id="d983a-129">**Cause**</span></span>  
  
 <span data-ttu-id="d983a-130">[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]是 WCF 自定义绑定。</span><span class="sxs-lookup"><span data-stu-id="d983a-130">The [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] is a WCF custom binding.</span></span> <span data-ttu-id="d983a-131">因此，尽管[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理控制台显示[!INCLUDE[wcfadapter_short](../../includes/wcfadapter-short-md.md)]，它不会显示 WCF 自定义绑定，并因此，不会显示基于 WCF 的[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="d983a-131">So, although the [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] Administration console displays the [!INCLUDE[wcfadapter_short](../../includes/wcfadapter-short-md.md)], it does not display the WCF custom bindings and hence, does not display the WCF-based [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)].</span></span>  
  
 <span data-ttu-id="d983a-132">**解决方法**</span><span class="sxs-lookup"><span data-stu-id="d983a-132">**Resolution**</span></span>  
  
 <span data-ttu-id="d983a-133">你可以显式添加[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]到[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理控制台中所述的步骤[将 Oracle 数据库适配器添加到 BizTalk Server 管理控制台](../../adapters-and-accelerators/adapter-oracle-database/adding-the-oracle-database-adapter-to-biztalk-server-administration-console.md)。</span><span class="sxs-lookup"><span data-stu-id="d983a-133">You can explicitly add the [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] to the [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] Administration console by following the steps mentioned in [Adding the Oracle Database Adapter to BizTalk Server Administration Console](../../adapters-and-accelerators/adapter-oracle-database/adding-the-oracle-database-adapter-to-biztalk-server-administration-console.md).</span></span>  
  
###  <a name="BKMK_OraDBXMLRetrieve"></a><span data-ttu-id="d983a-134">检索具有多个 65,536 节点的 XML 输出时出错</span><span class="sxs-lookup"><span data-stu-id="d983a-134">Error while retrieving XML output with more than 65,536 nodes</span></span>  
 <span data-ttu-id="d983a-135">**问题**</span><span class="sxs-lookup"><span data-stu-id="d983a-135">**Problem**</span></span>  
  
 <span data-ttu-id="d983a-136">在检索 XML 输出，有多个 65,536 节点时，该适配器将报告以下错误。</span><span class="sxs-lookup"><span data-stu-id="d983a-136">The adapter gives the following error when retrieving XML output that has more than 65,536 nodes.</span></span>  
  
```  
Maximum number of items that can be serialized or deserialized in an object graph is '65536'.  
Change the object graph or increase the MaxItemsInObjectGraph quota.  
```  
  
 <span data-ttu-id="d983a-137">**可能的原因**</span><span class="sxs-lookup"><span data-stu-id="d983a-137">**Cause**</span></span>  
  
 <span data-ttu-id="d983a-138">适配器不能序列化和反序列化具有多个 65,536 项的对象。</span><span class="sxs-lookup"><span data-stu-id="d983a-138">The adapter cannot serialize and deserialize an object with more than 65,536 items.</span></span>  
  
 <span data-ttu-id="d983a-139">**解决方法**</span><span class="sxs-lookup"><span data-stu-id="d983a-139">**Resolution**</span></span>  
  
 <span data-ttu-id="d983a-140">可以通过设置来解决此问题`maxItemsInObjectGraph`参数。</span><span class="sxs-lookup"><span data-stu-id="d983a-140">You can fix this issue by setting the `maxItemsInObjectGraph` parameter.</span></span> <span data-ttu-id="d983a-141">你可以设置这在以下两种方法之一：</span><span class="sxs-lookup"><span data-stu-id="d983a-141">You can set this in either of the following two ways:</span></span>  
  
-   <span data-ttu-id="d983a-142">将此参数设置通过更改`maxItemsInObjectGraph`中的参数`ServiceBehavior`服务类中的属性。</span><span class="sxs-lookup"><span data-stu-id="d983a-142">Set this parameter by changing the `maxItemsInObjectGraph` parameter in the `ServiceBehavior` attribute on your service class.</span></span>  
  
-   <span data-ttu-id="d983a-143">将以下代码添加到你的应用程序的 app.config 文件。</span><span class="sxs-lookup"><span data-stu-id="d983a-143">Add the following to your application's app.config file.</span></span>  
  
    ```  
    <behaviors>  
      <endpointBehaviors>  
        <behavior name="NewBehavior">  
          <dataContractSerializer maxItemsInObjectGraph="65536000" />  
        </behavior>  
      </endpointBehaviors>  
    </behaviors>  
    ```  
  
 <span data-ttu-id="d983a-144">示例 app.config 类似如下所示。</span><span class="sxs-lookup"><span data-stu-id="d983a-144">A sample app.config looks like this.</span></span>  
  
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
      <endpoint   behaviorConfiguration="NewBehavior" binding="oracleDBBinding"  
       contract="IOutboundContract" name="oracle_ICalculator" />  
    </client>  
  </system.serviceModel>  
</configuration>  
```  
  
###  <a name="BKMK_OraDBPerfOps"></a><span data-ttu-id="d983a-145">在 Oracle 数据库上执行操作时出错</span><span class="sxs-lookup"><span data-stu-id="d983a-145">Error while performing operations on the Oracle database</span></span>  
 <span data-ttu-id="d983a-146">**问题**</span><span class="sxs-lookup"><span data-stu-id="d983a-146">**Problem**</span></span>  
  
 <span data-ttu-id="d983a-147">适配器执行针对使用 Oracle 数据库的任何操作时将报告以下错误[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="d983a-147">The adapter gives the following error when performing any operation on the Oracle database using [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)].</span></span>  
  
-   <span data-ttu-id="d983a-148">**BizTalk server**</span><span class="sxs-lookup"><span data-stu-id="d983a-148">**For BizTalk Server**</span></span>  
  
    ```  
    System.ArgumentNullException: Value cannot be null.  
    ```  
  
 <span data-ttu-id="d983a-149">**可能的原因**</span><span class="sxs-lookup"><span data-stu-id="d983a-149">**Cause**</span></span>  
  
 <span data-ttu-id="d983a-150">未指定消息的 WCF 操作。</span><span class="sxs-lookup"><span data-stu-id="d983a-150">The WCF action for the message is not specified.</span></span> <span data-ttu-id="d983a-151">WCF 需要为每个操作，在 LOB 应用程序上执行的操作会告知适配器指定的 SOAP 操作。</span><span class="sxs-lookup"><span data-stu-id="d983a-151">WCF requires a SOAP action to be specified for every operation, which informs the adapter about the operation to be performed on the LOB application.</span></span>  
  
 <span data-ttu-id="d983a-152">**解决方法**</span><span class="sxs-lookup"><span data-stu-id="d983a-152">**Resolution**</span></span>  
  
 <span data-ttu-id="d983a-153">指定的 SOAP 操作中发送端口或 BizTalk 业务流程中的消息上下文属性。</span><span class="sxs-lookup"><span data-stu-id="d983a-153">Specify the SOAP action in the send port or as a message context property in a BizTalk orchestration.</span></span> <span data-ttu-id="d983a-154">有关说明，请参阅[配置 Oracle 数据库的 SOAP 操作](../../adapters-and-accelerators/adapter-oracle-database/configure-the-soap-action-for-oracle-database.md)。</span><span class="sxs-lookup"><span data-stu-id="d983a-154">For instructions, see [Configure the SOAP action for Oracle Database](../../adapters-and-accelerators/adapter-oracle-database/configure-the-soap-action-for-oracle-database.md).</span></span> <span data-ttu-id="d983a-155">请参阅[消息和消息架构](messages-and-message-schemas-for-biztalk-adapter-for-oracle-database.md)若要查看的每个操作的操作的列表。</span><span class="sxs-lookup"><span data-stu-id="d983a-155">See [Messages and Message Schemas](messages-and-message-schemas-for-biztalk-adapter-for-oracle-database.md) to see a list of actions for each operation.</span></span>  
  
###  <a name="BKMK_OraDBXmlParsing"></a><span data-ttu-id="d983a-156">由于指定的操作中的不正确的操作名称 XmlReaderParsingException</span><span class="sxs-lookup"><span data-stu-id="d983a-156">XmlReaderParsingException due to an incorrect operation name in the specified action</span></span>  
 <span data-ttu-id="d983a-157">**问题**</span><span class="sxs-lookup"><span data-stu-id="d983a-157">**Problem**</span></span>  
  
 <span data-ttu-id="d983a-158">将消息发送到 Oracle 数据库时，BizTalk Server 管理控制台提供了以下错误：</span><span class="sxs-lookup"><span data-stu-id="d983a-158">The BizTalk Server Administration Console gives the following error when sending messages to an Oracle database:</span></span>  
  
```  
Microsoft.ServiceModel.Channels.Common.XmlReaderParsingException: Invalid argument:  
<BtsActionMapping xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xmlns:xsd="http://www.w3.org/2001/XMLSchema">  
  <Operation Name="<operation_name>" Action="<action>" />  
</BtsActionMapping>  
```  
  
 <span data-ttu-id="d983a-159">**可能的原因**</span><span class="sxs-lookup"><span data-stu-id="d983a-159">**Cause**</span></span>  
  
 <span data-ttu-id="d983a-160">如果通过导入创建的端口绑定文件中配置 WCF 自定义端口[!INCLUDE[consumeadapterservlong](../../includes/consumeadapterservlong-md.md)]，采用以下格式指定端口中的操作：</span><span class="sxs-lookup"><span data-stu-id="d983a-160">If you configure a WCF-Custom port by importing the port binding file created by the [!INCLUDE[consumeadapterservlong](../../includes/consumeadapterservlong-md.md)], the action in the port is specified in the following format:</span></span>  
  
```  
<BtsActionMapping>  
  <Operation Name="Op1" Action="http://MyService/Svc/Op1" />  
</BtsActionMapping>  
```  
  
 <span data-ttu-id="d983a-161">在以上格式中，操作名称受生成架构时选择该操作。</span><span class="sxs-lookup"><span data-stu-id="d983a-161">In the above format, the operation name is governed by the operation you chose while generating the schema.</span></span> <span data-ttu-id="d983a-162">例如，如果你生成 Insert 操作对表的架构，操作中的操作名称将"插入"。</span><span class="sxs-lookup"><span data-stu-id="d983a-162">For example, if you generated schema for the Insert operation on a table, the operation name in the action will be "Insert".</span></span> <span data-ttu-id="d983a-163">但是中的逻辑端口的操作名称创建在 BizTalk 业务流程中[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]可能不同。</span><span class="sxs-lookup"><span data-stu-id="d983a-163">However, the operation name in the logical port created in the BizTalk orchestration in [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)] might be different.</span></span>  
  
 <span data-ttu-id="d983a-164">**解决方法**</span><span class="sxs-lookup"><span data-stu-id="d983a-164">**Resolution**</span></span>  
  
 <span data-ttu-id="d983a-165">请确保操作名称在这两个逻辑端口 (在 BizTalk 业务流程中[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]) 和 （在 BizTalk Server 管理控制台） 的物理端口都相同。</span><span class="sxs-lookup"><span data-stu-id="d983a-165">Make sure the operation names in both the logical port (in the BizTalk orchestration in [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]) and the physical port (in BizTalk Server Administration Console) are same.</span></span>  
  
###  <a name="BKMK_OraDBConnURI"></a><span data-ttu-id="d983a-166">在 BizTalk 中指定的 WCF 自定义端口的连接 URI 时出错</span><span class="sxs-lookup"><span data-stu-id="d983a-166">Error while specifying a connection URI for a WCF-Custom port in BizTalk</span></span>  
 <span data-ttu-id="d983a-167">**问题**</span><span class="sxs-lookup"><span data-stu-id="d983a-167">**Problem**</span></span>  
  
 [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]<span data-ttu-id="d983a-168">指定连接 URI 来连接到 Oracle 数据库时，则报告以下错误。</span><span class="sxs-lookup"><span data-stu-id="d983a-168"> gives the following error when you specify a connection URI to connect to the Oracle database.</span></span>  
  
```  
Error saving properties.  
(System.ArgumentException) The specified address is invalid.  
(System.ArgumentException) Invalid address;  
"<connection URI>" is not a well-formed absolute uri.  
```  
  
 <span data-ttu-id="d983a-169">**可能的原因**</span><span class="sxs-lookup"><span data-stu-id="d983a-169">**Cause**</span></span>  
  
 <span data-ttu-id="d983a-170">连接 URI 不符合标准的编码格式。</span><span class="sxs-lookup"><span data-stu-id="d983a-170">The connection URI does not adhere to the standard encoding format.</span></span> <span data-ttu-id="d983a-171">例如，参数的值可能包含一个空格。</span><span class="sxs-lookup"><span data-stu-id="d983a-171">For example, the value for a parameter might contain a space.</span></span>  
  
 <span data-ttu-id="d983a-172">**解决方法**</span><span class="sxs-lookup"><span data-stu-id="d983a-172">**Resolution**</span></span>  
  
 <span data-ttu-id="d983a-173">请确保你指定的 URI 符合标准的编码格式的连接。</span><span class="sxs-lookup"><span data-stu-id="d983a-173">Make sure the connection URI you specify adheres to the standard encoding format.</span></span> <span data-ttu-id="d983a-174">例如，必须通过"%20"替换为空格。</span><span class="sxs-lookup"><span data-stu-id="d983a-174">For example, a blank space must be replaced by "%20".</span></span>  
  
###  <a name="BKMK_OraDBInvalCursor"></a><span data-ttu-id="d983a-175">无效的游标异常时调用采用 REF CURSOR 参数的存储的过程</span><span class="sxs-lookup"><span data-stu-id="d983a-175">Invalid cursor exception while invoking stored procedures that take REF CURSOR parameters</span></span>  
 <span data-ttu-id="d983a-176">**问题**</span><span class="sxs-lookup"><span data-stu-id="d983a-176">**Problem**</span></span>  
  
 <span data-ttu-id="d983a-177">在调用时采用 REF CURSOR 输入 Oracle 数据库中的过程，你可能会出现以下异常：</span><span class="sxs-lookup"><span data-stu-id="d983a-177">When you invoke procedures in the Oracle database that take REF CURSOR inputs, you might get the following exception:</span></span>  
  
```  
Microsoft.ServiceModel.Channels.Common.TargetSystemException: ORA-01001: invalid cursor ---> Oracle.DataAccess.Client.OracleException  
```  
  
 <span data-ttu-id="d983a-178">**可能的原因**</span><span class="sxs-lookup"><span data-stu-id="d983a-178">**Cause**</span></span>  
  
 <span data-ttu-id="d983a-179">正在调用的过程的 PL/SQL 块无法管道 REF Cursor，即，在 REF CURSOR 无法获取分配给出 REF CURSOR。</span><span class="sxs-lookup"><span data-stu-id="d983a-179">The PL/SQL block for the procedure that you are invoking could be piping the REF CURSORs, that is, the IN REF CURSOR could be getting assigned to the OUT REF CURSOR.</span></span>  
  
 <span data-ttu-id="d983a-180">**解决方法**</span><span class="sxs-lookup"><span data-stu-id="d983a-180">**Resolution**</span></span>  
  
 <span data-ttu-id="d983a-181">PL/SQL 块必须不通过管道传递到而不正确处理 OUT REF Cursor IN。</span><span class="sxs-lookup"><span data-stu-id="d983a-181">The PL/SQL block must not pipe the IN to the OUT REF CURSORs without proper processing.</span></span>  
  
###  <a name="BKMK_OraDBValidateResp"></a><span data-ttu-id="d983a-182">验证使用 BizTalk Server ReadLOB 操作的响应时出错。</span><span class="sxs-lookup"><span data-stu-id="d983a-182">Error while validating the response for the ReadLOB operation using BizTalk Server</span></span>  
 <span data-ttu-id="d983a-183">**问题**</span><span class="sxs-lookup"><span data-stu-id="d983a-183">**Problem**</span></span>  
  
 <span data-ttu-id="d983a-184">执行 ReadLOB 操作使用时[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]与[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]，从 Oracle 数据库响应未通过验证对 Web 服务描述语言 (WSDL)。</span><span class="sxs-lookup"><span data-stu-id="d983a-184">While performing a ReadLOB operation using the [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] with [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)], the response from the Oracle database fails validation against the Web Services Description Language (WSDL).</span></span>  
  
 <span data-ttu-id="d983a-185">**可能的原因**</span><span class="sxs-lookup"><span data-stu-id="d983a-185">**Cause**</span></span>  
  
 <span data-ttu-id="d983a-186">WSDL 包含的程序定义执行的基于服务的请求，但不是需要为 BizTalk 方案 StreamBody 节点名称。</span><span class="sxs-lookup"><span data-stu-id="d983a-186">The WSDL contains a StreamBody node name that is defined for execution of service-based requests, but is not needed for BizTalk scenarios.</span></span> <span data-ttu-id="d983a-187">因此，输出 XML，不包含 StreamBody 节点，相比的 WSDL 中，验证将失败。</span><span class="sxs-lookup"><span data-stu-id="d983a-187">Therefore, when the output XML, which does not contain the StreamBody node, is compared with the WSDL, validation fails.</span></span>  
  
 <span data-ttu-id="d983a-188">**解决方法**</span><span class="sxs-lookup"><span data-stu-id="d983a-188">**Resolution**</span></span>  
  
 <span data-ttu-id="d983a-189">使用 BizTalk Server 生成的输出进行验证时，请从 WSDL 删除 StreamBody 节点。</span><span class="sxs-lookup"><span data-stu-id="d983a-189">Remove the StreamBody node from the WSDL when validating against the output that was generated using BizTalk Server.</span></span> <span data-ttu-id="d983a-190">执行以下步骤，若要这样做：</span><span class="sxs-lookup"><span data-stu-id="d983a-190">Perform the following steps to do so:</span></span>  
  
1.  <span data-ttu-id="d983a-191">WSDL 包含 StreamBody 节点如下所示。</span><span class="sxs-lookup"><span data-stu-id="d983a-191">The WSDL containing the StreamBody node looks like this.</span></span>  
  
    ```  
    <xs:element name="ReadLOBResponse">  
        <xs:annotation>  
          <xs:documentation>  
            <doc:action xmlns:doc="http://schemas.microsoft.com/servicemodel/adapters/metadata/documentation">http://Microsoft.LobServices.OracleDB/2007/03/SCOTT/Table/TBL_ALL_DATATYPES/ReadLOB/response\</doc:action>  
          </xs:documentation>  
        </xs:annotation>  
        <xs:complexType>  
          <xs:sequence>  
            <xs:element minOccurs="1" maxOccurs="1" name="ReadLOBResult" nillable="true" type="ns3:StreamBody" />  
          </xs:sequence>  
        </xs:complexType>  
      </xs:element>  
    ```  
  
     <span data-ttu-id="d983a-192">将替换为以下前面。</span><span class="sxs-lookup"><span data-stu-id="d983a-192">Replace the preceding with the following.</span></span>  
  
    ```  
    <xs:element name="ReadLOBResponse">  
     <xs:annotation>  
     <xs:documentation>  
      <doc:action xmlns:doc="http://schemas.microsoft.com/servicemodel/adapters/metadata/documentation">http://Microsoft.LobServices.OracleDB/2007/03/SCOTT/Table/TBL_ALL_DATATYPES/ReadLOB/response\</doc:action>   
      </xs:documentation>  
      </xs:annotation>  
     <xs:complexType>  
     <xs:sequence>  
      <xs:element minOccurs="1" maxOccurs="1" name="ReadLOBResult" type="xs:base64Binary" />   
      </xs:sequence>  
      </xs:complexType>  
      </xs:element>  
    ```  
  
     <span data-ttu-id="d983a-193">在此步骤中，删除类型引用 ="ns3:StreamBody"原始 XSD 中的并替换类型 ="xs:base64Binary"。</span><span class="sxs-lookup"><span data-stu-id="d983a-193">In this step, you removed the reference to type="ns3:StreamBody" in the original XSD and replaced it with type="xs:base64Binary".</span></span> <span data-ttu-id="d983a-194">此外，你可以从原始 XSD 删除 nillable ="true"值。</span><span class="sxs-lookup"><span data-stu-id="d983a-194">Also, you removed the nillable="true" value from the original XSD.</span></span>  
  
2.  <span data-ttu-id="d983a-195">从 WSDL 删除以下。</span><span class="sxs-lookup"><span data-stu-id="d983a-195">Remove the following from the WSDL.</span></span>  
  
    ```  
    <xs:complexType name="StreamBody">  
        <xs:sequence>  
          <xs:element minOccurs="1" maxOccurs="1" name="Stream">  
            <xs:simpleType>  
              <xs:restriction base="xs:base64Binary">  
                <xs:minLength value="0" />  
              </xs:restriction>  
            </xs:simpleType>  
          </xs:element>  
        </xs:sequence>  
      </xs:complexType>  
      <xs:element name="StreamBody" nillable="true" type="ns3:StreamBody" />  
    ```  
  
    > [!NOTE]
    >  <span data-ttu-id="d983a-196">不支持 ReadLOB 操作[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="d983a-196">ReadLOB operation is not supported with [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)].</span></span> <span data-ttu-id="d983a-197">应使用表选择操作将从中读取 LOB 数据[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]解决方案。</span><span class="sxs-lookup"><span data-stu-id="d983a-197">You should use a table Select operation to read LOB data from a [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] solution.</span></span>  
  
###  <a name="BKMK_OraDBSchemaValidateFail"></a><span data-ttu-id="d983a-198">架构验证在轮询的情况下可能会失败</span><span class="sxs-lookup"><span data-stu-id="d983a-198">Schema validation may fail in polling scenarios</span></span>  
 <span data-ttu-id="d983a-199">**问题**</span><span class="sxs-lookup"><span data-stu-id="d983a-199">**Problem**</span></span>  
  
 <span data-ttu-id="d983a-200">在方案中的架构验证失败其中[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]轮询数据库包含 ROWID 或 UNROWID 类型的字段的表。</span><span class="sxs-lookup"><span data-stu-id="d983a-200">Schema validation fails in scenarios where the [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] polls database tables that contain fields of type ROWID or UNROWID.</span></span>  
  
 <span data-ttu-id="d983a-201">**可能的原因**</span><span class="sxs-lookup"><span data-stu-id="d983a-201">**Cause**</span></span>  
  
 <span data-ttu-id="d983a-202">在设计时时适配器生成包含 ROWID 或 UNROWID，类型的字段的表的元数据架构包括"nillable = false"，这意味着 ROWID 或 UNROWID 类型的字段不能为 null。</span><span class="sxs-lookup"><span data-stu-id="d983a-202">At design-time, when the adapter generates metadata for the table containing fields of type ROWID or UNROWID, the schema includes “nillable=false”, which means that fields of type ROWID or UNROWID cannot be null.</span></span> <span data-ttu-id="d983a-203">但是，在运行时时该适配器中检索元数据，ROWID 或 UNROWID 类型的字段包含 null 值。</span><span class="sxs-lookup"><span data-stu-id="d983a-203">However, at run-time when the adapter retrieves the metadata, the fields of type ROWID or UNROWID contain null values.</span></span> <span data-ttu-id="d983a-204">因此架构验证将失败。</span><span class="sxs-lookup"><span data-stu-id="d983a-204">Hence the schema validation fails.</span></span>  
  
 <span data-ttu-id="d983a-205">**解决方法**</span><span class="sxs-lookup"><span data-stu-id="d983a-205">**Resolution**</span></span>  
  
 <span data-ttu-id="d983a-206">如果你使用[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]与[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]，你可以选择禁用架构验证。</span><span class="sxs-lookup"><span data-stu-id="d983a-206">If you are using the [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] with [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)], you may choose to disable schema validation.</span></span> <span data-ttu-id="d983a-207">或者，您可以手动编辑架构更改"nillbale = true"对于 ROWID 和 UNROWID 数据类型。</span><span class="sxs-lookup"><span data-stu-id="d983a-207">Alternatively, you may manually edit the schema to change “nillbale=true” for ROWID and UNROWID data types.</span></span>  
  
###  <a name="BKMK_OraDBUnreasonConv"></a><span data-ttu-id="d983a-208">不合理 conversion 请求错误时执行作为参数的存储过程带有记录类型</span><span class="sxs-lookup"><span data-stu-id="d983a-208">'Unreasonable conversion requested' error when executing stored procedures with Record Types as parameters</span></span>  
 <span data-ttu-id="d983a-209">**可能的原因**</span><span class="sxs-lookup"><span data-stu-id="d983a-209">**Cause**</span></span>  
  
 <span data-ttu-id="d983a-210">假设 Oracle 存储过程采用一种记录类型作为参数。</span><span class="sxs-lookup"><span data-stu-id="d983a-210">Consider a scenario where an Oracle stored procedure takes a Record Type as a parameter.</span></span> <span data-ttu-id="d983a-211">假定记录类型声明为\<表名\>%rowtype，其中表具有长整型数据类型的列。</span><span class="sxs-lookup"><span data-stu-id="d983a-211">Assume that the Record Type is declared as \<table name\>%ROWTYPE, where the table has a column of LONG data type.</span></span> <span data-ttu-id="d983a-212">当[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]遇到的长数据类型，它设置数据类型的大小等于指定的值**LongDatatypeColumnSize**绑定属性。</span><span class="sxs-lookup"><span data-stu-id="d983a-212">When the [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] encounters the LONG data type, it sets the size of the data type equal to the value specified for the **LongDatatypeColumnSize** binding property.</span></span> <span data-ttu-id="d983a-213">但是，Oracle 数据库未定义 LONG 数据类型的大小。</span><span class="sxs-lookup"><span data-stu-id="d983a-213">However, the Oracle database does not define a size for the LONG data type.</span></span> <span data-ttu-id="d983a-214">因此，当适配器调用存储的过程时，它会导致不合理 conversion 请求错误。</span><span class="sxs-lookup"><span data-stu-id="d983a-214">So, when the adapter invokes the stored procedure, it results in an ‘Unreasonable conversion requested’ error.</span></span>  
  
 <span data-ttu-id="d983a-215">**解决方法**</span><span class="sxs-lookup"><span data-stu-id="d983a-215">**Resolution**</span></span>  
  
 <span data-ttu-id="d983a-216">如果记录类型 LONG 数据类型，您必须显式定义它作为包的一部分。</span><span class="sxs-lookup"><span data-stu-id="d983a-216">If a Record Type has a LONG data type, you must explicitly define it as part of a package.</span></span>  
  
###  <a name="BKMK_OraDBAdapRecognize"></a><span data-ttu-id="d983a-217">适配器无法识别的物理端口上的操作，即使使用适配器服务外接程序生成的绑定文件用于创建端口</span><span class="sxs-lookup"><span data-stu-id="d983a-217">The adapter does not recognize the action on the physical port even though you use the binding file generated by the Consume Adapter Service add-in to create the ports</span></span>  
 <span data-ttu-id="d983a-218">**问题**</span><span class="sxs-lookup"><span data-stu-id="d983a-218">**Problem**</span></span>  
  
 <span data-ttu-id="d983a-219">在使用后[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]若要生成对 Oracle 数据库的特定操作的架构外, 接程序还会创建端口绑定文件。</span><span class="sxs-lookup"><span data-stu-id="d983a-219">After you use the [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)] to generate schema for a specific operation on the Oracle database, the add-in also creates a port binding file.</span></span> <span data-ttu-id="d983a-220">可以导入此文件使用绑定的[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]BizTalk Server 中创建的物理端口的管理控制台。</span><span class="sxs-lookup"><span data-stu-id="d983a-220">You can import this binding file using the [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] Administration console to create physical ports in BizTalk Server.</span></span> <span data-ttu-id="d983a-221">但是，当消息发送到使用此类端口 Oracle 数据库时，该适配器将无法了解在端口上指定的操作，并提供了类似于以下错误：</span><span class="sxs-lookup"><span data-stu-id="d983a-221">However, when you send messages to the Oracle database using such ports, the adapter fails to understand the action specified on the port and gives an error similar to the following:</span></span>  
  
```  
Microsoft.ServiceModel.Channels.Common.UnsupportedOperationException: Incorrect Action   
<BtsActionMapping xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xmlns:xsd="http://www.w3.org/2001/XMLSchema">  
  <Operation Name="<op_name>" Action="<action>" />  
</BtsActionMapping>. Correct the specified Action, or refer to the documentation on the allowed formats for the Actions.  
```  
  
 <span data-ttu-id="d983a-222">**可能的原因**</span><span class="sxs-lookup"><span data-stu-id="d983a-222">**Cause**</span></span>  
  
 <span data-ttu-id="d983a-223">在创建逻辑端口 BizTalk 业务流程中时，指定这些端口上的操作的某些名称，或只需使用如 Operation_1、 Operation_2 等的默认名称。但是，在生成的绑定文件[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]，操作名称是与为其生成元数据的 Oracle 数据库操作的名称相同。</span><span class="sxs-lookup"><span data-stu-id="d983a-223">When you create logical ports in a BizTalk orchestration, you specify certain names for the operations on those ports or you just use the default names like Operation_1, Operation_2, etc. However, in the binding file generated by the [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)], the operation name is same as the name of the Oracle database operation for which you generate metadata.</span></span> <span data-ttu-id="d983a-224">例如，如果 Oracle 数据库中生成 ACCOUNTACTIVITY 表选择操作的元数据，操作将设置为以下：</span><span class="sxs-lookup"><span data-stu-id="d983a-224">For example, if you generate metadata for Select operation on ACCOUNTACTIVITY table in the Oracle database, the action will be set to the following:</span></span>  
  
```  
<Operation Name="Select" Action="http://Microsoft.LobServices.OracleDB/2007/03/SCOTT/Table/ACCOUNTACTIVITY/Select" />  
```  
  
 <span data-ttu-id="d983a-225">当你导入的绑定文件时，物理端口设置相同的操作。</span><span class="sxs-lookup"><span data-stu-id="d983a-225">When you import the binding file, the same action is set on physical port.</span></span> <span data-ttu-id="d983a-226">因此，逻辑端口 （Operation_1、 Operation_2 等） 上的操作名称与上的物理端口，从而导致错误的操作中指定的操作名称不匹配。</span><span class="sxs-lookup"><span data-stu-id="d983a-226">So, the operation names on the logical port (Operation_1, Operation_2, etc.) do not match the operation names specified in the action on the physical port, resulting in an error.</span></span>  
  
 <span data-ttu-id="d983a-227">**解决方法**</span><span class="sxs-lookup"><span data-stu-id="d983a-227">**Resolution**</span></span>  
  
 <span data-ttu-id="d983a-228">请确保逻辑端口中的操作名称指定为中的物理端口的操作的一部分的操作名称相同。</span><span class="sxs-lookup"><span data-stu-id="d983a-228">Make sure the operation name in the logical port is the same as the operation name specified as part of the action in the physical port.</span></span> <span data-ttu-id="d983a-229">执行以下操作之一：</span><span class="sxs-lookup"><span data-stu-id="d983a-229">Do one of the following:</span></span>  
  
-   <span data-ttu-id="d983a-230">对为其生成元数据，例如选择操作从 Operation_1 等更改 BizTalk 业务流程中的逻辑端口中的操作名称。</span><span class="sxs-lookup"><span data-stu-id="d983a-230">Change the operation name in the logical port in BizTalk orchestration from Operation_1, etc. to the operation for which you generate metadata, for example Select.</span></span>  
  
-   <span data-ttu-id="d983a-231">将中的物理端口上的操作的操作名称更改为中的逻辑端口的操作名称。</span><span class="sxs-lookup"><span data-stu-id="d983a-231">Change the operation name in the action on the physical port to the operation name in the logical port.</span></span> <span data-ttu-id="d983a-232">例如，你无法更改中类似于下面的物理端口的操作：</span><span class="sxs-lookup"><span data-stu-id="d983a-232">For example, you could change the action in the physical port to resemble the following:</span></span>  
  
    ```  
    <Operation Name="Operation_1" Action="http://Microsoft.LobServices.OracleDB/2007/03/SCOTT/Table/ACCOUNTACTIVITY/Select" />  
    ```  
  
###  <a name="BKMK_OraDBOverflowExcep"></a><span data-ttu-id="d983a-233">适配器引发溢出异常 ("System.OverflowException") 上执行操作</span><span class="sxs-lookup"><span data-stu-id="d983a-233">Adapter throws an overflow exception (“System.OverflowException”) on executing an operation</span></span>  
 <span data-ttu-id="d983a-234">**问题**</span><span class="sxs-lookup"><span data-stu-id="d983a-234">**Problem**</span></span>  
  
 <span data-ttu-id="d983a-235">如果你尝试执行操作包含在数据集或弱类型 REF CURSOR 的 Oracle 数值数据类型，请使用该适配器，该适配器可能引发溢出异常。</span><span class="sxs-lookup"><span data-stu-id="d983a-235">Using the adapter, if you try to perform an operation containing Oracle numeric data types inside DataSets or weakly-typed REF CURSORS, the adapter might throw an overflow exception.</span></span>  
  
 <span data-ttu-id="d983a-236">**可能的原因**</span><span class="sxs-lookup"><span data-stu-id="d983a-236">**Cause**</span></span>  
  
 <span data-ttu-id="d983a-237">如果你提供在数据集或弱类型 REF CURSOR，无法容纳到相应的.NET 类型内的 Oracle 数值数据类型为较大的值，将发生这种情况。</span><span class="sxs-lookup"><span data-stu-id="d983a-237">This happens if you supply a large value for the Oracle numeric data type inside DataSets or weakly-typed REF CURSORS that cannot fit into the respective .NET type.</span></span>  
  
 <span data-ttu-id="d983a-238">**解决方法**</span><span class="sxs-lookup"><span data-stu-id="d983a-238">**Resolution**</span></span>  
  
 <span data-ttu-id="d983a-239">如果你想要将较大的值传递的数据集或弱类型 REF CURSOR 内的 Oracle 数值数据类型，则必须启用安全设置的值键入**EnableSafeTyping**属性绑定到**true**.</span><span class="sxs-lookup"><span data-stu-id="d983a-239">If you want to pass large values for the Oracle numeric data type inside DataSets or weakly-typed REF CURSORS, you must enable safe typing by setting the value of the **EnableSafeTyping** binding property to **true**.</span></span> <span data-ttu-id="d983a-240">启用安全键入将在数据集或弱类型 REF CURSOR 内的 Oracle 数值数据类型公开为字符串。</span><span class="sxs-lookup"><span data-stu-id="d983a-240">Enabling safe typing exposes the Oracle numeric data type inside DataSets or weakly-typed REF CURSORS as strings.</span></span>  
  
###  <a name="BKMK_OraDBRootNode"></a><span data-ttu-id="d983a-241">与 RootNode TypeName BizTalk 项目中的错误</span><span class="sxs-lookup"><span data-stu-id="d983a-241">Error with RootNode TypeName in BizTalk Projects</span></span>  
 <span data-ttu-id="d983a-242">**问题**</span><span class="sxs-lookup"><span data-stu-id="d983a-242">**Problem**</span></span>  
  
 <span data-ttu-id="d983a-243">在 BizTalk 项目中[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]，如果从架构生成[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]包含无效字符或保留的字**RootNode TypeName**属性，编译项目时将出现以下错误:</span><span class="sxs-lookup"><span data-stu-id="d983a-243">In a BizTalk project in [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)], if the schemas generated from the [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)] contains invalid characters or reserved words for the **RootNode TypeName** property, the following error will occur while compiling the project:</span></span>  
  
```  
Node <node reference> - Specify a valid .NET type name for this root node.  
The current .NET type name of this root node is invalid (it is a reserved BizTalk Keyword or is an invalid C# identifier).  
```  
  
 <span data-ttu-id="d983a-244">**解决方法**</span><span class="sxs-lookup"><span data-stu-id="d983a-244">**Resolution**</span></span>  
  
1.  <span data-ttu-id="d983a-245">右键单击该错误并选择中引用的 rood 节点**属性**。</span><span class="sxs-lookup"><span data-stu-id="d983a-245">Right-click the rood node referenced in the error and select **Properties**.</span></span>  
  
2.  <span data-ttu-id="d983a-246">有关**RootNode TypeName**属性，删除任何非法字符或保留字，例如，圆点 （.）。</span><span class="sxs-lookup"><span data-stu-id="d983a-246">For the **RootNode TypeName** property, remove any illegal characters or reserved words, for example, dot (.).</span></span>  
  
###  <a name="BKMK_OraDBInvalBinding"></a><span data-ttu-id="d983a-247">使用 Visual Studio 中的适配器时出现的无效的绑定警告</span><span class="sxs-lookup"><span data-stu-id="d983a-247">Invalid binding warning when using the adapter in Visual Studio</span></span>  
 <span data-ttu-id="d983a-248">**问题**</span><span class="sxs-lookup"><span data-stu-id="d983a-248">**Problem**</span></span>  
  
 <span data-ttu-id="d983a-249">当你使用该适配器创建的应用程序在[!INCLUDE[btsVStudio2008](../../includes/btsvstudio2008-md.md)]并打开生成的适配器的配置文件 (app.config)，你看到类似于以下警告：</span><span class="sxs-lookup"><span data-stu-id="d983a-249">When you use the adapter to create an application in [!INCLUDE[btsVStudio2008](../../includes/btsvstudio2008-md.md)] and you open the configuration file (app.config) generated by the adapter, you see a warning similar to the following:</span></span>  
  
```  
The element 'bindings' has invalid child element 'oracleDBBinding'. List of possible elements expected: 'basicHttpBinding, customBinding, ...  
```  
  
 <span data-ttu-id="d983a-250">**可能的原因**</span><span class="sxs-lookup"><span data-stu-id="d983a-250">**Cause**</span></span>  
  
 <span data-ttu-id="d983a-251">由于会出现此警告[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]绑定， `oracleDBBinding`，不标准绑定随[!INCLUDE[firstref_btsWinCommFoundation](../../includes/firstref-btswincommfoundation-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="d983a-251">This warning appears because the [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] binding, `oracleDBBinding`, is not a standard binding shipped with the [!INCLUDE[firstref_btsWinCommFoundation](../../includes/firstref-btswincommfoundation-md.md)].</span></span>  
  
 <span data-ttu-id="d983a-252">**解决方法**</span><span class="sxs-lookup"><span data-stu-id="d983a-252">**Resolution**</span></span>  
  
 <span data-ttu-id="d983a-253">可以安全地忽略此警告。</span><span class="sxs-lookup"><span data-stu-id="d983a-253">You can safely ignore this warning.</span></span>  
  
###  <a name="BKMK_OraDBNotification"></a><span data-ttu-id="d983a-254">BizTalk Server 引发异常，如果你在同一应用程序使用多个通知架构或跨同一个主机上的多个应用程序使用通知架构</span><span class="sxs-lookup"><span data-stu-id="d983a-254">BizTalk Server throws an exception if you use more than one Notification schema in the same application or use the Notification schema across multiple applications on the same host</span></span>  
 <span data-ttu-id="d983a-255">**问题**</span><span class="sxs-lookup"><span data-stu-id="d983a-255">**Problem**</span></span>  
  
 <span data-ttu-id="d983a-256">BizTalk Server 引发 XLANG 异常或异常指出应用程序找不到文档规范，因为多个架构匹配的消息类型。</span><span class="sxs-lookup"><span data-stu-id="d983a-256">BizTalk Server throws an XLANG exception or an exception stating that the application cannot locate the document specification because multiple schemas matched the message type.</span></span>  
  
 <span data-ttu-id="d983a-257">**可能的原因**</span><span class="sxs-lookup"><span data-stu-id="d983a-257">**Cause**</span></span>  
  
 <span data-ttu-id="d983a-258">由于以下任一发生这种情况：</span><span class="sxs-lookup"><span data-stu-id="d983a-258">This happens because of either of the following:</span></span>  
  
-   <span data-ttu-id="d983a-259">在你生成多个通知架构在 BizTalk Server 项目中，将其部署到 BizTalk Server 应用程序，，然后运行应用程序从 Oracle 数据库接收通知。</span><span class="sxs-lookup"><span data-stu-id="d983a-259">You have generated more than one Notification schema in a BizTalk Server project, deployed it to a BizTalk Server application, and then ran the application to receive notifications from the Oracle database.</span></span> <span data-ttu-id="d983a-260">由于通知架构是公用的冲突之间没有部署 BizTalk Server 应用程序中的架构。</span><span class="sxs-lookup"><span data-stu-id="d983a-260">Because the Notification schemas are common, there is a conflict between the schemas that are deployed in the BizTalk Server application.</span></span>  
  
-   <span data-ttu-id="d983a-261">发生多个项目，你已为每个 BizTalk 服务器到单独的 BizTalk Server 应用程序在同一主机上的每个项目部署的项目生成通知架构，然后运行应用程序或应用程序接收来自通知Oracle 数据库中。</span><span class="sxs-lookup"><span data-stu-id="d983a-261">In case of multiple projects, you have generated a Notification schema for each of the BizTalk Server projects, deployed each project to a separate BizTalk Server application on the same host, and then ran an application or applications to receive notifications from the Oracle database.</span></span> <span data-ttu-id="d983a-262">因为架构和程序集都可访问 BizTalk Server 中的应用程序，各种 BizTalk Server 应用程序和程序集下部署的常见架构之间存在不冲突。</span><span class="sxs-lookup"><span data-stu-id="d983a-262">Because the schemas and assemblies are accessible across the applications in BizTalk Server, there is a conflict between the common schemas deployed under various BizTalk Server applications and assemblies.</span></span>  
  
 <span data-ttu-id="d983a-263">**解决方法**</span><span class="sxs-lookup"><span data-stu-id="d983a-263">**Resolution**</span></span>  
  
 <span data-ttu-id="d983a-264">BizTalk Server 应用程序使用单个通知架构文件。</span><span class="sxs-lookup"><span data-stu-id="d983a-264">Use a single Notification schema file for a BizTalk Server application.</span></span> <span data-ttu-id="d983a-265">如果你需要在同一主机上的多个 BizTalk Server 应用程序中使用通知架构，创建包含单个通知架构的应用程序，然后使用 BizTalk Server 中的所有其他应用程序中的通知架构。</span><span class="sxs-lookup"><span data-stu-id="d983a-265">If you need to use the Notification schema in multiple BizTalk Server applications on the same host, create an application containing a single Notification schema, and then use the notification schema from all other applications in BizTalk Server.</span></span>  
  
###  <a name="BKMK_MemUsage"></a><span data-ttu-id="d983a-266">内存使用情况和线程计数的增加而在事务处理的入站操作中使用该适配器时</span><span class="sxs-lookup"><span data-stu-id="d983a-266">Memory usage and thread count increases when using the adapter in a transacted inbound operation</span></span>  
 <span data-ttu-id="d983a-267">**问题**</span><span class="sxs-lookup"><span data-stu-id="d983a-267">**Problem**</span></span>  
  
 <span data-ttu-id="d983a-268">在事务处理的入站操作中，如轮询，**如果没有数据轮询表中可用**和适配器继续轮询，通过一段时间则会遇到内存使用量和线程计数的增加。</span><span class="sxs-lookup"><span data-stu-id="d983a-268">In a transacted inbound operation, such as Polling, **if there is no data available in the table being polled** and the adapter continues to poll, over a period of time you experience an increase in the memory usage and the thread count.</span></span>  
  
 <span data-ttu-id="d983a-269">**可能的原因**</span><span class="sxs-lookup"><span data-stu-id="d983a-269">**Cause**</span></span>  
  
 <span data-ttu-id="d983a-270">**如果没有数据轮询表中可用**之后，每个接收超时周期[!INCLUDE[firstref_btsWinCommFoundation](../../includes/firstref-btswincommfoundation-md.md)]生成新的线程来继续轮询操作。</span><span class="sxs-lookup"><span data-stu-id="d983a-270">**If there is no data available in the table being polled**, after every receive timeout cycle, [!INCLUDE[firstref_btsWinCommFoundation](../../includes/firstref-btswincommfoundation-md.md)] spawns a new thread to continue the polling operation.</span></span> <span data-ttu-id="d983a-271">因此，通过一段时间会增加线程计数和内存使用情况。</span><span class="sxs-lookup"><span data-stu-id="d983a-271">Hence, the thread count and memory usage increases over a period of time.</span></span> <span data-ttu-id="d983a-272">但是，如果正在轮询一次的表具有一些数据，同一个线程继续执行所有后续的轮询。</span><span class="sxs-lookup"><span data-stu-id="d983a-272">However, if the table being polled has some data, the same thread continues to perform all subsequent polls.</span></span>  
  
 <span data-ttu-id="d983a-273">**解决方法**</span><span class="sxs-lookup"><span data-stu-id="d983a-273">**Resolution**</span></span>  
  
 <span data-ttu-id="d983a-274">我们建议设置**ReceiveTimeout**为最大可能值，这是 24.20:31:23.6470000 （24 天），以便生成新线程，仅每隔 24 天。</span><span class="sxs-lookup"><span data-stu-id="d983a-274">We recommend setting the **ReceiveTimeout** to the maximum possible value, which is 24.20:31:23.6470000 (24 days) so that a new thread is spawned only every 24 days.</span></span> <span data-ttu-id="d983a-275">这将确保，内存使用情况和线程计数不会增长过多时间太短。</span><span class="sxs-lookup"><span data-stu-id="d983a-275">This will ensure that the memory usage and thread count does not grow too much too soon.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="d983a-276">如果已设置 SqlAdapterInboundTransactionBehavior，请确保 TransactionTimeout 也被配置为最大可能值，该值是 24.20:31:23.6470000 （24 天）。</span><span class="sxs-lookup"><span data-stu-id="d983a-276">If SqlAdapterInboundTransactionBehavior has been set, make sure the TransactionTimeout is also configured to maximum possible value, which is 24.20:31:23.6470000 (24 days).</span></span> <span data-ttu-id="d983a-277">在使用此解决方法，我们可以添加 SqlAdapterInboundTransactionBehavior，仅当事务的隔离级别必须进行配置。</span><span class="sxs-lookup"><span data-stu-id="d983a-277">When using this workaround, we can add the SqlAdapterInboundTransactionBehavior only if the transaction isolation level has to be configured.</span></span> <span data-ttu-id="d983a-278">否则，它是一种最佳做法来删除该行为。</span><span class="sxs-lookup"><span data-stu-id="d983a-278">Else, it is a best practice to remove that behavior.</span></span>  
  
 <span data-ttu-id="d983a-279">有关详细信息**ReceiveTimeout**绑定属性，请参阅[阅读有关 Oracle 数据库适配器绑定属性](../../adapters-and-accelerators/adapter-oracle-database/read-about-the-oracle-database-adapter-binding-properties.md)。</span><span class="sxs-lookup"><span data-stu-id="d983a-279">For more information about the **ReceiveTimeout** binding property, see [Read about the Oracle Database adapter binding properties](../../adapters-and-accelerators/adapter-oracle-database/read-about-the-oracle-database-adapter-binding-properties.md).</span></span> <span data-ttu-id="d983a-280">指定绑定属性的说明，请参阅[用于 Oracle 数据库配置的绑定属性](../../adapters-and-accelerators/adapter-oracle-database/configure-the-binding-properties-for-oracle-database.md)。</span><span class="sxs-lookup"><span data-stu-id="d983a-280">For instructions on specifying binding properties, see [Configure the binding properties for Oracle Database](../../adapters-and-accelerators/adapter-oracle-database/configure-the-binding-properties-for-oracle-database.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="d983a-281">使用的适配器时[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]，将超时设置为较大的值不会影响的适配器的功能。</span><span class="sxs-lookup"><span data-stu-id="d983a-281">When using the adapter with [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)], setting the timeout to a large value does not impact the functionality of the adapter.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d983a-282">另请参阅</span><span class="sxs-lookup"><span data-stu-id="d983a-282">See Also</span></span>  
[<span data-ttu-id="d983a-283">对 Oracle 数据库适配器进行故障排除</span><span class="sxs-lookup"><span data-stu-id="d983a-283">Troubleshoot the Oracle Database adapter</span></span>](../../adapters-and-accelerators/adapter-oracle-database/troubleshoot-the-oracle-database-adapter.md)  
[<span data-ttu-id="d983a-284">解决与 Oracle 数据库适配器的安装问题</span><span class="sxs-lookup"><span data-stu-id="d983a-284">Troubleshoot installation issues with the Oracle Database adapter</span></span>](../../adapters-and-accelerators/adapter-oracle-database/troubleshoot-installation-issues-with-the-oracle-database-adapter.md)