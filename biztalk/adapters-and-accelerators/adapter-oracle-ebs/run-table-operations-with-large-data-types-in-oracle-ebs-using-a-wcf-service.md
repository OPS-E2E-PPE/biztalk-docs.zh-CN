---
title: 完成对表包含 Oracle E-business Suite 使用 WCF 服务模型中的大型数据类型的操作 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 93ba3191-d234-424a-b2da-dcf384df4985
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 9869cd49ed09d80a866f3dcbb6f4b9429788339b
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36982558"
---
# <a name="complete-operations-on-tables-with-large-data-types-in-oracle-e-business-suite-using-the-wcf-service-model"></a>完成对表包含 Oracle E-business Suite 使用 WCF 服务模型中的大型数据类型的操作
[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]使适配器客户端能够执行对界面表和视图的较大的数据类型，如 BLOB、 CLOB、 NCLOB、 和 BFILE 操作。  

- 对于类型的列适配器 BLOB、 CLOB、 和 NCLOB，使客户端能够读取以及更新的数据。 该适配器公开 Read_\<*LOBColName* \>和 Update_\<*LOBColName* \>操作来读取和更新数据，其中\<*LOBColName* \>是较大的数据类型列的名称。 如果有多个大型数据类型列的单个接口表中，适配器将公开，因为许多读取和更新该表的接口的操作。  

- 对于类型 BFILE 列，适配器客户端只能读取的数据。 该适配器公开 Read_\<*LOBColName* \>操作从 BFILE 类型的列读取数据。 如果有多个大型数据类型列的单个接口表中，适配器将公开任意数量的读取操作的接口表。  

  有关这些操作的详细信息，请参阅[对界面表、 界面视图、 表和包含 LOB 数据的视图的操作](../../adapters-and-accelerators/adapter-oracle-ebs/read-and-update-on-interface-tables-and-views-with-large-object-data-types.md)。  

## <a name="about-the-examples-used-in-this-topic"></a>有关使用在本主题中的示例  
 本主题中的示例更新 CUSTOMER 数据库表中的 BLOB 列 （照片），然后从同一列中检索数据。 通过运行这些示例提供的脚本创建表。 有关示例的详细信息，请参阅[适用于 Oracle EBS 适配器示例](../../adapters-and-accelerators/adapter-oracle-ebs/samples-for-the-oracle-ebs-adapter.md)。 示例中， **LargeDataTypes_ServiceModel**，后者基于本主题中，还提供与[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]示例。  

> [!NOTE]
>  本主题列出了用于更新和读取基本的数据库表中的较大的数据类型的列的详细的任务。 用于更新和读取的接口表中的较大的数据类型的列，必须执行一组相同的任务。  

## <a name="the-wcf-client-class"></a>WCF 客户端类  
 对表具有通过大数据类型的操作生成的 WCF 客户端名称[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]基于下表中列出的表的名称。  


|     项目     |                     WCF 客户端名称                      |
|------------------|----------------------------------------------------------|
| 接口表 | [A p p _] InterfaceTables_*[SCHEMA]\\*[TABLE_NAME] 客户端 |

 [A p p _] = Oracle E-business Suite 应用程序; 的实际名称例如，查找。  

 [架构] = 集合的项目;例如，应用程序。  

 [TABLE_NAME] = 表; 的名称例如，MS_SAMPLE_EMPLOYEE。  

 [VIEW_NAME] = 视图; 的名称例如，MS_SAMPLE_EMPLOYEE_View。  

### <a name="method-signature-for-invoking-operations-on-tables"></a>调用表操作的方法签名  
 下表显示了对表的基本操作的方法签名。 签名是相同的视图，只不过视图命名空间和名称替换这些表。  

|运算|方法签名|  
|---------------|----------------------|  
|Update_\<*column_name*\>|public void Update_\<*column_name*\>（字符串筛选器，byte [] 的数据）;|  
|Read_\<*column_name*\>|公共 System.IO.Stream Read_\<*column_name*\>（字符串筛选器）;|  

 例如，下面的代码演示对应用程序架构下的客户数据库表的 Update_PHOTO 和 Read_PHOTO 操作生成的 WCF 客户端类的方法签名。  

```  
public partial class Tables_APPS_CUSTOMERClient : System.ServiceModel.ClientBase<Tables_APPS_CUSTOMER>, Tables_APPS_CUSTOMER {      

    public void Update_PHOTO(string FILTER, byte[] DATA);  

    public System.IO.Stream Read_PHOTO(string FILTER);  
}  
```  

 此代码片段**Tables_APPS_CUSTOMERClient**是 WCF 中的类的生成的 OracleEBSBindingClient.cs 名称[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]。 Update_PHOTO 和 Read_PHOTO 可以调用以更新和读取表中的较大的数据类型的列的方法。  

### <a name="parameters-for-table-operations"></a>用于表操作的参数  
 本部分提供了 Update_ 所需的参数\<*column_name* \>和 Read_\<*column_name* \>操作。  

|操作名称|Parameters|  
|--------------------|----------------|  
|Update_\<*column_name*\>|需要以下参数：<br /><br /> -   `string FILTER`. 此参数必须包含 where 子句表示针对其数据的更新的记录。 例如， `"WHERE Name='Mindy Martin'"`。<br />-   `byte[] DATA`. 包含要更新的大型数据类型列中数据的字节数组。|  
|Read_\<*column_name*\>|需要以下参数：<br /><br /> -   `string FILTER`. 此参数必须包含 where 子句，它表示具有要读取数据的记录。 例如， `"WHERE Name='Mindy Martin'"`。|  

## <a name="creating-a-wcf-client-to-invoke-operations-on-tables-with-columns-of-large-data-types"></a>创建 WCF 客户端来调用具有较大的数据类型的列的表操作  
 通用组执行对 Oracle E-business Suite 使用 WCF 客户端的操作所需的操作涉及到一组任务中所述[与 Oracle E-business Suite 适配器的 WCF 服务模型概述](../../adapters-and-accelerators/adapter-oracle-ebs/overview-of-the-wcf-service-model-with-the-oracle-e-business-suite-adapter.md)。 本部分介绍如何创建 WCF 客户端以调用 Update_PHOTO 和 Read_PHOTO 客户数据库表上的操作。  

#### <a name="to-create-a-wcf-client"></a>若要创建 WCF 客户端  

1. 在 Visual Studio 中创建一个 Visual C# 项目。 有关本主题中，创建一个控制台应用程序。  

2. 生成客户数据库表上的 Update_PHOTO 和 Read_PHOTO 操作的 WCF 客户端类。 有关生成 WCF 客户端类的详细信息，请参阅[生成 WCF 客户端或 WCF 服务协定为 Oracle E-business Suite 解决方案项目](../../adapters-and-accelerators/adapter-oracle-ebs/create-a-wcf-client-or-wcf-service-contract-for-oracle-ebs-solution-artifacts.md)。  

   > [!IMPORTANT]
   >  生成 WCF 客户端类之前，请确保设置**EnableBizTalkCompatibilityMode**属性绑定到 false。  

3. 在解决方案资源管理器，添加对引用`Microsoft.Adapters.OracleEBS`并`Microsoft.ServiceModel.Channels`， `System.Transactions`。  

4. 打开 Program.cs 文件并添加以下命名空间：  

   -   `Microsoft.Adapters.OracleEBS`  

   -   `System.ServiceModel`  

   -   `System.Transactions`  

   -   `System.IO`  

5. 打开 Program.cs 文件，如下面的代码段中所述创建客户端。  

   ```  

             Tables_APPS_CUSTOMERClient client = new Tables_APPS_CUSTOMERClient("OracleEBSBinding_Tables_APPS_CUSTOMER");  

   client.ClientCredentials.UserName.UserName = "<Enter user name here>";  
   client.ClientCredentials.UserName.Password = "<Enter password here>";  
   ```  

    在此代码段，`Tables_APPS_CUSTOMERClient`是 OracleEBSBindingClient.cs 中定义的 WCF 客户端。 此文件由生成[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]。  

   > [!NOTE]
   >  在此片段中，您可以使用的绑定和终结点地址从配置文件 app.config。在代码中，可以显式指定这些值。 指定客户端绑定的不同方法的详细信息，请参阅[配置客户端绑定适用于 Oracle E-business Suite](../../adapters-and-accelerators/adapter-oracle-ebs/configure-a-client-binding-for-the-oracle-e-business-suite.md)。  

6. 为客户端设置的凭据。  

   ```  
   client.ClientCredentials.UserName.UserName = "myuser";  
   client.ClientCredentials.UserName.Password = "mypassword";  
   ```  

   > [!IMPORTANT]
   >  在此示例中，正在执行对数据库表的操作。 但是，如果您正在执行对界面表的操作，则必须设置应用程序上下文通过指定相应的值**OracleUserName**， **OraclePassword**，和**OracleEBSResponsibilityName**绑定属性。 打开客户端之前，必须指定这些绑定属性。 有关应用程序上下文的详细信息，请参阅[设置应用程序上下文](../../adapters-and-accelerators/adapter-oracle-ebs/set-application-context.md)。  

7. 打开客户端，如下面的代码段中所述：  

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

8. 调用客户表上的 Update_PHOTO 操作。  

    Update_PHOTO 操作要求要更新的数据的字节数组。 在此代码片段中，使用 FileStream 类创建照片，SamplePhoto.jpg 的字节数组。 若要运行此应用程序，该文件必须复制到项目的 bin 目录。  

   > [!IMPORTANT]
   >  必须在事务中，执行 Update_PHOTO 操作因此**UseAmbientTransaction**绑定属性必须设置为**true**和 Update_PHOTO 操作必须在中执行事务作用域。 可以设置**UseAmbientTransaction**属性绑定在 app.config 中或通过显式将其设置为在应用程序中`binding.UseAmbientTransaction = true`。 请注意，是否您在代码中显式指定的绑定属性，则必须先完成才能打开客户端。  

   ```  
   byte[] photo;  

   using (FileStream fs = new FileStream("SamplePhoto.jpg", FileMode.Open))  
   {  
       try  
       {  
           Console.WriteLine("Reading the photo");  
           int count = 0;  
           photo = new byte[fs.Length];  
           while ((count += fs.Read(photo, count, (int)(((fs.Length - count) > 4096) ? 4096 : fs.Length - count))) < fs.Length) ;  
       }  
       catch(Exception ex)  
       {  
           Console.WriteLine("Exception: " + ex.Message);  
           throw;  
       }  
   }  

   Console.WriteLine("Updating data for the 'PHOTO' column");  
   // Invoking the Update_PHOTO operation inside a transaction scope  
   using (TransactionScope tx = new TransactionScope())  
   {  
       string filter = "WHERE Name='Mindy Martin'";  
       client.Update_PHOTO(filter, photo);  
       tx.Complete();  
   }  

   ```  

9. 调用客户表上的 Read_PHOTO 操作。  

     Read_PHOTO 提供 System.IO.Stream 窗体中的输出。 适配器客户端必须实现要从 Read_PHOTO 操作中读取数据的 FileStream 类。 Read_PHOTO 操作完成后，文件 PhotoCopy.jpg 复制项目的 bin 目录下。  

    ```  
    using (FileStream fs = new FileStream("PhotoCopy.jpg", FileMode.Create))  
    {  
        Console.WriteLine("Reading photo data");  
        String ReadFilter = "WHERE NAME='Mindy Martin'";  
        Stream photoStream = client.Read_PHOTO(ReadFilter);  
        Console.WriteLine("Photo data read -- writing to PhotoCopy.jpg");  

        int count;  
        int length = 0;  
        byte[] buffer = new byte[4096];  
        while ((count = photoStream.Read(buffer, 0, 4096)) > 0)  
        {  
            fs.Write(buffer, 0, count);  
            length+=count;  
        }  
        Console.WriteLine("{0} bytes written to PhotoCopy.jpg", length);  
    }  

    Console.WriteLine("Photo updated and read back -- Hit <RETURN> to end");  
    Console.ReadLine();  
    ```  

10. 关闭客户端，如下面的代码段中所述：  

    ```  
    client.Close();  
    Console.WriteLine("Press any key to exit...");  
    Console.ReadLine();  
    ```  

11. 生成项目，然后运行它。 应用程序更新照片的 CUSTOMER 表的列，然后读 PHOTO 列的内容。  

## <a name="see-also"></a>请参阅  
 [开发 Oracle E-business Suite 应用程序使用 WCF 服务模型](../../adapters-and-accelerators/adapter-oracle-ebs/develop-oracle-e-business-suite-applications-using-the-wcf-service-model.md)