---
title: 使用 SAP 适配器的 WCF 服务模型概述 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- WCF service model, overview of using
ms.assetid: 02a4b43e-ade0-4dba-b8f6-074bca7cbe5c
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 17ce25d78b40763f78d214276bb9311898653389
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65373138"
---
# <a name="overview-of-the-wcf-service-model-with-the-sap-adapter"></a>使用 SAP 适配器的 WCF 服务模型概述
当使用操作的[!INCLUDE[adaptersap](../../includes/adaptersap-md.md)]图面，您的代码可作为客户端或服务到适配器。  
  
 你的代码充当客户端来调用以下类型的 SAP 系统的操作：  
  
- 调用远程函数调用 (RFC)。  
  
- 调用事务性远程函数调用 (tRFC)。  
  
- 调用业务应用程序编程接口 (BAPI)。  
  
- 发送一个中间文档 (IDOC)  
  
  你的代码充当接收以下类型的操作的服务：  
  
- 接收 RFC （RFC 服务器）  
  
- 接收 tRFC （tRFC 服务器）  
  
- 接收 IDOC。  
  
> [!NOTE]
>  由于 Bapi 是公开位于企业对象存储库 (BOR) 中的业务对象上的 SAP 系统的方法，因此无法接收 Bapi。  
  
 在[!INCLUDE[firstref_btsWinCommFoundation](../../includes/firstref-btswincommfoundation-md.md)]服务模型，为.NET 接口，表示客户端和服务之间存在的服务协定和操作表示为此接口上的方法。 [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]和 WCF 提供的工具，您可以从该适配器公开的元数据生成此接口的目标的操作。 这些工具还创建一个可用于调用服务接口中公开的操作的 WCF 客户端类。 客户端应用程序可以调用 WCF 客户端类来调用在适配器上的操作的方法。 若要实现服务以接收从操作[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]，您需要实现为目标操作生成的接口。  
  
 以下各节说明如何使用 WCF 服务模型来创建客户端和服务代码[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]。  
  
## <a name="creating-a-wcf-client-and-invoking-operations-on-sap"></a>创建 WCF 客户端和针对 SAP 调用操作  
 若要使用的 WCF 服务模型上调用操作[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]，必须首先生成的目标操作的 WCF 客户端类。 然后，可以创建 WCF 客户端，此类的实例，并调用其方法来执行 SAP 系统的操作。  
  
#### <a name="to-invoke-operations-on-the-sap-adapter"></a>若要调用上的 SAP 适配器的操作  
  
1. 生成 WCF 客户端类和帮助程序代码。 使用[!INCLUDE[addadapterservreflong](../../includes/addadapterservreflong-md.md)]或 ServiceModel Metadata Utility Tool (svcutil.exe) 来生成 WCF 客户端类的 SAP 系统项目针对你想要。 有关如何生成 WCF 客户端的详细信息，请参阅[生成 WCF 客户端或 SAP 解决方案项目的 WCF 服务约定](../../adapters-and-accelerators/adapter-sap/generate-a-wcf-client-or-a-wcf-service-contract-for-sap-solution-artifacts.md)。  
  
2. 通过指定客户端绑定创建的 WCF 客户端实例。 指定客户端绑定涉及到指定的绑定和 WCF 客户端将使用的终结点地址。 可以在代码中以强制方式或在配置中以声明方式执行此操作。 有关如何指定客户端绑定的详细信息，请参阅[配置客户端 SAP 系统的绑定](../../adapters-and-accelerators/adapter-sap/configure-a-client-binding-for-the-sap-system.md)。 以下代码创建可用于调用 RFC SAP 系统上的 WCF 客户端。 它还设置了 SAP 系统的凭据。 WCF 客户端从配置初始化。  
  
   ```  
   RfcClient rfcClient = new RfcClient("SAPBinding_Rfc");  
  
   rfcClient.ClientCredentials.UserName.UserName = "YourUserName";  
   rfcClient.ClientCredentials.UserName.Password = "YourPassword";  
   ```  
  
3. 打开 WCF 客户端。  
  
   ```  
   rfcClient.Open();  
   ```  
  
4. 调用在步骤 2 中创建的 WCF 客户端来执行 SAP 系统的操作方法。 下面的代码调用**SD_RFC_CUSTOMER_GET**的 WCF 客户端以调用 RFC SAP 系统上的方法。  
  
   ```  
   microsoft.lobservices.sap._2007._03.Types.Rfc.RFCCUST[] customers =   
       new microsoft.lobservices.sap._2007._03.Types.Rfc.RFCCUST[0];  
  
   rfcClient.SD_RFC_CUSTOMER_GET(string.Empty, "AB*", ref customers);  
   ```  
  
5. 关闭 WCF 客户端。  
  
   ```  
   rfcClient.Close();  
  
   ```  
  
## <a name="creating-and-implementing-a-wcf-service-by-using-the-sap-adapter"></a>创建和使用 SAP 适配器实现的 WCF 服务  
 使用 WCF 服务模型来接收从操作[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]，则必须首先生成表示公开的服务协定的.NET 接口 （也称为 WCF 服务约定）[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]操作。 有关如何执行此操作的详细信息，请参阅[生成 WCF 客户端或 SAP 解决方案项目的 WCF 服务约定](../../adapters-and-accelerators/adapter-sap/generate-a-wcf-client-or-a-wcf-service-contract-for-sap-solution-artifacts.md)。  
  
 然后，您通过实现生成的接口实现的 WCF 服务。 此类包含业务逻辑来处理该操作并返回到适配器的响应。 然后，使用服务主机 (**System.ServiceModel.ServiceHost**) 来承载此服务的实例。  
  
#### <a name="to-create-and-implement-a-wcf-service"></a>若要创建和实现 WCF 服务  
  
1. 生成的 WCF 服务协定和帮助器类。 使用[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]或 svcutil.exe 来生成针对你想要的 SAP 系统项目的 WCF 服务协定 （接口）。 有关如何生成 WCF 客户端的详细信息，请参阅[生成 WCF 客户端或 SAP 解决方案项目的 WCF 服务约定](../../adapters-and-accelerators/adapter-sap/generate-a-wcf-client-or-a-wcf-service-contract-for-sap-solution-artifacts.md)。  
  
2. 实现在步骤 1 中生成的接口和帮助程序类中的 WCF 服务。 如果遇到错误时处理操作的数据，处理该操作的方法可以引发异常返回到 SAP 系统，则为错误否则该方法必须返回该操作适当 （生成） 的响应类的实例。 必须按如下所示属性的 WCF 服务类：  
  
   ```  
   [ServiceBehavior(InstanceContextMode = InstanceContextMode.Single)]  
   ```  
  
   1. 如果您使用了[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]若要生成的界面，可以实现你的逻辑中生成适当的方法中直接**SAPBindingService**类。 可以 SAPBindingService.cs 中找到此类。 下面的代码子类**SAPBindingService**类。  
  
      ```  
      [ServiceBehavior(InstanceContextMode = InstanceContextMode.Single,UseSynchronizationContext = false)]  
      class RfcServerClass : SAPBindingNamespace.SAPBindingService  
      {  
          public override Z_RFC_MKD_ADDResponse Z_RFC_MKD_ADD(Z_RFC_MKD_ADDRequest request)  
          {  
              // If either parameter is null throw an exception   
              if (request.X == null || request.Y == null)  
                  throw new System.ArgumentNullException();  
  
              // Add the two operands  
              int result = (int) (request.X + request.Y);  
  
              return new Z_RFC_MKD_ADDResponse(result);  
          }  
      }  
      ```  
  
   2. 如果使用 svcutil.exe 生成的界面，必须创建实现接口的类，并在此类的 appropriatemethod 中实现自己的逻辑。  
  
3. 创建在步骤 2 中创建的 WCF 服务的实例。  
  
   ```  
   // create service instance  
   RfcServerClass rfcServerInstance = new RfcServerClass();  
   ```  
  
4. 创建的实例**System.ServiceModel.ServiceHost**使用 WCF 服务和基本连接 URI。 基本连接 URI 不能包含 userinfoparams 或 query_string。  
  
   ```  
   // Enable service host  
   Uri[] baseUri = new Uri[] { new Uri("sap://a/YourSAPHost/00") };  
   ServiceHost srvHost = new ServiceHost(pollingInstance, baseUri);  
   ```  
  
5. 创建**SAPBinding**并设置其绑定属性来配置操作。 可以在代码中显式或配置中以声明方式执行此操作。 至少，您必须设置**AcceptCredentialsInUri**到**true**。  
  
   ```  
   // Create and configure a binding for the service endpoint. NOTE: binding  
   // parameters are set here for clarity, but these are already set in the  
   // the generated configuration file  
   SAPBinding binding = new SAPBinding();  
  
   // The credentials are included in the connection URI, so set this property to true  
   binding.AcceptCredentialsInUri = true;  
   ```  
  
6. 将服务终结点添加到服务主机。 若要执行此操作：  
  
   -   使用在步骤 5 中创建的绑定。  
  
   -   指定连接 URI，其中包含的凭据，并指定侦听器连接 （SAP 网关，网关服务和程序 ID） query_string 中。 有关 SAP 连接 URI 的详细信息，请参阅[创建 SAP 系统连接 URI](../../adapters-and-accelerators/adapter-sap/create-the-sap-system-connection-uri.md)。  
  
   -   指定服务协定。 这是接口的表示的 WCF 服务约定的名称。 对于 Rfc，它是"Rfc"。  
  
   ```  
   // Add service endpoint   
   // NOTE: The contract for the service endpoint is "Rfc".  
   //       This is the generated WCF service contract (interface) -- see SAPBindingInterface.cs.  
   Uri serviceUri = new Uri("sap://User=YourUserName;Passwd=YourPassword;Client=800;Lang=EN;@a/YourSAPHost/00?ListenerGwServ=SAPGW00&ListenerGwHost=YourSapHost&ListenerProgramId=SAPAdapter");  
   srvHost.AddServiceEndpoint("Rfc", binding, serviceUri);  
   ```  
  
7. 若要从 SAP 系统接收操作，打开服务主机。 SAP 系统调用的程序 ID 和步骤 6 中的服务 URI 中指定系统上的操作时，将调用您的 WCF 服务。  
  
   ```  
   // Open the service host to begin receiving the operation.  
   srvHost.Open();  
   ```  
  
8. 若要停止接收操作，请关闭服务主机。  
  
   > [!IMPORTANT]
   >  该适配器将继续接收操作，直到关闭服务主机。 当你不再想要接收操作时，应始终关闭服务主机。  
  
   ```  
   srvHost.Close();  
   ```  
  
## <a name="see-also"></a>请参阅  
[开发 SAP 应用程序使用 WCF 服务模型](../../adapters-and-accelerators/adapter-sap/develop-sap-applications-using-the-wcf-service-model.md)