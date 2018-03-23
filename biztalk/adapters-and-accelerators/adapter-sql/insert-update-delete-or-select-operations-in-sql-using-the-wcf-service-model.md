---
title: 插入、 更新、 删除或选择中使用 WCF 服务模型的 SQL 操作 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 340048ad-ce28-4acf-ae4e-f18bdb3b6f47
caps.latest.revision: ''
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: d2bc522a1b0b60a9ba0b8407228dd1db65c4e6f0
ms.sourcegitcommit: 8418b1a8f38b7f56979cd6e203f0b591e2f40fe1
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/23/2018
---
# <a name="insert-update-delete-or-select-operations-in-sql-using-the-wcf-service-model"></a>插入、 更新、 删除或选择中使用 WCF 服务模型的 SQL 操作
[!INCLUDE[adaptersql](../../includes/adaptersql-md.md)]发现一组的 SQL Server 数据库表和视图的基本 Insert、 Select、 Update 和 Delete 操作。 通过使用这些操作，你可以执行简单的 SQL Insert、 Select、 Update 和 Delete 语句由 Where 限定目标表或视图上的子句。 本主题将说明了如何使用 WCF 服务模型执行这些操作。  
  
 有关如何的适配器支持这些操作的详细信息，请参阅[插入、 更新、 删除和选择操作对表和视图与 SQL 适配器](../../adapters-and-accelerators/adapter-sql/insert-update-delete-and-select-on-tables-and-views-with-the-sql-adapter.md)。  
  
> [!NOTE]
>  如果您正在执行包含的用户定义类型的列的表上的操作，请确保您参考[对表和视图使用了 SQL 适配器的用户定义类型的操作](../../adapters-and-accelerators/adapter-sql/operations-on-tables-and-views-with-user-defined-types-using-the-sql-adapter.md)开始开发你的应用程序之前。  
  
## <a name="about-the-examples-used-in-this-topic"></a>有关在本主题中使用的示例  
 本主题中的示例对执行操作员工表。 员工表是通过运行这些示例使用提供的 SQL 脚本创建的。 有关示例的详细信息，请参阅[适配器示例](../../adapters-and-accelerators/accelerator-rosettanet/adapter-samples.md)。 示例中， **EmployeeBasicOps**，后者基于本主题中，还提供了与[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]示例。  
  
## <a name="the-wcf-client-class"></a>WCF 客户端类  
 WCF 客户端生成的基本 SQL 操作的名称，[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]发现基于名称的表或视图，如以下表中列出。  
  
|SQL Server 数据库项目|WCF 客户端名称|  
|----------------------------------|---------------------|  
|表|TableOp_[Schema]_[TABLE_NAME]Client|  
|视图|ViewOp_[Schema]_[VIEW_NAME]Client|  
  
 [架构] = SQL Server 集合项目;例如，dbo。  
  
 [TABLE_NAME] = 表; 的名称例如，员工。  
  
 [VIEW_NAME] = 视图; 的名称例如，Employee_View。  
  
### <a name="method-signature-for-invoking-operations-on-tables"></a>调用对表的操作的方法签名  
 下表显示对表的基本操作的方法签名。 签名是相同的视图，只不过视图命名空间和名称替换那些表。  
  
|运算|方法签名|  
|---------------|----------------------|  
|Insert|long[] Insert([TABLE_NS].[TABLE_NAME][] Rows);|  
|选择|[TABLE_NS].[TABLE_NAME][] Select(string COLUMNS, string QUERY);|  
|Update|int Update([TABLE_NS].[TABLE_NAME].RowPair[] Rows);|  
|删除|int Delete([TABLE_NS].[TABLE_NAME][] Rows);|  
  
 [TABLE_NS] = 表命名空间; 的名称例如，schemas.microsoft.com.Sql._2008._05.Types.Tables.dbo.Employee。  
  
 [TABLE_NAME] = 表; 的名称例如，员工。  
  
 例如，下面的代码演示生成的默认"dbo"架构下的员工表上的删除、 插入、 选择和更新操作的 WCF 客户端类的方法签名。  
  
```  
public partial class TableOp_dbo_EmployeeClient : System.ServiceModel.ClientBase<TableOp_dbo_Employee>, TableOp_dbo_Employee {      
    public int Delete(schemas.microsoft.com.Sql._2008._05.Types.Tables.dbo.Employee[] Rows);  
  
    public long[] Insert(schemas.microsoft.com.Sql._2008._05.Types.Tables.dbo.Employee[] Rows);  
  
    public schemas.microsoft.com.Sql._2008._05.Types.Tables.dbo.Employee[] Select(string Columns, string Query);  
  
    public int Update(schemas.microsoft.com.Sql._2008._05.TableOp.dbo.Employee.RowPair[] Rows);  
}  
```  
  
 在此代码段，TableOp_dbo_EmployeeClient 是 WCF 中的类的生成的 SqlAdapterBindingClient.cs 名称[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]。  
  
### <a name="parameters-for-table-operations"></a>参数用于表操作  
 本部分提供每个表操作所需的参数  
  
 **插入操作**  
  
|插入操作类型|记录集|  
|---------------------------|---------------|  
|多个记录|应插入到表的 INSERTRECORDS 的集合。|  
  
 插入操作返回的长整型数据类型的数组，并将存储插入的行中，标识值，如果有的话。 如果表中没有标识列，返回值为 NULL。  
  
 **选择操作**  
  
|COLUMN_NAMES|QUERY|  
|-------------------|-----------|  
|以逗号分隔的目标; 中的列名称列表例如，"Employee_ID，指定内容"。 列列表指定应在结果集中返回目标的列。 未指定列列表中的列将设置为其.NET 默认值中返回的记录集。 对于 nillable 列，此值是**null**。|指定的查询; 的目标行的 SQL WHERE 子句的内容例如，"指定内容 = '经理'"。 你可以将此参数设置为**null**返回目标的所有行。|  
  
 选择操作的返回值是一个强类型化结果集包含指定的列和目标表或视图中的行。  
  
 **更新操作**  
  
|对的第一行|第二行对|  
|---------------------------|----------------------------|  
|对对应于需要可更新的新值的记录的第一个记录，即它对应于 UPDATE 语句的 SET 子句。 可以使用设置这`RowPair.After`。|记录对的第二个记录对应的行的旧值，即，它对应于 UPDATE 语句的 WHERE 子句。 可以使用设置这`RowPair.Before`。|  
  
 更新操作的返回值是 Int32 数据类型，表示更新的行数。  
  
> [!IMPORTANT]
>  时指定包含要更新的记录，你必须在提供值时的所有列，即使所有的值不会被更新。 例如，如果行具有五个列和更新操作更新仅 2 列作为 RowPair.Before 的一部分，则必须传递所有 5 列的值。 但是，对于 RowPair.After，可以指定仅将更新的列。  
  
 **删除操作**  
  
 删除操作将作为一个强类型的输入数组的记录。 删除操作的返回值是 Int32 数据类型，表示删除的行数。  
  
## <a name="creating-a-wcf-client-to-invoke-operations-on-tables-and-views"></a>创建 WCF 客户端来调用操作对表和视图  
 泛型的执行 SQL Server 使用 WCF 客户端上的操作所需的操作集涉及到一组任务中所述[与 SQL 适配器的 WCF 服务模型概述](../../adapters-and-accelerators/adapter-sql/overview-of-the-wcf-service-model-with-the-sql-adapter.md)。 本部分介绍如何创建 WCF 客户端来调用基本插入、 选择、 更新表的删除操作。  
  
#### <a name="to-create-a-wcf-client-to-perform-operations-on-tables"></a>若要创建的 WCF 客户端，以对表执行操作  
  
1.  在 Visual Studio 中创建 Visual C# 项目。 有关本主题中，创建一个控制台应用程序。  
  
2.  生成 WCF 客户端类插入、 选择、 更新和删除员工表上的操作。 有关生成 WCF 客户端类的详细信息，请参阅[为 SQL Server 项目生成 WCF 客户端或 WCF 服务协定](../../adapters-and-accelerators/adapter-sql/generate-a-wcf-client-or-wcf-service-contract-for-sql-server-artifacts.md)。  
  
    > [!IMPORTANT]
    >  在生成 WCF 客户端类前, 请确保你设置**EnableBizTalkCompatibilityMode**绑定属性为 false。  
  
3.  在解决方案资源管理器，添加对引用`Microsoft.Adapters.Sql`和`Microsoft.ServiceModel.Channels`。  
  
4.  打开 Program.cs 文件并创建客户端，如下面的代码段中所述。  
  
    ```  
  
              TableOp_dbo_EmployeeClient client = new TableOp_dbo_EmployeeClient("SqlAdapterBinding_TableOp_dbo_Employee");  
    client.ClientCredentials.UserName.UserName = "<Enter user name here>";  
    client.ClientCredentials.UserName.Password = "<Enter password here>";  
    ```  
  
     在此代码段，`TableOp_dbo_EmployeeClient`是 SqlAdapterBindingClient.cs 中定义的 WCF 客户端。 此文件由生成[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]。 `SqlAdapterBinding_TableOp_dbo_Employee` 是客户端终结点配置的名称，并在 app.config 中定义。此文件也会生成由[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]，其中包含的绑定属性和其他配置设置。  
  
    > [!NOTE]
    >  在此代码段中，你使用的绑定和终结点地址从配置文件。 你还可显式指定这些值在代码中。 指定客户端绑定的不同方法的详细信息，请参阅[为该 SQL 适配器配置客户端绑定](../../adapters-and-accelerators/adapter-sql/configure-a-client-binding-for-the-sql-adapter.md)。  
  
5.  下面的代码段中所述，请打开客户端：  
  
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
  
6.  调用上员工表的插入操作。  
  
    ```  
    long[] recordsInserted;  
  
    schemas.microsoft.com.Sql._2008._05.Types.Tables.dbo.Employee[] insertRecord =  
    new schemas.microsoft.com.Sql._2008._05.Types.Tables.dbo.Employee[1];  
  
    insertRecord[0] = new schemas.microsoft.com.Sql._2008._05.Types.Tables.dbo.Employee();  
    insertRecord[0].Name = "John Smith";  
    insertRecord[0].Designation = "Manager";  
    insertRecord[0].Salary = 500000;  
  
    try  
    {  
       Console.WriteLine("Inserting new table entry...");  
       recordsInserted = client.Insert(insertRecord);  
    }  
    catch (Exception ex)  
    {  
       Console.WriteLine("Exception: " + ex.Message);  
       throw;  
    }  
  
    Console.WriteLine("Record inserted");  
    Console.WriteLine("Press any key to continue ...");  
    Console.ReadLine();  
    ```  
  
     你可以替换前面的代码段，来执行选择、 更新或删除操作以及。 你还可以将代码片段，可在单个应用程序中执行所有操作。 有关如何执行这些操作的代码段。  
  
7.  关闭客户端，如下面的代码段中所述：  
  
    ```  
    client.Close();  
    Console.WriteLine("Press any key to exit...");  
    Console.ReadLine();  
    ```  
  
8.  生成项目，然后运行它。 应用程序在员工表中插入一条记录。  
  
###   <a name="select-operation"></a>选择操作  
 下面的代码演示了面向员工表选择操作。 选择操作选择的最新记录插入到表。 返回的记录将写入控制台。  
  
```  
schemas.microsoft.com.Sql._2008._05.Types.Tables.dbo.Employee[] selectRecords;  
  
try  
{  
   Console.WriteLine("Selecting Row...");  
   selectRecords = client.Select("*", "where [Employee_ID] = (select IDENT_CURRENT('Employee'))");  
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
   Console.WriteLine("Employee ID        : " + selectRecords[i].Employee_ID);  
   Console.WriteLine("Employee Name      : " + selectRecords[i].Name);  
   Console.WriteLine("Employee Desigation: " + selectRecords[i].Designation);  
   Console.WriteLine();  
}  
Console.WriteLine("********************************************");  
Console.WriteLine("Press any key to continue ...");  
Console.ReadLine();  
```  
  
###   <a name="update-operation"></a>更新操作  
 下面的代码演示了面向员工表的更新操作。  
  
```  
int result;  
  
schemas.microsoft.com.Sql._2008._05.TableOp.dbo.Employee.RowPair updateRecordPair =  
   new schemas.microsoft.com.Sql._2008._05.TableOp.dbo.Employee.RowPair();  
  
schemas.microsoft.com.Sql._2008._05.Types.Tables.dbo.Employee updateRecord =   
   new schemas.microsoft.com.Sql._2008._05.Types.Tables.dbo.Employee();  
  
schemas.microsoft.com.Sql._2008._05.TableOp.dbo.Employee.RowPair[] updateArray =  
   new schemas.microsoft.com.Sql._2008._05.TableOp.dbo.Employee.RowPair[1];  
  
updateRecord = insertRecord[0];  
updateRecord.Name = "Jeff Smith";  
  
updateRecordPair.After = updateRecord;  
updateRecordPair.Before = selectRecords[0];  
  
updateArray[0] = updateRecordPair;  
  
try  
{  
   Console.WriteLine("Updating the database...");  
   result = client.Update(updateArray);  
}  
catch (Exception ex)  
{  
   Console.WriteLine("Exception: " + ex.Message);  
   throw;  
}  
  
Console.WriteLine("Updated Record for {0}", updateRecordPair.Before.Name);  
Console.WriteLine("The new name for the employee is {0}", updateRecordPair.After.Name);  
Console.WriteLine("Press any key to continue ...");  
Console.ReadLine();  
```  
  
###   <a name="delete-operation"></a>删除操作  
 下面的代码演示了面向员工表的删除操作。  
  
```  
int deleteSuccess;  
  
schemas.microsoft.com.Sql._2008._05.Types.Tables.dbo.Employee[] deleteRecords =  
   new schemas.microsoft.com.Sql._2008._05.Types.Tables.dbo.Employee[1];  
  
deleteRecords = client.Select("*", "where [Employee_ID] = (select IDENT_CURRENT('Employee'))");  
  
Console.WriteLine("Following employees will be deleted from the database:");  
for (int i = 0; i < deleteRecords.Length; i++)  
{  
   Console.WriteLine("Name: {0}", deleteRecords[i].Name);  
}  
Console.WriteLine("Press any key to begin deletion...");  
Console.ReadLine();  
  
try  
{  
   Console.WriteLine("Deleting employee record...");  
   deleteSuccess = client.Delete(deleteRecords);  
}  
  
catch (Exception ex)  
{  
   Console.WriteLine("Exception: " + ex.Message);  
   throw;  
}  
```  
  
## <a name="see-also"></a>另请参阅  
[使用 WCF 服务模型开发应用程序](../../adapters-and-accelerators/adapter-sql/develop-sql-applications-using-the-wcf-service-model.md)