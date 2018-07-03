---
title: 使用 Oracle E-business Suite 适配器的 WCF 服务模型概述 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: aeeac8a4-a4bc-4963-951c-0c806e232f1e
caps.latest.revision: 11
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 1a591c06b89464f640ea4992b927a68a62e69307
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36994622"
---
# <a name="overview-of-the-wcf-service-model-with-the-oracle-e-business-suite-adapter"></a>使用 Oracle E-business Suite 适配器的 WCF 服务模型概述
[!INCLUDE[adapteroracleebusinesslong](../../includes/adapteroracleebusinesslong-md.md)]公开为 WCF 服务的 Oracle E-business Suite 系统。 若要对 Oracle E-business Suite 的项目，例如若要调用的存储的过程执行操作调用上的适配器，这反过来会对执行 Oracle E-business Suite 操作的操作。 你的代码充当客户端提供的适配器的 WCF 服务。  
  
 在[!INCLUDE[firstref_btsWinCommFoundation](../../includes/firstref-btswincommfoundation-md.md)]服务模型，为.NET 接口，表示客户端和服务之间存在的服务协定和操作表示为此接口上的方法。 [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]和 WCF 提供的工具，您可以从该适配器公开的元数据生成此接口的目标的操作。 这些工具还创建一个可用于调用服务接口中公开的操作的 WCF 客户端类。 客户端应用程序可以调用 WCF 客户端类来调用在适配器上的操作的方法。  
  
 以下部分介绍如何使用 WCF 服务模型来调用使用 WCF 客户端的操作。  
  
## <a name="invoking-operations-on-the-oracle-e-business-suite-with-a-wcf-client"></a>针对 Oracle E-business Suite 使用 WCF 客户端调用操作  
 若要使用的 WCF 服务模型上调用操作[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]，必须首先生成的目标操作的 WCF 客户端类。 然后，可以创建 WCF 客户端，此类的实例，并调用其方法来执行对 Oracle E-business Suite 的这些操作。  
  
#### <a name="to-invoke-operations-on-the-oracle-e-business-adapter"></a>若要调用 Oracle E-business 适配器上的操作  
  
1. 生成 WCF 客户端类和帮助程序代码。 使用[!INCLUDE[addadapterservreflong](../../includes/addadapterservreflong-md.md)]或 ServiceModel Metadata Utility Tool (svcutil.exe) 生成 WCF 客户端类 Oracle E-business Suite 项目针对你想要。 有关如何生成 WCF 客户端的详细信息，请参阅[为 Oracle 电子商务解决方案项目生成 WCF 客户端或 WCF 服务约定](../../adapters-and-accelerators/adapter-oracle-ebs/create-a-wcf-client-or-wcf-service-contract-for-oracle-ebs-solution-artifacts.md)。  
  
2. 创建 WCF 客户端实例并配置 WCF 客户端。 配置 WCF 客户端涉及到指定的绑定和客户端将使用的终结点地址 （连接 URI）。 可以在代码中以强制方式或在配置中以声明方式执行此操作。 以下代码将创建 WCF 客户端面向**的客户界面**中的并发程序**应收帐款**Oracle E-business Suite 中应用程序。 它还设置 Oracle E-business Suite 的凭据。 WCF 客户端从配置初始化。  
  
   ```  
   ConcurrentPrograms_ARClient client = new ConcurrentPrograms_ARClient("OracleEBSBinding_ConcurrentPrograms_AR"); //picking the binding and address from app.config  
  
   client.ClientCredentials.UserName.UserName = "myuser";  
   client.ClientCredentials.UserName.Password = "mypassword";  
   ```  
  
   > [!NOTE]
   >  可以在代码中指定的客户端绑定和终结点地址，也可以在 app.config 配置文件中声明。 前面的代码片段使用后者。 有关如何使用任一方法的详细信息，请参阅[适用于 Oracle E-business Suite 中配置客户端绑定](../../adapters-and-accelerators/adapter-oracle-ebs/configure-a-client-binding-for-the-oracle-e-business-suite.md)。  
  
3. 打开 WCF 客户端。  
  
   ```  
   client.Open();  
   ```  
  
4. 调用在步骤 2 中创建的 WCF 客户端来执行对 Oracle E-business Suite 操作的方法。 下面的代码调用**的客户界面**中的并发程序**应收帐款**Oracle E-business Suite 中应用程序。  
  
   ```  
   string Result = client.RACUST(null, null, null, description, null, recipro_cust, org_id);  
   ```  
  
    **RACUST**是客户界面并发程序的实际名称。 **客户界面**是并发程序的友好名称。  
  
5. 关闭 WCF 客户端。  
  
   ```  
   client.Close();  
   ```  
  
## <a name="see-also"></a>请参阅  
 [开发 Oracle E-business Suite 应用程序使用 WCF 通道模型](../../adapters-and-accelerators/adapter-oracle-ebs/develop-oracle-e-business-suite-applications-using-the-wcf-service-model.md)