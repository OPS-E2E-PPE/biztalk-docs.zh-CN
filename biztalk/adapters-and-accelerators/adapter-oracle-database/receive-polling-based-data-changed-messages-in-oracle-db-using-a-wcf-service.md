---
title: 使用 WCF 服务模型的 Oracle 数据库中接收基于轮询的数据更改消息 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- WCF service model, receiving polling-based messages
- how to, receive polling-based message
- polling-based messages, receiving by using the WCF service model
ms.assetid: 0324e8bf-d9d1-46f5-b896-b9fc8e61d514
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: fd36081bd92c3bfae13916ed7d984fcd5de9763f
ms.sourcegitcommit: 3fd1c85d9dc2ce7b77da75a5c2087cc48cfcbe50
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/17/2018
ms.locfileid: "22217221"
---
# <a name="receive-polling-based-data-changed-messages-in-oracle-database-using-the-wcf-service-model"></a><span data-ttu-id="95136-102">使用 WCF 服务模型的 Oracle 数据库中接收基于轮询的数据更改消息</span><span class="sxs-lookup"><span data-stu-id="95136-102">Receive Polling-based Data-changed Messages in Oracle Database using the WCF Service Model</span></span>
<span data-ttu-id="95136-103">你可以配置[!INCLUDE[adapteroracle](../../includes/adapteroracle-md.md)]接收基于轮询的数据更改消息所依据的 Oracle 表或视图。</span><span class="sxs-lookup"><span data-stu-id="95136-103">You can configure the [!INCLUDE[adapteroracle](../../includes/adapteroracle-md.md)] to receive polling-based data changed messages against an Oracle table or view.</span></span> <span data-ttu-id="95136-104">若要接收数据更改的消息，该适配器定期执行针对一个 Oracle 表或视图后, 跟一个可选的 PL/SQL 代码块的 SQL 查询。</span><span class="sxs-lookup"><span data-stu-id="95136-104">To receive data-changed messages, the adapter periodically executes a SQL query against an Oracle table or view followed by an optional PL/SQL code block.</span></span> <span data-ttu-id="95136-105">然后返回 SQL 查询的结果[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]到应用程序作为强类型的结果集在入站 POLLINGSTMT 操作中。</span><span class="sxs-lookup"><span data-stu-id="95136-105">The results of the SQL query are then returned by the [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] to your application as a strongly-typed result set in an inbound POLLINGSTMT operation.</span></span> <span data-ttu-id="95136-106">有关用于配置和对 Oracle 执行轮询机制的详细信息数据库使用[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]，请参阅[Oracle 数据库适配器中接收基于轮询的数据更改消息](../../adapters-and-accelerators/adapter-oracle-database/receive-polling-based-data-changed-messages-in-oracle-database-adapter.md)。</span><span class="sxs-lookup"><span data-stu-id="95136-106">For more information about the mechanism used to configure and perform polling on an Oracle database using the [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)], see [Receive polling-based data-changed messages in Oracle Database adapter](../../adapters-and-accelerators/adapter-oracle-database/receive-polling-based-data-changed-messages-in-oracle-database-adapter.md).</span></span> <span data-ttu-id="95136-107">我们强烈建议你阅读然后再继续本主题。</span><span class="sxs-lookup"><span data-stu-id="95136-107">We strongly recommended that you read this topic before proceeding.</span></span>  
  
 <span data-ttu-id="95136-108">若要接收 POLLINGSTMT 操作，当使用 WCF 服务模型时，你必须：</span><span class="sxs-lookup"><span data-stu-id="95136-108">To receive the POLLINGSTMT operation when you use the WCF service model, you must:</span></span>  
  
-   <span data-ttu-id="95136-109">POLLINGSTMT 操作从适配器公开的元数据生成 WCF 服务协定 （接口）。</span><span class="sxs-lookup"><span data-stu-id="95136-109">Generate a WCF service contract (interface) for the POLLINGSTMT operation from the metadata exposed by the adapter.</span></span> <span data-ttu-id="95136-110">若要执行此操作，请使用[!INCLUDE[addadapterservreflong](../../includes/addadapterservreflong-md.md)]或 ServiceModel 元数据实用工具 (svcutil.exe)。</span><span class="sxs-lookup"><span data-stu-id="95136-110">To do this, you use the [!INCLUDE[addadapterservreflong](../../includes/addadapterservreflong-md.md)] or the ServiceModel Metadata Utility Tool (svcutil.exe).</span></span>  
  
-   <span data-ttu-id="95136-111">实现此接口从 WCF 服务。</span><span class="sxs-lookup"><span data-stu-id="95136-111">Implement a WCF service from this interface.</span></span>  
  
-   <span data-ttu-id="95136-112">托管此 WCF 服务使用服务主机 (**System.ServiceModel.ServiceHost**)。</span><span class="sxs-lookup"><span data-stu-id="95136-112">Host this WCF service using a service host (**System.ServiceModel.ServiceHost**).</span></span>  
  
 <span data-ttu-id="95136-113">本部分中的主题提供信息和过程来帮助你对 Oracle 数据库表和视图的 WCF 服务模型中执行轮询。</span><span class="sxs-lookup"><span data-stu-id="95136-113">The topics in this section provide information and procedures to help you perform polling on Oracle database tables and views in the WCF service model.</span></span>  
  
## <a name="about-the-examples-used-in-this-topic"></a><span data-ttu-id="95136-114">有关在本主题中使用的示例</span><span class="sxs-lookup"><span data-stu-id="95136-114">About the Examples Used in this Topic</span></span>  
 <span data-ttu-id="95136-115">本主题中的示例使用 /SCOTT/ACCOUNTACTIVITY 表和 /SCOTT/Package/ACCOUNT_PKG/PROCESS_ACTIVITY 函数。</span><span class="sxs-lookup"><span data-stu-id="95136-115">The examples in this topic use the /SCOTT/ACCOUNTACTIVITY table and the /SCOTT/Package/ACCOUNT_PKG/PROCESS_ACTIVITY function.</span></span> <span data-ttu-id="95136-116">一个脚本来生成这些项目附带[!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)]示例。</span><span class="sxs-lookup"><span data-stu-id="95136-116">A script to generate these artifacts is supplied with the [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)] samples.</span></span> <span data-ttu-id="95136-117">有关这些示例的详细信息，请参阅[适配器示例](../../adapters-and-accelerators/accelerator-rosettanet/adapter-samples.md)。</span><span class="sxs-lookup"><span data-stu-id="95136-117">For more information about the samples, see [Adapter Samples](../../adapters-and-accelerators/accelerator-rosettanet/adapter-samples.md).</span></span>  
  
## <a name="configuring-polling-in-the-wcf-service-model"></a><span data-ttu-id="95136-118">在 WCF 服务模型中配置轮询</span><span class="sxs-lookup"><span data-stu-id="95136-118">Configuring Polling in the WCF Service Model</span></span>  
 <span data-ttu-id="95136-119">你配置[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]设置绑定属性和一个可选的连接属性 （参数） 对 Oracle 数据库表和视图执行轮询。</span><span class="sxs-lookup"><span data-stu-id="95136-119">You configure the [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] to perform polling on Oracle database tables and views by setting binding properties and an optional connection property (parameter).</span></span> <span data-ttu-id="95136-120">其中一些属性是必需的并且某些，产生任何影响，同时在设计时和运行时就必须设置。</span><span class="sxs-lookup"><span data-stu-id="95136-120">Some of these properties are mandatory, and some, to have an effect, must be set both at design-time and run-time.</span></span>  
  
-   <span data-ttu-id="95136-121">在设计时连接参数和绑定属性时设置连接到 Oracle 数据库生成的 WCF 服务协定。</span><span class="sxs-lookup"><span data-stu-id="95136-121">At design-time, you set connection parameters and binding properties when you connect to the Oracle Database to generate a WCF service contract.</span></span>  
  
-   <span data-ttu-id="95136-122">在运行时用于创建服务主机的 OracleDBBinding 对象上设置绑定属性。</span><span class="sxs-lookup"><span data-stu-id="95136-122">At runtime you set binding properties on the OracleDBBinding object that you use to create the service host.</span></span> <span data-ttu-id="95136-123">向服务主机添加服务侦听器时设置的连接参数。</span><span class="sxs-lookup"><span data-stu-id="95136-123">You set the connection parameter when you add a service listener to the service host.</span></span>  
  
 <span data-ttu-id="95136-124">以下列表提供的绑定属性和连接参数用于配置轮询的简要概述：</span><span class="sxs-lookup"><span data-stu-id="95136-124">The following list provides a brief overview of the binding properties and connection parameters used to configure polling:</span></span>  
  
-   <span data-ttu-id="95136-125">**PollingStatement**绑定属性。</span><span class="sxs-lookup"><span data-stu-id="95136-125">The **PollingStatement** binding property.</span></span> <span data-ttu-id="95136-126">在设计时和在运行时，必须设置此绑定属性。</span><span class="sxs-lookup"><span data-stu-id="95136-126">You must set this binding property both at design-time and at run-time.</span></span>  
  
-   <span data-ttu-id="95136-127">可选的绑定的属性。</span><span class="sxs-lookup"><span data-stu-id="95136-127">Optional binding properties.</span></span> <span data-ttu-id="95136-128">这些只需在运行时设置。</span><span class="sxs-lookup"><span data-stu-id="95136-128">These only have to be set at run-time.</span></span>  
  
-   <span data-ttu-id="95136-129">**AcceptCredentialsInUri**绑定属性。</span><span class="sxs-lookup"><span data-stu-id="95136-129">The **AcceptCredentialsInUri** binding property.</span></span> <span data-ttu-id="95136-130">必须将此绑定属性设置为**true**在运行期间如果你想要启用连接 URI 中的凭据。</span><span class="sxs-lookup"><span data-stu-id="95136-130">You must set this binding property to **true** during run-time if you want to enable credentials in the connection URI.</span></span> <span data-ttu-id="95136-131">将服务终结点添加到服务主机时，用户名和密码必须处在连接 URI。</span><span class="sxs-lookup"><span data-stu-id="95136-131">The user name and password must be present in the connection URI when you add a service endpoint to the service host.</span></span>  
  
-   <span data-ttu-id="95136-132">**PollingId**查询中连接 URI 的字符串参数。</span><span class="sxs-lookup"><span data-stu-id="95136-132">The **PollingId** query string parameter in the connection URI.</span></span> <span data-ttu-id="95136-133">如果你想要更改 POLLINGSTMT 操作的命名空间，则必须设置此连接属性同时在设计时和运行时。</span><span class="sxs-lookup"><span data-stu-id="95136-133">If you want to change the namespace of the POLLINGSTMT operation, you must set this connection property both at design-time and run-time.</span></span>  
  
 <span data-ttu-id="95136-134">绑定属性以及用于配置轮询的连接参数的完整说明，请参阅[Oracle 数据库适配器中接收基于轮询的数据更改消息](../../adapters-and-accelerators/adapter-oracle-database/receive-polling-based-data-changed-messages-in-oracle-database-adapter.md)。</span><span class="sxs-lookup"><span data-stu-id="95136-134">For a complete description of the binding properties and connection parameters used to configure polling, see [Receive polling-based data-changed messages in Oracle Database adapter](../../adapters-and-accelerators/adapter-oracle-database/receive-polling-based-data-changed-messages-in-oracle-database-adapter.md).</span></span>  
  
## <a name="the-wcf-service-contract-and-class"></a><span data-ttu-id="95136-135">WCF 服务协定和类</span><span class="sxs-lookup"><span data-stu-id="95136-135">The WCF Service Contract and Class</span></span>  
 <span data-ttu-id="95136-136">您使用两个[!INCLUDE[addadapterservreflong](../../includes/addadapterservreflong-md.md)]或 ServiceModel 元数据实用工具 (svcutil.exe) 来创建 WCF 服务协定 （接口），并支持 POLLINGSTMT 操作的类。</span><span class="sxs-lookup"><span data-stu-id="95136-136">You use either the [!INCLUDE[addadapterservreflong](../../includes/addadapterservreflong-md.md)] or the ServiceModel Metadata Utility Tool (svcutil.exe) to create a WCF service contract (interface) and supporting classes for the POLLINGSTMT operation.</span></span>  
  
 <span data-ttu-id="95136-137">当您连接到 Oracle 数据库使用这些工具来生成服务协定 POLLINGSTMT 操作之一：</span><span class="sxs-lookup"><span data-stu-id="95136-137">When you connect to the Oracle database with either of these tools to generate a service contract for the POLLINGSTMT operation:</span></span>  
  
-   <span data-ttu-id="95136-138">必须指定**PollingStatement**绑定属性。</span><span class="sxs-lookup"><span data-stu-id="95136-138">You must specify the **PollingStatement** binding property.</span></span> <span data-ttu-id="95136-139">适配器使用 SELECT 语句中此绑定属性生成 POLLINGSTMT 操作返回的强类型化结果集的正确元数据。</span><span class="sxs-lookup"><span data-stu-id="95136-139">The adapter uses the SELECT statement in this binding property to generate the correct metadata for the strongly-typed result set returned by the POLLINGSTMT operation.</span></span>  
  
-   <span data-ttu-id="95136-140">在连接 URI 中，可以选择指定 PollingId 参数。</span><span class="sxs-lookup"><span data-stu-id="95136-140">You can optionally specify a PollingId parameter in the connection URI.</span></span> <span data-ttu-id="95136-141">适配器使用此参数来生成 POLLINGSTMT 操作的命名空间。</span><span class="sxs-lookup"><span data-stu-id="95136-141">The adapter uses this parameter to generate the namespace for the POLLINGSTMT operation.</span></span>  
  
 <span data-ttu-id="95136-142">在下面的示例：</span><span class="sxs-lookup"><span data-stu-id="95136-142">In the following examples:</span></span>  
  
-   <span data-ttu-id="95136-143">**PollingStatement**设置为"选择 \* 从 ACCOUNTACTIVITY FOR UPDATE"。</span><span class="sxs-lookup"><span data-stu-id="95136-143">**PollingStatement** is set to "SELECT \* FROM ACCOUNTACTIVITY FOR UPDATE".</span></span>  
  
-   <span data-ttu-id="95136-144">**PollingId**设置为"AcctActivity"。</span><span class="sxs-lookup"><span data-stu-id="95136-144">**PollingId** is set to "AcctActivity".</span></span>  
  
### <a name="the-wcf-service-contract-interface"></a><span data-ttu-id="95136-145">WCF 服务协定 （接口）</span><span class="sxs-lookup"><span data-stu-id="95136-145">The WCF Service Contract (Interface)</span></span>  
 <span data-ttu-id="95136-146">下面的代码演示为 POLLINGSTMT 操作生成的 WCF 服务协定 （接口）。</span><span class="sxs-lookup"><span data-stu-id="95136-146">The following code shows the WCF service contract (interface) generated for the POLLINGSTMT operation.</span></span>  
  
```  
[System.CodeDom.Compiler.GeneratedCodeAttribute("System.ServiceModel", "3.0.0.0")]  
[System.ServiceModel.ServiceContractAttribute(Namespace="http://Microsoft.LobServices.OracleDB/2007/03", ConfigurationName="POLLINGSTMT_OperationGroup")]  
public interface POLLINGSTMT_OperationGroup {  
  
    // CODEGEN: Generating message contract since the wrapper namespace (http://Microsoft.LobServices.OracleDB/2007/03/POLLINGSTMTAcctActivity)  
    // of message POLLINGSTMT does not match the default value (http://Microsoft.LobServices.OracleDB/2007/03)  
    [System.ServiceModel.OperationContractAttribute(IsOneWay=true, Action="http://Microsoft.LobServices.OracleDB/2007/03/POLLINGSTMT")]  
    void POLLINGSTMT(POLLINGSTMT request);  
}  
```  
  
### <a name="the-message-contracts"></a><span data-ttu-id="95136-147">消息协定</span><span class="sxs-lookup"><span data-stu-id="95136-147">The Message Contracts</span></span>  
 <span data-ttu-id="95136-148">由连接 URI 中的 PollingId 参数修改消息协定命名空间。</span><span class="sxs-lookup"><span data-stu-id="95136-148">The message contract namespace is modified by the PollingId parameter in the connection URI.</span></span> <span data-ttu-id="95136-149">请求消息返回一组强类型的记录。</span><span class="sxs-lookup"><span data-stu-id="95136-149">The request message returns a set of strongly-typed records.</span></span>  
  
```  
[System.Diagnostics.DebuggerStepThroughAttribute()]  
[System.CodeDom.Compiler.GeneratedCodeAttribute("System.ServiceModel", "3.0.0.0")]  
[System.ServiceModel.MessageContractAttribute(WrapperName="POLLINGSTMT", WrapperNamespace="http://Microsoft.LobServices.OracleDB/2007/03/POLLINGSTMTAcctActivity", IsWrapped=true)]  
public partial class POLLINGSTMT {  
  
    [System.ServiceModel.MessageBodyMemberAttribute(Namespace="http://Microsoft.LobServices.OracleDB/2007/03/POLLINGSTMTAcctActivity", Order=0)]  
    public microsoft.lobservices.oracledb._2007._03.POLLINGSTMTAcctActivity.POLLINGSTMTRECORD[] POLLINGSTMTRECORD;  
  
    public POLLINGSTMT() {  
    }  
  
    public POLLINGSTMT(microsoft.lobservices.oracledb._2007._03.POLLINGSTMTAcctActivity.POLLINGSTMTRECORD[] POLLINGSTMTRECORD) {  
        this.POLLINGSTMTRECORD = POLLINGSTMTRECORD;  
    }  
}  
```  
  
### <a name="the-data-contract-namespace"></a><span data-ttu-id="95136-150">数据协定 Namespace</span><span class="sxs-lookup"><span data-stu-id="95136-150">The Data Contract Namespace</span></span>  
 <span data-ttu-id="95136-151">数据协定是一项服务以抽象方式描述要交换的数据的客户端之间达成的正式协议。</span><span class="sxs-lookup"><span data-stu-id="95136-151">A data contract is a formal agreement between a service and a client that abstractly describes the data to be exchanged.</span></span> <span data-ttu-id="95136-152">也就是说，以便进行通信，客户端和服务不必共享相同的类型，只是相同的数据协定。</span><span class="sxs-lookup"><span data-stu-id="95136-152">That is, in order to communicate, the client and the service do not have to share the same types, only the same data contracts.</span></span>  
  
 <span data-ttu-id="95136-153">发生数据更改消息，数据协定命名空间，你还要修改由 PollingId 参数 （如果指定） 中连接 URI。</span><span class="sxs-lookup"><span data-stu-id="95136-153">In case of data change messages, the data contract namespace is also modified by the PollingId parameter (if specified) in the connection URI.</span></span> <span data-ttu-id="95136-154">数据协定组成一个类，表示查询结果集中的强类型的记录。</span><span class="sxs-lookup"><span data-stu-id="95136-154">The data contract is composed of a class that represents a strongly-typed record in the query result set.</span></span> <span data-ttu-id="95136-155">在此示例中省略类定义的详细信息。</span><span class="sxs-lookup"><span data-stu-id="95136-155">The details of the class definition are omitted in this example.</span></span> <span data-ttu-id="95136-156">此类包含表示在结果集中的列的属性。</span><span class="sxs-lookup"><span data-stu-id="95136-156">The class contains properties that represent the columns in the result set.</span></span>  
  
 <span data-ttu-id="95136-157">在以下示例中，使用 PollingId"AcctActivity"。</span><span class="sxs-lookup"><span data-stu-id="95136-157">In the following example, the PollingId “AcctActivity” is used.</span></span>  
  
```  
namespace microsoft.lobservices.oracledb._2007._03.POLLINGSTMTAcctActivity {  
    using System.Runtime.Serialization;  
  
    [System.Diagnostics.DebuggerStepThroughAttribute()]  
    [System.CodeDom.Compiler.GeneratedCodeAttribute("System.Runtime.Serialization", "3.0.0.0")]  
    [System.Runtime.Serialization.DataContractAttribute(Name="POLLINGSTMTRECORD", Namespace="http://Microsoft.LobServices.OracleDB/2007/03/POLLINGSTMTAcctActivity")]  
    public partial class POLLINGSTMTRECORD : object, System.Runtime.Serialization.IExtensibleDataObject {…}  
     }  
}  
```  
  
### <a name="wcf-service-class"></a><span data-ttu-id="95136-158">WCF 服务类</span><span class="sxs-lookup"><span data-stu-id="95136-158">WCF Service Class</span></span>  
 <span data-ttu-id="95136-159">[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]还会生成一个具有为 WCF 服务类实现服务协定 （接口） 从存根 （stub） 文件。</span><span class="sxs-lookup"><span data-stu-id="95136-159">The [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)] also generates a file that has a stub for the WCF service class implemented from the service contract (interface).</span></span> <span data-ttu-id="95136-160">文件的名称是 OracleDBBindingService.cs。</span><span class="sxs-lookup"><span data-stu-id="95136-160">The name of the file is OracleDBBindingService.cs.</span></span> <span data-ttu-id="95136-161">你可以将插入的逻辑来处理此类直接 POLLINGSTMT 操作。</span><span class="sxs-lookup"><span data-stu-id="95136-161">You can insert the logic to process the POLLINGSTMT operation directly into this class.</span></span> <span data-ttu-id="95136-162">如果使用 svcutil.exe 来生成服务协定接口，则必须自行实现此类。</span><span class="sxs-lookup"><span data-stu-id="95136-162">If you use svcutil.exe to generate the service contract interface, you must implement this class yourself.</span></span> <span data-ttu-id="95136-163">下面的代码演示生成的 WCF 服务类[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="95136-163">The following code shows the WCF service class generated by the [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)].</span></span>  
  
```  
namespace OracleDBBindingNamespace {  
  
    public class OracleDBBindingService : POLLINGSTMT_OperationGroup {  
  
        // CODEGEN: Generating message contract since the wrapper namespace (http://Microsoft.LobServices.OracleDB/2007/03/POLLINGSTMTAcctActivity)   
        // of message POLLINGSTMT does not match the default value (http://Microsoft.LobServices.OracleDB/2007/03)  
        public virtual void POLLINGSTMT(POLLINGSTMT request) {  
            throw new System.NotImplementedException("The method or operation is not implemented.");  
        }  
    }  
}  
```  
  
## <a name="receiving-the-pollingstmt-operation"></a><span data-ttu-id="95136-164">接收 POLLINGSTMT 操作</span><span class="sxs-lookup"><span data-stu-id="95136-164">Receiving the POLLINGSTMT Operation</span></span>  
  
#### <a name="to-receive-polling-data-from-the-oracle-database-adapter"></a><span data-ttu-id="95136-165">从 Oracle 数据库适配器接收轮询数据</span><span class="sxs-lookup"><span data-stu-id="95136-165">To receive polling data from the Oracle Database adapter</span></span>  
  
1.  <span data-ttu-id="95136-166">使用[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]或 svcutil.exe 生成 WCF 服务协定 （接口），并用于 POLLINGSTMT 操作帮助器类。</span><span class="sxs-lookup"><span data-stu-id="95136-166">Use the [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)] or svcutil.exe to generate a WCF service contract (interface) and helper classes for the POLLINGSTMT operation.</span></span> <span data-ttu-id="95136-167">有关详细信息，请参阅[生成 WCF 客户端或 Oracle 数据库解决方案项目关联的 WCF 服务协定](../../adapters-and-accelerators/adapter-oracle-database/create-a-wcf-client-or-wcf-service-contract-for-oracle-db-solution-artifacts.md)。</span><span class="sxs-lookup"><span data-stu-id="95136-167">For more information, see [Generate a WCF client or a WCF service contract for Oracle Database solution artifacts](../../adapters-and-accelerators/adapter-oracle-database/create-a-wcf-client-or-wcf-service-contract-for-oracle-db-solution-artifacts.md).</span></span> <span data-ttu-id="95136-168">至少，你必须将设置**PollingStatement**绑定时连接到该适配器的属性。</span><span class="sxs-lookup"><span data-stu-id="95136-168">At a minimum, you must set the **PollingStatement** binding property when you connect to the adapter.</span></span> <span data-ttu-id="95136-169">在连接 URI 中，可以选择指定 PollingId 参数。</span><span class="sxs-lookup"><span data-stu-id="95136-169">You can optionally specify a PollingId parameter in the connection URI.</span></span> <span data-ttu-id="95136-170">如果你使用[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]，你应设置你的配置所必需的所有绑定参数。</span><span class="sxs-lookup"><span data-stu-id="95136-170">If you are using the [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)], you should set all of the binding parameters necessary for your configuration.</span></span> <span data-ttu-id="95136-171">这可确保它们正确设置生成的配置文件中。</span><span class="sxs-lookup"><span data-stu-id="95136-171">This guarantees that they are properly set in the generated configuration file.</span></span>  
  
2.  <span data-ttu-id="95136-172">实现 WCF 服务从步骤 1 中生成的接口和帮助程序类。</span><span class="sxs-lookup"><span data-stu-id="95136-172">Implement a WCF service from the interface and helper classes generated in step 1.</span></span> <span data-ttu-id="95136-173">此类的 POLLINGSTMT 方法可能会引发异常中止轮询事务，如果遇到错误则处理从 POLLINGSTMT 操作; 接收的数据否则该方法不返回任何内容。</span><span class="sxs-lookup"><span data-stu-id="95136-173">The POLLINGSTMT method of this class can throw an exception to abort the polling transaction, if an error is encountered processing the data received from the POLLINGSTMT operation; otherwise the method does not return anything.</span></span> <span data-ttu-id="95136-174">必须属性 WCF 服务类，如下所示：</span><span class="sxs-lookup"><span data-stu-id="95136-174">You must attribute the WCF service class as follows:</span></span>  
  
    ```  
    [ServiceBehavior(InstanceContextMode = InstanceContextMode.Single)]  
    ```  
  
    1.  <span data-ttu-id="95136-175">如果你使用[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]若要生成界面，可以实现你的逻辑直接在**POLLINGSTMT**中生成方法**OracleDBBindingService**类。</span><span class="sxs-lookup"><span data-stu-id="95136-175">If you used the [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)] to generate the interface, you can implement your logic directly in the **POLLINGSTMT** method in the generated **OracleDBBindingService** class.</span></span> <span data-ttu-id="95136-176">OracleDBBindingService.cs 中找不到此类。</span><span class="sxs-lookup"><span data-stu-id="95136-176">This class can be found in OracleDBBindingService.cs.</span></span> <span data-ttu-id="95136-177">此示例中的此代码子类**OracleDBBindingService**类。</span><span class="sxs-lookup"><span data-stu-id="95136-177">This code in this example sub-classes the **OracleDBBindingService** class.</span></span>  
  
        ```  
        [ServiceBehavior(InstanceContextMode = InstanceContextMode.Single)]  
  
        public class PollingStmtService : OracleDBBindingService  
        {  
            public override void POLLINGSTMT(POLLINGSTMT request)  
            {  
                Console.WriteLine("\nNew Polling Records Received");  
                Console.WriteLine("Tx Id\tAccount\tAmount\tDate\t\t\tDescription");  
                for (int i = 0; i < request.POLLINGSTMTRECORD.Length; i++)  
                {  
                    Console.WriteLine("{0}\t{1}\t{2}\t{3}\t{4}", request.POLLINGSTMTRECORD[i].TID,  
                                        request.POLLINGSTMTRECORD[i].ACCOUNT,  
                                        request.POLLINGSTMTRECORD[i].AMOUNT,  
                                        request.POLLINGSTMTRECORD[i].TRANSDATE,  
                                        request.POLLINGSTMTRECORD[i].DESCRIPTION);  
                }  
            }  
        }  
        ```  
  
    2.  <span data-ttu-id="95136-178">如果使用 svcutil.exe 来生成界面，你必须创建 WCF 服务实现的接口和实现你的逻辑中**POLLINGSTMT**此类的方法。</span><span class="sxs-lookup"><span data-stu-id="95136-178">If you used svcutil.exe to generate the interface, you must create a WCF service that implements the interface and implement your logic in the **POLLINGSTMT** method of this class.</span></span>  
  
3.  <span data-ttu-id="95136-179">创建在步骤 2 中创建的 WCF 服务的实例。</span><span class="sxs-lookup"><span data-stu-id="95136-179">Create an instance of the WCF service created in step 2.</span></span>  
  
    ```  
    // create service instance  
    PollingStmtService pollingInstance = new PollingStmtService();  
    ```  
  
4.  <span data-ttu-id="95136-180">创建的实例**System.ServiceModel.ServiceHost**使用 WCF 服务和数据库连接 URI。</span><span class="sxs-lookup"><span data-stu-id="95136-180">Create an instance of **System.ServiceModel.ServiceHost** by using the WCF service and a base connection URI.</span></span> <span data-ttu-id="95136-181">Userinfoparams 或 query_string，不能包含基连接 URI。</span><span class="sxs-lookup"><span data-stu-id="95136-181">The base connection URI cannot contain userinfoparams or a query_string.</span></span>  
  
    ```  
    // Enable service host  
    Uri[] baseUri = new Uri[] { new Uri("oracledb://Adapter") };  
    ServiceHost srvHost = new ServiceHost(pollingInstance, baseUri);  
    ```  
  
5.  <span data-ttu-id="95136-182">创建**OracleDBBinding**和通过设置其绑定属性中配置的轮询操作。</span><span class="sxs-lookup"><span data-stu-id="95136-182">Create an **OracleDBBinding** and configure the polling operation by setting its binding properties.</span></span> <span data-ttu-id="95136-183">可以在代码中显式或配置中以声明方式执行此操作。</span><span class="sxs-lookup"><span data-stu-id="95136-183">You can do this either explicitly in code or declaratively in configuration.</span></span> <span data-ttu-id="95136-184">至少，你必须指定轮询语句和轮询间隔。</span><span class="sxs-lookup"><span data-stu-id="95136-184">At a minimum, you must specify the polling statement and polling interval.</span></span> <span data-ttu-id="95136-185">在此示例中，你指定的凭据作为 URI 的一部分以便还必须设置**AcceptCredentialsInUri**到**true**。</span><span class="sxs-lookup"><span data-stu-id="95136-185">In this example, you specify the credentials as part of the URI so you must also set the **AcceptCredentialsInUri** to **true**.</span></span>  
  
    ```  
    // Create and configure a binding for the service endpoint. NOTE: binding  
    // parameters are set here for clarity, but these are already set in the  
    // the generated configuration file  
    OracleDBBinding binding = new OracleDBBinding();  
  
    // The credentials are included in the connection URI, so set this property to true  
    binding.AcceptCredentialsInUri = true;  
  
    // Same as statement specified in Configure Adapter dialog box  
    binding.PollingStatement = "SELECT * FROM ACCOUNTACTIVITY FOR UPDATE";  
    binding.PostPollStatement = "BEGIN ACCOUNT_PKG.PROCESS_ACTIVITY(); END;";  
  
    // Be sure to set the interval long enough to complete processing before  
    // the next poll  
    binding.PollingInterval = 15;  
    // Polling is transactional; be sure to set an adequate isolation level   
    // for your environment  
    binding.TransactionIsolationLevel = TransactionIsolationLevel.ReadCommitted;  
    ```  
  
6.  <span data-ttu-id="95136-186">将服务终结点添加到服务主机。</span><span class="sxs-lookup"><span data-stu-id="95136-186">Add a service endpoint to the service host.</span></span> <span data-ttu-id="95136-187">为此，请执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="95136-187">To do this:</span></span>  
  
    -   <span data-ttu-id="95136-188">使用在步骤 5 中创建的绑定。</span><span class="sxs-lookup"><span data-stu-id="95136-188">Use the binding created in step 5.</span></span>  
  
    -   <span data-ttu-id="95136-189">指定连接 URI，其中包含凭据并根据需要 PollingId。</span><span class="sxs-lookup"><span data-stu-id="95136-189">Specify a connection URI that contains credentials and, if needed, a PollingId.</span></span>  
  
    -   <span data-ttu-id="95136-190">作为"POLLINGSTMT_OperationGroup"指定的协定。</span><span class="sxs-lookup"><span data-stu-id="95136-190">Specify the contract as "POLLINGSTMT_OperationGroup".</span></span>  
  
    ```  
    // Add service endpoint: be sure to specify POLLINGSTMT_OperationGroup as the contract  
    Uri serviceUri = new Uri("oracledb://User=SCOTT;Password=TIGER@Adapter?PollingId=AcctActivity");  
    srvHost.AddServiceEndpoint("POLLINGSTMT_OperationGroup", binding, serviceUri);  
    ```  
  
7.  <span data-ttu-id="95136-191">若要接收轮询数据，请打开服务主机。</span><span class="sxs-lookup"><span data-stu-id="95136-191">To receive polling data, open the service host.</span></span> <span data-ttu-id="95136-192">每当查询返回一个结果集，该适配器将返回数据。</span><span class="sxs-lookup"><span data-stu-id="95136-192">The adapter will return data whenever the query returns a result set.</span></span>  
  
    ```  
    // Open the service host to begin polling  
    srvHost.Open();  
    ```  
  
8.  <span data-ttu-id="95136-193">若要终止轮询，关闭服务主机。</span><span class="sxs-lookup"><span data-stu-id="95136-193">To terminate polling, close the service host.</span></span>  
  
    > [!IMPORTANT]
    >  <span data-ttu-id="95136-194">适配器将继续轮询，直到关闭服务主机。</span><span class="sxs-lookup"><span data-stu-id="95136-194">The adapter will continue to poll until the service host is closed.</span></span>  
  
    ```  
    srvHost.Close();  
    ```  
  
### <a name="example"></a><span data-ttu-id="95136-195">示例</span><span class="sxs-lookup"><span data-stu-id="95136-195">Example</span></span>  
 <span data-ttu-id="95136-196">下面的示例演示针对/SCOTT/ACCOUNTACTIVITY 表执行的轮询查询。</span><span class="sxs-lookup"><span data-stu-id="95136-196">The following example shows a polling query that executes against the /SCOTT/ACCOUNTACTIVITY table.</span></span> <span data-ttu-id="95136-197">后轮询语句调用将处理的记录移到另一个表 /SCOTT/ACCOUNTHISTORY Oracle 函数。</span><span class="sxs-lookup"><span data-stu-id="95136-197">The post-poll statement invokes an Oracle function that moves the processed records to another table /SCOTT/ACCOUNTHISTORY.</span></span> <span data-ttu-id="95136-198">要修改 POLLINGSTMT 操作的命名空间，请在连接 URI 中设置"AccountActivity"的 PollingId 参数。</span><span class="sxs-lookup"><span data-stu-id="95136-198">The namespace of the POLLINGSTMT operation is modified by setting the PollingId parameter to "AccountActivity" in the connection URI.</span></span> <span data-ttu-id="95136-199">在此示例中，通过子类分类生成创建 POLLINGSTMT 操作的 WCF 服务**OracleDBBindingService**类; 但是，你可以直接在生成的类中实现你的逻辑。</span><span class="sxs-lookup"><span data-stu-id="95136-199">In this example, the WCF service for the POLLINGSTMT operation is created by sub-classing the generated **OracleDBBindingService** class; however, you can implement your logic directly in the generated class.</span></span>  
  
```  
using System;  
using System.Collections.Generic;  
using System.Text;  
  
// Add these three references to use the Oracle adapter  
using System.ServiceModel;  
using Microsoft.ServiceModel.Channels;  
using Microsoft.Adapters.OracleDB;  
  
using microsoft.lobservices.oracledb._2007._03.POLLINGSTMTAcctActivity;  
using OracleDBBindingNamespace;  
  
namespace OraclePollingSM  
{  
    [ServiceBehavior(InstanceContextMode = InstanceContextMode.Single)]  
  
    public class PollingStmtService : OracleDBBindingService  
    {  
        public override void POLLINGSTMT(POLLINGSTMT request)  
        {  
            Console.WriteLine("\nNew Polling Records Received");  
            Console.WriteLine("Tx Id\tAccount\tAmount\tDate\t\t\tDescription");  
            for (int i = 0; i < request.POLLINGSTMTRECORD.Length; i++)  
            {  
                Console.WriteLine("{0}\t{1}\t{2}\t{3}\t{4}", request.POLLINGSTMTRECORD[i].TID,  
                                    request.POLLINGSTMTRECORD[i].ACCOUNT,  
                                    request.POLLINGSTMTRECORD[i].AMOUNT,  
                                    request.POLLINGSTMTRECORD[i].TRANSDATE,  
                                    request.POLLINGSTMTRECORD[i].DESCRIPTION);  
  
            }  
            Console.WriteLine("\nHit <RETURN> to stop polling");  
         }  
    }  
  
    class Program  
    {  
        static void Main(string[] args)  
        {  
            ServiceHost srvHost = null;  
  
            // This URI is used to specify the address for the ServiceEndpoint  
            // It must contain credentials and the PollingId (if any) that was used to generate  
            // the WCF service callback interface  
            Uri serviceUri = new Uri("OracleDb://User=SCOTT;Password=TIGER@Adapter?PollingId=AcctActivity");  
  
            // This URI is used to initialize the ServiceHost. It cannot contain  
            // userinfoparms (credentials) or a query_string (PollingId); otherwise,  
            // an exception is thrown when the ServiceHost is initialized.  
            Uri[] baseUri = new Uri[] { new Uri("OracleDb://Adapter") };  
  
            Console.WriteLine("Sample started, initializing service host -- please wait");  
  
            // create an instanc of the WCF service callback class  
            PollingStmtService pollingInstance = new PollingStmtService();  
  
            try  
            {  
                // Create a ServiceHost with the service callback instance and a base URI (address)  
                srvHost = new ServiceHost(pollingInstance, baseUri);  
  
                // Create and configure a binding for the service endpoint. Note: binding  
                // parameters are set here for clarity but these are already set in the  
                // generated configuration file  
                //  
                // The following properties are set  
                //    AcceptCredentialsInUri (true) to enable credentials in the connection URI for AddServiceEndpoint  
                //    PollingStatement  
                //    PostPollStatement calls PROCESS_ACTIVITY on Oracle. This procedure moves the queried records to  
                //                      the ACCOUNTHISTORY table  
                //    PollingInterval (15 seconds)  
                //    TransactionIsolationLevel   
  
                OracleDBBinding binding = new OracleDBBinding();  
  
                // The Credentials are included in the Connection Uri so set this property true  
                binding.AcceptCredentialsInUri = true;  
  
                // Same as statement specified in Configure Adapter dialog box  
                binding.InboundOperationType = InboundOperation.Polling;  
                binding.PollingStatement = "SELECT * FROM ACCOUNTACTIVITY FOR UPDATE";  
                binding.PostPollStatement = "BEGIN ACCOUNT_PKG.PROCESS_ACTIVITY(); END;";  
  
                // Be sure to set the interval long enough to complete processing before  
                // the next poll  
                binding.PollingInterval = 15;  
  
                // Polling is transactional, be sure to set an adequate isolation level   
                // for your environment  
                binding.TransactionIsolationLevel = TransactionIsolationLevel.ReadCommitted;  
  
                // Add service endpoint: be sure to specify POLLINGSTMT_OperationGroup as the contract  
                srvHost.AddServiceEndpoint("POLLINGSTMT_OperationGroup", binding, serviceUri);  
  
                Console.WriteLine("Opening the service host");  
                // Open the service host to begin polling  
                srvHost.Open();  
  
                // Wait to receive request  
                Console.WriteLine("\nPolling started. Returned records will be written to the console.");  
                Console.WriteLine("Hit <RETURN> to stop polling");  
                Console.ReadLine();  
            }  
            catch (Exception e)  
            {  
                Console.WriteLine("Exception :" + e.Message);  
                Console.ReadLine();  
  
                /* If there is an Oracle Error it will be specified in the inner exception */  
                if (e.InnerException != null)  
                {  
                    Console.WriteLine("InnerException: " + e.InnerException.Message);  
                    Console.ReadLine();  
                }  
            }  
            finally  
            {  
                // IMPORTANT: you must close the ServiceHost to stop polling  
                if (srvHost.State == CommunicationState.Opened)  
                    srvHost.Close();  
                else  
                    srvHost.Abort();  
            }  
  
        }  
    }  
}  
```  
  
## <a name="see-also"></a><span data-ttu-id="95136-200">另请参阅</span><span class="sxs-lookup"><span data-stu-id="95136-200">See Also</span></span>  
 [<span data-ttu-id="95136-201">开发使用 WCF 服务模型的 Oracle 数据库应用程序</span><span class="sxs-lookup"><span data-stu-id="95136-201">Develop Oracle Database applications using the WCF Service Model</span></span>](../../adapters-and-accelerators/adapter-oracle-database/develop-oracle-database-applications-using-the-wcf-service-model.md)