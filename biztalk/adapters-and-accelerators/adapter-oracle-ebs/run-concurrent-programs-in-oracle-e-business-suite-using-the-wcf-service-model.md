---
title: 调用并发程序中使用 WCF 服务模型的 Oracle E-business Suite |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: e227c60f-f6fe-40bf-bf41-2784a4428ad0
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 2265c1509a89dca7ead1b124267182bcaaa7fa0e
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65374658"
---
# <a name="invoke-concurrent-programs-in-oracle-e-business-suite-using-the-wcf-service-model"></a>调用 Oracle E-business Suite 使用 WCF 服务模型中的并发程序
Oracle E-business Suite 公开您可以执行对 Oracle 应用程序的特定操作的并发程序。 每个 Oracle 应用程序一的组标准的并发程序 （即在所有操作都相同） 和某些特定于 Oracle 应用程序的并发程序。 [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]公开所有的并发程序作为适配器客户端可以调用的操作。 有关适配器如何支持并发程序的详细信息，请参阅[操作对并发程序](../../adapters-and-accelerators/adapter-oracle-ebs/operations-on-concurrent-programs.md)。  
  
> [!NOTE]
>  对于那些不公开其元数据的并发程序，Oracle E-business 适配器公开这些并发程序的每个 100 的可选参数。 若要成功调用这些并发程序，用户必须请查阅 Oracle E-business Suite 文档以找出需要一个值，用于并发程序的参数，然后指定它们。 此类的并发程序的一个示例是**日记本的导入**(实际名称：**GLLEZL**) 中**总帐**应用程序。  
  
## <a name="about-the-examples-used-in-this-topic"></a>有关使用在本主题中的示例  
 本主题中的示例调用**MS_SAMPLE_COPY_EMP_DATA**并发程序中后, 跟**Get_Status**并发程序能够了解第一个并发程序的状态。 从这些并发程序中调用**应用程序对象库**应用程序。 **MS_SAMPLE_COPY_EMP_DATA**通过在运行这些示例提供的脚本。 有关示例的详细信息，请参阅[适用于 Oracle EBS 适配器示例](../../adapters-and-accelerators/adapter-oracle-ebs/samples-for-the-oracle-ebs-adapter.md)。 示例中， **ConcurrentProgram_ServiceModel**，后者基于本主题中，还提供与[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]示例。  
  
## <a name="the-wcf-client-class"></a>WCF 客户端类  
 生成用于调用并发程序的 WCF 客户端名称[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]下表中列出。  
  
|项目|WCF 客户端名称|  
|--------------|---------------------|  
|并发程序|ConcurrentPrograms_[APP_NAME]Client|  
  
 [A p p _] = Oracle E-business Suite 应用程序; 的实际名称例如，查找。  
  
### <a name="method-signature-for-invoking-concurrent-programs"></a>用于调用并发程序的方法签名  
 下表显示了并发程序的方法签名。  
  
|操作|方法签名|  
|---------------|----------------------|  
|并发程序|公共\<返回类型\>< Concurrent_program_name > （参数 1，参数 2，...）|  
  
 例如，下面的代码演示的方法签名，用于为生成 WCF 客户端类**MS_SAMPLE_COPY_EMP_DATA**并**Get_Status**并发程序。  
  
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
  
 此代码片段**ConcurrentPrograms_FNDClient**是 WCF 中的类的生成的 OracleEBSBindingClient.cs 名称[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]。 **MS_SAMPLE_COPY_EMP_DATA**是方法调用并发程序的名称。 **GetStatusForConcurrentProgram**是要调用并发程序来获取第一个并发程序的状态的方法的名称。  
  
> [!NOTE]
>  **GetStatusForConcurrentProgram**的实际名称**Get_Status**并发程序。  
  
## <a name="creating-a-wcf-client-to-invoke-concurrent-programs"></a>创建 WCF 客户端以调用并发程序  
 通用组执行对 Oracle E-business Suite 使用 WCF 客户端的操作所需的操作涉及到一组任务中所述[与 Oracle E-business Suite 适配器的 WCF 服务模型概述](../../adapters-and-accelerators/adapter-oracle-ebs/overview-of-the-wcf-service-model-with-the-oracle-e-business-suite-adapter.md)。 本部分介绍如何创建 WCF 客户端以调用**MS_SAMPLE_COPY_EMP_DATA**并**Get_Status**并发程序。  
  
#### <a name="to-create-a-wcf-client"></a>若要创建 WCF 客户端  
  
1. 在 Visual Studio 中创建一个 Visual C# 项目。 有关本主题中，创建一个控制台应用程序。  
  
2. 生成的 WCF 客户端类**MS_SAMPLE_COPY_EMP_DATA**并**Get_Status**并发程序。 有关生成 WCF 客户端类的详细信息，请参阅[生成 WCF 客户端或 WCF 服务协定为 Oracle E-business Suite 解决方案项目](../../adapters-and-accelerators/adapter-oracle-ebs/create-a-wcf-client-or-wcf-service-contract-for-oracle-ebs-solution-artifacts.md)。  
  
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
   ConcurrentPrograms_FNDClient client = new ConcurrentPrograms_FNDClient(binding, address);  
   ```  
  
    在此代码段，`ConcurrentPrograms_FNDClient`是 OracleEBSBindingClient.cs 中定义的 WCF 客户端。 此文件由生成[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]。  
  
   > [!NOTE]
   >  此代码片段显式应用程序代码中指定的绑定和终结点地址。 此外可以从还生成的应用程序配置文件 app.config 文件中，使用这些值[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]。 指定客户端绑定的不同方法的详细信息，请参阅[配置客户端绑定适用于 Oracle E-business Suite](../../adapters-and-accelerators/adapter-oracle-ebs/configure-a-client-binding-for-the-oracle-e-business-suite.md)。  
  
6. 为客户端设置的凭据。  
  
   ```  
   client.ClientCredentials.UserName.UserName = "myuser";  
   client.ClientCredentials.UserName.Password = "mypassword";  
   ```  
  
7. 由于正在调用并发程序 Oracle E-business Suite 应用程序中的，必须设置应用程序上下文。 在此示例中，若要设置应用程序上下文中，您指定**OracleUserName**， **OraclePassword**，并**OracleEBSResponsibilityName**绑定属性。 有关应用程序上下文的详细信息，请参阅[设置应用程序上下文](../../adapters-and-accelerators/adapter-oracle-ebs/set-application-context.md)。  
  
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
  
9. 调用**MS_SAMPLE_COPY_EMP_DATA**并**Get_Status**并发程序。  
  
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
  
11. 生成项目，然后运行它。 应用程序调用**MS_SAMPLE_COPY_EMP_DATA**并返回请求 id。 然后将该 ID 传递给**Get_Status**并发程序，它最后的状态**MS_SAMPLE_COPY_EMP_DATA**列程序。  
  
## <a name="see-also"></a>请参阅  
 [开发 Oracle E-business Suite 应用程序使用 WCF 服务模型](../../adapters-and-accelerators/adapter-oracle-ebs/develop-oracle-e-business-suite-applications-using-the-wcf-service-model.md)