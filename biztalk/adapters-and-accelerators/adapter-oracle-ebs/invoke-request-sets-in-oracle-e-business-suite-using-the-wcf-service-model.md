---
title: 调用请求集 Oracle E-business Suite 使用 WCF 服务模型中的 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: bb6ec551-c069-4133-add5-2ba83d20405d
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c85ee6a77bcd93deaceafde03cec9fb8b1d4f6ef
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36971046"
---
# <a name="invoke-request-sets-in-oracle-e-business-suite-using-the-wcf-service-model"></a>调用请求集 Oracle E-business Suite 使用 WCF 服务模型中
[!INCLUDE[adapteroracleebusinesslong](../../includes/adapteroracleebusinesslong-md.md)] 可以在 Oracle E-business Suite 中执行请求集。 请求集划分为一个或多个阶段，并且每个阶段包含了一组报表和并发程序。 有关如何在适配器支持请求集的详细信息，请参阅[对请求设置操作](../../adapters-and-accelerators/adapter-oracle-ebs/operations-on-request-sets.md)。  
  
## <a name="the-wcf-client-class"></a>WCF 客户端类  
 WCF 客户端生成有关调用请求集的名称[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]下表中列出。  
  
|项目|WCF 客户端名称|  
|--------------|---------------------|  
|请求组|RequestSets_ [APP_NAME] 客户端|  
  
 [A p p _] = Oracle E-business Suite 应用程序; 的实际名称例如，SQLAP。  
  
### <a name="method-signature-for-invoking-request-sets"></a>用于调用请求集的方法签名  
 下表显示了请求集的方法签名。  
  
|运算|方法签名|  
|---------------|----------------------|  
|请求组|公共\<返回类型\>\<请求设置名称\>（参数 1，参数 2，...）|  
  
 例如，下面的代码演示的方法签名，用于为生成 WCF 客户端类**reqset_singlestage**请求组。  
  
> [!NOTE]
>  这是自定义请求组，可能不是 Oracle 电子商务解决方案实例上可用。  
  
```  
public partial class RequestSets_SQLAPClient : System.ServiceModel.ClientBase<RequestSets_SQLAP>, RequestSets_SQLAP{      
  
    public string REQSTG(  
      schemas.microsoft.com.OracleEBS._2008._05.Options.SetRelClassOptions SetRelClassOptions,  
      schemas.microsoft.com.OracleEBS._2008._05.Options.SetPrintOptions SetPrintOptions,   
      schemas.microsoft.com.OracleEBS._2008._05.Options.SetRepeatOptions SetRepeatOptions,   
      schemas.microsoft.com.OracleEBS._2008._05.Options.SetNlsOptions SetNlsOptions,  
      string StartTime,  
      schemas.microsoft.com.OracleEBS._2008._05.RequestSetStage.SQLAP.REQSTG.set1 set1_set1);  
}  
```  
  
 此代码片段**RequestSets_SQLAPClient**是 WCF 中的类的生成的 OracleEBSBindingClient.cs 名称[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]。 **REQSTG**是要调用请求集的方法的名称。  
  
## <a name="creating-a-wcf-client-to-invoke-request-sets"></a>创建 WCF 客户端以调用请求集  
 通用组执行对 Oracle E-business Suite 使用 WCF 客户端的操作所需的操作涉及到一组任务中所述[与 Oracle E-business Suite 适配器的 WCF 服务模型概述](../../adapters-and-accelerators/adapter-oracle-ebs/overview-of-the-wcf-service-model-with-the-oracle-e-business-suite-adapter.md)。 本部分介绍如何创建 WCF 客户端以调用**reqset_singlestage**请求组。  
  
#### <a name="to-create-a-wcf-client"></a>若要创建 WCF 客户端  
  
1. 在 Visual Studio 中创建一个 Visual C# 项目。 有关本主题中，创建一个控制台应用程序。  
  
2. 生成的 WCF 客户端类**reqset_singlestage**请求组。 有关生成 WCF 客户端类的详细信息，请参阅[生成 WCF 客户端或 WCF 服务协定为 Oracle E-business Suite 解决方案项目](../../adapters-and-accelerators/adapter-oracle-ebs/create-a-wcf-client-or-wcf-service-contract-for-oracle-ebs-solution-artifacts.md)。  
  
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
   RequestSets_SQLAPClient client = new RequestSets_SQLAPClient(binding, address);  
   ```  
  
    在此代码段，`RequestSets_SQLAPClient`是 OracleEBSBindingClient.cs 中定义的 WCF 客户端。 此文件由生成[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]。  
  
   > [!NOTE]
   >  此代码片段显式应用程序代码中指定的绑定和终结点地址。 此外可以从还生成的应用程序配置文件 app.config 文件中，使用这些值[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]。 有关指定客户端绑定的不同方法的详细信息，请参阅[配置客户端绑定适用于 Oracle E-business Suite](../../adapters-and-accelerators/adapter-oracle-ebs/configure-a-client-binding-for-the-oracle-e-business-suite.md)。  
  
6. 为客户端设置的凭据。  
  
   ```  
   client.ClientCredentials.UserName.UserName = "myuser";  
   client.ClientCredentials.UserName.Password = "mypassword";  
   ```  
  
7. 因为调用请求集 Oracle E-business Suite 应用程序中的，必须设置应用程序上下文。 在此示例中，若要设置应用程序上下文中，您指定**OracleUserName**， **OraclePassword**，并**OracleEBSResponsibilityName**绑定属性。 有关应用程序上下文的详细信息，请参阅[设置应用程序上下文](../../adapters-and-accelerators/adapter-oracle-ebs/set-application-context.md)。  
  
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
  
9. 调用**reqset_singlestage**请求组。  
  
    ```  
    string RequestID;  
  
    schemas.microsoft.com.OracleEBS._2008._05.RequestSetStage.SQLAP.REQSTG.set1 param =  
        new schemas.microsoft.com.OracleEBS._2008._05.RequestSetStage.SQLAP.REQSTG.set1();  
  
    param.INSPARAMPROG = new schemas.microsoft.com.OracleEBS._2008._05.RequestSetConcurrentProgram.SQLAP.REQSTG.set1.SQLAP1.INSPARAMPROG();  
    param.INSPARAMPROG.p_id = "123";  
    param.INSPARAMPROG.p_name = "MyName";  
  
    try  
    {  
        Console.WriteLine("Invoking the reqset_singlestage request set");  
        RequestID = client.REQSTG(null, null, null, null, null, param);  
        Console.WriteLine("The request ID generated for the request set is : " + RequestID);  
        Console.WriteLine("*****************************************************************");  
        Console.WriteLine("\nHit <RETURN> to end");  
        Console.ReadLine();  
    }  
    catch (Exception ex)  
    {  
        Console.WriteLine("Exception : " + ex);  
        throw;  
    }  
    ```  
  
10. 关闭客户端，如下面的代码段中所述：  
  
    ```  
    client.Close();  
    ```  
  
11. 生成项目，然后运行它。 应用程序调用**reqset_singlestage**请求设置，并返回一个请求 ID，写入到控制台。  
  
## <a name="see-also"></a>请参阅  
 [开发 Oracle E-business Suite 应用程序使用 WCF 服务模型](../../adapters-and-accelerators/adapter-oracle-ebs/develop-oracle-e-business-suite-applications-using-the-wcf-service-model.md)