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
# <a name="run-an-insert-operation-on-a-table-in-sql-using-the-wcf-channel-model"></a>在 SQL 中使用 WCF 通道模型运行上一个表的插入操作
[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]发现一组基本的 Insert、 Select、 Update 和 Delete 操作上 SQL Server 数据库表和视图。 通过使用这些操作，你可以执行简单 SQL Insert、 Select、 Update 和 Delete 语句限定由 Where 子句对目标表或视图。 本主题将说明了如何执行插入操作上使用 WCF 通道模型的 SQL Server 数据库表。  
  
 适配器如何支持这些操作的详细信息，请参阅[Insert、 Update、 Delete 和选择操作对表和视图与 SQL 适配器](../../adapters-and-accelerators/adapter-sql/insert-update-delete-and-select-on-tables-and-views-with-the-sql-adapter.md)。 有关如何使用 WCF 通道模型的 SQL 服务器上执行操作的详细信息，请参阅[与 SQL 适配器的 WCF 通道模型概述](../../adapters-and-accelerators/adapter-sql/overview-of-the-wcf-channel-model-with-the-sql-adapter.md)。  
  
## <a name="about-the-examples-used-in-this-topic"></a>有关使用在本主题中的示例  
 本主题中的示例执行在 Employee 表上的操作。 通过运行这些示例提供的 SQL 脚本创建员工表。 有关示例的详细信息，请参阅[适用于 SQL 适配器示例](../../adapters-and-accelerators/adapter-sql/samples-for-the-sql-adapter.md)。 示例中， **EmployeeInsertOp**，后者基于本主题中，还提供与[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]示例。  
  
## <a name="the-insert-message"></a>插入消息  
 若要对使用 WCF 通道模型的 SQL Server 数据库执行操作，必须具有特定于操作的请求消息。 要在 SQL Server 数据库中执行插入操作的 Employee 表上的请求消息类似于以下内容：  
  
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
  
 必须将该消息复制到一个文件，例如 InsertRequest.xml。 此文件使用在此示例中，若要将请求消息发送到 SQL Server 使用[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]。 有关对表的操作的消息架构的详细信息，请参阅[Insert、 Update、 Delete 和对表和视图的选择操作的消息架构](../../adapters-and-accelerators/adapter-sql/message-schemas-for-insert-update-delete-and-select-on-tables-and-views.md)。  
  
## <a name="creating-a-wcf-channel-application"></a>创建 WCF 通道应用程序  
 本部分将说明了如何创建 WCF 通道应用程序，以执行插入操作上的 Employee 表。  
  
#### <a name="to-create-a-wcf-channel-application-for-inserting-records-into-the-employee-table"></a>若要创建的 WCF 通道应用程序将记录插入到 Employee 表  
  
1.  在 Visual Studio 中创建一个 Visual C# 项目。 有关本主题中，创建一个控制台应用程序。  
  
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
  
5.  创建并打开通道工厂。 此应用程序将请求消息发送到 SQL Server 并接收响应，因此您必须实现 IRequestChannel 接口。  
  
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
  
7.  创建并发送请求消息。  
  
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
  
     在创建请求消息时，必须指定指示对 SQL Server 表适配器执行的操作的消息操作。 若要执行的 Employee 表插入操作，消息操作是`TableOp/Insert/dbo/Employee`。 有关如何确定对表进行各种操作的消息操作的信息，请参阅[Insert、 Update、 Delete 和对表和视图的选择操作的消息架构](../../adapters-and-accelerators/adapter-sql/message-schemas-for-insert-update-delete-and-select-on-tables-and-views.md)。  
  
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
  
10. 生成项目。 后生成项目时，必须执行以下任务：  
  
    -   将复制的请求消息，InsertRequest.xml，与可执行项目所在的位置。 通常情况下，此位置为 \bin\Debug\ 项目目录下。  
  
    -   在此示例中使用的"Employee"表包含一个点用户定义类型 (UDT)。 因此，然后再运行该项目，您必须创建 Point udt 程序集中所述[创建用户定义类型](https://docs.microsoft.com/sql/relational-databases/clr-integration-database-objects-user-defined-types/creating-user-defined-types)。 此外必须将复制程序集 DLL 与可执行项目在同一位置。 通常情况下，此位置为 \bin\Debug\ 项目目录下。  
  
11. 运行应用程序。 响应消息，Response.xml，保存在应用程序中指定的位置。 响应消息包含新添加的员工的 ID，如下所示：  
  
    ```  
    <InsertResponse xmlns="http://schemas.microsoft.com/Sql/2008/05/TableOp/dbo/Employee">  
      <InsertResult>  
        <long xmlns="http://schemas.microsoft.com/2003/10/Serialization/Arrays">10006</long>  
      </InsertResult>  
    </InsertResponse>  
    ```  
  
     因为 Employee 表具有标识列作为 Employee_ID 列，插入操作将返回新插入记录的标识列的值。 如果在表中没有标识列，返回值为 NULL。  
  
## <a name="see-also"></a>请参阅  
[开发 SQL 应用程序使用 WCF 通道模型](../../adapters-and-accelerators/adapter-sql/develop-sql-applications-using-the-wcf-channel-model.md)