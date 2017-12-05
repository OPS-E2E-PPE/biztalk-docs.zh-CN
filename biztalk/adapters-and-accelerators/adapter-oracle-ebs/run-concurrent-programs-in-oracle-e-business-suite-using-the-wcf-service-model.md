---
title: "调用中使用 WCF 服务模型的 Oracle E-business Suite 的并发程序 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: e227c60f-f6fe-40bf-bf41-2784a4428ad0
caps.latest.revision: "7"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 1c9ff6b37f2e18c03a364e3f584ea9f79b547f1e
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/28/2017
---
# <a name="invoke-concurrent-programs-in-oracle-e-business-suite-using-the-wcf-service-model"></a>调用中使用 WCF 服务模型的 Oracle E-business Suite 的并发程序
Oracle E-business Suite 公开可以执行以执行对 Oracle 应用程序的特定操作的并发程序。 每个 Oracle 应用程序具有一套标准的并发程序 （即在所有操作都相同） 和某些特定于 Oracle 应用程序的并发程序。 [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]公开所有的并发程序作为适配器客户端可以调用的操作。 有关如何适配器支持并发程序的详细信息，请参阅[并发程序上的操作](../../adapters-and-accelerators/adapter-oracle-ebs/operations-on-concurrent-programs.md)。  
  
> [!NOTE]
>  对于不公开其元数据的并发程序，Oracle E-business 适配器为每个这些并发程序公开 100 的可选参数。 若要成功调用这些并发程序，用户必须咨询 Oracle E-business Suite 文档以找出需要一个值，并发程序的参数，然后指定它们。 这样的并发程序的一个示例是**日志导入**(实际名称： **GLLEZL**) 中**常规分类帐**应用程序。  
  
## <a name="about-the-examples-used-in-this-topic"></a>有关在本主题中使用的示例  
 本主题中的示例时，将调用**MS_SAMPLE_COPY_EMP_DATA**并发程序后, 跟**Get_Status**并发程序知道的第一个并发程序的状态。 这些并发程序调用从**应用程序对象库**应用程序。 **MS_SAMPLE_COPY_EMP_DATA**通过运行这些示例使用提供的脚本。 有关示例的详细信息，请参阅[Oracle EBS 适配器的示例](../../adapters-and-accelerators/adapter-oracle-ebs/samples-for-the-oracle-ebs-adapter.md)。 示例中， **ConcurrentProgram_ServiceModel**，后者基于本主题中，还提供了与[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]示例。  
  
## <a name="the-wcf-client-class"></a>WCF 客户端类  
 为调用的并发程序生成 WCF 客户端的名称[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]下表中列出。  
  
|项目|WCF 客户端名称|  
|--------------|---------------------|  
|并发程序|ConcurrentPrograms_ [APP_NAME] 客户端|  
  
 [APP_NAME] = Oracle E-business Suite 应用程序; 实际名称例如，查找。  
  
### <a name="method-signature-for-invoking-concurrent-programs"></a>用于调用并发程序的方法签名  
 下表显示的并发程序的方法签名。  
  
|运算|方法签名|  
|---------------|----------------------|  
|并发程序|公共\<返回类型\>< Concurrent_program_name > (param 1，param 2，...)|  
  
 例如，下面的代码演示方法签名，用于生成 WCF 客户端类**MS_SAMPLE_COPY_EMP_DATA**和**Get_Status**并发程序。  
  
```  
public partial class ConcurrentPrograms_FNDClient : System.ServiceModel.ClientBase<ConcurrentPrograms_FND>, ConcurrentPrograms_FND {      
  
    public string MS_SAMPLE_COPY_EMP_DATA(schemas.microsoft.com.OracleEBS._2008._05.Options.SetOptions SetOptions,  
      schemas.microsoft.com.OracleEBS._2008._05.Options.SetPrintOptions SetPrintOptions,  
      schemas.microsoft.com.OracleEBS._2008._05.Options.SetRepeatOptions SetRepeatOptions,  
      string Description, string StartTime);  
  
    public bool GetStatusForConcurrentProgram(string RequestId, out string Phase, out string Status,  
      out string DevPhase, out string DevStatus, out string Message);  
}  
```  
  
 在此代码段， **ConcurrentPrograms_FNDClient**是 WCF 中的类的生成的 OracleEBSBindingClient.cs 名称[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]。 **MS_SAMPLE_COPY_EMP_DATA**是要调用的并发程序的方法的名称。 **GetStatusForConcurrentProgram**是要调用的并发程序来获取第一个并发程序状态的方法的名称。  
  
> [!NOTE]
>  **GetStatusForConcurrentProgram**是实际名称**Get_Status**并发程序。  
  
## <a name="creating-a-wcf-client-to-invoke-concurrent-programs"></a>创建 WCF 客户端来调用并发程序  
 泛型组执行对 Oracle E-business Suite 使用 WCF 客户端的操作所需的操作涉及到一组任务中所述[与 Oracle E-business Suite 适配器的 WCF 服务模型概述](../../adapters-and-accelerators/adapter-oracle-ebs/overview-of-the-wcf-service-model-with-the-oracle-e-business-suite-adapter.md)。 本部分介绍如何创建 WCF 客户端来调用**MS_SAMPLE_COPY_EMP_DATA**和**Get_Status**并发程序。  
  
#### <a name="to-create-a-wcf-client"></a>若要创建 WCF 客户端  
  
1.  在 Visual Studio 中创建 Visual C# 项目。 有关本主题中，创建一个控制台应用程序。  
  
2.  生成的 WCF 客户端类**MS_SAMPLE_COPY_EMP_DATA**和**Get_Status**并发程序。 有关生成 WCF 客户端类的详细信息，请参阅[生成 WCF 客户端或 Oracle E-business Suite 解决方案项目关联的 WCF 服务协定](../../adapters-and-accelerators/adapter-oracle-ebs/create-a-wcf-client-or-wcf-service-contract-for-oracle-ebs-solution-artifacts.md)。  
  
    > [!IMPORTANT]
    >  在生成 WCF 客户端类前, 请确保你设置**EnableBizTalkCompatibilityMode**绑定属性为 false。  
  
3.  在解决方案资源管理器，添加对引用`Microsoft.Adapters.OracleEBS`和`Microsoft.ServiceModel.Channels`。  
  
4.  打开 Program.cs 文件并添加以下命名空间：  
  
    -   `Microsoft.Adapters.OracleEBS`  
  
    -   `System.ServiceModel`  
  
5.  打开 Program.cs 文件并创建客户端，如下面的代码段中所述。  
  
    ```  
    OracleEBSBinding binding = new OracleEBSBinding();  
    EndpointAddress address = new EndpointAddress("oracleebs://ebs_instance_name");  
    ConcurrentPrograms_FNDClient client = new ConcurrentPrograms_FNDClient(binding, address);  
    ```  
  
     在此代码段，`ConcurrentPrograms_FNDClient`是 OracleEBSBindingClient.cs 中定义的 WCF 客户端。 此文件由生成[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]。  
  
    > [!NOTE]
    >  在此代码段，则显式应用程序代码中指定的绑定和终结点地址。 你还可以从还生成的应用程序配置文件 app.config，使用这些值[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]。 指定客户端绑定的不同方法的详细信息，请参阅[配置客户端绑定 Oracle E-business Suite](../../adapters-and-accelerators/adapter-oracle-ebs/configure-a-client-binding-for-the-oracle-e-business-suite.md)。  
  
6.  为客户端设置的凭据。  
  
    ```  
    client.ClientCredentials.UserName.UserName = "myuser";  
    client.ClientCredentials.UserName.Password = "mypassword";  
    ```  
  
7.  由于正在调用 Oracle E-business Suite 应用程序中的并发程序，你必须设置应用程序上下文。 在此示例中，若要设置应用程序上下文中，你指定**OracleUserName**， **OraclePassword**，和**OracleEBSResponsibilityName**绑定属性。 有关应用程序上下文的详细信息，请参阅[设置应用程序上下文](../../adapters-and-accelerators/adapter-oracle-ebs/set-application-context.md)。  
  
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
  
9. 调用**MS_SAMPLE_COPY_EMP_DATA**和**Get_Status**并发程序。  
  
    ```  
    string RequestID;  
    bool Result;  
    string Phase;  
    string Status;  
    string DevPhase;  
    string DevStatus;  
    string Message;  
  
    try  
    {  
        Console.WriteLine("Invoking the MS_SAMPLE_COPY_EMP_DATA concurrent program");  
        RequestID = client.MS_SAMPLE_COPY_EMP_DATA(null, null, null, null, null);  
        Console.WriteLine("The request ID generated for the concurrent program is : " + RequestID);  
        Console.WriteLine("********************************************************");  
        Console.WriteLine("\nWaiting for 60 seconds for the concurrent program to be complete");  
        System.Threading.Thread.Sleep(60000);  
        Console.WriteLine("\nInvoking the Get_Status concurrent program");  
        Result = client.GetStatusForConcurrentProgram(RequestID, out Phase, out Status, out DevPhase, out DevStatus, out Message);  
        Console.WriteLine("\nResult is  : " + Result);  
        Console.WriteLine("Phase is     : " + Phase);  
        Console.WriteLine("Status is    : " + Status);  
        Console.WriteLine("DevPhase is  : " + DevPhase);  
        Console.WriteLine("DevStatus is : " + DevStatus);  
        Console.WriteLine("Message is   : " + Message);  
        Console.WriteLine("********************************************************");  
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
  
11. 生成项目，然后运行它。 应用程序时，将调用**MS_SAMPLE_COPY_EMP_DATA**并返回请求 id。 然后将 ID 传递给**Get_Status**并发程序，最后提供的状态**MS_SAMPLE_COPY_EMP_DATA**列程序。  
  
## <a name="see-also"></a>另请参阅  
 [开发 Oracle E-business Suite 应用程序使用 WCF 服务模型](../../adapters-and-accelerators/adapter-oracle-ebs/develop-oracle-e-business-suite-applications-using-the-wcf-service-model.md)