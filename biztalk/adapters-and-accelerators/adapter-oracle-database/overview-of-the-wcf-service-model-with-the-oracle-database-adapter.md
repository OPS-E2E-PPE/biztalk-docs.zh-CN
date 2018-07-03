---
title: 使用 Oracle 数据库适配器的 WCF 服务模型概述 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- WCF service model, overview
- invoking operations
- WCF service, creating and implementing
ms.assetid: 8ed765e5-b5e6-46bd-bcd6-282219caf75d
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: de5fff554249546244c59aed5c1dceff9a527411
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "37006062"
---
# <a name="overview-of-the-wcf-service-model-with-the-oracle-database-adapter"></a>使用 Oracle 数据库适配器的 WCF 服务模型概述
当使用操作的[!INCLUDE[adapteroracle](../../includes/adapteroracle-md.md)]图面，您的代码可作为客户端或服务到适配器。 对于几乎所有操作的[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]图面，您的代码是客户端。 也就是说，你的应用程序调用适配器; 上的操作若要将记录插入到 Oracle 表的示例。 为其代码充当到服务的唯一操作[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]用于 POLLINGSMT 操作。 在这种情况下，适配器将轮询查询操作的结果发送到你的应用程序。  
  
 在[!INCLUDE[firstref_btsWinCommFoundation](../../includes/firstref-btswincommfoundation-md.md)]服务模型，为.NET 接口，表示客户端和服务之间存在的服务协定和操作表示为此接口上的方法。 [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]和 WCF 提供的工具，您可以从该适配器公开的元数据生成此接口的目标的操作。 这些工具还创建一个可用于调用服务接口中公开的操作的 WCF 客户端类。 客户端应用程序可以调用 WCF 客户端类来调用在适配器上的操作的方法。 若要实现服务以接收从 POLLINGSTMT 操作[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]，您需要实现为 POLLINGSTMT 操作生成的接口。  
  
 以下各节说明如何使用 WCF 服务模型来创建客户端和服务代码[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]。  
  
## <a name="creating-and-invoking-operations-on-a-wcf-client-by-using-the-oracle-database-adapter"></a>创建和使用 Oracle 数据库适配器调用 WCF 客户端上的操作  
 若要使用的 WCF 服务模型上调用操作[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]，必须首先生成的目标操作的 WCF 客户端类。 然后，可以创建 WCF 客户端，此类的实例，并调用其方法来执行对 Oracle 数据库的操作。  
  
#### <a name="to-invoke-operations-on-the-oracle-database-adapter"></a>若要调用的 Oracle 数据库适配器上的操作  
  
1. 生成 WCF 客户端类和帮助程序代码。 使用[!INCLUDE[addadapterservreflong](../../includes/addadapterservreflong-md.md)]或 ServiceModel Metadata Utility Tool (svcutil.exe) 生成 WCF 客户端类针对 Oracle 数据库项目所需工作。 有关如何生成 WCF 客户端的详细信息，请参阅[为 Oracle 数据库项目生成 WCF 客户端或 WCF 服务约定](../../adapters-and-accelerators/adapter-oracle-database/create-a-wcf-client-or-wcf-service-contract-for-oracle-db-solution-artifacts.md)。  
  
2. 通过指定客户端绑定创建的 WCF 客户端实例。 指定客户端绑定涉及到指定的绑定和 WCF 客户端将使用的终结点地址。 可以在代码中以强制方式或在配置中以声明方式执行此操作。 有关如何指定客户端绑定的详细信息，请参阅[配置客户端绑定用于 Oracle 数据库](../../adapters-and-accelerators/adapter-oracle-database/configure-a-client-binding-for-the-oracle-database.md)。 以下代码创建可用于执行数据操作语言 (DML) 操作 Oracle 数据库表 （/SCOTT/ACCOUNTACTIVITY） 上的 WCF 客户端。 它还设置用于 Oracle 数据库的凭据。 WCF 客户端从配置初始化。  
  
   ```  
   SCOTTTableACCOUNTACTIVITYClient aaTableClient =   
       new SCOTTTableACCOUNTACTIVITYClient("OracleDBBinding_SCOTT.Table.ACCOUNTACTIVITY");  
  
   aaTableClient.ClientCredentials.UserName.UserName = "SCOTT";  
   aaTableClient.ClientCredentials.UserName.Password = "TIGER";  
   ```  
  
3. 打开 WCF 客户端。  
  
   ```  
   aaTableClient.Open();  
   ```  
  
4. 调用在步骤 2 中创建的 WCF 客户端在 Oracle 数据库上执行操作方法。 下面的代码调用**选择**WCF 客户端 ACCOUNTACTIVITY 表上执行以下 SQL SELECT 查询的方法： `SELECT * FROM ACCOUNTACTIVITY`。  
  
   ```  
   // create a record set parameter to hold the SELECT query result set and invoke the Select operation;  
   microsoft.lobservices.oracledb._2007._03.SCOTT.Table.ACCOUNTACTIVITY.ACCOUNTACTIVITYRECORDSELECT[] selectRecords;  
   selectRecords = aaTableClient.Select("*", null);  
   ```  
  
5. 关闭 WCF 客户端。  
  
   ```  
   aaTableClient.Close();  
   ```  
  
   有关执行对表和视图，包括使用更高版本，在选择操作的 DML 操作的详细信息请参阅[执行基本的 Insert、 Update、 Delete 和通过使用 WCF 服务模型选择操作](../../adapters-and-accelerators/adapter-oracle-database/insert-update-delete-select-operations-in-oracle-db-using-a-wcf-service.md)。  
  
## <a name="creating-and-implementing-a-wcf-service-by-using-the-oracle-database-adapter"></a>创建和使用 Oracle 数据库适配器实现的 WCF 服务  
 [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]可以执行轮询 Oracle 数据库表或视图。 此功能允许您指定的适配器应定期执行对 Oracle 数据库的 SQL SELECT 查询。 此查询的结果返回到你的应用程序通过特殊操作，POLLINGSTMT 操作。 若要接收结果的轮询查询，你的应用程序必须实现服务协定的[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]POLLINGSTMT 操作公开。  
  
 若要实现接收 POLLINGSTMT 操作的服务，必须首先生成表示公开的服务协定的.NET 接口 （也称为 WCF 服务约定） [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] POLLINGSTMT 操作。 有关如何执行此操作的详细信息，请参阅[为 Oracle 数据库项目生成 WCF 客户端或 WCF 服务约定](../../adapters-and-accelerators/adapter-oracle-database/create-a-wcf-client-or-wcf-service-contract-for-oracle-db-solution-artifacts.md)。  
  
 然后，通过实现生成的接口实现的 WCF 服务。 此类包含业务逻辑以处理 POLLINGSTMT 消息并将响应返回到适配器。 然后，使用服务主机 (**System.ServiceModel.ServiceHost**) 来承载此服务的实例。 有关详细信息，请参阅[通过使用 WCF 服务模型基于接收轮询的数据更改消息](../../adapters-and-accelerators/adapter-oracle-database/receive-polling-based-data-changed-messages-in-oracle-db-using-a-wcf-service.md)。  
  
## <a name="see-also"></a>请参阅  
 [使用 WCF 服务模型开发 Oracle 数据库应用程序](../../adapters-and-accelerators/adapter-oracle-database/develop-oracle-database-applications-using-the-wcf-service-model.md)