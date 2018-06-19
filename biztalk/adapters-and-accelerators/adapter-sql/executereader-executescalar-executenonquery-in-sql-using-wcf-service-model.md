---
title: ExecuteReader、 ExecuteScalar 或 ExecuteNonQuery SQL 使用 WCF 服务模型中的操作 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 62f166af-b657-491b-b20d-1ae7886f27ce
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f886463e2b38b358e5f6a9da8b7e67aabdc9c3ef
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22224645"
---
# <a name="executereader-executescalar-or-executenonquery-operations-in-sql-using-wcf-service-model"></a>ExecuteReader、 ExecuteScalar 或 ExecuteNonQuery SQL 使用 WCF 服务模型中的操作
[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]如公开泛型的 SQL Server 操作**ExecuteNonQuery**， **ExecuteReader**，和**ExecuteScalar**。 这些操作可用于 SQL Server 数据库执行任何 SQL 语句。 这些操作因响应为 SQL 语句所获取的类型而异。 有关如何适配器支持这些操作的详细信息，请参阅[支持 ExecuteNonQuery、 ExecuteReader 和 ExecuteScalar 操作](../../adapters-and-accelerators/adapter-oracle-ebs/support-for-executenonquery-executereader-and-executescalar-operations.md)。  
  
 本主题演示如何执行**ExecuteReader**操作使用[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]使用 WCF 服务模型。 你可以按照同一套执行本主题中所述的过程**ExecuteNonQuery**和**ExecuteScalar**操作。  
  
## <a name="about-the-examples-used-in-this-topic"></a>有关在本主题中使用的示例  
 本主题中的示例使用**ExecuteReader**操作执行 ADD_EMP_DETAILS 存储过程。 此存储的过程将记录添加到员工表，并返回记录的员工 ID。 通过运行这些示例使用提供的 SQL 脚本创建 ADD_EMP_DETAILS 存储过程。 有关示例的详细信息，请参阅[适配器示例](../../adapters-and-accelerators/accelerator-rosettanet/adapter-samples.md)。 示例中， **Execute_Reader**，后者基于本主题中，还提供了与[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]示例。  
  
## <a name="the-wcf-client-class"></a>WCF 客户端类  
 调用泛型操作 （ExecuteNonQuery、 ExecuteReader 或 ExecuteScalar） 使用的生成 WCF 客户端的名称[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]下表中列出。  
  
|操作|WCF 客户端名称|  
|----------------|---------------------|  
|ExecuteNonQuery、 ExecuteReader 或 ExecuteScalar|GenericTableOpClient|  
  
### <a name="method-signature-for-invoking-generic-operations"></a>调用泛型操作的方法签名  
 下表显示了要调用的泛型操作所公开的方法的签名。  
  
|运算|方法签名|  
|---------------|----------------------|  
|ExecuteNonQuery|int ExecuteNonQuery （字符串查询）|  
|ExecuteReader|System.Data.DataSet [] ExecuteReader （字符串查询）|  
|ExecuteScalar|字符串 ExecuteScalar(string Query)|  
  
 例如，泛型操作方法的签名所示下面的代码段。  
  
```  
public partial class GenericTableOpClient : System.ServiceModel.ClientBase<GenericTableOp>, GenericTableOp {  
  public int ExecuteNonQuery(string Query);  
  public System.Data.DataSet[] ExecuteReader(string Query);  
  public string ExecuteScalar(string Query);  
}  
```  
  
 在此代码段  
  
-   `GenericTableOpClient`是类的名称。 在此示例中，你可以使用此类创建客户端以调用的泛型操作，ExecuteReader。  
  
-   `public System.Data.DataSet[] ExecuteReader(string Query)`是你在此示例中调用 ADD_EMP_DETAILS 调用的方法存储过程。  
  
## <a name="creating-a-wcf-client-to-invoke-an-executereader-operation"></a>创建 WCF 客户端以调用 ExecuteReader 操作  
 泛型的执行 SQL Server 使用 WCF 客户端上的操作所需的操作集涉及到一组任务中所述[与 SQL 适配器的 WCF 通道模型概述](../../adapters-and-accelerators/adapter-sql/overview-of-the-wcf-channel-model-with-the-sql-adapter.md)。 本节具体介绍如何创建时，将调用一个 WCF 客户端**ExecuteReader**操作执行 ADD_EMP_DETAILS 存储过程。 此存储的过程是通过运行与每个示例提供的 SQL 脚本创建的。  
  
#### <a name="to-create-a-wcf-client-to-invoke-executereader-operation"></a>若要创建 WCF 客户端以调用 ExecuteReader 操作  
  
1.  在 Visual Studio 中创建 Visual C# 项目。 有关本主题中，创建一个控制台应用程序。  
  
2.  生成的 WCF 客户端类**ExecuteReader**泛型操作。 当你连接到 SQL Server 数据库使用时，此操作才可用根节点下[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]。 有关生成 WCF 客户端类的详细信息，请参阅[为 SQL Server 项目生成 WCF 客户端或 WCF 服务协定](../../adapters-and-accelerators/adapter-sql/generate-a-wcf-client-or-wcf-service-contract-for-sql-server-artifacts.md)。  
  
    > [!IMPORTANT]
    >  在生成 WCF 客户端类前, 请确保你设置**EnableBizTalkCompatibilityMode**绑定属性为 false。  
  
3.  在解决方案资源管理器，添加对引用`Microsoft.Adapters.Sql`和`Microsoft.ServiceModel.Channels`。  
  
4.  打开 Program.cs 文件并创建客户端，如下面的代码段中所述。  
  
    ```  
  
            GenericTableOpClient client = new GenericTableOpClient("SqlAdapterBinding_GenericTableOp");  
    client.ClientCredentials.UserName.UserName = "<Enter username here>";  
    client.ClientCredentials.UserName.Password = "<Enter password here>";  
    ```  
  
     在此代码段，`GenericTableOpClient`是 SqlAdapterBindingClient.cs 中定义的 WCF 客户端。 此文件由生成[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]。 `SqlAdapterBinding_GenericTableOp`是客户端终结点配置的名称，并在 app.config 中定义。此文件也会生成由[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]，其中包含的绑定属性和其他配置设置。  
  
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
  
6.  调用**ExecuteReader** ADD_EMP_DETAILS 操作存储过程。 调用 ExecuteReader 操作之前，必须添加`System.Data`到你的代码的命名空间。  
  
    ```  
    string query = "EXEC ADD_EMP_DETAILS 'Tom Smith', 'Manager', 500000";  
    DataSet[] dsArray = client.ExecuteReader(query);  
  
    Console.WriteLine("Invoking the ADD_EMP_DETAILS stored procedure using ExecuteReader");  
    Console.WriteLine("*****************************************************");  
    foreach (DataSet dataSet in dsArray)  
    {  
       foreach (DataTable tab in dsArray[0].Tables)  
       {  
           foreach (DataRow row in tab.Rows)  
           {  
              for (int i = 0; i < tab.Columns.Count; i++)  
              {  
                 Console.WriteLine("The ID for the newly added employee is : " + row[i]);  
              }  
           }  
        }  
    }  
    Console.WriteLine("*****************************************************");  
  
    ```  
  
7.  关闭客户端，如下面的代码段中所述：  
  
    ```  
    client.Close();  
    Console.WriteLine("Press any key to exit...");  
    Console.ReadLine();  
    ```  
  
8.  生成项目，然后运行它。 新插入的员工的员工 ID 显示在控制台中。