---
title: 插入、 更新、 删除或在 SQL 中使用 WCF 服务模型中选择操作 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 340048ad-ce28-4acf-ae4e-f18bdb3b6f47
caps.latest.revision: 14
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: dcf58b5ff9a379b7b28647e0d5b07475d08310db
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "37011164"
---
# <a name="insert-update-delete-or-select-operations-in-sql-using-the-wcf-service-model"></a>插入、 更新、 删除或在 SQL 中使用 WCF 服务模型中选择操作
[!INCLUDE[adaptersql](../../includes/adaptersql-md.md)]发现一组基本的 Insert、 Select、 Update 和 Delete 操作上 SQL Server 数据库表和视图。 通过使用这些操作，你可以执行简单 SQL Insert、 Select、 Update 和 Delete 语句限定由 Where 子句对目标表或视图。 本主题将说明了如何使用 WCF 服务模型执行这些操作。  
  
 适配器如何支持这些操作的详细信息，请参阅[Insert、 Update、 Delete 和选择操作对表和视图与 SQL 适配器](../../adapters-and-accelerators/adapter-sql/insert-update-delete-and-select-on-tables-and-views-with-the-sql-adapter.md)。  
  
> [!NOTE]
>  如果您正在执行对具有用户定义类型的列的表操作，请确保您参考[对表和视图使用 SQL 适配器的用户定义类型的操作](../../adapters-and-accelerators/adapter-sql/operations-on-tables-and-views-with-user-defined-types-using-the-sql-adapter.md)开始开发应用程序之前。  
  
## <a name="about-the-examples-used-in-this-topic"></a>有关使用在本主题中的示例  
 本主题中的示例执行在 Employee 表上的操作。 通过运行这些示例提供的 SQL 脚本创建员工表。 有关示例的详细信息，请参阅[适配器示例](../../adapters-and-accelerators/accelerator-rosettanet/adapter-samples.md)。 示例中， **EmployeeBasicOps**，后者基于本主题中，还提供与[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]示例。  
  
## <a name="the-wcf-client-class"></a>WCF 客户端类  
 WCF 客户端生成的基本 SQL 操作的名称，[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]可发现下表中列出基于表或视图的名称。  
  
|SQL Server 数据库项目|WCF 客户端名称|  
|----------------------------------|---------------------|  
|表|TableOp_[Schema]_[TABLE_NAME]Client|  
|“查看”|ViewOp_[Schema]_[VIEW_NAME]Client|  
  
 [架构] = 集合的 SQL Server 项目;例如，dbo。  
  
 [TABLE_NAME] = 表; 的名称例如，员工。  
  
 [VIEW_NAME] = 视图; 的名称例如，Employee_View。  
  
### <a name="method-signature-for-invoking-operations-on-tables"></a>调用表操作的方法签名  
 下表显示了对表的基本操作的方法签名。 签名是相同的视图，只不过视图命名空间和名称替换这些表。  
  
|运算|方法签名|  
|---------------|----------------------|  
|Insert|long[] Insert([TABLE_NS].[TABLE_NAME][] Rows);|  
|选择|[TABLE_NS]。[TABLE_NAME][选择 （字符串列，查询字符串）;]|  
|Update|int Update([TABLE_NS].[TABLE_NAME].RowPair[] Rows);|  
|DELETE|int Delete ([TABLE_NS]。 [TABLE_NAME] [] 行）;|  
  
 [TABLE_NS] = 表命名空间; 的名称例如，schemas.microsoft.com.Sql._2008._05.Types.Tables.dbo.Employee。  
  
 [TABLE_NAME] = 表; 的名称例如，员工。  
  
 例如，下面的代码演示对 Employee 表下的默认"dbo"架构的 Delete、 Insert、 Select 和 Update 操作生成的 WCF 客户端类的方法签名。  
  
```  
public partial class TableOp_dbo_EmployeeClient : System.ServiceModel.ClientBase<TableOp_dbo_Employee>, TableOp_dbo_Employee {      
    public int Delete(schemas.microsoft.com.Sql._2008._05.Types.Tables.dbo.Employee[] Rows);  
  
    public long[] Insert(schemas.microsoft.com.Sql._2008._05.Types.Tables.dbo.Employee[] Rows);  
  
    public schemas.microsoft.com.Sql._2008._05.Types.Tables.dbo.Employee[] Select(string Columns, string Query);  
  
    public int Update(schemas.microsoft.com.Sql._2008._05.TableOp.dbo.Employee.RowPair[] Rows);  
}  
```  
  
 在此代码段，TableOp_dbo_EmployeeClient 是 WCF 中的类的生成的 SqlAdapterBindingClient.cs 名称[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]。  
  
### <a name="parameters-for-table-operations"></a>用于表操作的参数  
 本部分提供了每个表操作所需的参数  
  
 **插入操作**  
  
|插入操作类型|记录集|  
|---------------------------|---------------|  
|多个记录|应插入到表的 INSERTRECORDS 的集合。|  
  
 插入操作返回的 Long 数据类型的数组，并将存储插入的行的标识值，如果有。 如果在表中没有标识列，返回值为 NULL。  
  
 **选择操作**  
  
|COLUMN_NAMES|QUERY|  
|-------------------|-----------|  
|以逗号分隔的目标; 中的列名称列表例如，"Employee_ID，指定"。 列列表中指定的目标应在结果集中返回的列。 未指定列列表中的列将设置为其返回的记录集的.NET 默认值。 对于 nillable 列，此值是**null**。|指定的查询; 目标行的 SQL WHERE 子句的内容例如，"名称 = Manager"。 可以将此参数设置为**null**返回目标的所有行。|  
  
 选择操作的返回值是强类型化结果集包含指定的列和目标表或视图中的行。  
  
 **更新操作**  
  
|该对的第一行|该对的第二行|  
|---------------------------|----------------------------|  
|对与需要进行更新的新值相对应的记录的第一个记录，即它对应于 UPDATE 语句的 SET 子句。 可以使用设置这`RowPair.After`。|记录对的第二个记录对应的行的旧值，也就是说，它对应于 UPDATE 语句的 WHERE 子句。 可以使用设置这`RowPair.Before`。|  
  
 更新操作的返回值是 Int32 数据类型，表示更新的行数。  
  
> [!IMPORTANT]
>  同时指定要更新的记录，必须提供值的所有列，即使无法获得更新的所有值。 例如，如果某行具有五个列和更新操作更新仅 2 列作为 RowPair.Before 的一部分，则必须传递所有 5 个列的值。 但是，对于 RowPair.After，可以指定仅将更新的列。  
  
 **删除操作**  
  
 删除操作将作为强类型的输入数组的记录。 删除操作的返回值是 Int32 数据类型，表示删除的行数。  
  
## <a name="creating-a-wcf-client-to-invoke-operations-on-tables-and-views"></a>创建 WCF 客户端以调用上表和视图的操作  
 通用组对 SQL Server 使用 WCF 客户端执行操作所需的操作涉及到一组任务中所述[与 SQL 适配器的 WCF 服务模型概述](../../adapters-and-accelerators/adapter-sql/overview-of-the-wcf-service-model-with-the-sql-adapter.md)。 本部分介绍如何创建 WCF 客户端以调用基本的 Insert、 Select、 Update 对表的删除操作。  
  
#### <a name="to-create-a-wcf-client-to-perform-operations-on-tables"></a>若要创建 WCF 客户端以对表执行操作  
  
1. 在 Visual Studio 中创建一个 Visual C# 项目。 有关本主题中，创建一个控制台应用程序。  
  
2. 生成 WCF 客户端类的 Insert、 Select、 Update 和删除 Employee 表上的操作。 有关生成 WCF 客户端类的详细信息，请参阅[为 SQL Server 项目生成 WCF 客户端或 WCF 服务约定](../../adapters-and-accelerators/adapter-sql/generate-a-wcf-client-or-wcf-service-contract-for-sql-server-artifacts.md)。  
  
   > [!IMPORTANT]
   >  生成 WCF 客户端类之前，请确保设置**EnableBizTalkCompatibilityMode**属性绑定到 false。  
  
3. 在解决方案资源管理器，添加对引用`Microsoft.Adapters.Sql`和`Microsoft.ServiceModel.Channels`。  
  
4. 打开 Program.cs 文件，如下面的代码段中所述创建客户端。  
  
   ```  
  
             TableOp_dbo_EmployeeClient client = new TableOp_dbo_EmployeeClient("SqlAdapterBinding_TableOp_dbo_Employee");  
   client.ClientCredentials.UserName.UserName = "<Enter user name here>";  
   client.ClientCredentials.UserName.Password = "<Enter password here>";  
   ```  
  
    在此代码段，`TableOp_dbo_EmployeeClient`是 SqlAdapterBindingClient.cs 中定义的 WCF 客户端。 此文件由生成[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]。 `SqlAdapterBinding_TableOp_dbo_Employee` 客户端终结点配置的名称，并在 app.config 中定义。此文件也由生成[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]，其中包含的绑定属性和其他配置设置。  
  
   > [!NOTE]
   >  在此片段中，您使用的绑定和终结点地址从配置文件。 在代码中，可以显式指定这些值。 指定客户端绑定的不同方法的详细信息，请参阅[为 SQL 适配器配置客户端绑定](../../adapters-and-accelerators/adapter-sql/configure-a-client-binding-for-the-sql-adapter.md)。  
  
5. 打开客户端，如下面的代码段中所述：  
  
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
  
6. 调用上的 Employee 表的插入操作。  
  
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
  
    您可以替换上述代码段中执行 Select、 Update 或 Delete 操作。 也可以附加代码片段，可在单个应用程序中执行所有操作。 有关如何执行这些操作的代码片段。  
  
7. 关闭客户端，如下面的代码段中所述：  
  
   ```  
   client.Close();  
   Console.WriteLine("Press any key to exit...");  
   Console.ReadLine();  
   ```  
  
8. 生成项目，然后运行它。 应用程序在 Employee 表中插入一条记录。  
  
###   <a name="select-operation"></a>选择操作  
 下面的代码演示了面向 Employee 表的选择操作。 选择操作选择插入到表中的最后一个记录。 返回的记录写入到控制台中。  
  
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
 下面的代码演示了面向 Employee 表的更新操作。  
  
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
 下面的代码演示的删除操作的目标的 Employee 表。  
  
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
  
## <a name="see-also"></a>请参阅  
[使用 WCF 服务模型开发应用程序](../../adapters-and-accelerators/adapter-sql/develop-sql-applications-using-the-wcf-service-model.md)