---
title: 在上运行操作表和视图使用 SQL 使用 WCF 服务模型中的大型数据类型 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 7d33e17c-e09e-4a57-9acc-43095e67ed8c
caps.latest.revision: 14
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 1da0def828c1dbfa8511dc61b529fa02cb53ca5a
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/28/2017
ms.locfileid: "25967123"
---
# <a name="run-operations-on-tables-and-views-with-large-data-types-in-sql-using-the-wcf-service-model"></a>在上运行操作表和视图使用 SQL 使用 WCF 服务模型中的大型数据类型
[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]使适配器客户端读取和更新的大型数据类型列中的数据，它是、 varchar （max）、 nvarchar 或 varbinary （max）。 若要从这类列读取数据，适配器客户端可以使用选择的操作。 若要插入或更新到此类列的数据，该适配器都公开一组\<*column_name* \>操作，其中\< *column_name* \>是的名称类型 varchar （max）、 nvarchar 或 varbinary （max） 列。  
  
 此外，在 SQL Server 中，你可以存储非结构化的数据，例如文本文档和图像的 varbinay(max) 列。 此类非结构化的数据称为 FILESTREAM 数据。 FILESTREAM 数据可以存储为文件系统上的文件。 [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]使客户端 FILESTREAM 数据输入到类型 varbinary （max） 列。 [FILESTREAM 存储](https://docs.microsoft.com/sql/relational-databases/blob/filestream-sql-server)提供了更多信息。 
  
 本主题提供必须执行某些任务有关的信息的计算机上运行 SQL Server 和运行适配器客户端将无法插入或更新 FILESTREAM 数据的计算机。 本主题还说明了执行组\<*column_name* \>操作插入 FILESTREAM 数据。  
  
> [!NOTE]
>  如果您正在执行包含的用户定义类型的列的表上的操作，请确保您参考[对表和视图使用了 SQL 适配器的用户定义类型的操作](../../adapters-and-accelerators/adapter-sql/operations-on-tables-and-views-with-user-defined-types-using-the-sql-adapter.md)。  
  
## <a name="prerequisites"></a>先决条件  
 在运行 SQL Server 的计算机和运行适配器客户端的计算机上，必须执行以下任务。  
  
-   **运行 SQL Server 的计算机上**  
  
    -   你必须在 SQL Server 实例上启用 FILESTREAM。 请参阅[启用和配置 FILESTREAM](https://docs.microsoft.com/sql/relational-databases/blob/enable-and-configure-filestream)。
  
    -   你必须创建启用 FILESTREAM 的数据库。 请参阅[创建启用 FILESTREAM 的数据库](https://docs.microsoft.com/sql/relational-databases/blob/create-a-filestream-enabled-database)。
  
    -   你必须有一个表以存储 FILESTREAM 数据。 请参阅[创建表以存储 FILESTREAM 数据](https://docs.microsoft.com/sql/relational-databases/blob/create-a-table-for-storing-filestream-data)，
  
-   **运行适配器客户端的计算机上**  
  
    -   你必须安装的 SQL 客户端连接 SDK。 你可以通过运行 SQL Server 安装程序并选择安装 SQL 客户端连接 SDK **SQL 客户端连接 SDK**中**功能选择**向导页。 适配器使用 sqlncli10.dll，安装 SQL 客户端连接 SDK，与执行 FILESTREAM 操作。  
  
 完成这些任务后，你将插入或更新 SQL Server 数据库表中的 FILESTREAM 数据。  
  
## <a name="how-this-topic-demonstrates-operations-on-large-data-types"></a>本主题演示对大型数据类型执行操作的方式  
 若要演示如何执行集\<*column_name* \>对表较大的数据类型的操作需要一个表，**记录**，具有列**Id**和**文档**:  
  
-   **记录**通过运行这些示例使用提供的 SQL 脚本创建表，并且所有数据。 有关详细信息，请参阅[适配器示例](../../adapters-and-accelerators/accelerator-rosettanet/adapter-samples.md)。  
  
-   **Id**列是 uniqueidentifier 类型，采用 GUID。 假定**Id**列已有一个 GUID`438B7B4C-5491-409F-BCC1-78817C399EC3`。  
  
-   **文档**列属于类型 varbinary （max）。 若要更新**文档**列中，适配器公开**SetDocument**操作。  
  
> [!NOTE]
>  对于 SQL Server，为了演示 FILESTREAM 操作，假定**文档**列可以存储 FILESTREAM 数据。  
  
## <a name="about-the-examples-used-in-this-topic"></a>有关在本主题中使用的示例  
 本主题中的示例执行操作**记录**表。 **记录**通过运行这些示例使用提供的 SQL 脚本创建表。 有关示例的详细信息，请参阅[适配器示例](../../adapters-and-accelerators/accelerator-rosettanet/adapter-samples.md)。 示例中， **Records_FILESTREAM_Op**，后者基于本主题中，还提供了与[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]示例。  
  
## <a name="the-wcf-client-class"></a>WCF 客户端类  
 为对大型数据的操作生成 WCF 客户端的名称类型[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]发现，基于名称的表或视图，如以下表中列出。  
  
|SQL Server 数据库项目|WCF 客户端名称|  
|----------------------------------|---------------------|  
|表|TableOp_ [架构] _ [TABLE_NAME] 客户端|  
|视图|ViewOp_ [架构] _ [VIEW_NAME] 客户端|  
  
 [架构] = SQL Server 集合项目;例如，dbo。  
  
### <a name="method-signature-for-invoking-operations-on-columns-of-large-data-types"></a>调用在较大的数据类型的列上的操作的方法签名  
 下表显示对表的基本操作的方法签名。 签名是相同的视图，只不过视图命名空间和名称替换那些表。  
  
|运算|方法签名|  
|---------------|----------------------|  
|设置\<*column_name*\>|公共 void 集\<*column_name*\>（字符串筛选器，byte [] 数据）;|  
  
 \<*column_name* \> = 较大的数据类型的列的名称。  
  
 例如，下面的代码演示方法签名，用于生成 WCF 客户端类**SetDocument**操作**记录**下的默认"dbo"架构的表。  
  
```  
public partial class TableOp_dbo_RecordsClient : System.ServiceModel.ClientBase<TableOp_dbo_Records>, TableOp_dbo_Records {      
    public void SetDocument (string Filter, byte[] Data);  
}  
```  
  
 在此代码段， **TableOp_dbo_RecordsClient**是 WCF 中的类的生成的 SqlAdapterBindingClient.cs 名称[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]。  
  
### <a name="parameters-for-operations-on-columns-of-large-data-types"></a>较大的数据类型的列上的操作的参数  
 本部分提供了通过一组所需的参数\<*column_name* \>操作。  
  
|参数名称|Description|  
|--------------------|-----------------|  
|字符串筛选器|指定 WHERE 子句基于适配器在其上更新的记录大的数据类型的列。|  
|byte [] 数据|指定必须更新为较大的数据类型的列的值。|  
  
 集\<*column_name* \>操作不返回任何值。  
  
## <a name="creating-a-wcf-client-to-invoke-operations-on-columns-of-large-data-types"></a>创建 WCF 客户端以调用较大的数据类型的列上的操作  
 泛型的执行 SQL Server 使用 WCF 客户端上的操作所需的操作集涉及到一组任务中所述[与 SQL 适配器的 WCF 服务模型概述](../../adapters-and-accelerators/adapter-sql/overview-of-the-wcf-service-model-with-the-sql-adapter.md)。 本部分介绍如何创建 WCF 客户端来调用**SetDocument**操作**记录**表。 适配器公开**SetDocument**操作，以更新中的较大的数据类型的列的数据。  
  
#### <a name="to-create-a-wcf-client"></a>若要创建 WCF 客户端  
  
1.  在 Visual Studio 中创建 Visual C# 项目。 有关本主题中，创建一个控制台应用程序。  
  
2.  生成的 WCF 客户端类**SetDocument**操作**记录**表。 有关生成 WCF 客户端类的详细信息，请参阅[为 SQL Server 项目生成 WCF 客户端或 WCF 服务协定](../../adapters-and-accelerators/adapter-sql/generate-a-wcf-client-or-wcf-service-contract-for-sql-server-artifacts.md)。  
  
3.  在解决方案资源管理器，添加对引用`Microsoft.Adapters.Sql`， `Microsoft.ServiceModel.Channels`，和`System.Transactions`。  
  
4.  打开 Program.cs 文件并添加`System.Transactions`命名空间。  
  
5.  在 Program.cs 中，如下面的代码段中所述创建客户端。  
  
    ```  
  
              TableOp_dbo_RecordsClient client = new TableOp_dbo_RecordsClient("SqlAdapterBinding_TableOp_dbo_Records");  
    client.ClientCredentials.UserName.UserName = "";  
    client.ClientCredentials.UserName.Password = "";  
  
    ```  
  
     在此代码段，`TableOp_dbo_RecordsClient`是 SqlAdapterBindingClient.cs 中定义的 WCF 客户端。 此文件由生成[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]。 `SqlAdapterBinding_TableOp_dbo_Records`是客户端终结点配置的名称，并在 app.config 中定义。此文件也会生成由[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]，其中包含的绑定属性和其他配置设置。  
  
    > [!CAUTION]
    >  若要对 FILESTREAM 数据执行操作，必须始终连接到 SQL Server 使用 Windows 身份验证。 若要使用 Windows 身份验证进行连接，必须提供有空的用户名和密码，如前面的代码段中所示。 此外，在使用 Windows 身份验证连接到 SQL Server，你必须已执行的步骤中所述[连接到 SQL Server 使用 Windows 身份验证与 SQL 适配器](../../adapters-and-accelerators/adapter-sql/connect-to-sql-server-using-windows-authentication-with-the-sql-adapter.md)。  
  
    > [!NOTE]
    >  在此代码段中，你使用的绑定和终结点地址从配置文件。 你还可显式指定这些值在代码中。 指定客户端绑定的不同方法的详细信息，请参阅[为该 SQL 适配器配置客户端绑定](../../adapters-and-accelerators/adapter-sql/configure-a-client-binding-for-the-sql-adapter.md)。  
  
6.  下面的代码段中所述，请打开客户端：  
  
    ```  
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
    ```  
  
7.  调用**SetDocument**操作**记录**表。  
  
    > [!CAUTION]
    >  集 *< column_name >* 必须始终在事务中执行操作。 若要确保此操作，请集 *< column_name >* 必须在事务范围内调用操作和**UseAmbientTransaction**绑定属性必须设置为**true**app.config 中。  
  
    ```  
    using (TransactionScope tx = new TransactionScope())  
    {  
        string filter = "WHERE Id='438B7B4C-5491-409F-BCC1-78817C399EC3'";  
        byte[] data = ASCIIEncoding.ASCII.GetBytes("Sample data");  
        client.SetDocument(filter, data);  
        tx.Complete();  
    }  
    ```  
  
     在这里，应用程序将字符串"示例数据"转换为 base64 编码的字符串，并满足筛选条件的记录中对其进行更新。  
  
8.  关闭客户端，如下面的代码段中所述：  
  
    ```  
    client.Close();  
    Console.WriteLine("Press any key to exit...");  
    Console.ReadLine();  
    ```  
  
9. 生成项目，然后运行它。 应用程序更新**文档**中的列**记录**表。  
  
## <a name="see-also"></a>另请参阅  
[使用 WCF 服务模型开发应用程序](../../adapters-and-accelerators/adapter-sql/develop-sql-applications-using-the-wcf-service-model.md)