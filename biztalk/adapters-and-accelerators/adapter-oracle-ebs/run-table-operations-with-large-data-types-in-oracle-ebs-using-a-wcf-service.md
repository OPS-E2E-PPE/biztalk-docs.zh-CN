---
title: 完成对表中使用 WCF 服务模型的 Oracle E-business Suite 的较大的数据类型的操作 |Microsoft 文档
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
ms.openlocfilehash: 720da748059d3fe3da376ea42495a2587577f5ee
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/28/2017
ms.locfileid: "25967587"
---
# <a name="complete-operations-on-tables-with-large-data-types-in-oracle-e-business-suite-using-the-wcf-service-model"></a>完成对表中使用 WCF 服务模型的 Oracle E-business Suite 的较大的数据类型的操作
[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]使适配器客户端可以执行对接口表和视图的较大的数据类型，如 BLOB、 CLOB、 NCLOB、 和 BFILE 操作。  
  
-   列类型的适配器 BLOB、 CLOB、 和 NCLOB，使客户端可以读取，以及更新数据。 适配器公开 Read_\<*LOBColName* \>和 Update_\<*LOBColName* \>操作来读取和更新数据分别，其中\<*LOBColName* \>是具有较大的数据类型列的名称。 如果没有具有单个接口表中的较大的数据类型的多个列，适配器将公开为许多读取和更新接口该表的操作。  
  
-   对于类型 BFILE 列，适配器客户端只能读取的数据。 适配器公开 Read_\<*LOBColName* \>操作从 BFILE 类型的列读取数据。 如果没有具有单个接口表中的较大的数据类型的多个列，该适配器将公开许多读取接口表的操作。  
  
 有关这些操作的详细信息，请参阅[接口表、 界面视图、 表和包含 LOB 数据的视图上的操作](../../adapters-and-accelerators/adapter-oracle-ebs/read-and-update-on-interface-tables-and-views-with-large-object-data-types.md)。  
  
## <a name="about-the-examples-used-in-this-topic"></a>有关在本主题中使用的示例  
 本主题中的示例更新的客户数据库表中的 BLOB 列 （照片），然后从同一列中检索数据。 通过运行这些示例使用提供的脚本创建表。 有关示例的详细信息，请参阅[Oracle EBS 适配器的示例](../../adapters-and-accelerators/adapter-oracle-ebs/samples-for-the-oracle-ebs-adapter.md)。 示例中， **LargeDataTypes_ServiceModel**，后者基于本主题中，还提供了与[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]示例。  
  
> [!NOTE]
>  本主题列出更新和读取基数据库表中的较大的数据类型的列的详细的任务。 你必须为更新和读取列接口表中的大型数据类型执行相同的任务集。  
  
## <a name="the-wcf-client-class"></a>WCF 客户端类  
 为具有较大的数据类型由对表操作生成 WCF 客户端的名称[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]基于表的名称，如以下表中列出。  
  
|项目|WCF 客户端名称|  
|--------------|---------------------|  
|接口表|InterfaceTables_ [APP_NAME] _ [架构]\_[TABLE_NAME] 客户端|  
  
 [APP_NAME] = Oracle E-business Suite 应用程序; 实际名称例如，查找。  
  
 [架构] = 项目; 的集合例如，应用程序。  
  
 [TABLE_NAME] = 表; 的名称例如，MS_SAMPLE_EMPLOYEE。  
  
 [VIEW_NAME] = 视图; 的名称例如，MS_SAMPLE_EMPLOYEE_View。  
  
### <a name="method-signature-for-invoking-operations-on-tables"></a>调用对表的操作的方法签名  
 下表显示对表的基本操作的方法签名。 签名是相同的视图，只不过视图命名空间和名称替换那些表。  
  
|运算|方法签名|  
|---------------|----------------------|  
|Update_\<*column_name*\>|公共 void Update_\<*column_name*\>（字符串筛选器，byte [] 数据）;|  
|Read_\<*column_name*\>|公共 System.IO.Stream Read_\<*column_name*\>（字符串筛选器）;|  
  
 例如，下面的代码演示的方法签名的应用程序架构下的客户数据库表上的 Update_PHOTO 和 Read_PHOTO 操作生成的 WCF 客户端类。  
  
```  
public partial class Tables_APPS_CUSTOMERClient : System.ServiceModel.ClientBase<Tables_APPS_CUSTOMER>, Tables_APPS_CUSTOMER {      
  
    public void Update_PHOTO(string FILTER, byte[] DATA);  
  
    public System.IO.Stream Read_PHOTO(string FILTER);  
}  
```  
  
 在此代码段， **Tables_APPS_CUSTOMERClient**是 WCF 中的类的生成的 OracleEBSBindingClient.cs 名称[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]。 Update_PHOTO 和 Read_PHOTO 是可以调用更新和读取表中的较大的数据类型的列的方法。  
  
### <a name="parameters-for-table-operations"></a>参数用于表操作  
 本部分提供所需的 Update_ 参数\<*column_name* \>和 Read_\<*column_name* \>操作。  
  
|操作名称|Parameters|  
|--------------------|----------------|  
|Update_\<*column_name*\>|需要以下参数：<br /><br /> -   `string FILTER`. 此参数必须包含 where 子句指示针对其数据的更新的记录。 例如， `"WHERE Name='Mindy Martin'"`。<br />-   `byte[] DATA`. 包含要更新的大型数据类型列中的数据的字节数组。|  
|Read_\<*column_name*\>|需要以下参数：<br /><br /> -   `string FILTER`. 此参数必须包含 where 子句，它表示具有要读取数据的记录。 例如， `"WHERE Name='Mindy Martin'"`。|  
  
## <a name="creating-a-wcf-client-to-invoke-operations-on-tables-with-columns-of-large-data-types"></a>创建 WCF 客户端来调用对具有较大的数据类型的列的表的操作  
 泛型组执行对 Oracle E-business Suite 使用 WCF 客户端的操作所需的操作涉及到一组任务中所述[与 Oracle E-business Suite 适配器的 WCF 服务模型概述](../../adapters-and-accelerators/adapter-oracle-ebs/overview-of-the-wcf-service-model-with-the-oracle-e-business-suite-adapter.md)。 本部分介绍如何创建 WCF 客户端来调用 Update_PHOTO 和 Read_PHOTO 客户数据库表上的操作。  
  
#### <a name="to-create-a-wcf-client"></a>若要创建 WCF 客户端  
  
1.  在 Visual Studio 中创建 Visual C# 项目。 有关本主题中，创建一个控制台应用程序。  
  
2.  生成 WCF 客户端类上的客户数据库表的 Update_PHOTO 和 Read_PHOTO 操作。 有关生成 WCF 客户端类的详细信息，请参阅[生成 WCF 客户端或 Oracle E-business Suite 解决方案项目关联的 WCF 服务协定](../../adapters-and-accelerators/adapter-oracle-ebs/create-a-wcf-client-or-wcf-service-contract-for-oracle-ebs-solution-artifacts.md)。  
  
    > [!IMPORTANT]
    >  在生成 WCF 客户端类前, 请确保你设置**EnableBizTalkCompatibilityMode**绑定属性为 false。  
  
3.  在解决方案资源管理器，添加对引用`Microsoft.Adapters.OracleEBS`和`Microsoft.ServiceModel.Channels`， `System.Transactions`。  
  
4.  打开 Program.cs 文件并添加以下命名空间：  
  
    -   `Microsoft.Adapters.OracleEBS`  
  
    -   `System.ServiceModel`  
  
    -   `System.Transactions`  
  
    -   `System.IO`  
  
5.  打开 Program.cs 文件并创建客户端，如下面的代码段中所述。  
  
    ```  
  
              Tables_APPS_CUSTOMERClient client = new Tables_APPS_CUSTOMERClient("OracleEBSBinding_Tables_APPS_CUSTOMER");  
  
    client.ClientCredentials.UserName.UserName = "<Enter user name here>";  
    client.ClientCredentials.UserName.Password = "<Enter password here>";  
    ```  
  
     在此代码段，`Tables_APPS_CUSTOMERClient`是 OracleEBSBindingClient.cs 中定义的 WCF 客户端。 此文件由生成[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]。  
  
    > [!NOTE]
    >  在此代码段，你可以使用的绑定和终结点地址从配置文件 app.config。你还可显式指定这些值在代码中。 指定客户端绑定的不同方法的详细信息，请参阅[配置客户端绑定 Oracle E-business Suite](../../adapters-and-accelerators/adapter-oracle-ebs/configure-a-client-binding-for-the-oracle-e-business-suite.md)。  
  
6.  为客户端设置的凭据。  
  
    ```  
    client.ClientCredentials.UserName.UserName = "myuser";  
    client.ClientCredentials.UserName.Password = "mypassword";  
    ```  
  
    > [!IMPORTANT]
    >  在此示例中，你将要对数据库表的操作。 但是，如果您正在执行对接口表的操作，则必须设置应用程序上下文通过指定的相应值**OracleUserName**， **OraclePassword**，和**OracleEBSResponsibilityName**绑定属性。 打开客户端之前，必须指定这些绑定属性。 有关应用程序上下文的详细信息，请参阅[设置应用程序上下文](../../adapters-and-accelerators/adapter-oracle-ebs/set-application-context.md)。  
  
7.  下面的代码段中所述，请打开客户端：  
  
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
  
8.  调用对 CUSTOMER 表的 Update_PHOTO 操作。  
  
     Update_PHOTO 操作需要要更新的数据的字节数组。 在此代码段中，你可以使用 FileStream 类创建的照片，SamplePhoto.jpg 的字节数组。 此应用程序工作，必须文件复制到项目的 bin 目录中。  
  
    > [!IMPORTANT]
    >  Update_PHOTO 操作必须执行在事务中，因此**UseAmbientTransaction**绑定属性必须设置为**true** ，必须在执行该 Update_PHOTO 操作事务范围。 你可以设置**UseAmbientTransaction** app.config 中或通过将其显式设置为应用程序中绑定属性`binding.UseAmbientTransaction = true`。 请注意，是否您在代码中显式指定的绑定属性，则必须这样在打开客户端之前。  
  
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
  
9. 调用对 CUSTOMER 表的 Read_PHOTO 操作。  
  
     Read_PHOTO 提供 System.IO.Stream 形式的输出。 适配器客户端必须实现 FileStream 类来从 Read_PHOTO 操作中读取数据。 Read_PHOTO 操作完成后，文件 PhotoCopy.jpg 复制项目的 bin 目录下。  
  
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
  
11. 生成项目，然后运行它。 应用程序更新 CUSTOMER 表的照片列，然后读照片列的内容。  
  
## <a name="see-also"></a>另请参阅  
 [开发 Oracle E-business Suite 应用程序使用 WCF 服务模型](../../adapters-and-accelerators/adapter-oracle-ebs/develop-oracle-e-business-suite-applications-using-the-wcf-service-model.md)