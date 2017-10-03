---
title: "接收使用 WCF 服务模型的 Oracle E-business Suite 数据库更改通知 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 362193f5-2586-480f-a62e-1ed5e4ef342c
caps.latest.revision: "8"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e0350a6c16eca4a6639549cb5240f04fa1b8bebf
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="receive-oracle-e-business-suite-database-change-notifications-using-the-wcf-service-model"></a><span data-ttu-id="e5e32-102">接收使用 WCF 服务模型的 Oracle E-business Suite 数据库更改通知</span><span class="sxs-lookup"><span data-stu-id="e5e32-102">Receive Oracle E-Business Suite database change notifications using the WCF service model</span></span>
<span data-ttu-id="e5e32-103">本主题演示如何配置[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]从 Oracle 数据库接收查询通知消息。</span><span class="sxs-lookup"><span data-stu-id="e5e32-103">This topic demonstrates how to configure the [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] to receive query notification messages from an Oracle database.</span></span> <span data-ttu-id="e5e32-104">为了演示通知，考虑一个表，ACCOUNTACTIVITY，与"处理"列。</span><span class="sxs-lookup"><span data-stu-id="e5e32-104">To demonstrate notifications, consider a table, ACCOUNTACTIVITY, with a “Processed” column.</span></span> <span data-ttu-id="e5e32-105">一条新记录插入到此表时，将状态列的值设置为"n"。</span><span class="sxs-lookup"><span data-stu-id="e5e32-105">When a new record is inserted to this table, the value of the Status column is set to “n.”</span></span> <span data-ttu-id="e5e32-106">你可以配置适配器后，以通过使用 SQL 语句，以检索具有为"n"。"处理"列的所有记录的通知注册接收通知</span><span class="sxs-lookup"><span data-stu-id="e5e32-106">You can configure the adapter to receive notifications by registering for notifications using a SQL statement that retrieves all records that have “Processed” column as “n.”</span></span> <span data-ttu-id="e5e32-107">你可以通过指定的 SQL 语句来实现**NotificationStatement**绑定属性。</span><span class="sxs-lookup"><span data-stu-id="e5e32-107">You can do so by specifying the SQL statement for the **NotificationStatement** binding property.</span></span> <span data-ttu-id="e5e32-108">适配器客户端收到通知后，它可以包含执行对 Oracle 数据库的任何后续任务的逻辑。</span><span class="sxs-lookup"><span data-stu-id="e5e32-108">After the adapter client receives the notification, it can contain the logic to do any subsequent tasks on the Oracle database.</span></span> <span data-ttu-id="e5e32-109">在此示例中，为简单起见，适配器客户端列出表中具有"n。"的"处理"列的所有记录</span><span class="sxs-lookup"><span data-stu-id="e5e32-109">In this example, for the sake of simplicity, the adapter client lists all the records in the table that have the “Processed” column as “n.”</span></span>  
  
## <a name="configuring-notifications-with-the-oracle-e-business-adapter-binding-properties"></a><span data-ttu-id="e5e32-110">与 Oracle E-business 适配器绑定属性中配置通知</span><span class="sxs-lookup"><span data-stu-id="e5e32-110">Configuring Notifications with the Oracle E-Business Adapter Binding Properties</span></span>  
 <span data-ttu-id="e5e32-111">下表总结了[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]绑定属性，用于配置从 Oracle E-business Suite 接收通知。</span><span class="sxs-lookup"><span data-stu-id="e5e32-111">The table below summarizes the [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] binding properties that you use to configure receiving notifications from Oracle E-Business Suite.</span></span> <span data-ttu-id="e5e32-112">在运行.NET 应用程序以接收通知时，必须指定这些绑定属性。</span><span class="sxs-lookup"><span data-stu-id="e5e32-112">You must specify these binding properties while running the .NET application to receive notifications.</span></span>  
  
|<span data-ttu-id="e5e32-113">绑定属性</span><span class="sxs-lookup"><span data-stu-id="e5e32-113">Binding Property</span></span>|<span data-ttu-id="e5e32-114">Description</span><span class="sxs-lookup"><span data-stu-id="e5e32-114">Description</span></span>|  
|----------------------|-----------------|  
|<span data-ttu-id="e5e32-115">**InboundOperationType**</span><span class="sxs-lookup"><span data-stu-id="e5e32-115">**InboundOperationType**</span></span>|<span data-ttu-id="e5e32-116">指定你想要执行的入站的操作。</span><span class="sxs-lookup"><span data-stu-id="e5e32-116">Specifies the inbound operation that you want to perform.</span></span> <span data-ttu-id="e5e32-117">若要接收通知消息，请将此设置为**通知**。</span><span class="sxs-lookup"><span data-stu-id="e5e32-117">To receive notification messages, set this to **Notification**.</span></span>|  
|<span data-ttu-id="e5e32-118">**NotificationPort**</span><span class="sxs-lookup"><span data-stu-id="e5e32-118">**NotificationPort**</span></span>|<span data-ttu-id="e5e32-119">指定 ODP.NET 必须打开侦听从 Oracle 数据库的数据库更改通知的端口号。</span><span class="sxs-lookup"><span data-stu-id="e5e32-119">Specifies the port number that ODP.NET must open to listen for database change notification from Oracle database.</span></span>|  
|<span data-ttu-id="e5e32-120">**NotificationStatement**</span><span class="sxs-lookup"><span data-stu-id="e5e32-120">**NotificationStatement**</span></span>|<span data-ttu-id="e5e32-121">指定用来注册查询通知的 Select 语句。</span><span class="sxs-lookup"><span data-stu-id="e5e32-121">Specifies the Select statement used to register for query notifications.</span></span> <span data-ttu-id="e5e32-122">仅当指定的 Select 语句更改的结果集时，适配器获取一条通知消息。</span><span class="sxs-lookup"><span data-stu-id="e5e32-122">The adapter gets a notification message only when the result set for the specified Select statement changes.</span></span>|  
|<span data-ttu-id="e5e32-123">**NotifyOnListenerStart**</span><span class="sxs-lookup"><span data-stu-id="e5e32-123">**NotifyOnListenerStart**</span></span>|<span data-ttu-id="e5e32-124">指定启动侦听器时，适配器是否发送到适配器客户端通知。</span><span class="sxs-lookup"><span data-stu-id="e5e32-124">Specifies whether the adapter sends a notification to the adapter clients when the listener is started.</span></span>|  
  
 <span data-ttu-id="e5e32-125">有关这些属性的更完整说明，请参阅[了解针对 Oracle E-business Suite 绑定属性的 BizTalk 适配器](../../adapters-and-accelerators/adapter-oracle-ebs/read-about-the-biztalk-adapter-for-oracle-e-business-suite-binding-properties.md)。</span><span class="sxs-lookup"><span data-stu-id="e5e32-125">For a more complete description of these properties, see [Read about the BizTalk Adapter for Oracle E-Business Suite binding properties](../../adapters-and-accelerators/adapter-oracle-ebs/read-about-the-biztalk-adapter-for-oracle-e-business-suite-binding-properties.md).</span></span> <span data-ttu-id="e5e32-126">有关如何使用的完整说明[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]若要从 Oracle E-business Suite 接收通知，请阅读此主题的其余部分。</span><span class="sxs-lookup"><span data-stu-id="e5e32-126">For a complete description of how to use the [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] to receive notifications from Oracle E-Business Suite, read the remainder of this topic.</span></span>  
  
## <a name="configuring-notifications-using-the-wcf-service-model"></a><span data-ttu-id="e5e32-127">使用 WCF 服务模型配置通知</span><span class="sxs-lookup"><span data-stu-id="e5e32-127">Configuring Notifications Using the WCF Service Model</span></span>  
 <span data-ttu-id="e5e32-128">若要接收使用 WCF 服务模型的通知，你必须：</span><span class="sxs-lookup"><span data-stu-id="e5e32-128">To receive the notifications using the WCF service model, you must:</span></span>  
  
-   <span data-ttu-id="e5e32-129">为生成的 WCF 服务协定 （接口）**通知**从适配器公开的元数据的操作。</span><span class="sxs-lookup"><span data-stu-id="e5e32-129">Generate a WCF service contract (interface) for the **Notification** operation from the metadata exposed by the adapter.</span></span> <span data-ttu-id="e5e32-130">若要执行此操作，你无法使用[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="e5e32-130">To do this, you could use the [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)].</span></span>  
  
-   <span data-ttu-id="e5e32-131">生成的 WCF 客户端**选择**ACCOUNTACTIVITY 表上的操作。</span><span class="sxs-lookup"><span data-stu-id="e5e32-131">Generate a WCF client for the **Select** operation on the ACCOUNTACTIVITY table.</span></span> <span data-ttu-id="e5e32-132">若要执行此操作，你无法使用[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="e5e32-132">To do this, you could use the [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)].</span></span>  
  
-   <span data-ttu-id="e5e32-133">实现此接口从 WCF 服务。</span><span class="sxs-lookup"><span data-stu-id="e5e32-133">Implement a WCF service from this interface.</span></span>  
  
-   <span data-ttu-id="e5e32-134">托管此 WCF 服务使用服务主机 (**System.ServiceModel.ServiceHost**)。</span><span class="sxs-lookup"><span data-stu-id="e5e32-134">Host this WCF service using a service host (**System.ServiceModel.ServiceHost**).</span></span>  
  
## <a name="about-the-examples-used-in-this-topic"></a><span data-ttu-id="e5e32-135">有关在本主题中使用的示例</span><span class="sxs-lookup"><span data-stu-id="e5e32-135">About the Examples Used in this Topic</span></span>  
 <span data-ttu-id="e5e32-136">本主题中的示例接收 ACCOUNTACTIVITY 表的通知。</span><span class="sxs-lookup"><span data-stu-id="e5e32-136">The examples in this topic receives notification for the ACCOUNTACTIVITY table.</span></span> <span data-ttu-id="e5e32-137">在示例提供了一个脚本以生成表。</span><span class="sxs-lookup"><span data-stu-id="e5e32-137">A script to generate the table is supplied with the samples.</span></span> <span data-ttu-id="e5e32-138">有关这些示例的详细信息，请参阅[Oracle EBS 适配器的示例](../../adapters-and-accelerators/adapter-oracle-ebs/samples-for-the-oracle-ebs-adapter.md)。</span><span class="sxs-lookup"><span data-stu-id="e5e32-138">For more information about the samples, see [Samples for the Oracle EBS adapter](../../adapters-and-accelerators/adapter-oracle-ebs/samples-for-the-oracle-ebs-adapter.md).</span></span> <span data-ttu-id="e5e32-139">示例中， **Notification_ServiceModel**，后者基于本主题中，还提供了与[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]示例。</span><span class="sxs-lookup"><span data-stu-id="e5e32-139">A sample, **Notification_ServiceModel**, which is based on this topic, is also provided with the [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] samples.</span></span>  
  
## <a name="the-wcf-service-contract-and-class"></a><span data-ttu-id="e5e32-140">WCF 服务协定和类</span><span class="sxs-lookup"><span data-stu-id="e5e32-140">The WCF Service Contract and Class</span></span>  
 <span data-ttu-id="e5e32-141">你可以使用[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]创建 WCF 服务协定 （接口） 和支持类**通知**操作。</span><span class="sxs-lookup"><span data-stu-id="e5e32-141">You can use the [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)] to create a WCF service contract (interface) and supporting classes for the **Notification** operation.</span></span> <span data-ttu-id="e5e32-142">有关生成的 WCF 服务协定的详细信息，请参阅[生成 WCF 客户端或 Oracle E-business Suite 解决方案项目关联的 WCF 服务协定](../../adapters-and-accelerators/adapter-oracle-ebs/create-a-wcf-client-or-wcf-service-contract-for-oracle-ebs-solution-artifacts.md)。</span><span class="sxs-lookup"><span data-stu-id="e5e32-142">For more information about generating a WCF service contract, see [Generate a WCF client or a WCF service contract for Oracle E-Business Suite solution artifacts](../../adapters-and-accelerators/adapter-oracle-ebs/create-a-wcf-client-or-wcf-service-contract-for-oracle-ebs-solution-artifacts.md).</span></span>  
  
### <a name="the-wcf-service-contract-interface"></a><span data-ttu-id="e5e32-143">WCF 服务协定 （接口）</span><span class="sxs-lookup"><span data-stu-id="e5e32-143">The WCF Service Contract (Interface)</span></span>  
 <span data-ttu-id="e5e32-144">下面的代码演示为生成的 WCF 服务协定 （接口）**通知**操作。</span><span class="sxs-lookup"><span data-stu-id="e5e32-144">The following code shows the WCF service contract (interface) generated for the **Notification** operation.</span></span>  
  
```  
[System.CodeDom.Compiler.GeneratedCodeAttribute("System.ServiceModel", "3.0.0.0")]  
[System.ServiceModel.ServiceContractAttribute(Namespace="http://schemas.microsoft.com/OracleEBS/", ConfigurationName="Notification_")]  
public interface Notification_ {  
  
    // CODEGEN: Generating message contract since the wrapper namespace (http://schemas.microsoft.com/OracleEBS/2008/05/Notification/) of message Notification   
    // does not match the default value (http://schemas.microsoft.com/OracleEBS/)  
    [System.ServiceModel.OperationContractAttribute(IsOneWay=true, Action="Notification")]  
    void Notification(Notification request);  
}  
```  
  
### <a name="the-message-contracts"></a><span data-ttu-id="e5e32-145">消息协定</span><span class="sxs-lookup"><span data-stu-id="e5e32-145">The Message Contracts</span></span>  
 <span data-ttu-id="e5e32-146">下面是通知操作的消息协定。</span><span class="sxs-lookup"><span data-stu-id="e5e32-146">Following is the message contract for the Notification operation.</span></span>  
  
```  
[System.Diagnostics.DebuggerStepThroughAttribute()]  
[System.CodeDom.Compiler.GeneratedCodeAttribute("System.ServiceModel", "3.0.0.0")]  
[System.ServiceModel.MessageContractAttribute(WrapperName="Notification", WrapperNamespace="http://schemas.microsoft.com/OracleEBS/2008/05/Notification/", IsWrapped=true)]  
public partial class Notification {  
  
    [System.ServiceModel.MessageBodyMemberAttribute(Namespace="http://schemas.microsoft.com/OracleEBS/2008/05/Notification/", Order=0)]  
    public schemas.microsoft.com.OracleEBS._2008._05.Notification.NotificationDetails[] Details;  
  
    [System.ServiceModel.MessageBodyMemberAttribute(Namespace="http://schemas.microsoft.com/OracleEBS/2008/05/Notification/", Order=1)]  
    public string Info;  
  
    [System.ServiceModel.MessageBodyMemberAttribute(Namespace="http://schemas.microsoft.com/OracleEBS/2008/05/Notification/", Order=2)]  
    public string[] ResourceNames;  
  
    [System.ServiceModel.MessageBodyMemberAttribute(Namespace="http://schemas.microsoft.com/OracleEBS/2008/05/Notification/", Order=3)]  
    public string Source;  
  
    [System.ServiceModel.MessageBodyMemberAttribute(Namespace="http://schemas.microsoft.com/OracleEBS/2008/05/Notification/", Order=4)]  
    public string Type;  
  
    public Notification() {  
    }  
  
    public Notification(schemas.microsoft.com.OracleEBS._2008._05.Notification.NotificationDetails[] Details, string Info, string[] ResourceNames, string Source, string Type) {  
        this.Details = Details;  
        this.Info = Info;  
        this.ResourceNames = ResourceNames;  
        this.Source = Source;  
        this.Type = Type;  
    }  
}  
```  
  
### <a name="wcf-service-class"></a><span data-ttu-id="e5e32-147">WCF 服务类</span><span class="sxs-lookup"><span data-stu-id="e5e32-147">WCF Service Class</span></span>  
 <span data-ttu-id="e5e32-148">[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]还会生成一个具有为 WCF 服务类实现服务协定 （接口） 从存根 （stub） 文件。</span><span class="sxs-lookup"><span data-stu-id="e5e32-148">The [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)] also generates a file that has a stub for the WCF service class implemented from the service contract (interface).</span></span> <span data-ttu-id="e5e32-149">文件的名称是 OracleEBSBindingService.cs。</span><span class="sxs-lookup"><span data-stu-id="e5e32-149">The name of the file is OracleEBSBindingService.cs.</span></span> <span data-ttu-id="e5e32-150">你可以将插入的逻辑来处理**通知**直接插入此类操作。</span><span class="sxs-lookup"><span data-stu-id="e5e32-150">You can insert the logic to process the **Notification** operation directly into this class.</span></span> <span data-ttu-id="e5e32-151">下面的代码演示生成的 WCF 服务类[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="e5e32-151">The following code shows the WCF service class generated by the [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)].</span></span>  
  
```  
namespace OracleEBSBindingNamespace {  
  
    public class OracleEBSBindingService : Notification_ {  
  
        // CODEGEN: Generating message contract since the wrapper namespace (http://schemas.microsoft.com/OracleEBS/2008/05/Notification/) of message Notification   
        // does not match the default value (http://schemas.microsoft.com/OracleEBS/)  
        public virtual void Notification(Notification request) {  
            throw new System.NotImplementedException("The method or operation is not implemented.");  
        }  
    }  
}  
```  
  
## <a name="receiving-query-notifications-using-wcf-service-model"></a><span data-ttu-id="e5e32-152">使用 WCF 服务模型的接收查询通知</span><span class="sxs-lookup"><span data-stu-id="e5e32-152">Receiving Query Notifications Using WCF Service Model</span></span>  
 <span data-ttu-id="e5e32-153">本部分将说明了如何编写.NET 应用程序以接收查询通知使用[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="e5e32-153">This section provides instructions on how to write a .NET application to receive query notifications using the [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)].</span></span>  
  
#### <a name="to-receive-query-notifications"></a><span data-ttu-id="e5e32-154">若要接收查询通知</span><span class="sxs-lookup"><span data-stu-id="e5e32-154">To receive query notifications</span></span>  
  
1.  <span data-ttu-id="e5e32-155">使用[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]生成的 WCF 客户端**选择**操作**ACCOUNTACTIVITY**表。</span><span class="sxs-lookup"><span data-stu-id="e5e32-155">Use the [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)] to generate a WCF client for **Select** operation on the **ACCOUNTACTIVITY** table.</span></span> <span data-ttu-id="e5e32-156">此客户端将用于接收通知邮件后执行选择操作。</span><span class="sxs-lookup"><span data-stu-id="e5e32-156">You will use this client to perform Select operations after receiving a notification message.</span></span> <span data-ttu-id="e5e32-157">将新类，TableOperation.cs，添加到你的项目并添加下面的代码段，以执行选择操作。</span><span class="sxs-lookup"><span data-stu-id="e5e32-157">Add a new class, TableOperation.cs, to your project and add the following code snippet to perform a Select operation.</span></span>  
  
    ```  
    using System;  
    using System.Collections.Generic;  
    using System.Linq;  
    using System.Text;  
  
    namespace Notification_ServiceModel  
    {  
        class TableOperation  
        {  
            public void TableOp()  
            {  
                //////////////////////////////////////////////////////////////////////  
                // CREATING THE CLIENT AND SETTING CLIENT CREDENTIALS  
                //////////////////////////////////////////////////////////////////////  
  
                Tables_APPS_ACCOUNTACTIVITYClient client = new Tables_APPS_ACCOUNTACTIVITYClient();  
                client.ClientCredentials.UserName.UserName = "<Enter user name here>";  
                client.ClientCredentials.UserName.Password = "<Enter password here>";  
  
                ////////////////////////////////////////////////////////////////////  
                // OPENING THE CLIENT  
                //////////////////////////////////////////////////////////////////////  
                try  
                {  
                    Console.WriteLine("Opening the client ...");  
                    client.Open();  
                }  
                catch (Exception ex)  
                {  
                    Console.WriteLine("Exception: " + ex.Message);  
                    throw;  
                }  
  
                ////////////////////////////////////////////////////////////////////////////////////////  
                // SELECTING THE LAST INSERTED VALUES  
                ////////////////////////////////////////////////////////////////////////////////////////  
                Console.WriteLine("The application will now select the last inserted record");  
  
                schemas.microsoft.com.OracleEBS._2008._05.TableViewRecord.APPS.ACCOUNTACTIVITY.SelectRecord[] selectRecords;  
  
                try  
                {  
                    selectRecords = client.Select("*", "WHERE PROCESSED = 'n'");  
                }  
                catch (Exception ex)  
                {  
                    Console.WriteLine("Exception: " + ex.Message);  
                    throw;  
                }  
  
                Console.WriteLine("The details of the newly added records are:");  
                Console.WriteLine("********************************************");  
                for (int i = 0; i < selectRecords.Length; i++)  
                {  
                    Console.WriteLine("Transaction ID   : " + selectRecords[i].TID);  
                    Console.WriteLine("Account ID       : " + selectRecords[i].ACCOUNT);  
                    Console.WriteLine("Processed Status : " + selectRecords[i].PROCESSED);  
                    Console.WriteLine();  
                }  
                Console.WriteLine("********************************************");  
            }  
        }  
    }  
  
    ```  
  
2.  <span data-ttu-id="e5e32-158">使用[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]以生成 WCF 服务协定 （接口） 和用于帮助器类**通知**操作。</span><span class="sxs-lookup"><span data-stu-id="e5e32-158">Use the [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)] to generate a WCF service contract (interface) and helper classes for the **Notification** operation.</span></span>  
  
     <span data-ttu-id="e5e32-159">有关详细信息，请参阅[生成 WCF 客户端或 Oracle E-business Suite 解决方案项目关联的 WCF 服务协定](../../adapters-and-accelerators/adapter-oracle-ebs/create-a-wcf-client-or-wcf-service-contract-for-oracle-ebs-solution-artifacts.md)。</span><span class="sxs-lookup"><span data-stu-id="e5e32-159">For more information, see [Generate a WCF client or a WCF service contract for Oracle E-Business Suite solution artifacts](../../adapters-and-accelerators/adapter-oracle-ebs/create-a-wcf-client-or-wcf-service-contract-for-oracle-ebs-solution-artifacts.md).</span></span> <span data-ttu-id="e5e32-160">生成服务协定和帮助程序类时，可以选择指定的绑定属性。</span><span class="sxs-lookup"><span data-stu-id="e5e32-160">You can optionally specify the binding properties while generating the service contract and helper classes.</span></span> <span data-ttu-id="e5e32-161">这可确保它们正确设置生成的配置文件中。</span><span class="sxs-lookup"><span data-stu-id="e5e32-161">This guarantees that they are properly set in the generated configuration file.</span></span>  
  
3.  <span data-ttu-id="e5e32-162">实现 WCF 服务从在步骤 2 中生成的接口和帮助程序类。</span><span class="sxs-lookup"><span data-stu-id="e5e32-162">Implement a WCF service from the interface and helper classes generated in step 2.</span></span> <span data-ttu-id="e5e32-163">**通知**此类的方法可以处理从接收的数据遇到错误时引发异常中止操作，**通知**操作; 否则该方法将执行不返回任何内容。</span><span class="sxs-lookup"><span data-stu-id="e5e32-163">The **Notification** method of this class can throw an exception to abort the operation, if an error is encountered processing the data received from the **Notification** operation; otherwise the method does not return anything.</span></span> <span data-ttu-id="e5e32-164">必须属性 WCF 服务类，如下所示：</span><span class="sxs-lookup"><span data-stu-id="e5e32-164">You must attribute the WCF service class as follows:</span></span>  
  
    ```  
    [ServiceBehavior(InstanceContextMode = InstanceContextMode.Single)]  
    ```  
  
     <span data-ttu-id="e5e32-165">在**通知**方法，你可以直接实现你的应用程序逻辑。</span><span class="sxs-lookup"><span data-stu-id="e5e32-165">Within the **Notification** method, you can implement your application logic directly.</span></span> <span data-ttu-id="e5e32-166">OracleEBSBindingService.cs 中找不到此类。</span><span class="sxs-lookup"><span data-stu-id="e5e32-166">This class can be found in OracleEBSBindingService.cs.</span></span> <span data-ttu-id="e5e32-167">此示例中的此代码子类**OracleEBSBindingService**类。</span><span class="sxs-lookup"><span data-stu-id="e5e32-167">This code in this example sub-classes the **OracleEBSBindingService** class.</span></span> <span data-ttu-id="e5e32-168">在此代码中，接收的通知消息写入控制台。</span><span class="sxs-lookup"><span data-stu-id="e5e32-168">In this code, the notification message received is written to the console.</span></span> <span data-ttu-id="e5e32-169">此外， **TableOp**方法内的**TableOperation**类调用以执行选择操作。</span><span class="sxs-lookup"><span data-stu-id="e5e32-169">Additionally, the **TableOp** method within the **TableOperation** class is invoked to perform the Select operation.</span></span>  
  
    ```  
    [ServiceBehavior(InstanceContextMode = InstanceContextMode.Single)]  
  
    public class NotificationService : OracleEBSBindingNamespace.OracleEBSBindingService  
    {  
        public override void Notification(Notification request)  
        {  
            Console.WriteLine("\nNew Notification Received");  
            Console.WriteLine("*************************************************");  
            Console.WriteLine(request.Info);  
            Console.WriteLine(request.Source);  
            Console.WriteLine(request.Type);  
            Console.WriteLine("*************************************************");  
  
            TableOperation Ops = new TableOperation();  
            Ops.TableOp();  
  
        }  
    }  
    ```  
  
4.  <span data-ttu-id="e5e32-170">必须实现以下类用于 Oracle E-business Suite 传递凭据。</span><span class="sxs-lookup"><span data-stu-id="e5e32-170">You must implement the following class to pass credentials for the Oracle E-Business Suite.</span></span> <span data-ttu-id="e5e32-171">在应用程序的后半部分，将实例化此类，以传递凭据。</span><span class="sxs-lookup"><span data-stu-id="e5e32-171">In the latter part of the application, you will instantiate this class to pass on the credentials.</span></span>  
  
    ```  
    class NotificationCredentials : ClientCredentials, IServiceBehavior  
    {  
        public void AddBindingParameters(ServiceDescription serviceDescription, ServiceHostBase serviceHostBase, Collection<ServiceEndpoint> endpoints, BindingParameterCollection bindingParameters)  
        {  
            bindingParameters.Add(this);  
        }  
  
        public void ApplyDispatchBehavior(ServiceDescription serviceDescription, ServiceHostBase serviceHostBase)  
        { }  
  
        public void Validate(ServiceDescription serviceDescription, ServiceHostBase serviceHostBase)  
        { }  
  
        protected override ClientCredentials CloneCore()  
        {  
            ClientCredentials clone = new NotificationCredentials();  
            clone.UserName.UserName = this.UserName.UserName;  
            clone.UserName.Password = this.UserName.Password;  
            return clone;  
        }  
    }  
    ```  
  
5.  <span data-ttu-id="e5e32-172">创建**OracleEBSBinding**并配置适配器后，若要通过指定绑定属性接收查询通知。</span><span class="sxs-lookup"><span data-stu-id="e5e32-172">Create an **OracleEBSBinding** and configure the adapter to receive query notifications by specifying the binding properties.</span></span> <span data-ttu-id="e5e32-173">可以在代码中显式或配置中以声明方式执行此操作。</span><span class="sxs-lookup"><span data-stu-id="e5e32-173">You can do this either explicitly in code or declaratively in configuration.</span></span> <span data-ttu-id="e5e32-174">至少，你必须指定**InboundOperationType**和**NotificationStatement**绑定属性。</span><span class="sxs-lookup"><span data-stu-id="e5e32-174">At a minimum, you must specify the **InboundOperationType** and **NotificationStatement** binding properties.</span></span>  
  
    ```  
    OracleEBSBinding binding = new OracleEBSBinding();  
    binding.InboundOperationType = InboundOperation.Notification;  
    binding.NotificationStatement = "SELECT TID,ACCOUNT,PROCESSED FROM APPS.ACCOUNTACTIVITY WHERE PROCESSED = 'n'";  
    binding.NotifyOnListenerStart = true;  
    binding.NotificationPort = 10;  
    ```  
  
    > [!IMPORTANT]
    >  <span data-ttu-id="e5e32-175">值**NotificationPort**绑定属性必须设置为相同的端口号必须已添加到 Windows 防火墙例外列表。</span><span class="sxs-lookup"><span data-stu-id="e5e32-175">The value for the **NotificationPort** binding property must be set to the same port number that you must have added to the Windows Firewall exceptions list.</span></span> <span data-ttu-id="e5e32-176">有关如何将端口添加到 Windows 防火墙例外列表的说明，请参阅[http://go.microsoft.com/fwlink/?LinkID=196959](http://go.microsoft.com/fwlink/?LinkID=196959)。</span><span class="sxs-lookup"><span data-stu-id="e5e32-176">For instructions on how to add ports to Windows Firewall exceptions list, see [http://go.microsoft.com/fwlink/?LinkID=196959](http://go.microsoft.com/fwlink/?LinkID=196959).</span></span>  
  
    > [!IMPORTANT]
    >  <span data-ttu-id="e5e32-177">如果你未设置**NotificationPort**绑定属性，该适配器将假定默认值为-1 表示此绑定属性。</span><span class="sxs-lookup"><span data-stu-id="e5e32-177">If you do not set the **NotificationPort** binding property, the adapter will assume the default value of -1 for this binding property.</span></span> <span data-ttu-id="e5e32-178">在这种情况下，你将需要完全禁用 Windows 防火墙，以接收通知消息。</span><span class="sxs-lookup"><span data-stu-id="e5e32-178">In such a case, you will have to completely disable Windows Firewall to receive notification messages.</span></span>  
  
6.  <span data-ttu-id="e5e32-179">指定 Oracle E-business Suite 凭据，方法是实例化**NotificationCredentials**在步骤 4 中创建的类。</span><span class="sxs-lookup"><span data-stu-id="e5e32-179">Specify Oracle E-Business Suite credentials by instantiating the **NotificationCredentials** class you created in Step 4.</span></span>  
  
    ```  
    NotificationCredentials credentials = new NotificationCredentials();  
    credentials.UserName.UserName = "<Enter user name here>";  
    credentials.UserName.Password = "<Enter password here>";  
    ```  
  
7.  <span data-ttu-id="e5e32-180">创建在步骤 3 中创建的 WCF 服务的实例。</span><span class="sxs-lookup"><span data-stu-id="e5e32-180">Create an instance of the WCF service created in step 3.</span></span>  
  
    ```  
    // create service instance  
    NotificationService service = new NotificationService();  
    ```  
  
8.  <span data-ttu-id="e5e32-181">创建的实例**System.ServiceModel.ServiceHost**使用 WCF 服务和数据库连接 URI。</span><span class="sxs-lookup"><span data-stu-id="e5e32-181">Create an instance of **System.ServiceModel.ServiceHost** by using the WCF service and a base connection URI.</span></span> <span data-ttu-id="e5e32-182">你还必须指定此处的凭据。</span><span class="sxs-lookup"><span data-stu-id="e5e32-182">You must also specify the credentials here.</span></span>  
  
    ```  
    // Enable service host  
    Uri[] baseUri = new Uri[] { new Uri("oracleebs://ebs_instance_name") };  
    ServiceHost serviceHost = new ServiceHost(service, baseUri);  
    serviceHost.Description.Behaviors.Add(credentials);  
  
    ```  
  
9. <span data-ttu-id="e5e32-183">将服务终结点添加到服务主机。</span><span class="sxs-lookup"><span data-stu-id="e5e32-183">Add a service endpoint to the service host.</span></span> <span data-ttu-id="e5e32-184">为此，请执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="e5e32-184">To do this:</span></span>  
  
    -   <span data-ttu-id="e5e32-185">使用在步骤 5 中创建的绑定。</span><span class="sxs-lookup"><span data-stu-id="e5e32-185">Use the binding created in step 5.</span></span>  
  
    -   <span data-ttu-id="e5e32-186">指定连接 URI，其中包含凭据，如果需要，一个入站的 id。</span><span class="sxs-lookup"><span data-stu-id="e5e32-186">Specify a connection URI that contains credentials and, if required, an inbound ID.</span></span>  
  
    -   <span data-ttu-id="e5e32-187">作为"Notification_"指定的协定。</span><span class="sxs-lookup"><span data-stu-id="e5e32-187">Specify the contract as "Notification_".</span></span>  
  
    ```  
    // Add service endpoint: be sure to specify Notification_ as the contract  
    Uri ConnectionUri = new Uri("oracleebs://ebs_instance_name?");  
    serviceHost.AddServiceEndpoint("Notification_", binding, ConnectionUri);  
    ```  
  
10. <span data-ttu-id="e5e32-188">若要接收通知消息，请打开服务主机。</span><span class="sxs-lookup"><span data-stu-id="e5e32-188">To receive notification message, open the service host.</span></span>  
  
    ```  
    // Open the service host to begin receiving notifications  
    serviceHost.Open();  
    ```  
  
11. <span data-ttu-id="e5e32-189">若要停止接收通知，关闭服务主机。</span><span class="sxs-lookup"><span data-stu-id="e5e32-189">To stop receiving notifications, close the service host.</span></span>  
  
    ```  
    serviceHost.Close();  
    ```  
  
### <a name="example"></a><span data-ttu-id="e5e32-190">示例</span><span class="sxs-lookup"><span data-stu-id="e5e32-190">Example</span></span>  
 <span data-ttu-id="e5e32-191">下面的示例演示.NET 应用程序以接收 ACCOUNTACTIVITY 表的通知消息。</span><span class="sxs-lookup"><span data-stu-id="e5e32-191">The following example shows a .NET application to receive notification messages for the ACCOUNTACTIVITY table.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="e5e32-192">下面的代码段实例化**TableOperation.cs**类并调用**TableOp**方法。</span><span class="sxs-lookup"><span data-stu-id="e5e32-192">The following code snippet instantiates a **TableOperation.cs** class and invokes the **TableOp** method.</span></span> <span data-ttu-id="e5e32-193">类和方法所述步骤 1。</span><span class="sxs-lookup"><span data-stu-id="e5e32-193">The class and the method are described in Step 1.</span></span>  
  
```  
using System;  
using System.Collections.Generic;  
using System.Linq;  
using System.Text;  
  
using Microsoft.Adapters.OracleEBS;  
using Microsoft.ServiceModel.Channels;  
using System.ServiceModel;  
using System.ServiceModel.Description;  
using System.ServiceModel.Channels;  
using System.Collections.ObjectModel;  
  
namespace Notification_ServiceModel  
{  
    [ServiceBehavior(InstanceContextMode = InstanceContextMode.Single)]  
  
    public class NotificationService : OracleEBSBindingNamespace.OracleEBSBindingService  
    {  
        public override void Notification(Notification request)  
        {  
            Console.WriteLine("\nNew Notification Received");  
            Console.WriteLine("*************************************************");  
            Console.WriteLine(request.Info);  
            Console.WriteLine(request.Source);  
            Console.WriteLine(request.Type);  
            Console.WriteLine("*************************************************");  
  
            TableOperation Ops = new TableOperation();  
            Ops.TableOp();  
  
        }  
    }  
  
    class NotificationCredentials : ClientCredentials, IServiceBehavior  
    {  
        public void AddBindingParameters(ServiceDescription serviceDescription, ServiceHostBase serviceHostBase, Collection<ServiceEndpoint> endpoints, BindingParameterCollection bindingParameters)  
        {  
            bindingParameters.Add(this);  
        }  
  
        public void ApplyDispatchBehavior(ServiceDescription serviceDescription, ServiceHostBase serviceHostBase)  
        { }  
  
        public void Validate(ServiceDescription serviceDescription, ServiceHostBase serviceHostBase)  
        { }  
  
        protected override ClientCredentials CloneCore()  
        {  
            ClientCredentials clone = new NotificationCredentials();  
            clone.UserName.UserName = this.UserName.UserName;  
            clone.UserName.Password = this.UserName.Password;  
            return clone;  
        }  
    }  
  
    class Program  
    {  
        static void Main(string[] args)  
        {  
            ServiceHost serviceHost = null;  
            try  
            {  
                Console.WriteLine("Sample started...");  
                Console.WriteLine("Press any key to start receiving notifications...");  
                Console.ReadLine();  
  
                OracleEBSBinding binding = new OracleEBSBinding();  
                binding.InboundOperationType = InboundOperation.Notification;  
                binding.NotificationStatement = "SELECT TID,ACCOUNT,PROCESSED FROM APPS.ACCOUNTACTIVITY WHERE PROCESSED = 'n'";  
                binding.NotifyOnListenerStart = true;  
                binding.NotificationPort = 10;  
  
                // This URI is used to specify the address for the ServiceEndpoint  
                // It must contain the InboundId that was used to generate  
                // the WCF service callback interface  
                Uri ConnectionUri = new Uri("oracleebs://ebs_instance_name");  
  
                // This URI is used to initialize the ServiceHost. It cannot contain  
                // an InboundID; otherwise,an exception is thrown when  
                // the ServiceHost is initialized.  
                Uri[] baseUri = new Uri[] { new Uri("oracleebs://ebs_instance_name") };  
  
                NotificationCredentials credentials = new NotificationCredentials();  
                credentials.UserName.UserName = "<Enter user name here>";  
                credentials.UserName.Password = "<Enter password here>";  
  
                Console.WriteLine("Opening service host...");  
                NotificationService service = new NotificationService();  
                serviceHost = new ServiceHost(service, baseUri);  
                serviceHost.Description.Behaviors.Add(credentials);  
                serviceHost.AddServiceEndpoint("Notification_", binding, ConnectionUri);  
                serviceHost.Open();  
                Console.WriteLine("Service host opened...");  
                Console.WriteLine("Waiting for notification...");  
  
                Console.WriteLine("\nHit <RETURN> to stop receiving notification");  
                Console.ReadLine();  
            }  
            catch (Exception e)  
            {  
                Console.WriteLine("Exception :" + e.Message);  
                Console.ReadLine();  
  
                /* If there is an error it will be specified in the inner exception */  
                if (e.InnerException != null)  
                {  
                    Console.WriteLine("InnerException: " + e.InnerException.Message);  
                    Console.ReadLine();  
                }  
            }  
            finally  
            {  
                // IMPORTANT: you must close the ServiceHost to stop polling  
                if (serviceHost.State == CommunicationState.Opened)  
                    serviceHost.Close();  
                else  
                    serviceHost.Abort();  
            }  
  
        }  
    }  
}  
  
```  
  
## <a name="see-also"></a><span data-ttu-id="e5e32-194">另请参阅</span><span class="sxs-lookup"><span data-stu-id="e5e32-194">See Also</span></span>  
 [<span data-ttu-id="e5e32-195">开发 Oracle E-business Suite 应用程序使用 WCF 服务模型</span><span class="sxs-lookup"><span data-stu-id="e5e32-195">Develop Oracle E-Business Suite applications using the WCF Service Model</span></span>](../../adapters-and-accelerators/adapter-oracle-ebs/develop-oracle-e-business-suite-applications-using-the-wcf-service-model.md)