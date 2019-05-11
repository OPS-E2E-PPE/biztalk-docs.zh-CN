---
title: 通过使用 WCF 服务模型中调用 SQL Server 中的表值函数 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 48688bcc-36b4-4cc1-b078-17e7a5e1cf8c
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: cea9379337797daec243f2d40b15f183c6f54425
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65369322"
---
# <a name="invoke-table-valued-functions-in-sql-server-by-using-the-wcf-service-model"></a>通过使用 WCF 服务模型中调用 SQL Server 中的表值函数
可以使用[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)].NET 应用程序使用 WCF 服务模型来调用 SQL Server 中的表值函数中。 该适配器将表值函数公开为可以直接在 SQL Server 调用的方法。 有关如何在适配器支持标量函数的详细信息，请参阅[Execute Table-Valued 函数中使用 SQL 适配器的 SQL Server](../../adapters-and-accelerators/adapter-sql/execute-table-valued-functions-in-sql-server-using-the-sql-adapter.md)。  
  
 本主题演示如何在 SQL Server 数据库 TVF_EMPLOYEE 函数调用。 TVF_EMPLOYEE 函数采用指定的某位员工的**员工**表，并返回该员工记录。 TVF_EMPLOYEE 函数和**员工**通过运行这些示例提供的 SQL 脚本创建表。 有关详细信息，请参阅[适配器示例](../../adapters-and-accelerators/accelerator-rosettanet/adapter-samples.md)。  
  
## <a name="about-the-examples-used-in-this-topic"></a>有关使用在本主题中的示例  
 本主题中的示例在调用 TVF_EMPLOYEE 表值函数**员工**表。 TVF_EMPLOYEE 函数和**员工**通过运行这些示例提供的 SQL 脚本创建表。 示例中， **TableFunction_ServiceModel**，后者基于本主题中，还提供与[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]示例。 有关详细信息，请参阅[适配器示例](../../adapters-and-accelerators/accelerator-rosettanet/adapter-samples.md)。  
  
## <a name="the-wcf-client-class"></a>WCF 客户端类  
 生成用于调用标量函数中使用 SQL Server 的 WCF 客户端名称[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]下表中列出。  
  
|SQL Server 数据库项目|WCF 客户端名称|  
|----------------------------------|---------------------|  
|表值函数|TableValuedFunctions_[SCHEMA]Client|  
  
 [架构] = 集合的 SQL Server 项目;例如，dbo。  
  
### <a name="method-signature-for-invoking-table-valued-functions"></a>用于调用表值函数的方法签名  
 下表显示了对表的基本操作的方法签名。 签名是相同的视图，只不过视图命名空间和名称替换这些表。  
  
|操作|方法签名|  
|---------------|----------------------|  
|表值函数名称|public [NAMESPACE][FUNCTION_NAME][] [FUNCTION_NAME](param1, param2, …\)|  
  
 [NAMESPACE] = 命名空间，例如，schemas.microsoft.com.Sql._2008._05.Types.TableFunctionReturnTables.dbo.TVF_EMPLOYEE  
  
 [FUNCTION_NAME] = 表值函数的名称。  
  
 例如，下面的代码演示的方法签名，用于为生成 WCF 客户端类**TVF_EMPLOYEE**在 dbo 架构中，它将员工指定为参数并返回该雇员的标量函数记录。  
  
```  
public partial class TableValuedFunctions_dboClient : System.ServiceModel.ClientBase<TableValuedFunctions_dbo>, TableValuedFunctions_dbo {      
    public schemas.microsoft.com.Sql._2008._05.Types.TableFunctionReturnTables.dbo.TVF_EMPLOYEE[] TVF_EMPLOYEE(string emp_desig);  
}  
```  
  
 此代码片段**TableValuedFunctions_dboClient**是 WCF 中的类的生成的 SqlAdapterBindingClient.cs 名称[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]。  
  
### <a name="parameters-for-invoking-table-valued-functions"></a>调用表值函数的参数  
 通过公开的方法的参数[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]调用表值函数将与 SQL Server 中的函数定义中定义的参数相同。 例如，调用 TVF_EMPLOYEE 表值函数的参数相当 emp_desig，员工的代码。  
  
 同样，对于表值函数的返回值是与 SQL Server 中的函数定义中定义的返回值相同。 例如，TVF_EMPLOYEE 函数的返回值是一个数组类型 schemas.microsoft.com.Sql._2008._05.Types.TableFunctionReturnTables.dbo.TVF_EMPLOYEE [] 的记录。  
  
## <a name="creating-a-wcf-client-to-invoke-table-valued-functions"></a>创建 WCF 客户端调用表值函数  
 通用组对 SQL Server 使用 WCF 客户端执行操作所需的操作涉及到一组任务中所述[与 SQL 适配器的 WCF 服务模型概述](overview-of-the-wcf-service-model-with-the-sql-adapter.md)。 本部分介绍如何创建 WCF 客户端以调用**TVF_EMPLOYEE**表值函数。  
  
 
1. 创建 Visual C# 项目中的[!INCLUDE[btsVStudioNoVersion](../../includes/btsVStudioNoVersion-md.md)]。 有关本主题中，创建一个控制台应用程序。  
  
2. 生成的 WCF 客户端类**TVF_EMPLOYEE**标量函数。 有关生成 WCF 客户端类的详细信息，请参阅[为 SQL Server 项目生成 WCF 客户端或 WCF 服务约定](generate-a-wcf-client-or-wcf-service-contract-for-sql-server-artifacts.md)。  
  
3. 在解决方案资源管理器，添加对引用`Microsoft.Adapters.Sql`和`Microsoft.ServiceModel.Channels`。  
  
4. 打开 Program.cs，并创建一个客户端，如下面的代码段中所述。  
  
   ```  
  
             TableValuedFunctions_dboClient client = new TableValuedFunctions_dboClient("SqlAdapterBinding_TableValuedFunctions_dbo");  
   client.ClientCredentials.UserName.UserName = "<Enter user name here>";  
   client.ClientCredentials.UserName.Password = "<Enter password here>";  
   ```  
  
    在此代码段，`TableValuedFunctions_dboClient`是 SqlAdapterBindingClient.cs 中定义的 WCF 客户端。 此文件由生成[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]。 `SqlAdapterBinding_TableValuedFunctions_dbo` 客户端终结点配置的名称，并在 app.config 中定义。此文件也由生成[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]，其中包含的绑定属性和其他配置设置。  
  
   > [!NOTE]
   >  在此片段中，您使用的绑定和终结点地址从配置文件。 在代码中，可以显式指定这些值。 然后指定客户端绑定的不同方法的详细信息，请参阅[为 SQL 适配器配置客户端绑定](configure-a-client-binding-for-the-sql-adapter.md)。  
  
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
  
6. 调用**TVF_EMPLOYEE**函数以检索具有指定的"管理器"的所有员工记录。  
  
   ```  
   Console.WriteLine("Invoking the TVF_EMPLOYEE function");  
   schemas.microsoft.com.Sql._2008._05.Types.TableFunctionReturnTables.dbo.TVF_EMPLOYEE[] emp_details;  
   string emp_designation = "Manager";  
  
   try  
   {  
       emp_details = client.TVF_EMPLOYEE(emp_designation);  
   }  
   catch (Exception e)  
   {  
       Console.WriteLine("Exception: " + e.Message);  
       throw;  
   }  
   Console.WriteLine("The details for the employee with the 'Manager' designation are:");  
   Console.WriteLine("*******************************************************************");  
   for (int i = 0; i < emp_details.Length; i++)  
   {  
       Console.WriteLine("Employee ID        : " + emp_details[i].Employee_ID);  
       Console.WriteLine("Employee Name      : " + emp_details[i].Name);  
       Console.WriteLine("Employee Desigation: " + emp_details[i].Designation);  
       Console.WriteLine("Employee Salary    : " + emp_details[i].Salary);  
       Console.WriteLine();  
   }  
   ```  
  
7. 关闭客户端，如下面的代码段中所述：  
  
   ```  
   client.Close();  
   Console.WriteLine("Press any key to exit...");  
   Console.ReadLine();  
   ```  
  
8. 生成项目，然后运行它。 应用程序显示雇员 ID、 名称和具有"Manager"指定的所有员工的工资数据交换。  
  
## <a name="see-also"></a>请参阅  
[使用 WCF 服务模型开发应用程序](develop-sql-applications-using-the-wcf-service-model.md)