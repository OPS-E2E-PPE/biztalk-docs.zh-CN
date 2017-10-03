---
title: "使用 WCF 服务模型调用 SQL Server 中的标量函数 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: a331e275-3c81-41a8-9ba1-3a801ebc259a
caps.latest.revision: "7"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 0303378f6e265d3b5d86a1aa9cd4fb1e88df86fc
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="invoke-scalar-functions-in-sql-server-by-using-the-wcf-service-model"></a>使用 WCF 服务模型调用 SQL Server 中的标量函数
你可以使用[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]在.NET 应用程序中使用 WCF 服务模型调用 SQL Server 中的标量函数。 适配器将标量函数公开为可以直接在 SQL Server 调用的方法。 有关如何适配器支持标量函数的详细信息，请参阅[执行 SQL Server 使用的 SQL 适配器中的标量函数](../../adapters-and-accelerators/adapter-sql/execute-scalar-functions-in-sql-server-using-the-sql-adapter.md)。  
  
## <a name="how-this-topic-demonstrates-invoking-scalar-functions-using-the-wcf-service-model"></a>如何本主题演示如何调用使用 WCF 服务模型的标量函数  
 本主题演示如何调用中的 SQL Server 数据库的 GET_EMP_ID 函数。 GET_EMP_ID 函数采用的某位员工的指定**员工**表并返回相应的员工 id。 GET_EMP_ID 函数和**员工**通过运行这些示例使用提供的 SQL 脚本创建表。 有关详细信息，请参阅[适配器示例](../../adapters-and-accelerators/accelerator-rosettanet/adapter-samples.md)。  
  
## <a name="about-the-examples-used-in-this-topic"></a>有关在本主题中使用的示例  
 本主题中的示例调用 GET_EMP_ID 标量函数对员工表。 GET_EMP_ID 函数和**员工**通过运行这些示例使用提供的 SQL 脚本创建表。 示例中， **ScalarFunction_ServiceModel**，后者基于本主题中，还提供了与[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]示例。 有关详细信息，请参阅[适配器示例](../../adapters-and-accelerators/accelerator-rosettanet/adapter-samples.md)。  
  
## <a name="the-wcf-client-class"></a>WCF 客户端类  
 为调用中使用 SQL Server 的标量函数生成 WCF 客户端的名称[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]下表中列出。  
  
|SQL Server 数据库项目|WCF 客户端名称|  
|----------------------------------|---------------------|  
|标量函数|ScalarFunctions_ [架构] 客户端|  
  
 [架构] = SQL Server 集合项目;例如，dbo。  
  
### <a name="method-signature-for-invoking-scalar-functions"></a>方法调用标量函数的签名  
 下表显示对表的基本操作的方法签名。 签名是相同的视图，只不过视图命名空间和名称替换那些表。  
  
|运算|方法签名|  
|---------------|----------------------|  
|标量函数名称|公共*< return_type >**< scalar_function_name >*(param1，param2，...)|  
  
 \<*retrun_type*> = 在函数定义中定义的返回类型  
  
 \<*scalar_function_name*> = 标量函数的名称。  
  
 例如，下面的代码演示方法签名，用于生成 WCF 客户端类**GET_EMP_ID**标量函数，在 dbo 架构中，它将作为参数员工指定内容并返回员工 ID （整数）。  
  
```  
public partial class ScalarFunctions_dboClient : System.ServiceModel.ClientBase<ScalarFunctions_dbo>, ScalarFunctions_dbo {      
    public System.Nullable<int> GET_EMP_ID(string emp_desig);  
}  
```  
  
 在此代码段， **ScalarFunctions_dboClient**是 WCF 中的类的生成的 SqlAdapterBindingClient.cs 名称[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]。  
  
### <a name="parameters-for-invoking-scalar-functions"></a>调用标量函数的参数  
 通过公开的方法的参数[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]来调用一个标量函数都作为 SQL Server 中的标量函数定义中定义的参数相同。 例如，调用 GET_EMP_ID 标量函数的参数是 emp_desig 并且充分员工的代码。  
  
 同样，一个标量函数的返回值是与 SQL Server 中的标量函数定义中定义的返回值相同。 例如，GET_EMP_ID 函数的返回值是整数类型的员工的 ID。  
  
## <a name="creating-a-wcf-client-to-invoke-scalar-functions"></a>创建 WCF 客户端调用标量函数  
 泛型的执行 SQL Server 使用 WCF 客户端上的操作所需的操作集涉及到一组任务中所述[与 SQL 适配器的 WCF 服务模型概述](../../adapters-and-accelerators/adapter-sql/overview-of-the-wcf-service-model-with-the-sql-adapter.md)。 本部分介绍如何创建 WCF 客户端来调用**GET_EMP_ID**标量函数。  
  
#### <a name="to-create-a-wcf-client"></a>若要创建 WCF 客户端  
  
1.  创建 Visual C# 项目中的[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]。 有关本主题中，创建一个控制台应用程序。  
  
2.  生成的 WCF 客户端类**GET_EMP_ID**标量函数。 有关生成 WCF 客户端类的详细信息，请参阅[为 SQL Server 项目生成 WCF 客户端或 WCF 服务协定](../../adapters-and-accelerators/adapter-sql/generate-a-wcf-client-or-wcf-service-contract-for-sql-server-artifacts.md)。  
  
3.  在解决方案资源管理器，添加对引用`Microsoft.Adapters.Sql`和`Microsoft.ServiceModel.Channels`。  
  
4.  打开 Program.cs，如下面的代码段中所述创建客户端。  
  
    ```  
  
              ScalarFunctions_dboClient client = new ScalarFunctions_dboClient("SqlAdapterBinding_ScalarFunctions_dbo");  
    client.ClientCredentials.UserName.UserName = "<Enter user name here>";  
    client.ClientCredentials.UserName.Password = "<Enter password here>";  
    ```  
  
     在此代码段，`ScalarFunctions_dboClient`是 SqlAdapterBindingClient.cs 中定义的 WCF 客户端。 此文件由生成[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]。 `SqlAdapterBinding_ScalarFunctions_dbo`是客户端终结点配置的名称，并在 app.config 中定义。此文件也会生成由[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]，其中包含的绑定属性和其他配置设置。  
  
    > [!NOTE]
    >  在此代码段中，你使用的绑定和终结点地址从配置文件。 你还可显式指定这些值在代码中。 然后指定客户端绑定的不同方法的详细信息，请参阅[为该 SQL 适配器配置客户端绑定](../../adapters-and-accelerators/adapter-sql/configure-a-client-binding-for-the-sql-adapter.md)。  
  
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
  
6.  调用**GET_EMP_ID**函数可检索与指定为"Manager"员工的 ID。  
  
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
    >  为简单起见，**员工**表具有只有一个员工具有"Manager"标志。 如果您的目标表具有更多员工使用相同的代码，则必须相应地定义函数。  
  
7.  关闭客户端，如下面的代码段中所述：  
  
    ```  
    client.Close();  
    Console.WriteLine("Press any key to exit...");  
    Console.ReadLine();  
    ```  
  
8.  生成项目，然后运行它。 应用程序将显示带有"Manager"标志的员工的员工 ID。  
  
## <a name="see-also"></a>另请参阅  
[开发应用程序使用 WCF 服务模型](../../adapters-and-accelerators/adapter-sql/develop-sql-applications-using-the-wcf-service-model.md)