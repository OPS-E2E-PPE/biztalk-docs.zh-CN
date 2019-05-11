---
title: 在 SQL 中使用 WCF 通道模型运行上一个表的插入操作 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 3df95d78-3a9c-48c0-81ab-1f3206c5e3f7
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 0be345ab33e12068b9b5eb52fd75c65ff15361be
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65367984"
---
# <a name="run-an-insert-operation-on-a-table-in-sql-using-the-wcf-channel-model"></a><span data-ttu-id="5e23b-102">在 SQL 中使用 WCF 通道模型运行上一个表的插入操作</span><span class="sxs-lookup"><span data-stu-id="5e23b-102">Run an Insert Operation on a Table in SQL using the WCF Channel Model</span></span>
<span data-ttu-id="5e23b-103">[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]发现一组基本的 Insert、 Select、 Update 和 Delete 操作上 SQL Server 数据库表和视图。</span><span class="sxs-lookup"><span data-stu-id="5e23b-103">The [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] discovers a set of basic Insert, Select, Update, and Delete operations on SQL Server database tables and views.</span></span> <span data-ttu-id="5e23b-104">通过使用这些操作，你可以执行简单 SQL Insert、 Select、 Update 和 Delete 语句限定由 Where 子句对目标表或视图。</span><span class="sxs-lookup"><span data-stu-id="5e23b-104">By using these operations, you can perform simple SQL Insert, Select, Update, and Delete statements qualified by a Where clause on a target table or view.</span></span> <span data-ttu-id="5e23b-105">本主题将说明了如何执行插入操作上使用 WCF 通道模型的 SQL Server 数据库表。</span><span class="sxs-lookup"><span data-stu-id="5e23b-105">This topic provides instructions on how to perform an Insert operation on a SQL Server database table using the WCF channel model.</span></span>  
  
 <span data-ttu-id="5e23b-106">适配器如何支持这些操作的详细信息，请参阅[Insert、 Update、 Delete 和选择操作对表和视图与 SQL 适配器](../../adapters-and-accelerators/adapter-sql/insert-update-delete-and-select-on-tables-and-views-with-the-sql-adapter.md)。</span><span class="sxs-lookup"><span data-stu-id="5e23b-106">For more information on how the adapter supports these operations, see [Insert, Update, Delete, and Select Operations on Tables and Views with the SQL adapter](../../adapters-and-accelerators/adapter-sql/insert-update-delete-and-select-on-tables-and-views-with-the-sql-adapter.md).</span></span> <span data-ttu-id="5e23b-107">有关如何使用 WCF 通道模型的 SQL 服务器上执行操作的详细信息，请参阅[与 SQL 适配器的 WCF 通道模型概述](../../adapters-and-accelerators/adapter-sql/overview-of-the-wcf-channel-model-with-the-sql-adapter.md)。</span><span class="sxs-lookup"><span data-stu-id="5e23b-107">For more information about how to perform operations on SQL Server using the WCF Channel model, see [Overview of the WCF channel model with the SQL adapter](../../adapters-and-accelerators/adapter-sql/overview-of-the-wcf-channel-model-with-the-sql-adapter.md).</span></span>  
  
## <a name="about-the-examples-used-in-this-topic"></a><span data-ttu-id="5e23b-108">有关使用在本主题中的示例</span><span class="sxs-lookup"><span data-stu-id="5e23b-108">About the Examples Used in this Topic</span></span>  
 <span data-ttu-id="5e23b-109">本主题中的示例执行在 Employee 表上的操作。</span><span class="sxs-lookup"><span data-stu-id="5e23b-109">The example in this topic performs operations on the Employee table.</span></span> <span data-ttu-id="5e23b-110">通过运行这些示例提供的 SQL 脚本创建员工表。</span><span class="sxs-lookup"><span data-stu-id="5e23b-110">The Employee table is created by running the SQL script provided with the samples.</span></span> <span data-ttu-id="5e23b-111">有关示例的详细信息，请参阅[适用于 SQL 适配器示例](../../adapters-and-accelerators/adapter-sql/samples-for-the-sql-adapter.md)。</span><span class="sxs-lookup"><span data-stu-id="5e23b-111">For more information about samples, see [Samples for the SQL adapter](../../adapters-and-accelerators/adapter-sql/samples-for-the-sql-adapter.md).</span></span> <span data-ttu-id="5e23b-112">示例中， **EmployeeInsertOp**，后者基于本主题中，还提供与[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]示例。</span><span class="sxs-lookup"><span data-stu-id="5e23b-112">A sample, **EmployeeInsertOp**, which is based on this topic, is also provided with the [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] samples.</span></span>  
  
## <a name="the-insert-message"></a><span data-ttu-id="5e23b-113">插入消息</span><span class="sxs-lookup"><span data-stu-id="5e23b-113">The Insert Message</span></span>  
 <span data-ttu-id="5e23b-114">若要对使用 WCF 通道模型的 SQL Server 数据库执行操作，必须具有特定于操作的请求消息。</span><span class="sxs-lookup"><span data-stu-id="5e23b-114">To perform operations on the SQL Server database using the WCF channel model, you must have the request message specific to the operation.</span></span> <span data-ttu-id="5e23b-115">要在 SQL Server 数据库中执行插入操作的 Employee 表上的请求消息类似于以下内容：</span><span class="sxs-lookup"><span data-stu-id="5e23b-115">The request message to perform an Insert operation on the Employee table in the SQL Server database resembles the following:</span></span>  
  
```  
<Insert xmlns="http://schemas.microsoft.com/Sql/2008/05/TableOp/dbo/Employee">  
  <Rows>  
    <Employee xmlns="http://schemas.microsoft.com/Sql/2008/05/Types/Tables/dbo">  
      <Name>Tom Smith</Name>  
      <Designation>Manager</Designation>  
      <Salary>500000</Salary>  
   </Employee>  
  </Rows>  
</Insert>  
```  
  
 <span data-ttu-id="5e23b-116">此请求消息将插入以下详细信息的记录：</span><span class="sxs-lookup"><span data-stu-id="5e23b-116">This request message inserts a record with following details:</span></span>  
  
```  
Name = Tom Smith  
Designation = Manager  
Salary = 500000  
```  
  
 <span data-ttu-id="5e23b-117">必须将该消息复制到一个文件，例如 InsertRequest.xml。</span><span class="sxs-lookup"><span data-stu-id="5e23b-117">You must copy the message to a file, e.g. InsertRequest.xml.</span></span> <span data-ttu-id="5e23b-118">此文件使用在此示例中，若要将请求消息发送到 SQL Server 使用[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="5e23b-118">This file is used in this example to send the request message to SQL Server using the [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)].</span></span> <span data-ttu-id="5e23b-119">有关对表的操作的消息架构的详细信息，请参阅[Insert、 Update、 Delete 和对表和视图的选择操作的消息架构](../../adapters-and-accelerators/adapter-sql/message-schemas-for-insert-update-delete-and-select-on-tables-and-views.md)。</span><span class="sxs-lookup"><span data-stu-id="5e23b-119">For more information about the message schema for operations on table, see [Message Schemas for Insert, Update, Delete, and Select Operations on Tables and Views](../../adapters-and-accelerators/adapter-sql/message-schemas-for-insert-update-delete-and-select-on-tables-and-views.md).</span></span>  
  
## <a name="creating-a-wcf-channel-application"></a><span data-ttu-id="5e23b-120">创建 WCF 通道应用程序</span><span class="sxs-lookup"><span data-stu-id="5e23b-120">Creating a WCF Channel Application</span></span>  
 <span data-ttu-id="5e23b-121">本部分将说明了如何创建 WCF 通道应用程序，以执行插入操作上的 Employee 表。</span><span class="sxs-lookup"><span data-stu-id="5e23b-121">This section provides instructions on how to create a WCF channel application to perform an Insert operation on the Employee table.</span></span>  
  
#### <a name="to-create-a-wcf-channel-application-for-inserting-records-into-the-employee-table"></a><span data-ttu-id="5e23b-122">若要创建的 WCF 通道应用程序将记录插入到 Employee 表</span><span class="sxs-lookup"><span data-stu-id="5e23b-122">To create a WCF channel application for inserting records into the Employee table</span></span>  
  
1.  <span data-ttu-id="5e23b-123">在 Visual Studio 中创建一个 Visual C# 项目。</span><span class="sxs-lookup"><span data-stu-id="5e23b-123">Create a Visual C# project in Visual Studio.</span></span> <span data-ttu-id="5e23b-124">有关本主题中，创建一个控制台应用程序。</span><span class="sxs-lookup"><span data-stu-id="5e23b-124">For this topic, create a console application.</span></span>  
  
2.  <span data-ttu-id="5e23b-125">在解决方案资源管理器，添加对引用`Microsoft.Adapters.Sql`， `Microsoft.ServiceModel.Channels`， `System.ServiceModel`，和`System.Runtime.Serialization`。</span><span class="sxs-lookup"><span data-stu-id="5e23b-125">In the Solution Explorer, add reference to `Microsoft.Adapters.Sql`, `Microsoft.ServiceModel.Channels`, `System.ServiceModel`, and `System.Runtime.Serialization`.</span></span>  
  
3.  <span data-ttu-id="5e23b-126">打开 Program.cs 文件并添加以下命名空间：</span><span class="sxs-lookup"><span data-stu-id="5e23b-126">Open the Program.cs file and add the following namespaces:</span></span>  
  
    -   `Microsoft.Adapters.Sql`  
  
    -   `Microsoft.ServiceModel.Channels`  
  
    -   `System.ServiceModel`  
  
    -   `System.ServiceModel.Channels`  
  
    -   `System.Xml`  
  
4.  <span data-ttu-id="5e23b-127">创建绑定和终结点。</span><span class="sxs-lookup"><span data-stu-id="5e23b-127">Create the binding and endpoint.</span></span>  
  
    ```  
    SqlAdapterBinding binding = new SqlAdapterBinding();  
    EndpointAddress address = new EndpointAddress("mssql://mysqlserver//mydatabase?");  
  
    ```  
  
5.  <span data-ttu-id="5e23b-128">创建并打开通道工厂。</span><span class="sxs-lookup"><span data-stu-id="5e23b-128">Create and open the channel factory.</span></span> <span data-ttu-id="5e23b-129">此应用程序将请求消息发送到 SQL Server 并接收响应，因此您必须实现 IRequestChannel 接口。</span><span class="sxs-lookup"><span data-stu-id="5e23b-129">This application sends request message to SQL Server and receives a response, hence you must implement the IRequestChannel interface.</span></span>  
  
    ```  
    ChannelFactory<IRequestChannel> factory = new ChannelFactory<IRequestChannel>(binding, address);  
    factory.Credentials.UserName.UserName = "<Enter user name here>";  
    factory.Credentials.UserName.Password = "<Enter password here>";  
    factory.Open();  
    ```  
  
6.  <span data-ttu-id="5e23b-130">创建并打开通道。</span><span class="sxs-lookup"><span data-stu-id="5e23b-130">Create and open the channel.</span></span>  
  
    ```  
    IRequestChannel channel = factory.CreateChannel();  
    channel.Open();  
    ```  
  
7.  <span data-ttu-id="5e23b-131">创建并发送请求消息。</span><span class="sxs-lookup"><span data-stu-id="5e23b-131">Create and send the request message.</span></span>  
  
    ```  
    XmlReader readerIn;  
    Console.WriteLine("Creating the message");  
    try  
    {  
       readerIn = XmlReader.Create("InsertRequest.xml");  
       Console.WriteLine("Reader created");  
    }  
    catch (Exception ex)  
    {  
       Console.WriteLine("Exception: " + ex.Message);  
       throw;  
    }  
    Message messageIn = Message.CreateMessage(MessageVersion.Default, "TableOp/Insert/dbo/Employee", readerIn);  
    Message messageOut = channel.Request(messageIn);  
  
    ```  
  
     <span data-ttu-id="5e23b-132">在创建请求消息时，必须指定指示对 SQL Server 表适配器执行的操作的消息操作。</span><span class="sxs-lookup"><span data-stu-id="5e23b-132">While creating the request message, you must specify the message action that indicates the action that the adapter performs on the SQL Server table.</span></span> <span data-ttu-id="5e23b-133">若要执行的 Employee 表插入操作，消息操作是`TableOp/Insert/dbo/Employee`。</span><span class="sxs-lookup"><span data-stu-id="5e23b-133">To perform an Insert operation on the Employee table, the message action is `TableOp/Insert/dbo/Employee`.</span></span> <span data-ttu-id="5e23b-134">有关如何确定对表进行各种操作的消息操作的信息，请参阅[Insert、 Update、 Delete 和对表和视图的选择操作的消息架构](../../adapters-and-accelerators/adapter-sql/message-schemas-for-insert-update-delete-and-select-on-tables-and-views.md)。</span><span class="sxs-lookup"><span data-stu-id="5e23b-134">For information about how you can determine the message action for various operations on tables, see [Message Schemas for Insert, Update, Delete, and Select Operations on Tables and Views](../../adapters-and-accelerators/adapter-sql/message-schemas-for-insert-update-delete-and-select-on-tables-and-views.md).</span></span>  
  
8.  <span data-ttu-id="5e23b-135">获取响应消息。</span><span class="sxs-lookup"><span data-stu-id="5e23b-135">Get the response message.</span></span>  
  
    ```  
    XmlReader readerOut = messageOut.GetReaderAtBodyContents();  
    XmlDocument doc = new XmlDocument();  
    doc.Load(readerOut);  
    doc.Save("C:\\Response.xml");  
    ```  
  
9. <span data-ttu-id="5e23b-136">关闭消息、 通道和通道工厂。</span><span class="sxs-lookup"><span data-stu-id="5e23b-136">Close the message, channel, and channel factory.</span></span>  
  
    ```  
    messageOut.Close();  
    channel.Close();  
    factory.Close();  
    ```  
  
10. <span data-ttu-id="5e23b-137">生成项目。</span><span class="sxs-lookup"><span data-stu-id="5e23b-137">Build the project.</span></span> <span data-ttu-id="5e23b-138">后生成项目时，必须执行以下任务：</span><span class="sxs-lookup"><span data-stu-id="5e23b-138">After building the project, you must perform the following tasks:</span></span>  
  
    -   <span data-ttu-id="5e23b-139">将复制的请求消息，InsertRequest.xml，与可执行项目所在的位置。</span><span class="sxs-lookup"><span data-stu-id="5e23b-139">Copy the request message, InsertRequest.xml, at the same location as your project executable.</span></span> <span data-ttu-id="5e23b-140">通常情况下，此位置为 \bin\Debug\ 项目目录下。</span><span class="sxs-lookup"><span data-stu-id="5e23b-140">Typically, this location is \bin\Debug\ under your project directory.</span></span>  
  
    -   <span data-ttu-id="5e23b-141">在此示例中使用的"Employee"表包含一个点用户定义类型 (UDT)。</span><span class="sxs-lookup"><span data-stu-id="5e23b-141">The "Employee" table used in this example has a column of Point user-defined type (UDT).</span></span> <span data-ttu-id="5e23b-142">因此，然后再运行该项目，您必须创建 Point udt 程序集中所述[创建用户定义类型](https://docs.microsoft.com/sql/relational-databases/clr-integration-database-objects-user-defined-types/creating-user-defined-types)。</span><span class="sxs-lookup"><span data-stu-id="5e23b-142">So, before running the project, you must create the assembly for the Point UDT as described at [Creating User-Defined Types](https://docs.microsoft.com/sql/relational-databases/clr-integration-database-objects-user-defined-types/creating-user-defined-types).</span></span> <span data-ttu-id="5e23b-143">此外必须将复制程序集 DLL 与可执行项目在同一位置。</span><span class="sxs-lookup"><span data-stu-id="5e23b-143">You must also copy the assembly DLL at the same location as the project executable.</span></span> <span data-ttu-id="5e23b-144">通常情况下，此位置为 \bin\Debug\ 项目目录下。</span><span class="sxs-lookup"><span data-stu-id="5e23b-144">Typically, this location is \bin\Debug\ under your project directory.</span></span>  
  
11. <span data-ttu-id="5e23b-145">运行应用程序。</span><span class="sxs-lookup"><span data-stu-id="5e23b-145">Run the application.</span></span> <span data-ttu-id="5e23b-146">响应消息，Response.xml，保存在应用程序中指定的位置。</span><span class="sxs-lookup"><span data-stu-id="5e23b-146">The response message, Response.xml, is saved at the location you specified in the application.</span></span> <span data-ttu-id="5e23b-147">响应消息包含新添加的员工的 ID，如下所示：</span><span class="sxs-lookup"><span data-stu-id="5e23b-147">The response message contains the ID of the newly added employee and resembles the following:</span></span>  
  
    ```  
    <InsertResponse xmlns="http://schemas.microsoft.com/Sql/2008/05/TableOp/dbo/Employee">  
      <InsertResult>  
        <long xmlns="http://schemas.microsoft.com/2003/10/Serialization/Arrays">10006</long>  
      </InsertResult>  
    </InsertResponse>  
    ```  
  
     <span data-ttu-id="5e23b-148">因为 Employee 表具有标识列作为 Employee_ID 列，插入操作将返回新插入记录的标识列的值。</span><span class="sxs-lookup"><span data-stu-id="5e23b-148">Because the Employee table has the Employee_ID column as the identity column, the Insert operation returns the value for the identity column of the newly inserted record.</span></span> <span data-ttu-id="5e23b-149">如果在表中没有标识列，返回值为 NULL。</span><span class="sxs-lookup"><span data-stu-id="5e23b-149">If there is no identity column in a table, the return value is NULL.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5e23b-150">请参阅</span><span class="sxs-lookup"><span data-stu-id="5e23b-150">See Also</span></span>  
[<span data-ttu-id="5e23b-151">开发 SQL 应用程序使用 WCF 通道模型</span><span class="sxs-lookup"><span data-stu-id="5e23b-151">Develop SQL applications using the WCF Channel Model</span></span>](../../adapters-and-accelerators/adapter-sql/develop-sql-applications-using-the-wcf-channel-model.md)