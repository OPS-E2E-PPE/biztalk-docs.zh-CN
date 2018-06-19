---
title: ExecuteReader、 ExecuteScalar 或 ExecuteNonQuery 操作中使用 WCF 服务模型的 Oracle E-business Suite |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 54c42db1-9a4d-4003-af69-f75ff48b575a
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: eaffcdc59cd6093feababc8319c1f9f1964a0d05
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22217381"
---
# <a name="executereader-executescalar-or-executenonquery-operations-in-oracle-e-business-suite-using-the-wcf-service-model"></a>在使用 WCF 服务模型的 Oracle E-business Suite ExecuteReader、 ExecuteScalar 或 ExecuteNonQuery 操作
[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]如公开泛型操作**ExecuteNonQuery**， **ExecuteReader**，和**ExecuteScalar**。 这些操作可用于在 Oracle E-business Suite 上执行任何语句。 这些操作因响应为语句所获取的类型而异。 有关如何适配器支持这些操作的详细信息，请参阅[支持 ExecuteNonQuery、 ExecuteReader 和 ExecuteScalar 操作](../../adapters-and-accelerators/adapter-oracle-ebs/support-for-executenonquery-executereader-and-executescalar-operations.md)。  
  
 本主题演示如何执行**ExecuteReader**操作使用[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]使用 WCF 服务模型。 你可以按照同一套执行本主题中所述的过程**ExecuteNonQuery**和**ExecuteScalar**操作。  
  
## <a name="about-the-examples-used-in-this-topic"></a>有关在本主题中使用的示例  
 本主题中的示例执行**ExecuteReader**操作以执行 MS_SAMPLE_EMPLOYEE 接口表选择操作。 通过运行这些示例使用提供的脚本创建表。 有关示例的详细信息，请参阅[Oracle EBS 适配器的示例](../../adapters-and-accelerators/adapter-oracle-ebs/samples-for-the-oracle-ebs-adapter.md)。 示例中， **ExecuteReader**，后者基于本主题中，还提供了与[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]示例。  
  
## <a name="the-wcf-client-class"></a>WCF 客户端类  
 调用泛型操作 （ExecuteNonQuery、 ExecuteReader 或 ExecuteScalar） 使用的生成 WCF 客户端的名称[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]下表中列出。  
  
|操作|WCF 客户端名称|  
|----------------|---------------------|  
|ExecuteNonQuery、 ExecuteReader 或 ExecuteScalar|GenericOperation_Client|  
  
### <a name="method-signature-for-invoking-generic-operations"></a>调用泛型操作的方法签名  
 下表显示了要调用的泛型操作所公开的方法的签名。  
  
|运算|方法签名|  
|---------------|----------------------|  
|ExecuteNonQuery|int ExecuteNonQuery （字符串查询，string [] OutputRefCursorNames，出 System.Data.DataSet [] OutputRefCursors）|  
|ExecuteReader|System.Data.DataSet ExecuteReader(string Query)|  
|ExecuteScalar|字符串 ExecuteScalar(string Query)|  
  
 例如，泛型操作方法的签名所示下面的代码段。  
  
```  
public partial class GenericOperation_Client : System.ServiceModel.ClientBase<GenericOperation_>, GenericOperation_ {  
  public int ExecuteNonQuery(string Query, string[] OutputRefCursorNames, out System.Data.DataSet[] OutputRefCursors);  
  public System.Data.DataSet ExecuteReader(string Query);  
  public string ExecuteScalar(string Query);  
}  
```  
  
 在此代码段  
  
-   `GenericOperation_Client`是类的名称。 此类用于创建客户端以调用的泛型操作，ExecuteReader。  
  
-   `public System.Data.DataSet ExecuteReader(string Query)`是调用 MS_SAMPLE_EMPLOYEE 接口表上执行的 SELECT 语句的方法。  
  
## <a name="creating-a-wcf-client-to-invoke-an-executereader-operation"></a>创建 WCF 客户端以调用 ExecuteReader 操作  
 泛型组执行对 Oracle E-business Suite 使用 WCF 客户端的操作所需的操作涉及到一组任务中所述[与 Oracle E-business Suite 适配器的 WCF 服务模型概述](../../adapters-and-accelerators/adapter-oracle-ebs/overview-of-the-wcf-service-model-with-the-oracle-e-business-suite-adapter.md)。 本部分介绍如何创建 WCF 客户端来调用**ExecuteReader**操作。  
  
#### <a name="to-create-a-wcf-client-to-invoke-executereader-operation"></a>若要创建 WCF 客户端以调用 ExecuteReader 操作  
  
1.  在 Visual Studio 中创建 Visual C# 项目。 有关本主题中，创建一个控制台应用程序。  
  
2.  生成的 WCF 客户端类**ExecuteReader**泛型操作。 此操作时，位于根节点下你连接到 Oracle E-business Suite 使用[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]。 有关生成 WCF 客户端类的详细信息，请参阅[生成 WCF 客户端或 Oracle E-business Suite 解决方案项目关联的 WCF 服务协定](../../adapters-and-accelerators/adapter-oracle-ebs/create-a-wcf-client-or-wcf-service-contract-for-oracle-ebs-solution-artifacts.md)。  
  
    > [!IMPORTANT]
    >  在生成 WCF 客户端类前, 请确保你设置**EnableBizTalkCompatibilityMode**绑定属性为 false。  
  
3.  在解决方案资源管理器，添加对引用`Microsoft.Adapters.OracleEBS`和`Microsoft.ServiceModel.Channels`。  
  
4.  打开 Program.cs 文件并添加以下命名空间：  
  
    -   `Microsoft.Adapters.OracleEBS`  
  
    -   `System.ServiceModel`  
  
5.  在 Program.cs 文件中，如下面的代码段中所述创建客户端。  
  
    ```  
    OracleEBSBinding binding = new OracleEBSBinding();  
    EndpointAddress address = new EndpointAddress("oracleebs://ebs-72-11");  
    GenericOperation_Client client = new GenericOperation_Client(binding, address);  
    ```  
  
     在此代码段，`GenericOperation_Client`是 OracleEBSBindingClient.cs 中定义的 WCF 客户端。 此文件由生成[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]。  
  
    > [!NOTE]
    >  在此代码段，则显式应用程序代码中指定的绑定和终结点地址。 你可以从还生成的应用程序配置文件 app.config，使用这些值[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]。 有关指定客户端绑定的不同方法的详细信息，请参阅[配置客户端绑定 Oracle E-business Suite](../../adapters-and-accelerators/adapter-oracle-ebs/configure-a-client-binding-for-the-oracle-e-business-suite.md)。  
  
6.  为客户端设置的凭据。  
  
    ```  
    client.ClientCredentials.UserName.UserName = "myuser";  
    client.ClientCredentials.UserName.Password = "mypassword";  
    ```  
  
7.  由于您正在执行对接口表的操作，必须设置应用程序上下文。 在此示例中，若要设置应用程序上下文中，你指定**OracleUserName**， **OraclePassword**，和**OracleEBSResponsibilityName**绑定属性。 有关应用程序上下文的详细信息，请参阅[设置应用程序上下文](../../adapters-and-accelerators/adapter-oracle-ebs/set-application-context.md)。  
  
    ```  
    binding.OracleUserName = "myOracleEBSUserName";  
    binding.OraclePassword = "myOracleEBSPassword";  
    binding.OracleEBSResponsibilityName = "myOracleEBSResponsibility";  
    ```  
  
8.  下面的代码段中所述，请打开客户端：  
  
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
  
9. 调用**ExecuteReader**执行 MS_SAMPLE_EMPLOYEE 表上的选择操作的操作。 调用 ExecuteReader 操作之前，必须添加`System.Data`到你的代码的命名空间。  
  
    ```  
    string query = "SELECT * FROM MS_SAMPLE_EMPLOYEE";  
    DataSet ds = client.ExecuteReader(query);  
  
    Console.WriteLine("Invoking the SELECT statement using ExecuteReader");  
    Console.WriteLine("*****************************************************");  
    foreach (DataTable tab in ds.Tables)  
    {  
       foreach (DataRow row in tab.Rows)  
       {  
          Console.WriteLine("The details of the employee are: ");  
          for (int i = 0; i < tab.Columns.Count; i++)  
          {  
             Console.WriteLine(row[i]);  
          }  
          Console.WriteLine();  
       }  
    }  
    Console.WriteLine("*****************************************************");  
    Console.ReadLine();  
  
    ```  
  
10. 关闭客户端，如下面的代码段中所述：  
  
    ```  
    client.Close();  
    Console.WriteLine("Press any key to exit...");  
    Console.ReadLine();  
    ```  
  
11. 生成项目，然后运行它。 在控制台上显示 MS_SAMPLE_EMPLOYEE 表中的所有记录。  
  
## <a name="see-also"></a>另请参阅  
 [开发 Oracle E-business Suite 应用程序使用 WCF 服务模型](../../adapters-and-accelerators/adapter-oracle-ebs/develop-oracle-e-business-suite-applications-using-the-wcf-service-model.md)