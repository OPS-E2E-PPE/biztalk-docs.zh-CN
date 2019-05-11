---
title: 通过使用 WCF 服务模型中调用 SQL Server 中的标量函数 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: a331e275-3c81-41a8-9ba1-3a801ebc259a
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a776fa2d2afcd42bbf57aaee1f73e0647ca00ef7
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65369404"
---
# <a name="invoke-scalar-functions-in-sql-server-by-using-the-wcf-service-model"></a>通过使用 WCF 服务模型中调用 SQL Server 中的标量函数
可以使用[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]中使用 WCF 服务模型用于调用标量函数在 SQL Server 的.NET 应用程序。 该适配器将标量函数公开为可以直接在 SQL Server 调用的方法。 有关如何在适配器支持标量函数的详细信息，请参阅[执行 SQL Server 使用 SQL 适配器中的标量函数](../../adapters-and-accelerators/adapter-sql/execute-scalar-functions-in-sql-server-using-the-sql-adapter.md)。  

## <a name="how-this-topic-demonstrates-invoking-scalar-functions-using-the-wcf-service-model"></a>本主题演示调用标量函数使用 WCF 服务模型的方式  
 本主题演示如何在 SQL Server 数据库 GET_EMP_ID 函数调用。 GET_EMP_ID 函数采用指定的某位员工的**员工**表，并返回相应的员工 id。 GET_EMP_ID 函数和**员工**通过运行这些示例提供的 SQL 脚本创建表。 有关详细信息，请参阅[适配器示例](../../adapters-and-accelerators/accelerator-rosettanet/adapter-samples.md)。  

## <a name="about-the-examples-used-in-this-topic"></a>有关使用在本主题中的示例  
 本主题中的示例调用 GET_EMP_ID 标量函数在 Employee 表。 GET_EMP_ID 函数和**员工**通过运行这些示例提供的 SQL 脚本创建表。 示例中， **ScalarFunction_ServiceModel**，后者基于本主题中，还提供与[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]示例。 有关详细信息，请参阅[适配器示例](../../adapters-and-accelerators/accelerator-rosettanet/adapter-samples.md)。  

## <a name="the-wcf-client-class"></a>WCF 客户端类  
 生成用于调用标量函数中使用 SQL Server 的 WCF 客户端名称[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]下表中列出。  

|SQL Server 数据库项目|WCF 客户端名称|  
|----------------------------------|---------------------|  
|标量函数|ScalarFunctions_[SCHEMA]Client|  

 [架构] = 集合的 SQL Server 项目;例如，dbo。  

### <a name="method-signature-for-invoking-scalar-functions"></a>用于调用标量函数的方法签名  
 下表显示了对表的基本操作的方法签名。 签名是相同的视图，只不过视图命名空间和名称替换这些表。  


|      操作       |                             方法签名                             |
|----------------------|--------------------------------------------------------------------------|
| 标量函数名称 | public *<return_type>*<em><scalar_function_name></em>(param1, param2, …) |

 \<*retrun_type* \> = 函数定义中定义的返回类型  

 \<*scalar_function_name* \> = 标量函数的名称。  

 例如，下面的代码演示的方法签名，用于为生成 WCF 客户端类**GET_EMP_ID**在 dbo 架构中，它将员工指定为参数并返回员工 ID （标量函数整数）。  

```  
public partial class ScalarFunctions_dboClient : System.ServiceModel.ClientBase<ScalarFunctions_dbo>, ScalarFunctions_dbo {      
    public System.Nullable<int> GET_EMP_ID(string emp_desig);  
}  
```  

 此代码片段**ScalarFunctions_dboClient**是 WCF 中的类的生成的 SqlAdapterBindingClient.cs 名称[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]。  

### <a name="parameters-for-invoking-scalar-functions"></a>用于调用标量函数的参数  
 通过公开的方法的参数[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]来调用标量函数将与 SQL Server 中的标量函数定义中定义的参数相同。 例如，调用 GET_EMP_ID 标量函数的参数相当 emp_desig，员工的代码。  

 同样，对于标量函数的返回值是与 SQL Server 中的标量函数定义中定义的返回值相同。 例如，GET_EMP_ID 函数的返回值是整数类型的员工的 ID。  

## <a name="creating-a-wcf-client-to-invoke-scalar-functions"></a>创建 WCF 客户端以调用标量函数  
 通用组对 SQL Server 使用 WCF 客户端执行操作所需的操作涉及到一组任务中所述[与 SQL 适配器的 WCF 服务模型概述](../../adapters-and-accelerators/adapter-sql/overview-of-the-wcf-service-model-with-the-sql-adapter.md)。 本部分介绍如何创建 WCF 客户端以调用**GET_EMP_ID**标量函数。  

#### <a name="to-create-a-wcf-client"></a>若要创建 WCF 客户端  

1. 创建 Visual C# 项目中的[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]。 有关本主题中，创建一个控制台应用程序。  

2. 生成的 WCF 客户端类**GET_EMP_ID**标量函数。 有关生成 WCF 客户端类的详细信息，请参阅[为 SQL Server 项目生成 WCF 客户端或 WCF 服务约定](../../adapters-and-accelerators/adapter-sql/generate-a-wcf-client-or-wcf-service-contract-for-sql-server-artifacts.md)。  

3. 在解决方案资源管理器，添加对引用`Microsoft.Adapters.Sql`和`Microsoft.ServiceModel.Channels`。  

4. 打开 Program.cs，并创建一个客户端，如下面的代码段中所述。  

   ```  

             ScalarFunctions_dboClient client = new ScalarFunctions_dboClient("SqlAdapterBinding_ScalarFunctions_dbo");  
   client.ClientCredentials.UserName.UserName = "<Enter user name here>";  
   client.ClientCredentials.UserName.Password = "<Enter password here>";  
   ```  

    在此代码段，`ScalarFunctions_dboClient`是 SqlAdapterBindingClient.cs 中定义的 WCF 客户端。 此文件由生成[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]。 `SqlAdapterBinding_ScalarFunctions_dbo` 客户端终结点配置的名称，并在 app.config 中定义。此文件也由生成[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]，其中包含的绑定属性和其他配置设置。  

   > [!NOTE]
   >  在此片段中，您使用的绑定和终结点地址从配置文件。 在代码中，可以显式指定这些值。 然后指定客户端绑定的不同方法的详细信息，请参阅[为 SQL 适配器配置客户端绑定](../../adapters-and-accelerators/adapter-sql/configure-a-client-binding-for-the-sql-adapter.md)。  

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

6. 调用**GET_EMP_ID**函数来检索与指定为"Manager"员工的 ID。  

   ```  
   Console.WriteLine("Invoking the GET_EMP_ID function");  
   string emp_designation = "Manager";  
   try  
   {  
         System.Nullable<int> emp_id = client.GET_EMP_ID(emp_designation);  
         Console.WriteLine("The Employee ID for the employee with 'Manager' designation is:" + emp_id);  
   }  
   catch (Exception e)  
   {  
         Console.WriteLine("Exception: " + e.Message);  
         throw;  
   }  
   ```  

   > [!NOTE]
   >  为简单起见，**员工**表具有只有一个员工有"Manager"指定内容。 如果您的目标表具有相同标识的更多员工，必须相应地定义的函数。  

7. 关闭客户端，如下面的代码段中所述：  

   ```  
   client.Close();  
   Console.WriteLine("Press any key to exit...");  
   Console.ReadLine();  
   ```  

8. 生成项目，然后运行它。 应用程序将显示该员工的员工 ID，指定的"管理器"。  

## <a name="see-also"></a>请参阅  
[使用 WCF 服务模型开发应用程序](../../adapters-and-accelerators/adapter-sql/develop-sql-applications-using-the-wcf-service-model.md)