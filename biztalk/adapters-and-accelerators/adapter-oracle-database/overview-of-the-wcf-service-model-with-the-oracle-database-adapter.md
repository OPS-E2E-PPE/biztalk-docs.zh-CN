---
title: 与 Oracle 数据库适配器的 WCF 服务模型概述 |Microsoft 文档
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
ms.openlocfilehash: 100bacfeaf2e06d7ff491ec77f88e00980a96fa1
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22214381"
---
# <a name="overview-of-the-wcf-service-model-with-the-oracle-database-adapter"></a>与 Oracle 数据库适配器的 WCF 服务模型概述
当你使用操作的[!INCLUDE[adapteroracle](../../includes/adapteroracle-md.md)]图面，你的代码起作用作为客户端或服务进行适配器。 几乎所有操作，[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]图面，你的代码是客户端。 你的应用程序，即适配器; 上的操作时，将调用有关将记录插入 Oracle 表的示例。 仅有为其代码充当服务进行的操作[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]POLLINGSMT 操作是。 在这种情况下，该适配器将轮询查询操作的结果发送到你的应用程序。  
  
 在[!INCLUDE[firstref_btsWinCommFoundation](../../includes/firstref-btswincommfoundation-md.md)]服务模型，为.NET 接口，表示客户端和服务之间存在的服务协定和操作表示为此接口上的方法。 [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]并 WCF 提供使你能够从适配器公开的元数据生成目标操作此接口的工具。 这些工具还创建一个可用于调用服务接口中公开的操作的 WCF 客户端类。 客户端应用程序可以调用 WCF 客户端类，以调用在适配器上的操作的方法。 若要实现服务以接收从 POLLINGSTMT 操作[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]，实现为 POLLINGSTMT 操作生成的接口。  
  
 以下各节说明如何使用 WCF 服务模型来创建客户端和服务代码[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]。  
  
## <a name="creating-and-invoking-operations-on-a-wcf-client-by-using-the-oracle-database-adapter"></a>创建和使用 Oracle 数据库适配器调用 WCF 客户端上的操作  
 以使用 WCF 服务模型上调用操作[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]，你必须首先生成的目标操作一个 WCF 客户端类。 然后，你可以创建 WCF 客户端，此类的实例并调用其方法来执行对 Oracle 数据库的操作。  
  
#### <a name="to-invoke-operations-on-the-oracle-database-adapter"></a>若要调用的 Oracle 数据库适配器上的操作  
  
1.  生成 WCF 客户端类和帮助程序代码。 使用[!INCLUDE[addadapterservreflong](../../includes/addadapterservreflong-md.md)]或 ServiceModel 元数据实用工具 (svcutil.exe) 生成 WCF 客户端类在 Oracle 数据库项目目标需与之进行工作。 有关如何生成 WCF 客户端的详细信息，请参阅[的 Oracle 数据库项目生成 WCF 客户端或 WCF 服务约定](../../adapters-and-accelerators/adapter-oracle-database/create-a-wcf-client-or-wcf-service-contract-for-oracle-db-solution-artifacts.md)。  
  
2.  通过指定客户端绑定中创建的 WCF 客户端实例。 指定客户端绑定涉及到指定的绑定和 WCF 客户端将使用的终结点地址。 可以在代码中以强制方式或配置中以声明方式执行此操作。 有关如何指定客户端绑定的详细信息，请参阅[配置客户端绑定用于 Oracle 数据库](../../adapters-and-accelerators/adapter-oracle-database/configure-a-client-binding-for-the-oracle-database.md)。 以下代码将创建 WCF 客户端可用来执行对 Oracle 数据库表 （/SCOTT/ACCOUNTACTIVITY） 的数据操作语言 (DML) 操作。 它还将设置 Oracle 数据库的凭据。 WCF 客户端从配置初始化。  
  
    ```  
    SCOTTTableACCOUNTACTIVITYClient aaTableClient =   
        new SCOTTTableACCOUNTACTIVITYClient("OracleDBBinding_SCOTT.Table.ACCOUNTACTIVITY");  
  
    aaTableClient.ClientCredentials.UserName.UserName = "SCOTT";  
    aaTableClient.ClientCredentials.UserName.Password = "TIGER";  
    ```  
  
3.  打开 WCF 客户端。  
  
    ```  
    aaTableClient.Open();  
    ```  
  
4.  调用在步骤 2 中创建的 WCF 客户端在 Oracle 数据库上执行操作的方法。 下面的代码调用**选择**的 WCF 客户端，以在 ACCOUNTACTIVITY 表上执行以下 SQL SELECT 查询的方法： `SELECT * FROM ACCOUNTACTIVITY`。  
  
    ```  
    // create a record set parameter to hold the SELECT query result set and invoke the Select operation;  
    microsoft.lobservices.oracledb._2007._03.SCOTT.Table.ACCOUNTACTIVITY.ACCOUNTACTIVITYRECORDSELECT[] selectRecords;  
    selectRecords = aaTableClient.Select("*", null);  
    ```  
  
5.  关闭 WCF 客户端。  
  
    ```  
    aaTableClient.Close();  
    ```  
  
 有关执行 DML 操作对表和视图，包括使用更高版本，在选择操作的详细信息请参阅[执行基本插入、 更新、 删除和通过使用 WCF 服务模型的选择操作](../../adapters-and-accelerators/adapter-oracle-database/insert-update-delete-select-operations-in-oracle-db-using-a-wcf-service.md)。  
  
## <a name="creating-and-implementing-a-wcf-service-by-using-the-oracle-database-adapter"></a>创建和使用 Oracle 数据库适配器实现的 WCF 服务  
 [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]可对 Oracle 数据库表或视图执行轮询。 此功能允许你指定的适配器应定期执行对 Oracle 数据库的 SQL SELECT 查询。 此查询的结果返回到你的应用程序，通过特殊操作，POLLINGSTMT 操作。 接收结果轮询查询，你的应用程序必须实现服务协定， [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] POLLINGSTMT 操作公开。  
  
 若要实现服务以接收 POLLINGSTMT 操作，必须首先生成表示公开的服务协定的.NET 接口 （也称为 WCF 服务协定） [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] POLLINGSTMT 操作。 有关如何执行此操作的详细信息，请参阅[的 Oracle 数据库项目生成 WCF 客户端或 WCF 服务约定](../../adapters-and-accelerators/adapter-oracle-database/create-a-wcf-client-or-wcf-service-contract-for-oracle-db-solution-artifacts.md)。  
  
 然后通过实现该生成的接口实现 WCF 服务。 此类包含业务逻辑来处理 POLLINGSTMT 消息并返回对该适配器的响应。 然后使用服务主机 (**System.ServiceModel.ServiceHost**) 来承载此服务的实例。 有关详细信息，请参阅[使用 WCF 服务模型基于接收轮询的数据更改消息](../../adapters-and-accelerators/adapter-oracle-database/receive-polling-based-data-changed-messages-in-oracle-db-using-a-wcf-service.md)。  
  
## <a name="see-also"></a>另请参阅  
 [通过使用 WCF 服务模型开发 Oracle 数据库应用程序](../../adapters-and-accelerators/adapter-oracle-database/develop-oracle-database-applications-using-the-wcf-service-model.md)