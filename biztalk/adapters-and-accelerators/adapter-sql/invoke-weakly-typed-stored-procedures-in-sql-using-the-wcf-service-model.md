---
title: 调用中使用 WCF 服务模型的 SQL 弱类型存储过程 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: aaf74a40-4c03-4a4a-9b91-c21babe154fa
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 3ec0b8b8d022b4e96a6df4d7c0d49d8176f6cd1a
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22225061"
---
# <a name="invoke-weakly-typed-stored-procedures-in-sql-using-the-wcf-service-model"></a>调用中使用 WCF 服务模型的 SQL 弱类型存储过程
当您调用下列出的过程**过程**中的节点[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]，输出为数组形式的数据集。 本主题提供有关如何创建 WCF 客户端来调用存储的过程返回的数据集数组的 SQL Server 中的说明。  
  
> [!NOTE]
>  如果您正在执行包含的用户定义类型的列的表上的操作，请确保您参考[对表和视图使用了 SQL 适配器的用户定义类型的操作](../../adapters-and-accelerators/adapter-sql/operations-on-tables-and-views-with-user-defined-types-using-the-sql-adapter.md)开始开发你的应用程序之前。  
  
## <a name="about-the-examples-used-in-this-topic"></a>有关在本主题中使用的示例  
 本主题中的示例使用 GET_EMP_DETAILS 存储过程。 此存储的过程采用雇员 ID 作为输入参数并返回具有该 ID 员工所有对应的列 通过运行这些示例使用提供的 SQL 脚本创建 GET_EMP_DETAILS 存储过程。 有关示例的详细信息，请参阅[适配器示例](../../adapters-and-accelerators/accelerator-rosettanet/adapter-samples.md)。 示例中， **Execute_StoredProc**，后者基于本主题中，还提供了与[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]示例。  
  
## <a name="the-wcf-client-class"></a>WCF 客户端类  
 为调用下的存储的过程生成 WCF 客户端的名称**过程**节点使用[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]下表中列出。  
  
|SQL Server 数据库项目|WCF 客户端名称|  
|----------------------------------|---------------------|  
|过程 (下**过程**节点)|Procedures_ [架构] 客户端|  
  
 [架构] 是该过程所属的架构;例如，"dbo"。  
  
### <a name="method-signature-for-invoking-stored-procedures"></a>调用存储的过程的方法签名  
 下表显示了要调用的存储的过程所公开的方法的签名。  
  
|运算|方法签名|  
|---------------|----------------------|  
|过程名称|System.Data.DataSet [] [procedure_name] (param1，param2，...\)|  
  
 [procedure_name] 是过程; 的名称例如 GET_EMP_DETAILS  
  
 例如，要调用 GET_EMP_DETAILS 过程的方法的签名所示下面的代码段。  
  
```  
public partial class Procedures_dboClient : System.ServiceModel.ClientBase<Procedures_dbo>, Procedures_dbo {  
  public System.Data.DataSet[] GET_EMP_DETAILS(System.Nullable<int> emp_id, out int ReturnValue);  
}  
```  
  
 在此代码段  
  
-   `Procedures_dboClient`是 WCF 客户端类的名称。 在此示例中，你可以使用此类创建客户端来调用存储的过程。  
  
-   `public System.Data.DataSet[] GET_EMP_DETAILS(System.Nullable<int> emp_id, out int ReturnValue)`是在此示例中调用的方法来调用存储的过程。 此存储的过程采用雇员 ID，并返回的数据集数组。  
  
## <a name="create-a-wcf-client-to-invoke-a-stored-procedure-in-sql-server"></a>创建 WCF 客户端来调用 SQL Server 中的存储的过程  
 泛型的执行 SQL Server 使用 WCF 客户端上的操作所需的操作集涉及到一组任务中所述[与适配器的 WCF 服务模型概述](overview-of-the-wcf-service-model-with-the-sql-adapter.md)。 具体而言，本部分介绍如何创建调用存储的过程，这是一个数据集的数组的结果集的 WCF 客户端。 在本主题中，例如，可以调用 GET_EMP_DETAILS 存储过程。 此存储的过程是通过运行与每个示例提供的 SQL 脚本创建的。  
  
  
1.  在 Visual Studio 中创建 Visual C# 项目。 有关本主题中，创建一个控制台应用程序。  
  
2.  生成 GET_EMP_DETAILS 存储过程的 WCF 客户端类。 请确保你选择在过程**过程**节点。 有关生成 WCF 客户端类的详细信息，请参阅[为 SQL Server 项目生成 WCF 客户端或 WCF 服务协定](generate-a-wcf-client-or-wcf-service-contract-for-sql-server-artifacts.md)。  
  
    > [!IMPORTANT]
    >  在生成 WCF 客户端类前, 请确保你设置**EnableBizTalkCompatibilityMode**绑定属性为 false。  
  
3.  在解决方案资源管理器，添加对引用`Microsoft.Adapters.Sql`和`Microsoft.ServiceModel.Channels`。  
  
4.  打开 Program.cs 文件并创建客户端，如下面的代码段中所述。  
  
    ```  
  
              Procedures_dboClient client = new Procedures_dboClient("SqlAdapterBinding_Procedures_dbo");  
  
    client.ClientCredentials.UserName.UserName = "<Enter username here>";  
    client.ClientCredentials.UserName.Password = "<Enter password here>";  
    ```  
  
     在此代码段，`Procedures_dboClient`是 SqlAdapterBindingClient.cs 中定义的 WCF 客户端。 此文件由生成[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]。 `SqlAdapterBinding_Procedures_dbo`是客户端终结点配置的名称，并在 app.config 中定义。此文件也会生成由[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]，其中包含的绑定属性和其他配置设置。  
  
    > [!NOTE]
    >  在此代码段中，你使用的绑定和终结点地址从配置文件。 你还可显式指定这些值在代码中。 指定客户端绑定的不同方法的详细信息，请参阅[为该 SQL 适配器配置客户端绑定](configure-a-client-binding-for-the-sql-adapter.md)。  
  
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
  
6.  调用 GET_EMP_DETAILS 存储过程。 调用 GET_EMP_DETAILS 过程之前，必须添加`System.Data`到你的代码的命名空间。  
  
    ```  
    DataSet[] dataArray;  
    int returnCode;  
  
    try  
    {  
       Console.WriteLine("Calling a stored procedure...");  
       dataArray = client.GET_EMP_DETAILS(10001, out returnCode);  //Invoke the stored procedure  
    }  
    catch (Exception ex)  
    {  
       Console.WriteLine("Exception: " + ex.Message);  
       throw;  
    }  
    Console.WriteLine("The details for the employee with ID '10001' are:");  
    Console.WriteLine("*************************************************");  
  
    foreach (DataSet dataSet in dataArray)  
    {  
       foreach (DataTable tab in dataArray[0].Tables)  
       {  
          foreach (DataRow row in tab.Rows)  
          {  
             for (int i = 0; i < tab.Columns.Count; i++)  
             {  
                Console.WriteLine(row[i]);  
             }  
          }  
       }  
    }  
    Console.WriteLine("*************************************************");  
  
    ```  
  
7.  关闭客户端，如下面的代码段中所述：  
  
    ```  
    client.Close();  
    Console.WriteLine("Press any key to exit...");  
    Console.ReadLine();  
    ```  
  
8.  生成项目，然后运行它。 员工，为你的产品详细信息
9.  ovided ID，将显示在控制台上。  
  
## <a name="see-also"></a>另请参阅  
[开发应用程序使用 WCF 服务模型](develop-sql-applications-using-the-wcf-service-model.md)