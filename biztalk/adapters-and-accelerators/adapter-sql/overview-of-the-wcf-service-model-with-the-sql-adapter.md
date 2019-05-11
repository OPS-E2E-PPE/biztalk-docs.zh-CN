---
title: 与 SQL 适配器的 WCF 服务模型概述 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 7641bcc7-3845-4914-9b1b-cb86b998ea6d
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b36c80de06955643e0aff9b2261e6c353cff1c37
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65368501"
---
# <a name="overview-of-the-wcf-service-model-with-the-sql-adapter"></a>与 SQL 适配器的 WCF 服务模型概述
[!INCLUDE[adaptersql](../../includes/adaptersql-md.md)]公开为 WCF 服务的 SQL Server 操作。 若要对 SQL Server 项目，例如若要调用的存储的过程执行操作调用上的适配器，这反过来会对执行 SQL Server 操作的操作。 你的代码因此充当到提供的适配器的 WCF 服务的客户端。  
  
 在[!INCLUDE[firstref_btsWinCommFoundation](../../includes/firstref-btswincommfoundation-md.md)]服务模型，为.NET 接口，表示客户端和服务之间存在的服务协定和操作表示为此接口上的方法。 [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]和 WCF 提供的工具，您可以从该适配器公开的元数据生成此接口的目标的操作。 这些工具还创建一个可用于调用服务接口中公开的操作的 WCF 客户端类。 客户端应用程序可以调用 WCF 客户端类来调用在适配器上的操作的方法。 若要实现服务以接收从入站的操作[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]，实现为入站操作生成的接口。  
  
 以下部分介绍如何使用 WCF 服务模型来调用使用 WCF 客户端的操作。  
  
## <a name="invoking-operations-on-the-sql-server-with-a-wcf-client"></a>针对 SQL Server 使用 WCF 客户端调用操作  
 若要使用的 WCF 服务模型上调用操作[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]，必须首先生成的目标操作的 WCF 客户端类。 然后，可以创建 WCF 客户端，此类的实例，并调用其方法来执行这些操作在 SQL Server 系统上。 本部分概述了的典型.NET 适配器客户端应用程序如下所示。 特定主题中提供了有关如何执行不同的操作使用的适配器的 SQL Server 数据库的详细的说明。  
  
#### <a name="to-invoke-operations-on-the-sql-adapter"></a>若要调用 SQL 适配器上的操作  
  
1. 生成 WCF 客户端类和帮助程序代码。 使用[!INCLUDE[addadapterservreflong](../../includes/addadapterservreflong-md.md)]针对你想要的 SQL Server 数据库项目生成 WCF 客户端类。 有关如何生成 WCF 客户端的详细信息，请参阅[为 SQL Server 项目生成 WCF 客户端或 WCF 服务约定](../../adapters-and-accelerators/adapter-sql/generate-a-wcf-client-or-wcf-service-contract-for-sql-server-artifacts.md)。  
  
2. 创建 WCF 客户端实例并配置 WCF 客户端。 配置 WCF 客户端涉及到指定的绑定和客户端将使用的终结点地址 （连接 URI）。 可以在代码中以强制方式或在配置中以声明方式执行此操作。 以下代码将创建 WCF 客户端面向**选择**上的操作**员工**SQL Server 数据库中的表。 它还设置了 SQL Server 数据库的凭据。 WCF 客户端从配置初始化。  
  
   ```  
   TableOp_dbo_EmployeeClient client = new TableOp_dbo_EmployeeClient("SqlAdapterBinding_TableOp_dbo_Employee"); //picking the binding and address from the app.config  
  
   client.ClientCredentials.UserName.UserName = "myuser";  
   client.ClientCredentials.UserName.Password = "mypassword";  
   ```  
  
   > [!NOTE]
   >  可以在代码中指定的客户端绑定和终结点地址，也可以在 app.config 配置文件中声明。 前面的代码片段使用后者。 有关如何使用任一方法的详细信息，请参阅[为 SQL 适配器配置客户端绑定](../../adapters-and-accelerators/adapter-sql/configure-a-client-binding-for-the-sql-adapter.md)。  
  
3. 打开 WCF 客户端。  
  
   ```  
   client.Open();  
   ```  
  
4. 调用方法前一步骤中创建的 WCF 客户端执行针对 SQL server 数据库的选择操作。 下面的代码调用 WCF 客户端以调用 SQL Server 数据库表中的 SELECT 语句的选择方法。  
  
   ```  
   client.Select("*", "where [Name] = ‘John Smith’");  
   ```  
  
5. 关闭 WCF 客户端。  
  
   ```  
   client.Close();  
   ```  
  
## <a name="see-also"></a>请参阅  
[开发 SQL 应用程序使用 WCF 服务模型](../../adapters-and-accelerators/adapter-sql/develop-sql-applications-using-the-wcf-service-model.md)