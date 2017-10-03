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
# <a name="run-an-insert-operation-on-a-table-in-sql-using-the-wcf-channel-model"></a>运行 SQL 使用 WCF 通道模型中的表上的插入操作
[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]发现一组的 SQL Server 数据库表和视图的基本 Insert、 Select、 Update 和 Delete 操作。 通过使用这些操作，你可以执行简单的 SQL Insert、 Select、 Update 和 Delete 语句由 Where 限定目标表或视图上的子句。 本主题提供有关如何执行对使用 WCF 通道模型的 SQL Server 数据库表的插入操作的说明。  
  
 有关如何的适配器支持这些操作的详细信息，请参阅[插入、 更新、 删除和选择操作对表和视图与 SQL 适配器](../../adapters-and-accelerators/adapter-sql/insert-update-delete-and-select-on-tables-and-views-with-the-sql-adapter.md)。 有关如何在使用 WCF 通道模型的 SQL Server 上执行操作的详细信息，请参阅[与 SQL 适配器的 WCF 通道模型概述](../../adapters-and-accelerators/adapter-sql/overview-of-the-wcf-channel-model-with-the-sql-adapter.md)。  
  
## <a name="about-the-examples-used-in-this-topic"></a>有关在本主题中使用的示例  
 本主题中的示例对执行操作员工表。 员工表是通过运行这些示例使用提供的 SQL 脚本创建的。 有关示例的详细信息，请参阅[SQL 适配器的示例](../../adapters-and-accelerators/adapter-sql/samples-for-the-sql-adapter.md)。 示例中， **EmployeeInsertOp**，后者基于本主题中，还提供了与[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]示例。  
  
## <a name="the-insert-message"></a>插入消息  
 若要对使用 WCF 通道模型的 SQL Server 数据库执行操作，你必须使用特定于操作的请求消息。 要在 SQL Server 数据库中执行对员工表的插入操作的请求消息如下所示：  
  
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
  
 此请求消息将插入以下详细信息的记录：  
  
```  
Name = Tom Smith  
Designation = Manager  
Salary = 500000  
```  
  
 必须将消息复制到一个文件，例如 InsertRequest.xml。 此文件使用在此示例中，将请求消息发送到 SQL Server 使用[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]。 有关对表操作的消息架构的详细信息，请参阅[插入、 更新、 删除和选择表和视图上的操作的消息架构](../../adapters-and-accelerators/adapter-sql/message-schemas-for-insert-update-delete-and-select-on-tables-and-views.md)。  
  
## <a name="creating-a-wcf-channel-application"></a>创建 WCF 通道应用程序  
 本部分提供有关如何创建一个 WCF 通道应用程序来执行对员工表的插入操作的说明。  
  
#### <a name="to-create-a-wcf-channel-application-for-inserting-records-into-the-employee-table"></a>若要创建的 WCF 通道应用程序将记录插入到员工表  
  
1.  在 Visual Studio 中创建 Visual C# 项目。 有关本主题中，创建一个控制台应用程序。  
  
2.  在解决方案资源管理器，添加对引用`Microsoft.Adapters.Sql`， `Microsoft.ServiceModel.Channels`， `System.ServiceModel`，和`System.Runtime.Serialization`。  
  
3.  打开 Program.cs 文件并添加以下命名空间：  
  
    -   `Microsoft.Adapters.Sql`  
  
    -   `Microsoft.ServiceModel.Channels`  
  
    -   `System.ServiceModel`  
  
    -   `System.ServiceModel.Channels`  
  
    -   `System.Xml`  
  
4.  创建绑定和终结点。  
  
    ```  
    SqlAdapterBinding binding = new SqlAdapterBinding();  
    EndpointAddress address = new EndpointAddress("mssql://mysqlserver//mydatabase?");  
  
    ```  
  
5.  创建并打开通道工厂。 此应用程序将请求消息发送到 SQL Server，并收到响应，因此必须实现 IRequestChannel 接口。  
  
    ```  
    ChannelFactory<IRequestChannel> factory = new ChannelFactory<IRequestChannel>(binding, address);  
    factory.Credentials.UserName.UserName = "<Enter user name here>";  
    factory.Credentials.UserName.Password = "<Enter password here>";  
    factory.Open();  
    ```  
  
6.  创建并打开通道。  
  
    ```  
    IRequestChannel channel = factory.CreateChannel();  
    channel.Open();  
    ```  
  
7.  创建和发送的请求消息。  
  
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
  
     在创建请求消息时，必须指定，该值指示适配器执行 SQL Server 表的操作的消息操作。 若要执行对员工表的插入操作，则消息操作是`TableOp/Insert/dbo/Employee`。 有关如何确定对表的各种操作的消息操作的信息，请参阅[插入、 更新、 删除和选择表和视图上的操作的消息架构](../../adapters-and-accelerators/adapter-sql/message-schemas-for-insert-update-delete-and-select-on-tables-and-views.md)。  
  
8.  获取响应消息。  
  
    ```  
    XmlReader readerOut = messageOut.GetReaderAtBodyContents();  
    XmlDocument doc = new XmlDocument();  
    doc.Load(readerOut);  
    doc.Save("C:\\Response.xml");  
    ```  
  
9. 关闭消息、 通道和通道工厂。  
  
    ```  
    messageOut.Close();  
    channel.Close();  
    factory.Close();  
    ```  
  
10. 生成此项目。 生成项目时后, 必须执行以下任务：  
  
    -   将复制请求消息，InsertRequest.xml，与你的项目可执行文件所在的位置。 通常，此位置是项目目录下的 \bin\Debug\。  
  
    -   此示例中使用"员工"表具有点用户定义类型 (UDT) 的列。 因此之前运行该项目，您必须创建用户定义的点类型的程序集中所述[创建用户定义类型](https://docs.microsoft.com/sql/relational-databases/clr-integration-database-objects-user-defined-types/creating-user-defined-types)。 你还必须将复制的程序集 DLL 为可执行项目所在的位置。 通常，此位置是项目目录下的 \bin\Debug\。  
  
11. 运行该应用程序。 响应消息，Response.xml，保存应用程序中指定的位置。 响应消息包含新添加的员工的 ID，如下所示：  
  
    ```  
    <InsertResponse xmlns="http://schemas.microsoft.com/Sql/2008/05/TableOp/dbo/Employee">  
      <InsertResult>  
        <long xmlns="http://schemas.microsoft.com/2003/10/Serialization/Arrays">10006</long>  
      </InsertResult>  
    </InsertResponse>  
    ```  
  
     由于员工表具有标识列的 Employee_ID 列，插入操作将返回新插入的记录的标识列的值。 如果表中没有标识列，返回值为 NULL。  
  
## <a name="see-also"></a>另请参阅  
[开发 SQL 应用程序使用 WCF 通道模型](../../adapters-and-accelerators/adapter-sql/develop-sql-applications-using-the-wcf-channel-model.md)