---
title: Oracle E-business Suite 使用接收数据库更改通知 WCF 服务模型 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 362193f5-2586-480f-a62e-1ed5e4ef342c
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 02ab0b1be9862557319197f609c37bb151675e54
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36988846"
---
# <a name="receive-oracle-e-business-suite-database-change-notifications-using-the-wcf-service-model"></a><span data-ttu-id="b10a0-102">Oracle E-business Suite 使用接收数据库更改通知 WCF 服务模型</span><span class="sxs-lookup"><span data-stu-id="b10a0-102">Receive Oracle E-Business Suite database change notifications using the WCF service model</span></span>
<span data-ttu-id="b10a0-103">本主题演示如何配置[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]从 Oracle 数据库接收查询通知消息。</span><span class="sxs-lookup"><span data-stu-id="b10a0-103">This topic demonstrates how to configure the [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] to receive query notification messages from an Oracle database.</span></span> <span data-ttu-id="b10a0-104">为了演示通知，请考虑表中的，ACCOUNTACTIVITY，"处理"列。</span><span class="sxs-lookup"><span data-stu-id="b10a0-104">To demonstrate notifications, consider a table, ACCOUNTACTIVITY, with a “Processed” column.</span></span> <span data-ttu-id="b10a0-105">一条新记录插入到此表时，状态列的值设置为"n"。</span><span class="sxs-lookup"><span data-stu-id="b10a0-105">When a new record is inserted to this table, the value of the Status column is set to “n.”</span></span> <span data-ttu-id="b10a0-106">你可以配置适配器以通过使用检索到的具有"n"。 为"已处理"列的所有记录的 SQL 语句注册通知接收通知</span><span class="sxs-lookup"><span data-stu-id="b10a0-106">You can configure the adapter to receive notifications by registering for notifications using a SQL statement that retrieves all records that have “Processed” column as “n.”</span></span> <span data-ttu-id="b10a0-107">您可以通过指定的 SQL 语句来实现**NotificationStatement**属性绑定。</span><span class="sxs-lookup"><span data-stu-id="b10a0-107">You can do so by specifying the SQL statement for the **NotificationStatement** binding property.</span></span> <span data-ttu-id="b10a0-108">适配器客户端收到通知后，它可以包含用于执行对 Oracle 数据库的所有后续任务的逻辑。</span><span class="sxs-lookup"><span data-stu-id="b10a0-108">After the adapter client receives the notification, it can contain the logic to do any subsequent tasks on the Oracle database.</span></span> <span data-ttu-id="b10a0-109">在此示例中，为简单起见，适配器客户端列出所有记录表中的具有"处理"列作为"n"。</span><span class="sxs-lookup"><span data-stu-id="b10a0-109">In this example, for the sake of simplicity, the adapter client lists all the records in the table that have the “Processed” column as “n.”</span></span>  
  
## <a name="configuring-notifications-with-the-oracle-e-business-adapter-binding-properties"></a><span data-ttu-id="b10a0-110">使用 Oracle E-business 适配器的绑定属性中配置通知</span><span class="sxs-lookup"><span data-stu-id="b10a0-110">Configuring Notifications with the Oracle E-Business Adapter Binding Properties</span></span>  
 <span data-ttu-id="b10a0-111">下表总结了[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]绑定用于配置 Oracle E-business Suite 中接收通知的属性。</span><span class="sxs-lookup"><span data-stu-id="b10a0-111">The table below summarizes the [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] binding properties that you use to configure receiving notifications from Oracle E-Business Suite.</span></span> <span data-ttu-id="b10a0-112">必须运行.NET 应用程序以接收通知时指定这些绑定属性。</span><span class="sxs-lookup"><span data-stu-id="b10a0-112">You must specify these binding properties while running the .NET application to receive notifications.</span></span>  
  
|<span data-ttu-id="b10a0-113">绑定属性</span><span class="sxs-lookup"><span data-stu-id="b10a0-113">Binding Property</span></span>|<span data-ttu-id="b10a0-114">Description</span><span class="sxs-lookup"><span data-stu-id="b10a0-114">Description</span></span>|  
|----------------------|-----------------|  
|<span data-ttu-id="b10a0-115">**InboundOperationType**</span><span class="sxs-lookup"><span data-stu-id="b10a0-115">**InboundOperationType**</span></span>|<span data-ttu-id="b10a0-116">指定你想要执行的入站的操作。</span><span class="sxs-lookup"><span data-stu-id="b10a0-116">Specifies the inbound operation that you want to perform.</span></span> <span data-ttu-id="b10a0-117">若要接收通知消息，请将此设置为**通知**。</span><span class="sxs-lookup"><span data-stu-id="b10a0-117">To receive notification messages, set this to **Notification**.</span></span>|  
|<span data-ttu-id="b10a0-118">**NotificationPort**</span><span class="sxs-lookup"><span data-stu-id="b10a0-118">**NotificationPort**</span></span>|<span data-ttu-id="b10a0-119">指定 ODP.NET 必须打开从 Oracle 数据库的数据库更改通知侦听的端口号。</span><span class="sxs-lookup"><span data-stu-id="b10a0-119">Specifies the port number that ODP.NET must open to listen for database change notification from Oracle database.</span></span>|  
|<span data-ttu-id="b10a0-120">**NotificationStatement**</span><span class="sxs-lookup"><span data-stu-id="b10a0-120">**NotificationStatement**</span></span>|<span data-ttu-id="b10a0-121">指定用于对查询通知注册的 Select 语句。</span><span class="sxs-lookup"><span data-stu-id="b10a0-121">Specifies the Select statement used to register for query notifications.</span></span> <span data-ttu-id="b10a0-122">仅当指定的 Select 语句更改的结果集时，适配器将获取一条通知消息。</span><span class="sxs-lookup"><span data-stu-id="b10a0-122">The adapter gets a notification message only when the result set for the specified Select statement changes.</span></span>|  
|<span data-ttu-id="b10a0-123">**NotifyOnListenerStart**</span><span class="sxs-lookup"><span data-stu-id="b10a0-123">**NotifyOnListenerStart**</span></span>|<span data-ttu-id="b10a0-124">指定适配器是否启动侦听器时在向适配器客户端发送了通知。</span><span class="sxs-lookup"><span data-stu-id="b10a0-124">Specifies whether the adapter sends a notification to the adapter clients when the listener is started.</span></span>|  
  
 <span data-ttu-id="b10a0-125">有关这些属性的更完整说明，请参阅[了解关于 BizTalk Adapter for Oracle E-business Suite 绑定属性](../../adapters-and-accelerators/adapter-oracle-ebs/read-about-the-biztalk-adapter-for-oracle-e-business-suite-binding-properties.md)。</span><span class="sxs-lookup"><span data-stu-id="b10a0-125">For a more complete description of these properties, see [Read about the BizTalk Adapter for Oracle E-Business Suite binding properties](../../adapters-and-accelerators/adapter-oracle-ebs/read-about-the-biztalk-adapter-for-oracle-e-business-suite-binding-properties.md).</span></span> <span data-ttu-id="b10a0-126">有关如何使用的完整说明[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]若要从 Oracle E-business Suite 中接收通知，请阅读此主题的其余部分。</span><span class="sxs-lookup"><span data-stu-id="b10a0-126">For a complete description of how to use the [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] to receive notifications from Oracle E-Business Suite, read the remainder of this topic.</span></span>  
  
## <a name="configuring-notifications-using-the-wcf-service-model"></a><span data-ttu-id="b10a0-127">配置通知使用 WCF 服务模型</span><span class="sxs-lookup"><span data-stu-id="b10a0-127">Configuring Notifications Using the WCF Service Model</span></span>  
 <span data-ttu-id="b10a0-128">若要接收的通知使用 WCF 服务模型，您必须：</span><span class="sxs-lookup"><span data-stu-id="b10a0-128">To receive the notifications using the WCF service model, you must:</span></span>  
  
- <span data-ttu-id="b10a0-129">为生成的 WCF 服务协定 （接口）**通知**从由适配器公开的元数据的操作。</span><span class="sxs-lookup"><span data-stu-id="b10a0-129">Generate a WCF service contract (interface) for the **Notification** operation from the metadata exposed by the adapter.</span></span> <span data-ttu-id="b10a0-130">若要执行此操作，可以使用[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="b10a0-130">To do this, you could use the [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)].</span></span>  
  
- <span data-ttu-id="b10a0-131">生成的 WCF 客户端**选择**ACCOUNTACTIVITY 表上的操作。</span><span class="sxs-lookup"><span data-stu-id="b10a0-131">Generate a WCF client for the **Select** operation on the ACCOUNTACTIVITY table.</span></span> <span data-ttu-id="b10a0-132">若要执行此操作，可以使用[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="b10a0-132">To do this, you could use the [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)].</span></span>  
  
- <span data-ttu-id="b10a0-133">实现此接口中的 WCF 服务。</span><span class="sxs-lookup"><span data-stu-id="b10a0-133">Implement a WCF service from this interface.</span></span>  
  
- <span data-ttu-id="b10a0-134">托管此 WCF 服务使用服务主机 (**System.ServiceModel.ServiceHost**)。</span><span class="sxs-lookup"><span data-stu-id="b10a0-134">Host this WCF service using a service host (**System.ServiceModel.ServiceHost**).</span></span>  
  
## <a name="about-the-examples-used-in-this-topic"></a><span data-ttu-id="b10a0-135">有关使用在本主题中的示例</span><span class="sxs-lookup"><span data-stu-id="b10a0-135">About the Examples Used in this Topic</span></span>  
 <span data-ttu-id="b10a0-136">本主题中的示例接收 ACCOUNTACTIVITY 表通知。</span><span class="sxs-lookup"><span data-stu-id="b10a0-136">The examples in this topic receives notification for the ACCOUNTACTIVITY table.</span></span> <span data-ttu-id="b10a0-137">这些示例提供了一个脚本来生成表。</span><span class="sxs-lookup"><span data-stu-id="b10a0-137">A script to generate the table is supplied with the samples.</span></span> <span data-ttu-id="b10a0-138">有关示例的详细信息，请参阅[适用于 Oracle EBS 适配器示例](../../adapters-and-accelerators/adapter-oracle-ebs/samples-for-the-oracle-ebs-adapter.md)。</span><span class="sxs-lookup"><span data-stu-id="b10a0-138">For more information about the samples, see [Samples for the Oracle EBS adapter](../../adapters-and-accelerators/adapter-oracle-ebs/samples-for-the-oracle-ebs-adapter.md).</span></span> <span data-ttu-id="b10a0-139">示例中， **Notification_ServiceModel**，后者基于本主题中，还提供与[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]示例。</span><span class="sxs-lookup"><span data-stu-id="b10a0-139">A sample, **Notification_ServiceModel**, which is based on this topic, is also provided with the [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] samples.</span></span>  
  
## <a name="the-wcf-service-contract-and-class"></a><span data-ttu-id="b10a0-140">WCF 服务约定和类</span><span class="sxs-lookup"><span data-stu-id="b10a0-140">The WCF Service Contract and Class</span></span>  
 <span data-ttu-id="b10a0-141">可以使用[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]若要创建 WCF 服务协定 （接口） 和支持类**通知**操作。</span><span class="sxs-lookup"><span data-stu-id="b10a0-141">You can use the [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)] to create a WCF service contract (interface) and supporting classes for the **Notification** operation.</span></span> <span data-ttu-id="b10a0-142">有关生成的 WCF 服务协定的详细信息，请参阅[生成 WCF 客户端或 WCF 服务协定为 Oracle E-business Suite 解决方案项目](../../adapters-and-accelerators/adapter-oracle-ebs/create-a-wcf-client-or-wcf-service-contract-for-oracle-ebs-solution-artifacts.md)。</span><span class="sxs-lookup"><span data-stu-id="b10a0-142">For more information about generating a WCF service contract, see [Generate a WCF client or a WCF service contract for Oracle E-Business Suite solution artifacts](../../adapters-and-accelerators/adapter-oracle-ebs/create-a-wcf-client-or-wcf-service-contract-for-oracle-ebs-solution-artifacts.md).</span></span>  
  
### <a name="the-wcf-service-contract-interface"></a><span data-ttu-id="b10a0-143">WCF 服务协定 （接口）</span><span class="sxs-lookup"><span data-stu-id="b10a0-143">The WCF Service Contract (Interface)</span></span>  
 <span data-ttu-id="b10a0-144">下面的代码演示 WCF 服务协定 （接口） 为生成**通知**操作。</span><span class="sxs-lookup"><span data-stu-id="b10a0-144">The following code shows the WCF service contract (interface) generated for the **Notification** operation.</span></span>  
  
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
  
### <a name="the-message-contracts"></a><span data-ttu-id="b10a0-145">消息协定</span><span class="sxs-lookup"><span data-stu-id="b10a0-145">The Message Contracts</span></span>  
 <span data-ttu-id="b10a0-146">下面是通知操作的消息约定。</span><span class="sxs-lookup"><span data-stu-id="b10a0-146">Following is the message contract for the Notification operation.</span></span>  
  
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
  
### <a name="wcf-service-class"></a><span data-ttu-id="b10a0-147">WCF 服务类</span><span class="sxs-lookup"><span data-stu-id="b10a0-147">WCF Service Class</span></span>  
 <span data-ttu-id="b10a0-148">[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]还会生成一个具有实现服务协定 （接口） 中的 WCF 服务类的存根文件。</span><span class="sxs-lookup"><span data-stu-id="b10a0-148">The [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)] also generates a file that has a stub for the WCF service class implemented from the service contract (interface).</span></span> <span data-ttu-id="b10a0-149">文件的名称是 OracleEBSBindingService.cs。</span><span class="sxs-lookup"><span data-stu-id="b10a0-149">The name of the file is OracleEBSBindingService.cs.</span></span> <span data-ttu-id="b10a0-150">您可以将逻辑来处理**通知**直接在此类操作。</span><span class="sxs-lookup"><span data-stu-id="b10a0-150">You can insert the logic to process the **Notification** operation directly into this class.</span></span> <span data-ttu-id="b10a0-151">下面的代码演示生成的 WCF 服务类[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="b10a0-151">The following code shows the WCF service class generated by the [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)].</span></span>  
  
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
  
## <a name="receiving-query-notifications-using-wcf-service-model"></a><span data-ttu-id="b10a0-152">使用 WCF 服务模型的接收查询通知</span><span class="sxs-lookup"><span data-stu-id="b10a0-152">Receiving Query Notifications Using WCF Service Model</span></span>  
 <span data-ttu-id="b10a0-153">本部分说明了如何编写.NET 应用程序以接收查询通知使用[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="b10a0-153">This section provides instructions on how to write a .NET application to receive query notifications using the [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)].</span></span>  
  
#### <a name="to-receive-query-notifications"></a><span data-ttu-id="b10a0-154">若要接收查询通知</span><span class="sxs-lookup"><span data-stu-id="b10a0-154">To receive query notifications</span></span>  
  
1. <span data-ttu-id="b10a0-155">使用[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]生成的 WCF 客户端**选择**上的操作**ACCOUNTACTIVITY**表。</span><span class="sxs-lookup"><span data-stu-id="b10a0-155">Use the [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)] to generate a WCF client for **Select** operation on the **ACCOUNTACTIVITY** table.</span></span> <span data-ttu-id="b10a0-156">将使用此客户端收到通知消息后执行的 Select 操作。</span><span class="sxs-lookup"><span data-stu-id="b10a0-156">You will use this client to perform Select operations after receiving a notification message.</span></span> <span data-ttu-id="b10a0-157">向项目添加新类，TableOperation.cs，并添加下面的代码段，以执行选择操作。</span><span class="sxs-lookup"><span data-stu-id="b10a0-157">Add a new class, TableOperation.cs, to your project and add the following code snippet to perform a Select operation.</span></span>  
  
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
  
2. <span data-ttu-id="b10a0-158">使用[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]生成的 WCF 服务协定 （接口） 和帮助器类实现**通知**操作。</span><span class="sxs-lookup"><span data-stu-id="b10a0-158">Use the [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)] to generate a WCF service contract (interface) and helper classes for the **Notification** operation.</span></span>  
  
    <span data-ttu-id="b10a0-159">有关详细信息，请参阅[生成 WCF 客户端或 WCF 服务协定为 Oracle E-business Suite 解决方案项目](../../adapters-and-accelerators/adapter-oracle-ebs/create-a-wcf-client-or-wcf-service-contract-for-oracle-ebs-solution-artifacts.md)。</span><span class="sxs-lookup"><span data-stu-id="b10a0-159">For more information, see [Generate a WCF client or a WCF service contract for Oracle E-Business Suite solution artifacts](../../adapters-and-accelerators/adapter-oracle-ebs/create-a-wcf-client-or-wcf-service-contract-for-oracle-ebs-solution-artifacts.md).</span></span> <span data-ttu-id="b10a0-160">在生成服务协定和帮助程序类时，可以选择指定的绑定属性。</span><span class="sxs-lookup"><span data-stu-id="b10a0-160">You can optionally specify the binding properties while generating the service contract and helper classes.</span></span> <span data-ttu-id="b10a0-161">这可确保它们正确设置生成的配置文件中。</span><span class="sxs-lookup"><span data-stu-id="b10a0-161">This guarantees that they are properly set in the generated configuration file.</span></span>  
  
3. <span data-ttu-id="b10a0-162">实现在步骤 2 中生成的接口和帮助程序类中的 WCF 服务。</span><span class="sxs-lookup"><span data-stu-id="b10a0-162">Implement a WCF service from the interface and helper classes generated in step 2.</span></span> <span data-ttu-id="b10a0-163">**通知**此类方法可以引发异常来中止操作，如果遇到错误，处理从接收的数据**通知**操作; 否则该方法执行不返回任何内容。</span><span class="sxs-lookup"><span data-stu-id="b10a0-163">The **Notification** method of this class can throw an exception to abort the operation, if an error is encountered processing the data received from the **Notification** operation; otherwise the method does not return anything.</span></span> <span data-ttu-id="b10a0-164">必须按如下所示属性的 WCF 服务类：</span><span class="sxs-lookup"><span data-stu-id="b10a0-164">You must attribute the WCF service class as follows:</span></span>  
  
   ```  
   [ServiceBehavior(InstanceContextMode = InstanceContextMode.Single)]  
   ```  
  
    <span data-ttu-id="b10a0-165">内**通知**方法，可以直接实现应用程序逻辑。</span><span class="sxs-lookup"><span data-stu-id="b10a0-165">Within the **Notification** method, you can implement your application logic directly.</span></span> <span data-ttu-id="b10a0-166">可以 OracleEBSBindingService.cs 中找到此类。</span><span class="sxs-lookup"><span data-stu-id="b10a0-166">This class can be found in OracleEBSBindingService.cs.</span></span> <span data-ttu-id="b10a0-167">此代码在此示例中的嵌套类**OracleEBSBindingService**类。</span><span class="sxs-lookup"><span data-stu-id="b10a0-167">This code in this example sub-classes the **OracleEBSBindingService** class.</span></span> <span data-ttu-id="b10a0-168">在此代码中，收到的通知消息写入控制台。</span><span class="sxs-lookup"><span data-stu-id="b10a0-168">In this code, the notification message received is written to the console.</span></span> <span data-ttu-id="b10a0-169">此外， **TableOp**方法内的**TableOperation**类调用以执行选择操作。</span><span class="sxs-lookup"><span data-stu-id="b10a0-169">Additionally, the **TableOp** method within the **TableOperation** class is invoked to perform the Select operation.</span></span>  
  
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
  
4. <span data-ttu-id="b10a0-170">必须实现以下类用于传递用于 Oracle E-business Suite 的凭据。</span><span class="sxs-lookup"><span data-stu-id="b10a0-170">You must implement the following class to pass credentials for the Oracle E-Business Suite.</span></span> <span data-ttu-id="b10a0-171">在应用程序的后半部分，将实例化此类，以传递凭据。</span><span class="sxs-lookup"><span data-stu-id="b10a0-171">In the latter part of the application, you will instantiate this class to pass on the credentials.</span></span>  
  
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
  
5. <span data-ttu-id="b10a0-172">创建**OracleEBSBinding**并配置适配器后，若要通过指定的绑定属性接收查询通知。</span><span class="sxs-lookup"><span data-stu-id="b10a0-172">Create an **OracleEBSBinding** and configure the adapter to receive query notifications by specifying the binding properties.</span></span> <span data-ttu-id="b10a0-173">可以在代码中显式或配置中以声明方式执行此操作。</span><span class="sxs-lookup"><span data-stu-id="b10a0-173">You can do this either explicitly in code or declaratively in configuration.</span></span> <span data-ttu-id="b10a0-174">至少，您必须指定**InboundOperationType**并**NotificationStatement**绑定属性。</span><span class="sxs-lookup"><span data-stu-id="b10a0-174">At a minimum, you must specify the **InboundOperationType** and **NotificationStatement** binding properties.</span></span>  
  
   ```  
   OracleEBSBinding binding = new OracleEBSBinding();  
   binding.InboundOperationType = InboundOperation.Notification;  
   binding.NotificationStatement = "SELECT TID,ACCOUNT,PROCESSED FROM APPS.ACCOUNTACTIVITY WHERE PROCESSED = 'n'";  
   binding.NotifyOnListenerStart = true;  
   binding.NotificationPort = 10;  
   ```  
  
   > [!IMPORTANT]
   >  <span data-ttu-id="b10a0-175">值**NotificationPort**绑定属性必须设置为相同的端口号必须已添加到 Windows 防火墙例外列表。</span><span class="sxs-lookup"><span data-stu-id="b10a0-175">The value for the **NotificationPort** binding property must be set to the same port number that you must have added to the Windows Firewall exceptions list.</span></span> <span data-ttu-id="b10a0-176">有关如何将端口添加到 Windows 防火墙例外列表的说明，请参阅[ http://go.microsoft.com/fwlink/?LinkID=196959 ](http://go.microsoft.com/fwlink/?LinkID=196959)。</span><span class="sxs-lookup"><span data-stu-id="b10a0-176">For instructions on how to add ports to Windows Firewall exceptions list, see [http://go.microsoft.com/fwlink/?LinkID=196959](http://go.microsoft.com/fwlink/?LinkID=196959).</span></span>  
  
   > [!IMPORTANT]
   >  <span data-ttu-id="b10a0-177">如果未设置**NotificationPort**绑定属性，该适配器将假定-1，表示此绑定属性的默认值。</span><span class="sxs-lookup"><span data-stu-id="b10a0-177">If you do not set the **NotificationPort** binding property, the adapter will assume the default value of -1 for this binding property.</span></span> <span data-ttu-id="b10a0-178">在这种情况下，您将必须完全禁用 Windows 防火墙，以接收通知消息。</span><span class="sxs-lookup"><span data-stu-id="b10a0-178">In such a case, you will have to completely disable Windows Firewall to receive notification messages.</span></span>  
  
6. <span data-ttu-id="b10a0-179">指定 Oracle E-business Suite 凭据通过实例化**NotificationCredentials**步骤 4 中创建的类。</span><span class="sxs-lookup"><span data-stu-id="b10a0-179">Specify Oracle E-Business Suite credentials by instantiating the **NotificationCredentials** class you created in Step 4.</span></span>  
  
   ```  
   NotificationCredentials credentials = new NotificationCredentials();  
   credentials.UserName.UserName = "<Enter user name here>";  
   credentials.UserName.Password = "<Enter password here>";  
   ```  
  
7. <span data-ttu-id="b10a0-180">创建在步骤 3 中创建的 WCF 服务的实例。</span><span class="sxs-lookup"><span data-stu-id="b10a0-180">Create an instance of the WCF service created in step 3.</span></span>  
  
   ```  
   // create service instance  
   NotificationService service = new NotificationService();  
   ```  
  
8. <span data-ttu-id="b10a0-181">创建的实例**System.ServiceModel.ServiceHost**使用 WCF 服务和基本连接 URI。</span><span class="sxs-lookup"><span data-stu-id="b10a0-181">Create an instance of **System.ServiceModel.ServiceHost** by using the WCF service and a base connection URI.</span></span> <span data-ttu-id="b10a0-182">此外必须指定凭据。</span><span class="sxs-lookup"><span data-stu-id="b10a0-182">You must also specify the credentials here.</span></span>  
  
   ```  
   // Enable service host  
   Uri[] baseUri = new Uri[] { new Uri("oracleebs://ebs_instance_name") };  
   ServiceHost serviceHost = new ServiceHost(service, baseUri);  
   serviceHost.Description.Behaviors.Add(credentials);  
  
   ```  
  
9. <span data-ttu-id="b10a0-183">将服务终结点添加到服务主机。</span><span class="sxs-lookup"><span data-stu-id="b10a0-183">Add a service endpoint to the service host.</span></span> <span data-ttu-id="b10a0-184">为此，请执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="b10a0-184">To do this:</span></span>  
  
   - <span data-ttu-id="b10a0-185">使用在步骤 5 中创建的绑定。</span><span class="sxs-lookup"><span data-stu-id="b10a0-185">Use the binding created in step 5.</span></span>  
  
   - <span data-ttu-id="b10a0-186">指定连接 URI，其中包含的凭据，如果需要，入站 id。</span><span class="sxs-lookup"><span data-stu-id="b10a0-186">Specify a connection URI that contains credentials and, if required, an inbound ID.</span></span>  
  
   - <span data-ttu-id="b10a0-187">作为"Notification_"指定的协定。</span><span class="sxs-lookup"><span data-stu-id="b10a0-187">Specify the contract as "Notification_".</span></span>  
  
     ```  
     // Add service endpoint: be sure to specify Notification_ as the contract  
     Uri ConnectionUri = new Uri("oracleebs://ebs_instance_name?");  
     serviceHost.AddServiceEndpoint("Notification_", binding, ConnectionUri);  
     ```  
  
10. <span data-ttu-id="b10a0-188">若要接收通知消息，请打开服务主机。</span><span class="sxs-lookup"><span data-stu-id="b10a0-188">To receive notification message, open the service host.</span></span>  
  
    ```  
    // Open the service host to begin receiving notifications  
    serviceHost.Open();  
    ```  
  
11. <span data-ttu-id="b10a0-189">若要停止接收通知，请关闭服务主机。</span><span class="sxs-lookup"><span data-stu-id="b10a0-189">To stop receiving notifications, close the service host.</span></span>  
  
    ```  
    serviceHost.Close();  
    ```  
  
### <a name="example"></a><span data-ttu-id="b10a0-190">示例</span><span class="sxs-lookup"><span data-stu-id="b10a0-190">Example</span></span>  
 <span data-ttu-id="b10a0-191">下面的示例显示了.NET 应用程序以接收 ACCOUNTACTIVITY 表的通知消息。</span><span class="sxs-lookup"><span data-stu-id="b10a0-191">The following example shows a .NET application to receive notification messages for the ACCOUNTACTIVITY table.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="b10a0-192">下面的代码段实例化**TableOperation.cs**类，并调用**TableOp**方法。</span><span class="sxs-lookup"><span data-stu-id="b10a0-192">The following code snippet instantiates a **TableOperation.cs** class and invokes the **TableOp** method.</span></span> <span data-ttu-id="b10a0-193">步骤 1 中描述类和方法。</span><span class="sxs-lookup"><span data-stu-id="b10a0-193">The class and the method are described in Step 1.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="b10a0-194">请参阅</span><span class="sxs-lookup"><span data-stu-id="b10a0-194">See Also</span></span>  
 [<span data-ttu-id="b10a0-195">开发 Oracle E-business Suite 应用程序使用 WCF 服务模型</span><span class="sxs-lookup"><span data-stu-id="b10a0-195">Develop Oracle E-Business Suite applications using the WCF Service Model</span></span>](../../adapters-and-accelerators/adapter-oracle-ebs/develop-oracle-e-business-suite-applications-using-the-wcf-service-model.md)