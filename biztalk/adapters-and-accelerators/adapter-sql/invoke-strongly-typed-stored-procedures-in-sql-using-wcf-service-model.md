---
title: 调用强类型化 SQL 使用 WCF 服务模型中的存储过程 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: d56df5f6-b046-4fe4-a5b4-b29906093beb
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 5a4ceeba676785fbbcd66f192e30ec91816115c7
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65369306"
---
# <a name="invoke-strongly-typed-stored-procedures-in-sql-using-wcf-service-model"></a>调用强类型化 SQL 使用 WCF 服务模型中的存储过程
当您调用下列出的过程**Strongly-Typed 过程**中的节点[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]，输出采用强类型化结果集的形式。 本主题将说明了如何创建 WCF 客户端以调用返回强类型化结果集的 SQL Server 中的存储的过程。  
  
> [!NOTE]
>  如果您正在执行对具有用户定义类型的列的表操作，请确保您参考[对表和视图的用户定义类型的操作](../../adapters-and-accelerators/adapter-sql/operations-on-tables-and-views-with-user-defined-types-using-the-sql-adapter.md)开始开发应用程序之前。  
  
## <a name="about-the-examples-used-in-this-topic"></a>有关使用在本主题中的示例  
 本主题中的示例使用 GET_EMP_DETAILS 存储过程。 此存储的过程将员工 ID 作为输入参数并返回相应的所有列的员工与该 id。 通过运行这些示例提供的 SQL 脚本，创建 GET_EMP_DETAILS 存储过程。 有关示例的详细信息，请参阅[适配器示例](../../adapters-and-accelerators/accelerator-rosettanet/adapter-samples.md)。 示例中， **Execute_TypedStoredProcedure**，后者基于本主题中，还提供与[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]示例。  
  
## <a name="the-wcf-client-class"></a>WCF 客户端类  
 为调用存储的过程在生成 WCF 客户端的名称**Strongly-Typed 过程**节点使用[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]下表中列出。  
  
|SQL Server 数据库项目|WCF 客户端名称|  
|----------------------------------|---------------------|  
|过程 (下**Strongly-Typed 过程**节点)|TypedProcedures_[schema]Client|  
  
 [架构] 是该过程所属的架构;例如，"dbo"。  
  
### <a name="method-signature-for-invoking-stored-procedures"></a>用于调用存储的过程的方法签名  
 下表显示了用于调用存储的过程所公开的方法的签名。  
  
|操作|方法签名|  
|---------------|----------------------|  
|过程名称|[PROC_NS] [procedure_name](param1, param2, …\)|  
  
 [PROC_NS] 是过程的命名空间;例如 schemas.microsoft.com.Sql._2008._05.ProceduresResultSets.dbo.GET_EMP_DETAILS.StoredProcedureResultSet0]  
  
 [过程名称] 是过程; 的名称例如 GET_EMP_DETAILS  
  
 例如，要调用 GET_EMP_DETAILS 过程的方法的签名所示下面的代码段。  
  
```  
public partial class TypedProcedures_dboClient : System.ServiceModel.ClientBase<TypedProcedures_dbo>, TypedProcedures_dbo{  
public schemas.microsoft.com.Sql._2008._05.ProceduresResultSets.dbo.GET_EMP_DETAILS.StoredProcedureResultSet0[]   
  GET_EMP_DETAILS(System.Nullable<int> emp_id, out int ReturnValue);  
}  
```  
  
 此代码片段  
  
-   `TypedProcedures_dboClient` 是类的名称。 在此示例中，您可以使用此类创建的客户端来调用存储的过程。  
  
-   `public schemas.microsoft.com.Sql._2008._05.ProceduresResultSets.dbo.GET_EMP_DETAILS.StoredProcedureResultSet0[] GET_EMP_DETAILS(System.Nullable<int> emp_id, out int ReturnValue)` 是在此示例中调用的方法来调用存储的过程。 此存储的过程将员工 ID，并返回一个强类型化结果集。  
  
## <a name="creating-a-wcf-client-to-invoke-a-stored-procedure-in-sql-server"></a>创建 WCF 客户端以调用 SQL Server 中的存储的过程  
 通用组对 SQL Server 使用 WCF 客户端执行操作所需的操作涉及到一组任务中所述[与 SQL 适配器的 WCF 服务模型概述](overview-of-the-wcf-service-model-with-the-sql-adapter.md)。 具体而言，本部分介绍如何创建调用存储的过程的结果集是强类型化的 WCF 客户端。 在本主题中，例如，你将调用 GET_EMP_DETAILS 存储过程。 通过运行与每个示例提供的 SQL 脚本来创建此存储的过程。  
  
1. 在 Visual Studio 中创建一个 Visual C# 项目。 有关本主题中，创建一个控制台应用程序。  
  
2. 生成 GET_EMP_DETAILS 存储过程的 WCF 客户端类。 请确保选择下的过程**Strongly-Typed 过程**节点。 有关生成 WCF 客户端类的详细信息，请参阅[为 SQL Server 项目生成 WCF 客户端或 WCF 服务约定](generate-a-wcf-client-or-wcf-service-contract-for-sql-server-artifacts.md)。  
  
   > [!IMPORTANT]
   >  生成 WCF 客户端类之前，请确保设置**EnableBizTalkCompatibilityMode**属性绑定到 false。  
  
3. 在解决方案资源管理器，添加对引用`Microsoft.Adapters.Sql`和`Microsoft.ServiceModel.Channels`。  
  
4. 打开 Program.cs 文件，如下面的代码段中所述创建客户端。  
  
   ```  
  
             TypedProcedures_dboClient client = new TypedProcedures_dboClient("SqlAdapterBinding_TypedProcedures_dbo");  
   client.ClientCredentials.UserName.UserName = "<Enter username here>";  
   client.ClientCredentials.UserName.Password = "<Enter username here>";  
   ```  
  
    在此代码段，`TypedProcedures_dboClient`是 SqlAdapterBindingClient.cs 中定义的 WCF 客户端。 此文件由生成[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]。 `SqlAdapterBinding_TypedProcedures_dbo` 客户端终结点配置的名称，并在 app.config 中定义。此文件也由生成[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]，其中包含的绑定属性和其他配置设置。  
  
   > [!NOTE]
   >  在此片段中，您使用的绑定和终结点地址从配置文件。 在代码中，可以显式指定这些值。 指定客户端绑定的不同方法的详细信息，请参阅[为 SQL 适配器配置客户端绑定](configure-a-client-binding-for-the-sql-adapter.md)。  
  
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
  
6. 调用 GET_EMP_DETAILS 存储过程，如下面的代码段中所述。  
  
   ```  
   // Create array of type as specified in the method signature  
   schemas.microsoft.com.Sql._2008._05.ProceduresResultSets.dbo.GET_EMP_DETAILS.StoredProcedureResultSet0[] resultSet =  
      new schemas.microsoft.com.Sql._2008._05.ProceduresResultSets.dbo.GET_EMP_DETAILS.StoredProcedureResultSet0[1];  
   int returnCode;  
  
   try  
   {  
      Console.WriteLine("Calling a stored procedure...");  
      resultSet = client.GET_EMP_DETAILS(10001, out returnCode);  //Invoke the stored procedure  
   }  
   catch (Exception ex)  
   {  
      Console.WriteLine("Exception: " + ex.Message);  
      throw;  
   }  
   Console.WriteLine("The details for the employee with ID '10001' are:");  
   Console.WriteLine("*************************************************");  
  
   for (int i = 0; i < resultSet.Length; i++)  
      {  
         Console.WriteLine("Employee Name        : " + resultSet[i].Name);  
         Console.WriteLine("Employee Designation : " + resultSet[i].Designation);  
         Console.WriteLine("Employee Salary      : " + resultSet[i].Salary);  
      }  
  
   Console.WriteLine("*************************************************");  
  
   ```  
  
7. 关闭客户端，如下面的代码段中所述：  
  
   ```  
   client.Close();  
   Console.WriteLine("Press any key to exit...");  
   Console.ReadLine();  
   ```  
  
8. 生成项目，然后运行它。 在控制台上显示的名称、 指定的和员工 ID 的薪金。  
  
## <a name="see-also"></a>请参阅  
[使用 WCF 服务模型开发应用程序](develop-sql-applications-using-the-wcf-service-model.md)