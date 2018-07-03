---
title: 使用 Siebel 适配器的 WCF 服务模型概述 |Microsoft Docs
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
ms.openlocfilehash: 0f1b705b40cb5c7c78017f5a320a41ddb0cc1476
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36969534"
---
# <a name="overview-of-the-wcf-service-model-with-the-siebel-adapter"></a>使用 Siebel 适配器的 WCF 服务模型概述
[!INCLUDE[adaptersiebel](../../includes/adaptersiebel-md.md)]公开为 WCF 服务的 Siebel 系统。 若要在 Siebel 系统项目，例如若要调用的 Siebel 业务服务，方法上执行操作调用上的适配器，这反过来会对执行操作 Siebel 系统的操作。 你的代码因此充当到提供的适配器的 WCF 服务的客户端。  
  
 在[!INCLUDE[firstref_btsWinCommFoundation](../../includes/firstref-btswincommfoundation-md.md)]服务模型，为.NET 接口，表示客户端和服务之间存在的服务协定和操作表示为此接口上的方法。 [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]和 WCF 提供的工具，您可以从该适配器公开的元数据生成此接口的目标的操作。 这些工具还创建一个可用于调用服务接口中公开的操作的 WCF 客户端类。 客户端应用程序可以调用 WCF 客户端类来调用在适配器上的操作的方法。  
  
 以下部分介绍如何使用 WCF 服务模型来调用使用 WCF 客户端的操作。  
  
## <a name="invoking-operations-on-the-siebel-system-with-a-wcf-client"></a>调用具有 WCF 客户端的 Siebel 系统上的操作  
 若要使用的 WCF 服务模型上调用操作[!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]，必须首先生成的目标操作的 WCF 客户端类。 然后，可以创建 WCF 客户端，此类的实例，并调用其方法来执行这些操作在 Siebel 系统上。  
  
#### <a name="to-invoke-operations-on-the-siebel-adapter"></a>若要调用上的 Siebel 适配器的操作  
  
1. 生成 WCF 客户端类和帮助程序代码。 使用[!INCLUDE[addadapterservreflong](../../includes/addadapterservreflong-md.md)]或 ServiceModel Metadata Utility Tool (svcutil.exe) 生成 WCF 客户端类的 Siebel 系统项目针对你想要。 有关如何生成 WCF 客户端的详细信息，请参阅[为 Siebel 解决方案项目生成 WCF 客户端或 WCF 服务约定](../../adapters-and-accelerators/adapter-siebel/generate-a-wcf-client-or-a-wcf-service-contract-for-siebel-solution-artifacts.md)。  
  
2. 创建 WCF 客户端实例并配置 WCF 客户端。 配置 WCF 客户端涉及到指定的绑定和客户端将使用的终结点地址 （连接 URI）。 可以在代码中以强制方式或在配置中以声明方式执行此操作。 有关如何配置 WCF 客户端的详细信息，请参阅[为 Siebel 系统配置 WCF 客户端](../../adapters-and-accelerators/adapter-siebel/configure-a-wcf-client-for-a-siebel-system.md)。 以下代码创建提供程序针对时间戳 Siebel 业务服务的 WCF 客户端。 它还设置 Siebel 系统的凭据。 WCF 客户端从配置初始化。  
  
   ```  
   BusinessServices_TimeStamp_OperationClient client =  
       new BusinessServices_TimeStamp_OperationClient("SiebelBinding_BusinessServices_TimeStamp_Operation");  
  
   client.ClientCredentials.UserName.UserName = "YourUserName";  
   client.ClientCredentials.UserName.Password = "YourPassword";  
   ```  
  
3. 打开 WCF 客户端。  
  
   ```  
   client.Open();  
   ```  
  
4. 调用在步骤 2 中创建的 WCF 客户端在 Siebel 系统上执行操作方法。 下面的代码调用**Execute** WCF 客户端来调用方法**Execute** Siebel 系统上的时间戳业务服务的方法。  
  
   ```  
   // Create a parameter to hold the results and then invoke the Execute method of the TimeStamp business service.  
   microsoft.lobservices.siebel._2007._03.BusinessServices.TimeStamp.ExecuteResponseRecord er;  
   er = client.Execute();  
   ```  
  
5. 关闭 WCF 客户端。  
  
   ```  
   client.Close();  
   ```  
  
   有关调用 Siebel 业务服务方法的详细信息，请参阅[使用 Siebel 适配器使用 WCF 服务模型中调用业务服务方法](../../adapters-and-accelerators/adapter-siebel/run-business-service-methods-with-the-siebel-adapter-using-a-wcf-service.md) 
  
## <a name="see-also"></a>请参阅  
 [开发 Siebel 应用程序使用 WCF 服务模型](../../adapters-and-accelerators/adapter-siebel/develop-siebel-applications-using-the-wcf-service-model.md)