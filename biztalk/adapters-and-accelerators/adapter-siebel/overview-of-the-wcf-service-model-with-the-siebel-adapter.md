---
title: 与 Siebel 适配器的 WCF 服务模型概述 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- how to, invoke operations on the Siebel system with a WCF client
- WCF service model, overview of
ms.assetid: 0e812473-0f50-4972-8b07-ec8edc2ef000
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 3c638255b103a9c588f22d6ddcb2a75b81619b73
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22222109"
---
# <a name="overview-of-the-wcf-service-model-with-the-siebel-adapter"></a>与 Siebel 适配器的 WCF 服务模型概述
[!INCLUDE[adaptersiebel](../../includes/adaptersiebel-md.md)]公开作为 WCF 服务的 Siebel 系统。 若要在 Siebel 系统项目，例如，若要调用的 Siebel 业务服务，方法上执行操作你调用上的适配器，这反过来会对执行 Siebel 系统操作的操作。 你的代码因此充当客户端提供的适配器的 WCF 服务。  
  
 在[!INCLUDE[firstref_btsWinCommFoundation](../../includes/firstref-btswincommfoundation-md.md)]服务模型，为.NET 接口，表示客户端和服务之间存在的服务协定和操作表示为此接口上的方法。 [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]并 WCF 提供使你能够从适配器公开的元数据生成目标操作此接口的工具。 这些工具还创建一个可用于调用服务接口中公开的操作的 WCF 客户端类。 客户端应用程序可以调用 WCF 客户端类，以调用在适配器上的操作的方法。  
  
 以下部分介绍如何使用 WCF 服务模型来调用操作与 WCF 客户端。  
  
## <a name="invoking-operations-on-the-siebel-system-with-a-wcf-client"></a>调用 Siebel 系统与 WCF 客户端上的操作  
 以使用 WCF 服务模型上调用操作[!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]，你必须首先生成的目标操作一个 WCF 客户端类。 然后，你可以创建 WCF 客户端，此类的实例并调用其方法来执行这些操作 Siebel 系统上。  
  
#### <a name="to-invoke-operations-on-the-siebel-adapter"></a>若要在 Siebel 适配器上调用操作  
  
1.  生成 WCF 客户端类和帮助程序代码。 使用[!INCLUDE[addadapterservreflong](../../includes/addadapterservreflong-md.md)]或 ServiceModel 元数据实用工具 (svcutil.exe) 生成 WCF 客户端类 Siebel 系统项目针对你想要。 有关如何生成 WCF 客户端的详细信息，请参阅[为 Siebel 解决方案项目生成 WCF 客户端或 WCF 服务约定](../../adapters-and-accelerators/adapter-siebel/generate-a-wcf-client-or-a-wcf-service-contract-for-siebel-solution-artifacts.md)。  
  
2.  创建 WCF 客户端实例和配置 WCF 客户端。 配置 WCF 客户端涉及到指定的绑定和客户端将使用的终结点地址 （连接 URI）。 可以在代码中以强制方式或配置中以声明方式执行此操作。 有关如何配置 WCF 客户端的详细信息，请参阅[为 Siebel 系统配置 WCF 客户端](../../adapters-and-accelerators/adapter-siebel/configure-a-wcf-client-for-a-siebel-system.md)。 下面的代码创建面向 Siebel 时间戳业务服务的 WCF 客户端。 它还将设置 Siebel 系统的凭据。 WCF 客户端从配置初始化。  
  
    ```  
    BusinessServices_TimeStamp_OperationClient client =  
        new BusinessServices_TimeStamp_OperationClient("SiebelBinding_BusinessServices_TimeStamp_Operation");  
  
    client.ClientCredentials.UserName.UserName = "YourUserName";  
    client.ClientCredentials.UserName.Password = "YourPassword";  
    ```  
  
3.  打开 WCF 客户端。  
  
    ```  
    client.Open();  
    ```  
  
4.  调用在步骤 2 中创建的 WCF 客户端在 Siebel 系统上执行操作的方法。 下面的代码调用**执行**的 WCF 客户端以调用的方法**执行**Siebel 系统上的时间戳业务服务的方法。  
  
    ```  
    // Create a parameter to hold the results and then invoke the Execute method of the TimeStamp business service.  
    microsoft.lobservices.siebel._2007._03.BusinessServices.TimeStamp.ExecuteResponseRecord er;  
    er = client.Execute();  
    ```  
  
5.  关闭 WCF 客户端。  
  
    ```  
    client.Close();  
    ```  
  
 有关调用 Siebel 业务服务方法的详细信息，请参阅[与使用 WCF 服务模型的 Siebel 适配器调用业务服务的方法](../../adapters-and-accelerators/adapter-siebel/run-business-service-methods-with-the-siebel-adapter-using-a-wcf-service.md) 
  
## <a name="see-also"></a>另请参阅  
 [开发 Siebel 应用程序使用 WCF 服务模型](../../adapters-and-accelerators/adapter-siebel/develop-siebel-applications-using-the-wcf-service-model.md)