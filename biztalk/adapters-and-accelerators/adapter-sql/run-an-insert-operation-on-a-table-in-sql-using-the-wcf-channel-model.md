---
title: "运行 SQL 使用 WCF 通道模型中的表上的插入操作 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 3df95d78-3a9c-48c0-81ab-1f3206c5e3f7
caps.latest.revision: "7"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 7bceb236b660b80c1e46cb0410d799d994516c40
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="run-an-insert-operation-on-a-table-in-sql-using-the-wcf-channel-model"></a><span data-ttu-id="54ae4-102">运行 SQL 使用 WCF 通道模型中的表上的插入操作</span><span class="sxs-lookup"><span data-stu-id="54ae4-102">Run an Insert Operation on a Table in SQL using the WCF Channel Model</span></span>
<span data-ttu-id="54ae4-103">[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]发现一组的 SQL Server 数据库表和视图的基本 Insert、 Select、 Update 和 Delete 操作。</span><span class="sxs-lookup"><span data-stu-id="54ae4-103">The [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] discovers a set of basic Insert, Select, Update, and Delete operations on SQL Server database tables and views.</span></span> <span data-ttu-id="54ae4-104">通过使用这些操作，你可以执行简单的 SQL Insert、 Select、 Update 和 Delete 语句由 Where 限定目标表或视图上的子句。</span><span class="sxs-lookup"><span data-stu-id="54ae4-104">By using these operations, you can perform simple SQL Insert, Select, Update, and Delete statements qualified by a Where clause on a target table or view.</span></span> <span data-ttu-id="54ae4-105">本主题提供有关如何执行对使用 WCF 通道模型的 SQL Server 数据库表的插入操作的说明。</span><span class="sxs-lookup"><span data-stu-id="54ae4-105">This topic provides instructions on how to perform an Insert operation on a SQL Server database table using the WCF channel model.</span></span>  
  
 <span data-ttu-id="54ae4-106">有关如何的适配器支持这些操作的详细信息，请参阅[插入、 更新、 删除和选择操作对表和视图与 SQL 适配器](../../adapters-and-accelerators/adapter-sql/insert-update-delete-and-select-on-tables-and-views-with-the-sql-adapter.md)。</span><span class="sxs-lookup"><span data-stu-id="54ae4-106">For more information on how the adapter supports these operations, see [Insert, Update, Delete, and Select Operations on Tables and Views with the SQL adapter](../../adapters-and-accelerators/adapter-sql/insert-update-delete-and-select-on-tables-and-views-with-the-sql-adapter.md).</span></span> <span data-ttu-id="54ae4-107">有关如何在使用 WCF 通道模型的 SQL Server 上执行操作的详细信息，请参阅[与 SQL 适配器的 WCF 通道模型概述](../../adapters-and-accelerators/adapter-sql/overview-of-the-wcf-channel-model-with-the-sql-adapter.md)。</span><span class="sxs-lookup"><span data-stu-id="54ae4-107">For more information about how to perform operations on SQL Server using the WCF Channel model, see [Overview of the WCF channel model with the SQL adapter](../../adapters-and-accelerators/adapter-sql/overview-of-the-wcf-channel-model-with-the-sql-adapter.md).</span></span>  
  
## <a name="about-the-examples-used-in-this-topic"></a><span data-ttu-id="54ae4-108">有关在本主题中使用的示例</span><span class="sxs-lookup"><span data-stu-id="54ae4-108">About the Examples Used in this Topic</span></span>  
 <span data-ttu-id="54ae4-109">本主题中的示例对执行操作员工表。</span><span class="sxs-lookup"><span data-stu-id="54ae4-109">The example in this topic performs operations on the Employee table.</span></span> <span data-ttu-id="54ae4-110">员工表是通过运行这些示例使用提供的 SQL 脚本创建的。</span><span class="sxs-lookup"><span data-stu-id="54ae4-110">The Employee table is created by running the SQL script provided with the samples.</span></span> <span data-ttu-id="54ae4-111">有关示例的详细信息，请参阅[SQL 适配器的示例](../../adapters-and-accelerators/adapter-sql/samples-for-the-sql-adapter.md)。</span><span class="sxs-lookup"><span data-stu-id="54ae4-111">For more information about samples, see [Samples for the SQL adapter](../../adapters-and-accelerators/adapter-sql/samples-for-the-sql-adapter.md).</span></span> <span data-ttu-id="54ae4-112">示例中， **EmployeeInsertOp**，后者基于本主题中，还提供了与[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]示例。</span><span class="sxs-lookup"><span data-stu-id="54ae4-112">A sample, **EmployeeInsertOp**, which is based on this topic, is also provided with the [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] samples.</span></span>  
  
## <a name="the-insert-message"></a><span data-ttu-id="54ae4-113">插入消息</span><span class="sxs-lookup"><span data-stu-id="54ae4-113">The Insert Message</span></span>  
 <span data-ttu-id="54ae4-114">若要对使用 WCF 通道模型的 SQL Server 数据库执行操作，你必须使用特定于操作的请求消息。</span><span class="sxs-lookup"><span data-stu-id="54ae4-114">To perform operations on the SQL Server database using the WCF channel model, you must have the request message specific to the operation.</span></span> <span data-ttu-id="54ae4-115">要在 SQL Server 数据库中执行对员工表的插入操作的请求消息如下所示：</span><span class="sxs-lookup"><span data-stu-id="54ae4-115">The request message to perform an Insert operation on the Employee table in the SQL Server database resembles the following:</span></span>  
  
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
  
 <span data-ttu-id="54ae4-116">此请求消息将插入以下详细信息的记录：</span><span class="sxs-lookup"><span data-stu-id="54ae4-116">This request message inserts a record with following details:</span></span>  
  
```  
Name = Tom Smith  
Designation = Manager  
Salary = 500000  
```  
  
 <span data-ttu-id="54ae4-117">必须将消息复制到一个文件，例如 InsertRequest.xml。</span><span class="sxs-lookup"><span data-stu-id="54ae4-117">You must copy the message to a file, e.g. InsertRequest.xml.</span></span> <span data-ttu-id="54ae4-118">此文件使用在此示例中，将请求消息发送到 SQL Server 使用[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="54ae4-118">This file is used in this example to send the request message to SQL Server using the [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)].</span></span> <span data-ttu-id="54ae4-119">有关对表操作的消息架构的详细信息，请参阅[插入、 更新、 删除和选择表和视图上的操作的消息架构](../../adapters-and-accelerators/adapter-sql/message-schemas-for-insert-update-delete-and-select-on-tables-and-views.md)。</span><span class="sxs-lookup"><span data-stu-id="54ae4-119">For more information about the message schema for operations on table, see [Message Schemas for Insert, Update, Delete, and Select Operations on Tables and Views](../../adapters-and-accelerators/adapter-sql/message-schemas-for-insert-update-delete-and-select-on-tables-and-views.md).</span></span>  
  
## <a name="creating-a-wcf-channel-application"></a><span data-ttu-id="54ae4-120">创建 WCF 通道应用程序</span><span class="sxs-lookup"><span data-stu-id="54ae4-120">Creating a WCF Channel Application</span></span>  
 <span data-ttu-id="54ae4-121">本部分提供有关如何创建一个 WCF 通道应用程序来执行对员工表的插入操作的说明。</span><span class="sxs-lookup"><span data-stu-id="54ae4-121">This section provides instructions on how to create a WCF channel application to perform an Insert operation on the Employee table.</span></span>  
  
#### <a name="to-create-a-wcf-channel-application-for-inserting-records-into-the-employee-table"></a><span data-ttu-id="54ae4-122">若要创建的 WCF 通道应用程序将记录插入到员工表</span><span class="sxs-lookup"><span data-stu-id="54ae4-122">To create a WCF channel application for inserting records into the Employee table</span></span>  
  
1.  <span data-ttu-id="54ae4-123">在 Visual Studio 中创建 Visual C# 项目。</span><span class="sxs-lookup"><span data-stu-id="54ae4-123">Create a Visual C# project in Visual Studio.</span></span> <span data-ttu-id="54ae4-124">有关本主题中，创建一个控制台应用程序。</span><span class="sxs-lookup"><span data-stu-id="54ae4-124">For this topic, create a console application.</span></span>  
  
2.  <span data-ttu-id="54ae4-125">在解决方案资源管理器，添加对引用`Microsoft.Adapters.Sql`， `Microsoft.ServiceModel.Channels`， `System.ServiceModel`，和`System.Runtime.Serialization`。</span><span class="sxs-lookup"><span data-stu-id="54ae4-125">In the Solution Explorer, add reference to `Microsoft.Adapters.Sql`, `Microsoft.ServiceModel.Channels`, `System.ServiceModel`, and `System.Runtime.Serialization`.</span></span>  
  
3.  <span data-ttu-id="54ae4-126">打开 Program.cs 文件并添加以下命名空间：</span><span class="sxs-lookup"><span data-stu-id="54ae4-126">Open the Program.cs file and add the following namespaces:</span></span>  
  
    -   `Microsoft.Adapters.Sql`  
  
    -   `Microsoft.ServiceModel.Channels`  
  
    -   `System.ServiceModel`  
  
    -   `System.ServiceModel.Channels`  
  
    -   `System.Xml`  
  
4.  <span data-ttu-id="54ae4-127">创建绑定和终结点。</span><span class="sxs-lookup"><span data-stu-id="54ae4-127">Create the binding and endpoint.</span></span>  
  
    ```  
    SqlAdapterBinding binding = new SqlAdapterBinding();  
    EndpointAddress address = new EndpointAddress("mssql://mysqlserver//mydatabase?");  
  
    ```  
  
5.  <span data-ttu-id="54ae4-128">创建并打开通道工厂。</span><span class="sxs-lookup"><span data-stu-id="54ae4-128">Create and open the channel factory.</span></span> <span data-ttu-id="54ae4-129">此应用程序将请求消息发送到 SQL Server，并收到响应，因此必须实现 IRequestChannel 接口。</span><span class="sxs-lookup"><span data-stu-id="54ae4-129">This application sends request message to SQL Server and receives a response, hence you must implement the IRequestChannel interface.</span></span>  
  
    ```  
    ChannelFactory<IRequestChannel> factory = new ChannelFactory<IRequestChannel>(binding, address);  
    factory.Credentials.UserName.UserName = "<Enter user name here>";  
    factory.Credentials.UserName.Password = "<Enter password here>";  
    factory.Open();  
    ```  
  
6.  <span data-ttu-id="54ae4-130">创建并打开通道。</span><span class="sxs-lookup"><span data-stu-id="54ae4-130">Create and open the channel.</span></span>  
  
    ```  
    IRequestChannel channel = factory.CreateChannel();  
    channel.Open();  
    ```  
  
7.  <span data-ttu-id="54ae4-131">创建和发送的请求消息。</span><span class="sxs-lookup"><span data-stu-id="54ae4-131">Create and send the request message.</span></span>  
  
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
  
     <span data-ttu-id="54ae4-132">在创建请求消息时，必须指定，该值指示适配器执行 SQL Server 表的操作的消息操作。</span><span class="sxs-lookup"><span data-stu-id="54ae4-132">While creating the request message, you must specify the message action that indicates the action that the adapter performs on the SQL Server table.</span></span> <span data-ttu-id="54ae4-133">若要执行对员工表的插入操作，则消息操作是`TableOp/Insert/dbo/Employee`。</span><span class="sxs-lookup"><span data-stu-id="54ae4-133">To perform an Insert operation on the Employee table, the message action is `TableOp/Insert/dbo/Employee`.</span></span> <span data-ttu-id="54ae4-134">有关如何确定对表的各种操作的消息操作的信息，请参阅[插入、 更新、 删除和选择表和视图上的操作的消息架构](../../adapters-and-accelerators/adapter-sql/message-schemas-for-insert-update-delete-and-select-on-tables-and-views.md)。</span><span class="sxs-lookup"><span data-stu-id="54ae4-134">For information about how you can determine the message action for various operations on tables, see [Message Schemas for Insert, Update, Delete, and Select Operations on Tables and Views](../../adapters-and-accelerators/adapter-sql/message-schemas-for-insert-update-delete-and-select-on-tables-and-views.md).</span></span>  
  
8.  <span data-ttu-id="54ae4-135">获取响应消息。</span><span class="sxs-lookup"><span data-stu-id="54ae4-135">Get the response message.</span></span>  
  
    ```  
    XmlReader readerOut = messageOut.GetReaderAtBodyContents();  
    XmlDocument doc = new XmlDocument();  
    doc.Load(readerOut);  
    doc.Save("C:\\Response.xml");  
    ```  
  
9. <span data-ttu-id="54ae4-136">关闭消息、 通道和通道工厂。</span><span class="sxs-lookup"><span data-stu-id="54ae4-136">Close the message, channel, and channel factory.</span></span>  
  
    ```  
    messageOut.Close();  
    channel.Close();  
    factory.Close();  
    ```  
  
10. <span data-ttu-id="54ae4-137">生成此项目。</span><span class="sxs-lookup"><span data-stu-id="54ae4-137">Build the project.</span></span> <span data-ttu-id="54ae4-138">生成项目时后, 必须执行以下任务：</span><span class="sxs-lookup"><span data-stu-id="54ae4-138">After building the project, you must perform the following tasks:</span></span>  
  
    -   <span data-ttu-id="54ae4-139">将复制请求消息，InsertRequest.xml，与你的项目可执行文件所在的位置。</span><span class="sxs-lookup"><span data-stu-id="54ae4-139">Copy the request message, InsertRequest.xml, at the same location as your project executable.</span></span> <span data-ttu-id="54ae4-140">通常，此位置是项目目录下的 \bin\Debug\。</span><span class="sxs-lookup"><span data-stu-id="54ae4-140">Typically, this location is \bin\Debug\ under your project directory.</span></span>  
  
    -   <span data-ttu-id="54ae4-141">此示例中使用"员工"表具有点用户定义类型 (UDT) 的列。</span><span class="sxs-lookup"><span data-stu-id="54ae4-141">The "Employee" table used in this example has a column of Point user-defined type (UDT).</span></span> <span data-ttu-id="54ae4-142">因此之前运行该项目，您必须创建用户定义的点类型的程序集中所述[创建用户定义类型](https://docs.microsoft.com/sql/relational-databases/clr-integration-database-objects-user-defined-types/creating-user-defined-types)。</span><span class="sxs-lookup"><span data-stu-id="54ae4-142">So, before running the project, you must create the assembly for the Point UDT as described at [Creating User-Defined Types](https://docs.microsoft.com/sql/relational-databases/clr-integration-database-objects-user-defined-types/creating-user-defined-types).</span></span> <span data-ttu-id="54ae4-143">你还必须将复制的程序集 DLL 为可执行项目所在的位置。</span><span class="sxs-lookup"><span data-stu-id="54ae4-143">You must also copy the assembly DLL at the same location as the project executable.</span></span> <span data-ttu-id="54ae4-144">通常，此位置是项目目录下的 \bin\Debug\。</span><span class="sxs-lookup"><span data-stu-id="54ae4-144">Typically, this location is \bin\Debug\ under your project directory.</span></span>  
  
11. <span data-ttu-id="54ae4-145">运行该应用程序。</span><span class="sxs-lookup"><span data-stu-id="54ae4-145">Run the application.</span></span> <span data-ttu-id="54ae4-146">响应消息，Response.xml，保存应用程序中指定的位置。</span><span class="sxs-lookup"><span data-stu-id="54ae4-146">The response message, Response.xml, is saved at the location you specified in the application.</span></span> <span data-ttu-id="54ae4-147">响应消息包含新添加的员工的 ID，如下所示：</span><span class="sxs-lookup"><span data-stu-id="54ae4-147">The response message contains the ID of the newly added employee and resembles the following:</span></span>  
  
    ```  
    <InsertResponse xmlns="http://schemas.microsoft.com/Sql/2008/05/TableOp/dbo/Employee">  
      <InsertResult>  
        <long xmlns="http://schemas.microsoft.com/2003/10/Serialization/Arrays">10006</long>  
      </InsertResult>  
    </InsertResponse>  
    ```  
  
     <span data-ttu-id="54ae4-148">由于员工表具有标识列的 Employee_ID 列，插入操作将返回新插入的记录的标识列的值。</span><span class="sxs-lookup"><span data-stu-id="54ae4-148">Because the Employee table has the Employee_ID column as the identity column, the Insert operation returns the value for the identity column of the newly inserted record.</span></span> <span data-ttu-id="54ae4-149">如果表中没有标识列，返回值为 NULL。</span><span class="sxs-lookup"><span data-stu-id="54ae4-149">If there is no identity column in a table, the return value is NULL.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="54ae4-150">另请参阅</span><span class="sxs-lookup"><span data-stu-id="54ae4-150">See Also</span></span>  
[<span data-ttu-id="54ae4-151">开发 SQL 应用程序使用 WCF 通道模型</span><span class="sxs-lookup"><span data-stu-id="54ae4-151">Develop SQL applications using the WCF Channel Model</span></span>](../../adapters-and-accelerators/adapter-sql/develop-sql-applications-using-the-wcf-channel-model.md)