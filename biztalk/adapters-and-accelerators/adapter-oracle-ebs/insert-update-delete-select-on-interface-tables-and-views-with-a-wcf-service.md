---
title: 插入、 更新、 删除或选择对界面表和视图使用 WCF 服务模型的操作 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: ae613c0e-4d9a-4c66-99e4-dd0443f1d495
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 2ed57328a925496449ddd73f3c363b32f60dc811
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36983470"
---
# <a name="insert-update-delete-or-select-operations-on-interface-tables-and-views-using-the-wcf-service-model"></a>插入、 更新、 删除或选择对界面表和视图使用 WCF 服务模型的操作
[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]找到一组基本的 Insert、 Select、 Update 和 Delete 操作上的接口表。 通过使用这些操作，你可以执行简单的 Insert、 Select、 Update 和 Delete 语句由目标接口表上的 WHERE 子句限定。 本主题将说明了如何使用 WCF 服务模型执行这些操作。  

> [!NOTE]
>  [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]支持仅选择界面视图上的操作。  

 有关适配器如何支持这些操作的详细信息，请参阅[对界面表和界面视图操作](../../adapters-and-accelerators/adapter-oracle-ebs/operations-on-interface-tables-and-interface-views.md)。  

## <a name="about-the-examples-used-in-this-topic"></a>有关使用在本主题中的示例  
 本主题中的示例执行 MS_SAMPLE_EMPLOYEE 接口表的操作。 通过运行这些示例提供的脚本创建表。 有关示例的详细信息，请参阅[适用于 Oracle EBS 适配器示例](../../adapters-and-accelerators/adapter-oracle-ebs/samples-for-the-oracle-ebs-adapter.md)。 示例中， **Interface_Table_Ops**，后者基于本主题中，还提供与[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]示例。  

## <a name="the-wcf-client-class"></a>WCF 客户端类  
 WCF 客户端生成的基本操作的名称，[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]可发现下表中列出基于表或视图的名称。  


|     项目     |                     WCF 客户端名称                      |
|------------------|----------------------------------------------------------|
| 接口表 | [A p p _] InterfaceTables_*[SCHEMA]\\*[TABLE_NAME] 客户端 |
| 界面视图  |  [A p p _] InterfaceViews_*[SCHEMA]\\*[VIEW_NAME] 客户端  |

 [A p p _] = Oracle E-business Suite 应用程序; 的实际名称例如，查找。  

 [架构] = 集合的项目;例如，应用程序。  

 [TABLE_NAME] = 表; 的名称例如，MS_SAMPLE_EMPLOYEE。  

 [VIEW_NAME] = 视图; 的名称例如，MS_SAMPLE_EMPLOYEE_View。  

### <a name="method-signature-for-invoking-operations-on-tables"></a>调用表操作的方法签名  
 下表显示了上一个表的基本操作的方法签名。 签名是相同的视图，只不过视图命名空间和名称替换这些表。  

|运算|方法签名|  
|---------------|----------------------|  
|Insert|字符串插入 (InsertRecord [记录集);|  
|选择|SelectRecord [] 选择 (string COLUMN_NAMES，字符串筛选器);|  
|Update|字符串更新 （UpdateRecord 记录集，筛选器字符串）;|  
|DELETE|字符串删除 （字符串筛选器）;|  

 例如，下面的代码演示生成的 WCF 客户端类的方法签名，删除操作，插入、 选择和更新的默认应用程序架构下的 MS_SAMPLE_EMPLOYEE 接口表的操作。  

```  
public partial class InterfaceTables_FND_APPS_MS_SAMPLE_EMPLOYEEClient : System.ServiceModel.ClientBase<InterfaceTables_FND_APPS_MS_SAMPLE_EMPLOYEE>, InterfaceTables_FND_APPS_MS_SAMPLE_EMPLOYEE {      
    public SelectRecord[] Select(string COLUMN_NAMES, string FILTER);  

    public string Insert(InsertRecord[] RECORDSET);  

    public string Update(UpdateRecord RECORDSET, string FILTER);  

    public string Delete(string FILTER);  
}  
```  

 此代码片段**InterfaceTables_FND_APPS_MS_SAMPLE_EMPLOYEEClient**是 WCF 中的类的生成的 OracleEBSBindingClient.cs 名称[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]。  

### <a name="parameters-for-table-operations"></a>用于表操作的参数  
 本部分提供了每个表操作所需的参数  

 **选择操作**  

|COLUMN_NAMES|FILTER|  
|-------------------|------------|  
|以逗号分隔的目标; 中的列名称列表例如，"EMP_NO，指定"。 列列表中指定的目标应在结果集中返回的列。 未指定列列表中的列将设置为其返回的记录集的.NET 默认值。 对于 nillable 列，此值是**null**。|指定查询; 的目标行的 WHERE 子句的内容例如，"名称 = Manager"。 可以将此参数设置为**null**返回目标的所有行。|  

 选择操作的返回值是强类型化结果集包含指定的列和行。  

 **插入操作**  

|插入操作类型|记录集|  
|---------------------------|---------------|  
|多个记录|应插入到表的 INSERTRECORDS 的集合。|  

 插入操作的返回值是插入的行数。  

 **更新操作**  

|记录集|FILTER|  
|---------------|------------|  
|应在表中更新的记录的集合。|指定查询; 的目标行的 WHERE 子句的内容例如，"名称 = Manager"。 可以将此参数设置为**null**返回目标的所有行。|  

 对于更新操作的返回值是更新的行数。  

 **删除操作**  

 删除操作将作为输入的 WHERE 子句，指定要删除的行。 删除操作的返回值是删除的行数。  

## <a name="creating-a-wcf-client-to-invoke-operations-on-interface-tables-and-interface-views"></a>创建 WCF 客户端调用操作的接口表和界面视图  
 通用组执行对 Oracle E-business Suite 使用 WCF 客户端的操作所需的操作涉及到一组任务中所述[与 Oracle E-business Suite 适配器的 WCF 通道模型概述](../../adapters-and-accelerators/adapter-oracle-ebs/overview-of-the-wcf-channel-model-with-the-oracle-e-business-suite-adapter.md)。 本部分介绍如何创建 WCF 客户端以调用基本的 Insert、 Select、 Update 在界面表的删除操作。  

#### <a name="to-create-a-wcf-client-to-perform-operations-on-tables"></a>若要创建 WCF 客户端以对表执行操作  

1. 在 Visual Studio 中创建一个 Visual C# 项目。 有关本主题中，创建一个控制台应用程序。  

2. 生成 WCF 客户端类的 Insert、 Select、 Update 和删除 MS_SAMPLE_EMPLOYEE 接口表上的操作。 有关生成 WCF 客户端类的详细信息，请参阅[生成 WCF 客户端或 WCF 服务协定为 Oracle E-business Suite 解决方案项目](../../adapters-and-accelerators/adapter-oracle-ebs/create-a-wcf-client-or-wcf-service-contract-for-oracle-ebs-solution-artifacts.md)。  

   > [!IMPORTANT]
   >  生成 WCF 客户端类之前，请确保设置**EnableBizTalkCompatibilityMode**属性绑定到 false。  

3. 在解决方案资源管理器，添加对引用`Microsoft.Adapters.OracleEBS`和`Microsoft.ServiceModel.Channels`。  

4. 打开 Program.cs 文件并添加以下命名空间：  

   -   `Microsoft.Adapters.OracleEBS`  

   -   `System.ServiceModel`  

5. 打开 Program.cs 文件，如下面的代码段中所述创建客户端。  

   ```  
   OracleEBSBinding binding = new OracleEBSBinding();  
   EndpointAddress address = new EndpointAddress("oracleebs://ebs_instance_name");  
   InterfaceTables_FND_APPS_MS_SAMPLE_EMPLOYEEClient client = new InterfaceTables_FND_APPS_MS_SAMPLE_EMPLOYEEClient(binding, address);  
   ```  

    在此代码段，`InterfaceTables_FND_APPS_MS_SAMPLE_EMPLOYEEClient`是 OracleEBSBindingClient.cs 中定义的 WCF 客户端。 此文件由生成[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]。  

   > [!NOTE]
   >  此代码片段显式应用程序代码中指定的绑定和终结点地址。 您可以使用这些值还生成的应用程序配置文件 app.config 文件中，从[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]。 指定客户端绑定的不同方法的详细信息，请参阅[配置客户端绑定适用于 Oracle E-business Suite](../../adapters-and-accelerators/adapter-oracle-ebs/configure-a-client-binding-for-the-oracle-e-business-suite.md)。  

6. 为客户端设置的凭据。  

   ```  
   client.ClientCredentials.UserName.UserName = "myuser";  
   client.ClientCredentials.UserName.Password = "mypassword";  
   ```  

7. 由于您正在执行的操作在界面表，必须设置应用程序上下文。 在此示例中，若要设置应用程序上下文中，您指定**OracleUserName**， **OraclePassword**，并**OracleEBSResponsibilityName**绑定属性。 有关应用程序上下文的详细信息，请参阅[设置应用程序上下文](../../adapters-and-accelerators/adapter-oracle-ebs/set-application-context.md)。  

   ```  
   binding.OracleUserName = "myOracleEBSUserName";  
   binding.OraclePassword = "myOracleEBSPassword";  
   binding.OracleEBSResponsibilityName = "myOracleEBSResponsibility";  
   ```  

8. 打开客户端，如下面的代码段中所述：  

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

9. 调用 MS_SAMPLE_EMPLOYEE 表上的插入操作。  

    ```  
    Console.WriteLine("The application will insert a record in the MS_SAMPLE_EMPLOYEE interface table");  

    // The date values cannot contain time zone information. Hence, you must use  
    // DateTimeKind.Unspecified to not include the time zone information.  
    DateTime date = new DateTime(DateTime.Now.Ticks, DateTimeKind.Unspecified);  

    string result;  

    InsertRecord[] recordSet = new InsertRecord[1];  

    EMP_NO__COMPLEX_TYPE emp_no = new EMP_NO__COMPLEX_TYPE();  
    emp_no.Value = "10007";  

    NAME__COMPLEX_TYPE name = new NAME__COMPLEX_TYPE();  
    name.Value = "John Smith";  

    DESIGNATION__COMPLEX_TYPE desig = new DESIGNATION__COMPLEX_TYPE();  
    desig.Value = "Manager";  

    SALARY__COMPLEX_TYPE salary = new SALARY__COMPLEX_TYPE();  
    salary.Value = "500000";  

    JOIN_DATE__COMPLEX_TYPE doj = new JOIN_DATE__COMPLEX_TYPE();  
    doj.Value = date;  

    recordSet[0] = new InsertRecord();  
    recordSet[0].EMP_NO = emp_no;  
    recordSet[0].NAME = name;  
    recordSet[0].DESIGNATION = desig;  
    recordSet[0].SALARY = salary;  
    recordSet[0].JOIN_DATE = doj;  

    try  
    {  
       result = client.Insert(recordSet);   
    }  
    catch (Exception ex)  
    {  
       Console.WriteLine("Exception: " + ex.Message);  
       throw;  
    }  

    Console.WriteLine("Number of records inserted= " + result);  
    Console.WriteLine("Press any key to continue...");  
    Console.ReadLine();  

    ```  

     您可以替换上述代码段中执行 Select、 Update 或 Delete 操作。 也可以附加代码片段，可在单个应用程序中执行所有操作。 有关如何执行这些操作的代码片段，请参阅[选择操作](#BKMK_Select)，[更新操作](#BKMK_Update)，并[删除操作](#BKMK_Delete)分别。  

10. 关闭客户端，如下面的代码段中所述：  

    ```  
    client.Close();  
    Console.WriteLine("Press any key to exit...");  
    Console.ReadLine();  
    ```  

11. 生成项目，然后运行它。 应用程序在 MS_SAMPLE_EMPLOYEE 表中插入一条记录。  

###  <a name="BKMK_Select"></a> 选择操作  
 下面的代码演示了面向 MS_SAMPLE_EMPLOYEE 接口表的选择操作。 选择操作选择插入到表中的最后一个记录。 返回的记录写入到控制台。  

```  
Console.WriteLine("The application will now select the last inserted record");  
SelectRecord[] selectRecords;  
try  
{  
   selectRecords = client.Select("*", "WHERE EMP_NO LIKE 10007");  
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
   Console.WriteLine("Employee ID         : " + selectRecords[i].EMP_NO);  
   Console.WriteLine("Employee Name       : " + selectRecords[i].NAME);  
   Console.WriteLine("Employee Desigation : " + selectRecords[i].DESIGNATION);  
   Console.WriteLine("Employee Salary     : " + selectRecords[i].SALARY);  
   Console.WriteLine();  
}  
Console.WriteLine("********************************************");  
Console.WriteLine("Press any key to continue ...");  
Console.ReadLine();  
```  

###  <a name="BKMK_Update"></a> 更新操作  
 下面的代码演示了面向 MS_SAMPLE_EMPLOYEE 接口表的更新操作。  

```  
Console.WriteLine("The application will now update the employee name in the newly inserted record");  
string recordsUpdated;  
UpdateRecord updateRecordSet = new UpdateRecord();  
updateRecordSet.NAME = "Tom Smith";  
updateRecordSet.DESIGNATION = "Accountant";  

try  
{  
   recordsUpdated = client.Update(updateRecordSet, "WHERE EMP_NO LIKE 10007");  
}  
catch (Exception ex)  
{  
   Console.WriteLine("Exception: " + ex.Message);  
   throw;  
}  

Console.WriteLine("No of records updated: " + recordsUpdated);  
Console.WriteLine("Press any key to continue...");  
Console.ReadLine();  
```  

###  <a name="BKMK_Delete"></a> 删除操作  
 下面的代码演示了面向 MS_SAMPLE_EMPLOYEE 接口表的删除操作。  

```  
Console.WriteLine("The sample will now delete the record that it first inserted");  
string deletedRecords;  
try  
{  
   deletedRecords = client.Delete("WHERE EMP_NO LIKE 10007");  
}  
catch (Exception ex)  
{  
   Console.WriteLine("Exception: " + ex.Message);  
   throw;  
}  
Console.WriteLine("No of records deleted: " + deletedRecords);  
Console.WriteLine("Press any key to exit...");  
Console.ReadLine();  
```  

## <a name="see-also"></a>请参阅  
 [开发 Oracle E-business Suite 应用程序使用 WCF 服务模型](../../adapters-and-accelerators/adapter-oracle-ebs/develop-oracle-e-business-suite-applications-using-the-wcf-service-model.md)