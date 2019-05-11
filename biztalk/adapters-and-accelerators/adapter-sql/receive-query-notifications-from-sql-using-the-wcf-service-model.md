---
title: 从使用 WCF 服务模型的 SQL 接收查询通知 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 1c9def31-3c5a-4326-b798-31bde0ff2568
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e5cff3344128e1471b57b387aaa8597c22a11d85
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65368324"
---
# <a name="receive-query-notifications-from-sql-using-the-wcf-service-model"></a><span data-ttu-id="93712-102">从使用 WCF 服务模型的 SQL 接收查询通知</span><span class="sxs-lookup"><span data-stu-id="93712-102">Receive Query Notifications from SQL using the WCF Service Model</span></span>
<span data-ttu-id="93712-103">本主题演示如何配置[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]从 SQL Server 数据库接收查询通知消息。</span><span class="sxs-lookup"><span data-stu-id="93712-103">This topic demonstrates how to configure the [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] to receive query notification messages from a SQL Server database.</span></span> <span data-ttu-id="93712-104">为了演示通知，请考虑表中的，员工，"状态"列。</span><span class="sxs-lookup"><span data-stu-id="93712-104">To demonstrate notifications, consider a table, Employee, with a “Status” column.</span></span> <span data-ttu-id="93712-105">一条新记录插入到此表时，状态列的值设置为 0。</span><span class="sxs-lookup"><span data-stu-id="93712-105">When a new record is inserted to this table, the value of the Status column is set to 0.</span></span> <span data-ttu-id="93712-106">你可以配置适配器以通过使用用于检索作为"0。 具有状态列的所有记录的 SQL 语句注册通知接收通知</span><span class="sxs-lookup"><span data-stu-id="93712-106">You can configure the adapter to receive notifications by registering for notifications using a SQL statement that retrieves all records that have Status column as “0.”</span></span> <span data-ttu-id="93712-107">您可以通过指定的 SQL 语句来实现**NotificationStatement**属性绑定。</span><span class="sxs-lookup"><span data-stu-id="93712-107">You can do so by specifying the SQL statement for the **NotificationStatement** binding property.</span></span> <span data-ttu-id="93712-108">适配器客户端收到通知后，它可以包含用于执行 SQL Server 数据库上的所有后续任务的逻辑。</span><span class="sxs-lookup"><span data-stu-id="93712-108">After the adapter client receives the notification, it can contain the logic to do any subsequent tasks on the SQL Server database.</span></span> <span data-ttu-id="93712-109">在此示例中，为简单起见，适配器客户端列出所有记录表中的将状态列设为"0。</span><span class="sxs-lookup"><span data-stu-id="93712-109">In this example, for the sake of simplicity, the adapter client lists all the records in the table that have the Status column as “0.”</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="93712-110">如果您正在执行对具有用户定义类型的列的表操作，请确保您参考[对表和视图的用户定义类型使用 SQL 适配器操作](../../adapters-and-accelerators/adapter-sql/operations-on-tables-and-views-with-user-defined-types-using-the-sql-adapter.md)主题之前开始开发应用程序.</span><span class="sxs-lookup"><span data-stu-id="93712-110">If you are performing operation on tables that have columns of user-defined types, make sure you refer to [Operations on tables and views with user-defined types using the SQL adapter](../../adapters-and-accelerators/adapter-sql/operations-on-tables-and-views-with-user-defined-types-using-the-sql-adapter.md) topic before you start developing your application.</span></span>  
  
## <a name="configuring-notifications-with-the-sql-adapter-binding-properties"></a><span data-ttu-id="93712-111">使用 SQL 适配器的绑定属性中配置通知</span><span class="sxs-lookup"><span data-stu-id="93712-111">Configuring Notifications with the SQL Adapter Binding Properties</span></span>  
 <span data-ttu-id="93712-112">下表总结了[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]绑定用于配置 SQL Server 从接收通知的属性。</span><span class="sxs-lookup"><span data-stu-id="93712-112">The following table summarizes the [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] binding properties that you use to configure receiving notifications from SQL Server.</span></span> <span data-ttu-id="93712-113">必须运行.NET 应用程序以从 SQL Server 数据库中接收通知时指定这些绑定属性。</span><span class="sxs-lookup"><span data-stu-id="93712-113">You must specify these binding properties while running the .NET application to receive the notifications from a SQL Server database.</span></span>  
  
|<span data-ttu-id="93712-114">绑定属性</span><span class="sxs-lookup"><span data-stu-id="93712-114">Binding Property</span></span>|<span data-ttu-id="93712-115">Description</span><span class="sxs-lookup"><span data-stu-id="93712-115">Description</span></span>|  
|----------------------|-----------------|  
|<span data-ttu-id="93712-116">**InboundOperationType**</span><span class="sxs-lookup"><span data-stu-id="93712-116">**InboundOperationType**</span></span>|<span data-ttu-id="93712-117">指定你想要执行的入站的操作。</span><span class="sxs-lookup"><span data-stu-id="93712-117">Specifies the inbound operation that you want to perform.</span></span> <span data-ttu-id="93712-118">若要接收通知消息，请将此设置为**通知**。</span><span class="sxs-lookup"><span data-stu-id="93712-118">To receive notification messages, set this to **Notification**.</span></span>|  
|<span data-ttu-id="93712-119">**NotificationStatement**</span><span class="sxs-lookup"><span data-stu-id="93712-119">**NotificationStatement**</span></span>|<span data-ttu-id="93712-120">指定的 SQL 语句 (SELECT 或 EXEC \<*存储过程*\>) 用于对查询通知注册。</span><span class="sxs-lookup"><span data-stu-id="93712-120">Specifies the SQL statement (SELECT or EXEC \<*stored procedure*\>) used to register for query notifications.</span></span> <span data-ttu-id="93712-121">仅当指定的 SQL 语句更改的结果集时，适配器从 SQL Server 获取通知消息。</span><span class="sxs-lookup"><span data-stu-id="93712-121">The adapter gets a notification message from SQL Server only when the result set for the specified SQL statement changes.</span></span>|  
|<span data-ttu-id="93712-122">**NotifyOnListenerStart**</span><span class="sxs-lookup"><span data-stu-id="93712-122">**NotifyOnListenerStart**</span></span>|<span data-ttu-id="93712-123">指定适配器是否启动侦听器时在向适配器客户端发送了通知。</span><span class="sxs-lookup"><span data-stu-id="93712-123">Specifies whether the adapter sends a notification to the adapter clients when the listener is started.</span></span>|  
  
 <span data-ttu-id="93712-124">有关这些属性的更完整说明，请参阅[了解关于 BizTalk Adapter for SQL Server 适配器绑定属性](../../adapters-and-accelerators/adapter-sql/read-about-the-biztalk-adapter-for-sql-server-adapter-binding-properties.md)。</span><span class="sxs-lookup"><span data-stu-id="93712-124">For a more complete description of these properties, see [Read about the BizTalk Adapter for SQL Server adapter binding properties](../../adapters-and-accelerators/adapter-sql/read-about-the-biztalk-adapter-for-sql-server-adapter-binding-properties.md).</span></span> <span data-ttu-id="93712-125">有关如何使用的完整说明[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]若要从 SQL Server 中接收通知，请阅读更多。</span><span class="sxs-lookup"><span data-stu-id="93712-125">For a complete description of how to use the [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] to receive notifications from SQL Server, read further.</span></span>  
  
## <a name="configuring-notifications-using-the-wcf-service-model"></a><span data-ttu-id="93712-126">配置通知使用 WCF 服务模型</span><span class="sxs-lookup"><span data-stu-id="93712-126">Configuring Notifications Using the WCF Service Model</span></span>  
 <span data-ttu-id="93712-127">若要接收的通知使用 WCF 服务模型，您必须：</span><span class="sxs-lookup"><span data-stu-id="93712-127">To receive the notifications using the WCF service model, you must:</span></span>  
  
1. <span data-ttu-id="93712-128">为生成的 WCF 服务协定 （接口）**通知**从由适配器公开的元数据的操作。</span><span class="sxs-lookup"><span data-stu-id="93712-128">Generate a WCF service contract (interface) for the **Notification** operation from the metadata exposed by the adapter.</span></span> <span data-ttu-id="93712-129">若要执行此操作，可以使用[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="93712-129">To do this, you could use the [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)].</span></span>  
  
2. <span data-ttu-id="93712-130">生成的 WCF 客户端**选择**Employee 表上的操作。</span><span class="sxs-lookup"><span data-stu-id="93712-130">Generate a WCF client for the **Select** operation on the Employee table.</span></span> <span data-ttu-id="93712-131">若要执行此操作，可以使用[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="93712-131">To do this, you could use the [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)].</span></span>  
  
3. <span data-ttu-id="93712-132">实现此接口中的 WCF 服务。</span><span class="sxs-lookup"><span data-stu-id="93712-132">Implement a WCF service from this interface.</span></span>  
  
4. <span data-ttu-id="93712-133">托管此 WCF 服务使用服务主机 (**System.ServiceModel.ServiceHost**)。</span><span class="sxs-lookup"><span data-stu-id="93712-133">Host this WCF service using a service host (**System.ServiceModel.ServiceHost**).</span></span>  
  
## <a name="about-the-examples-used-in-this-topic"></a><span data-ttu-id="93712-134">有关使用在本主题中的示例</span><span class="sxs-lookup"><span data-stu-id="93712-134">About the Examples Used in this Topic</span></span>  
 <span data-ttu-id="93712-135">本主题中的示例接收为 Employee 表的通知。</span><span class="sxs-lookup"><span data-stu-id="93712-135">The examples in this topic receive notification for the Employee table.</span></span> <span data-ttu-id="93712-136">这些示例提供了一个脚本来生成表。</span><span class="sxs-lookup"><span data-stu-id="93712-136">A script to generate the table is supplied with the samples.</span></span> <span data-ttu-id="93712-137">有关示例的详细信息，请参阅[适用于 SQL 适配器示例](../../adapters-and-accelerators/adapter-sql/samples-for-the-sql-adapter.md)。</span><span class="sxs-lookup"><span data-stu-id="93712-137">For more information about the samples, see [Samples for the SQL adapter](../../adapters-and-accelerators/adapter-sql/samples-for-the-sql-adapter.md).</span></span> <span data-ttu-id="93712-138">示例中， **Notification_ServiceModel**，后者基于本主题中，还提供与[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]示例。</span><span class="sxs-lookup"><span data-stu-id="93712-138">A sample, **Notification_ServiceModel**, which is based on this topic, is also provided with the [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] samples.</span></span>  
  
## <a name="the-wcf-service-contract-and-class"></a><span data-ttu-id="93712-139">WCF 服务约定和类</span><span class="sxs-lookup"><span data-stu-id="93712-139">The WCF Service Contract and Class</span></span>  
 <span data-ttu-id="93712-140">可以使用[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]若要创建 WCF 服务协定 （接口） 和支持类**通知**操作。</span><span class="sxs-lookup"><span data-stu-id="93712-140">You can use the [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)] to create a WCF service contract (interface) and supporting classes for the **Notification** operation.</span></span> <span data-ttu-id="93712-141">有关生成的 WCF 服务协定的详细信息，请参阅[为 SQL Server 项目生成 WCF 客户端或 WCF 服务约定](../../adapters-and-accelerators/adapter-sql/generate-a-wcf-client-or-wcf-service-contract-for-sql-server-artifacts.md)。</span><span class="sxs-lookup"><span data-stu-id="93712-141">For more information about generating a WCF service contract, see [Generate a WCF Client or WCF Service Contract for SQL Server Artifacts](../../adapters-and-accelerators/adapter-sql/generate-a-wcf-client-or-wcf-service-contract-for-sql-server-artifacts.md).</span></span>  
  
### <a name="the-wcf-service-contract-interface"></a><span data-ttu-id="93712-142">WCF 服务协定 （接口）</span><span class="sxs-lookup"><span data-stu-id="93712-142">The WCF Service Contract (Interface)</span></span>  
 <span data-ttu-id="93712-143">下面的代码演示 WCF 服务协定 （接口） 为生成**通知**操作。</span><span class="sxs-lookup"><span data-stu-id="93712-143">The following code shows the WCF service contract (interface) generated for the **Notification** operation.</span></span>  
  
```  
[System.CodeDom.Compiler.GeneratedCodeAttribute("System.ServiceModel", "3.0.0.0")]  
[System.ServiceModel.ServiceContractAttribute(Namespace="http://schemas.microsoft.com/Sql/2008/05/", ConfigurationName="NotificationOperation")]  
public interface NotificationOperation {  
  
    // CODEGEN: Generating message contract since the wrapper namespace (http://schemas.microsoft.com/Sql/2008/05/Notification/) of message  
    // Notification does not match the default value (http://schemas.microsoft.com/Sql/2008/05/)  
    [System.ServiceModel.OperationContractAttribute(IsOneWay=true, Action="Notification")]  
    void Notification(Notification request);  
}  
```  
  
### <a name="the-message-contracts"></a><span data-ttu-id="93712-144">消息协定</span><span class="sxs-lookup"><span data-stu-id="93712-144">The Message Contracts</span></span>  
 <span data-ttu-id="93712-145">下面是通知操作的消息约定。</span><span class="sxs-lookup"><span data-stu-id="93712-145">Following is the message contract for the Notification operation.</span></span>  
  
```  
[System.Diagnostics.DebuggerStepThroughAttribute()]  
[System.CodeDom.Compiler.GeneratedCodeAttribute("System.ServiceModel", "3.0.0.0")]  
[System.ServiceModel.MessageContractAttribute(WrapperName="Notification", WrapperNamespace="http://schemas.microsoft.com/Sql/2008/05/Notification/", IsWrapped=true)]  
public partial class Notification {  
  
    [System.ServiceModel.MessageBodyMemberAttribute(Namespace="http://schemas.microsoft.com/Sql/2008/05/Notification/", Order=0)]  
    public string Info;  
  
    [System.ServiceModel.MessageBodyMemberAttribute(Namespace="http://schemas.microsoft.com/Sql/2008/05/Notification/", Order=1)]  
    public string Source;  
  
    [System.ServiceModel.MessageBodyMemberAttribute(Namespace="http://schemas.microsoft.com/Sql/2008/05/Notification/", Order=2)]  
    public string Type;  
  
    public Notification() {  
    }  
  
    public Notification(string Info, string Source, string Type) {  
        this.Info = Info;  
        this.Source = Source;  
        this.Type = Type;  
    }  
}  
```  
  
### <a name="wcf-service-class"></a><span data-ttu-id="93712-146">WCF 服务类</span><span class="sxs-lookup"><span data-stu-id="93712-146">WCF Service Class</span></span>  
 <span data-ttu-id="93712-147">[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]还会生成一个具有实现服务协定 （接口） 中的 WCF 服务类的存根文件。</span><span class="sxs-lookup"><span data-stu-id="93712-147">The [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)] also generates a file that has a stub for the WCF service class implemented from the service contract (interface).</span></span> <span data-ttu-id="93712-148">文件的名称是 SqlAdapterBindingService.cs。</span><span class="sxs-lookup"><span data-stu-id="93712-148">The name of the file is SqlAdapterBindingService.cs.</span></span> <span data-ttu-id="93712-149">您可以将逻辑来处理**通知**直接在此类操作。</span><span class="sxs-lookup"><span data-stu-id="93712-149">You can insert the logic to process the **Notification** operation directly into this class.</span></span> <span data-ttu-id="93712-150">下面的代码演示生成的 WCF 服务类[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="93712-150">The following code shows the WCF service class generated by the [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)].</span></span>  
  
```  
namespace SqlAdapterBindingNamespace {  
  
    public class SqlAdapterBindingService : NotificationOperation {  
  
        // CODEGEN: Generating message contract since the wrapper namespace (http://schemas.microsoft.com/Sql/2008/05/Notification/)   
        // of message Notification does not match the default value (http://schemas.microsoft.com/Sql/2008/05/)  
        public virtual void Notification(Notification request) {  
            throw new System.NotImplementedException("The method or operation is not implemented.");  
        }  
    }  
}  
```  
  
## <a name="receiving-query-notifications-using-wcf-service-model"></a><span data-ttu-id="93712-151">使用 WCF 服务模型的接收查询通知</span><span class="sxs-lookup"><span data-stu-id="93712-151">Receiving Query Notifications Using WCF Service Model</span></span>  
 <span data-ttu-id="93712-152">本部分说明了如何编写.NET 应用程序以接收查询通知使用[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="93712-152">This section provides instructions on how to write a .NET application to receive query notifications using the [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)].</span></span>  
  
#### <a name="to-receive-query-notifications"></a><span data-ttu-id="93712-153">若要接收查询通知</span><span class="sxs-lookup"><span data-stu-id="93712-153">To receive query notifications</span></span>  
  
1. <span data-ttu-id="93712-154">使用[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]生成的 WCF 客户端**选择**上的操作**员工**表。</span><span class="sxs-lookup"><span data-stu-id="93712-154">Use the [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)] to generate a WCF client for **Select** operation on the **Employee** table.</span></span> <span data-ttu-id="93712-155">将使用此客户端收到通知消息后执行的 Select 操作。</span><span class="sxs-lookup"><span data-stu-id="93712-155">You will use this client to perform Select operations after receiving a notification message.</span></span> <span data-ttu-id="93712-156">添加新类，TableOperation.cs 到你的项目并添加下面的代码段，以执行选择操作。</span><span class="sxs-lookup"><span data-stu-id="93712-156">Add a new class, TableOperation.cs to your project and add the following code snippet to perform a Select operation.</span></span>  
  
   ```  
   using System;  
   using System.Collections.Generic;  
   using System.Linq;  
   using System.Text;  
  
   namespace Notification_ServiceModel  
   {  
       public class TableOperation  
       {  
           public void TableOp()  
           {  
               ///////////////////////////////////////////////////////////////////////  
               // CREATING THE CLIENT  
               ///////////////////////////////////////////////////////////////////////  
  
               TableOp_dbo_EmployeeClient client = new TableOp_dbo_EmployeeClient("SqlAdapterBinding_TableOp_dbo_Employee");  
  
               client.ClientCredentials.UserName.UserName = "<Enter user name here>";  
               client.ClientCredentials.UserName.Password = "<Enter password here>";  
  
               ///////////////////////////////////////////////////////////////////////  
               // OPENING THE CLIENT  
               ///////////////////////////////////////////////////////////////////////  
  
               try  
               {  
                   Console.WriteLine("Opening Client...");  
                   client.Open();  
               }  
               catch (Exception ex)  
               {  
                   Console.WriteLine("Exception: " + ex.Message);  
                   throw;  
               }  
  
               ///////////////////////////////////////////////////////////////////////  
               // SELECTING THE LAST INSERTED RECORD FROM THE TABLE  
               ///////////////////////////////////////////////////////////////////////  
               schemas.microsoft.com.Sql._2008._05.Types.Tables.dbo.Employee[] selectRecords;  
  
               try  
               {  
                   selectRecords = client.Select("*", "where Status=0");  
               }  
  
               catch (Exception ex)  
               {  
                   Console.WriteLine("Exception: " + ex.Message);  
                   throw;  
               }  
  
               Console.WriteLine("The details of the newly added employee are:");  
               Console.WriteLine("********************************************");  
               for (int i = 0; i < selectRecords.Length; i++)  
               {  
                   Console.WriteLine("Employee Name      : " + selectRecords[i].Name);  
                   Console.WriteLine("Employee Designation: " + selectRecords[i].Designation);  
                   Console.WriteLine("Employee Status    : " + selectRecords[i].Status);  
                   Console.WriteLine();  
               }  
               Console.WriteLine("********************************************");  
  
   ```  
  
   > [!IMPORTANT]
   >  <span data-ttu-id="93712-157">由于此代码片段执行 Employee 表包含 Point UDT 列上的操作，因此请确保将 UDT DLL 放在项目的 \bin\Debug 文件夹下运行应用程序时。</span><span class="sxs-lookup"><span data-stu-id="93712-157">Because this code snippet performs operations on the Employee table that contains a Point UDT column, make sure you put the UDT DLL under the project’s \bin\Debug folder while running the application.</span></span>  
  
2. <span data-ttu-id="93712-158">使用[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]生成的 WCF 服务协定 （接口） 和帮助器类实现**通知**操作。</span><span class="sxs-lookup"><span data-stu-id="93712-158">Use the [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)] to generate a WCF service contract (interface) and helper classes for the **Notification** operation.</span></span>  
  
    <span data-ttu-id="93712-159">有关详细信息，请参阅[为 SQL Server 项目生成 WCF 客户端或 WCF 服务约定](../../adapters-and-accelerators/adapter-sql/generate-a-wcf-client-or-wcf-service-contract-for-sql-server-artifacts.md)。</span><span class="sxs-lookup"><span data-stu-id="93712-159">For more information, see [Generate a WCF Client or WCF Service Contract for SQL Server Artifacts](../../adapters-and-accelerators/adapter-sql/generate-a-wcf-client-or-wcf-service-contract-for-sql-server-artifacts.md).</span></span> <span data-ttu-id="93712-160">在生成服务协定和帮助程序类时，可以选择指定的绑定属性。</span><span class="sxs-lookup"><span data-stu-id="93712-160">You can optionally specify the binding properties while generating the service contract and helper classes.</span></span> <span data-ttu-id="93712-161">这可确保它们正确设置生成的配置文件中。</span><span class="sxs-lookup"><span data-stu-id="93712-161">This guarantees that they are properly set in the generated configuration file.</span></span>  
  
3. <span data-ttu-id="93712-162">实现在步骤 2 中生成的接口和帮助程序类中的 WCF 服务。</span><span class="sxs-lookup"><span data-stu-id="93712-162">Implement a WCF service from the interface and helper classes generated in step 2.</span></span> <span data-ttu-id="93712-163">**通知**此类方法可以引发异常来中止操作，如果遇到错误，处理从接收的数据**通知**操作; 否则该方法执行不返回任何内容。</span><span class="sxs-lookup"><span data-stu-id="93712-163">The **Notification** method of this class can throw an exception to abort the operation, if an error is encountered processing the data received from the **Notification** operation; otherwise the method does not return anything.</span></span> <span data-ttu-id="93712-164">必须按如下所示属性的 WCF 服务类：</span><span class="sxs-lookup"><span data-stu-id="93712-164">You must attribute the WCF service class as follows:</span></span>  
  
   ```  
   [ServiceBehavior(InstanceContextMode = InstanceContextMode.Single)]  
   ```  
  
    <span data-ttu-id="93712-165">内**通知**方法，可以直接实现应用程序逻辑。</span><span class="sxs-lookup"><span data-stu-id="93712-165">Within the **Notification** method, you can implement your application logic directly.</span></span> <span data-ttu-id="93712-166">可以 SqlAdapterBindingService.cs 中找到此类。</span><span class="sxs-lookup"><span data-stu-id="93712-166">This class can be found in SqlAdapterBindingService.cs.</span></span> <span data-ttu-id="93712-167">此代码在此示例中的嵌套类**SqlAdapterBindingService**类。</span><span class="sxs-lookup"><span data-stu-id="93712-167">This code in this example sub-classes the **SqlAdapterBindingService** class.</span></span> <span data-ttu-id="93712-168">在此代码中，收到的通知消息写入控制台。</span><span class="sxs-lookup"><span data-stu-id="93712-168">In this code, the notification message received is written to the console.</span></span> <span data-ttu-id="93712-169">此外， **TableOp**方法内的**TableOperation**类调用以执行选择操作。</span><span class="sxs-lookup"><span data-stu-id="93712-169">Additionally, the **TableOp** method within the **TableOperation** class is invoked to perform the Select operation.</span></span>  
  
   ```  
   [ServiceBehavior(InstanceContextMode = InstanceContextMode.Single)]  
  
   public class NotificationService : SqlAdapterBindingNamespace.SqlAdapterBindingService  
   {  
       public override void Notification(Notification request)  
       {  
           Console.WriteLine("\nNew Notification Received");  
           Console.WriteLine("*************************************************");  
           Console.WriteLine(request.Info);  
           Console.WriteLine(request.Source);  
           Console.WriteLine(request.Type);  
           Console.WriteLine("*************************************************");  
  
           // Invoke th TableOp method in the TableOperation class  
           TableOperation Ops = new TableOperation();  
           Ops.TableOp();  
       }  
   }  
   ```  
  
4. <span data-ttu-id="93712-170">因为[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]不接受凭据的连接 URI 的一部分，必须实现以下类用于传递 SQL Server 数据库的凭据。</span><span class="sxs-lookup"><span data-stu-id="93712-170">Because the [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] does not accept credentials as part of the connection URI, you must implement the following class to pass credentials for the SQL Server database.</span></span> <span data-ttu-id="93712-171">在应用程序的后半部分，将实例化此类，以传递的 SQL Server 凭据。</span><span class="sxs-lookup"><span data-stu-id="93712-171">In the latter part of the application, you will instantiate this class to pass on the SQL Server credentials.</span></span>  
  
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
  
5. <span data-ttu-id="93712-172">创建**SqlAdapterBinding**并配置适配器后，若要通过指定的绑定属性接收查询通知。</span><span class="sxs-lookup"><span data-stu-id="93712-172">Create a **SqlAdapterBinding** and configure the adapter to receive query notifications by specifying the binding properties.</span></span> <span data-ttu-id="93712-173">可以在代码中显式或配置中以声明方式执行此操作。</span><span class="sxs-lookup"><span data-stu-id="93712-173">You can do this either explicitly in code or declaratively in configuration.</span></span> <span data-ttu-id="93712-174">至少，您必须指定**InboundOperationType**并**NotificationStatement**绑定属性。</span><span class="sxs-lookup"><span data-stu-id="93712-174">At a minimum, you must specify the **InboundOperationType** and **NotificationStatement** binding properties.</span></span>  
  
   ```  
   SqlAdapterBinding binding = new SqlAdapterBinding();  
   binding.InboundOperationType = InboundOperation.Notification;  
   binding.NotificationStatement = "SELECT Employee_ID, Name FROM dbo.Employee WHERE Status=0";  
   binding.NotifyOnListenerStart = true;  
   ```  
  
6. <span data-ttu-id="93712-175">通过实例化指定的 SQL Server 数据库凭据**NotificationCredentials**步骤 4 中创建的类。</span><span class="sxs-lookup"><span data-stu-id="93712-175">Specify SQL Server database credentials by instantiating the **NotificationCredentials** class you created in Step 4.</span></span>  
  
   ```  
   NotificationCredentials credentials = new NotificationCredentials();  
   credentials.UserName.UserName = "<Enter user name here>";  
   credentials.UserName.Password = "<Enter password here>";  
   ```  
  
7. <span data-ttu-id="93712-176">创建在步骤 3 中创建的 WCF 服务的实例。</span><span class="sxs-lookup"><span data-stu-id="93712-176">Create an instance of the WCF service created in step 3.</span></span>  
  
   ```  
   // create service instance  
   NotificationService service = new NotificationService();  
   ```  
  
8. <span data-ttu-id="93712-177">创建的实例**System.ServiceModel.ServiceHost**使用 WCF 服务和基本连接 URI。</span><span class="sxs-lookup"><span data-stu-id="93712-177">Create an instance of **System.ServiceModel.ServiceHost** by using the WCF service and a base connection URI.</span></span> <span data-ttu-id="93712-178">此外必须指定凭据。</span><span class="sxs-lookup"><span data-stu-id="93712-178">You must also specify the credentials here.</span></span>  
  
   ```  
   // Enable service host  
   Uri[] baseUri = new Uri[] { new Uri("mssql://mysqlserver//mydatabase") };  
   ServiceHost serviceHost = new ServiceHost(service, baseUri);  
   serviceHost.Description.Behaviors.Add(credentials);  
  
   ```  
  
9. <span data-ttu-id="93712-179">将服务终结点添加到服务主机。</span><span class="sxs-lookup"><span data-stu-id="93712-179">Add a service endpoint to the service host.</span></span> <span data-ttu-id="93712-180">若要执行此操作：</span><span class="sxs-lookup"><span data-stu-id="93712-180">To do this:</span></span>  
  
   - <span data-ttu-id="93712-181">使用在步骤 5 中创建的绑定。</span><span class="sxs-lookup"><span data-stu-id="93712-181">Use the binding created in step 5.</span></span>  
  
   - <span data-ttu-id="93712-182">指定连接 URI，其中包含的凭据，如果需要，入站 id。</span><span class="sxs-lookup"><span data-stu-id="93712-182">Specify a connection URI that contains credentials and, if required, an inbound ID.</span></span>  
  
   - <span data-ttu-id="93712-183">作为"NotificationOperation"指定的协定。</span><span class="sxs-lookup"><span data-stu-id="93712-183">Specify the contract as "NotificationOperation".</span></span>  
  
     ```  
     // Add service endpoint: be sure to specify NotificationOperation as the contract  
     Uri ConnectionUri = new Uri("mssql://mysqlserver//mydatabase?");  
     serviceHost.AddServiceEndpoint("NotificationOperation", binding, ConnectionUri);  
     ```  
  
10. <span data-ttu-id="93712-184">若要接收通知消息，请打开服务主机。</span><span class="sxs-lookup"><span data-stu-id="93712-184">To receive notification message, open the service host.</span></span>  
  
    ```  
    // Open the service host to begin receiving notifications  
    serviceHost.Open();  
    ```  
  
11. <span data-ttu-id="93712-185">若要停止接收通知，请关闭服务主机。</span><span class="sxs-lookup"><span data-stu-id="93712-185">To stop receiving notifications, close the service host.</span></span>  
  
    ```  
    serviceHost.Close();  
    ```  
  
### <a name="example"></a><span data-ttu-id="93712-186">示例</span><span class="sxs-lookup"><span data-stu-id="93712-186">Example</span></span>  
 <span data-ttu-id="93712-187">下面的示例显示了.NET 应用程序以接收通知消息为 Employee 表。</span><span class="sxs-lookup"><span data-stu-id="93712-187">The following example shows a .NET application to receive notification messages for the Employee table.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="93712-188">下面的代码段实例化**TableOperation.cs**类，并调用**TableOp**方法。</span><span class="sxs-lookup"><span data-stu-id="93712-188">The following code snippet instantiates a **TableOperation.cs** class and invokes the **TableOp** method.</span></span> <span data-ttu-id="93712-189">步骤 1 中描述类和方法。</span><span class="sxs-lookup"><span data-stu-id="93712-189">The class and the method are described in Step 1.</span></span>  
  
```  
using System;  
using System.Collections.Generic;  
using System.Linq;  
using System.Text;  
  
using Microsoft.Adapters.Sql;  
using Microsoft.ServiceModel.Channels;  
using System.ServiceModel;  
using System.ServiceModel.Description;  
using System.ServiceModel.Channels;  
using System.Collections.ObjectModel;  
  
namespace Notification_ServiceModel  
{  
    [ServiceBehavior(InstanceContextMode = InstanceContextMode.Single)]  
    public class NotificationService : SqlAdapterBindingNamespace.SqlAdapterBindingService  
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
                SqlAdapterBinding binding = new SqlAdapterBinding();  
                binding.InboundOperationType = InboundOperation.Notification;  
                binding.NotificationStatement = "SELECT Employee_ID, Name FROM dbo.Employee WHERE Status=0";  
                binding.NotifyOnListenerStart = true;  
  
                // This URI is used to specify the address for the ServiceEndpoint  
                // It must contain the InboundId (if any) that was used to generate  
                // the WCF service callback interface  
                Uri ConnectionUri = new Uri("mssql://mysqlserver//mydatabase?");  
  
                // This URI is used to initialize the ServiceHost. It cannot contain  
                // a query_string (InboundID); otherwise,an exception is thrown when  
                // the ServiceHost is initialized.  
                Uri[] baseUri = new Uri[] { new Uri("mssql://mysqlserver//mydatabase") };  
  
                NotificationCredentials credentials = new NotificationCredentials();  
                credentials.UserName.UserName = "<Enter user name here>";  
                credentials.UserName.Password = "<Enter password here>";  
  
                Console.WriteLine("Opening service host...");  
                NotificationService service = new NotificationService();  
                serviceHost = new ServiceHost(service, baseUri);  
                serviceHost.Description.Behaviors.Add(credentials);  
                serviceHost.AddServiceEndpoint("NotificationOperation", binding, ConnectionUri);  
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
  
                // If there is an error it will be specified in the inner exception   
                if (e.InnerException != null)  
                {  
                    Console.WriteLine("InnerException: " + e.InnerException.Message);  
                    Console.ReadLine();  
                }  
            }  
            finally  
            {  
                // IMPORTANT: you must close the ServiceHost to stop receiving notifications  
                if (serviceHost.State == CommunicationState.Opened)  
                    serviceHost.Close();  
                else  
                    serviceHost.Abort();  
            }  
        }  
    }  
}  
  
```  
  
## <a name="see-also"></a><span data-ttu-id="93712-190">请参阅</span><span class="sxs-lookup"><span data-stu-id="93712-190">See Also</span></span>  
[<span data-ttu-id="93712-191">开发 SQL 应用程序使用 WCF 服务模型</span><span class="sxs-lookup"><span data-stu-id="93712-191">Develop SQL applications using the WCF Service model</span></span>](../../adapters-and-accelerators/adapter-sql/develop-sql-applications-using-the-wcf-service-model.md)