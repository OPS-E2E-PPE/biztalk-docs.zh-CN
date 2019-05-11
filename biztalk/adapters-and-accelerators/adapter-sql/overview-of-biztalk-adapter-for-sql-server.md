---
title: 适用于 SQL Server 的 BizTalk 适配器概述 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 8e46690e-d5c4-4d6b-b7a0-9a5adf4431cd
caps.latest.revision: 13
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 9a026cabfbfd2dfb846ec3dd2ca27483f5c564fc
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65368507"
---
# <a name="overview-of-biztalk-adapter-for-sql-server"></a>适用于 SQL Server 的 BizTalk 适配器概述
[!INCLUDE[adaptersql](../../includes/adaptersql-md.md)]公开为 WCF 服务的 SQL Server 数据库。 适配器客户端可以通过交换 SOAP 消息与适配器执行 SQL Server 数据库上的操作。 适配器将使用 SOAP 消息，并执行相应的 ADO.NET 调用，以执行该操作。 适配器返回到 SOAP 消息的窗体中的客户端从 SQL Server 数据库返回响应。  
  
 [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]图面 （如表、 视图和过程） 的 SQL Server 数据库中的项目的元数据。  此元数据描述窗体的 Web 服务描述语言 (WSDL) 中的 SOAP 消息的结构。 [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]使用[!INCLUDE[addadapterservreflong](../../includes/addadapterservreflong-md.md)]， [!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)]，和[!INCLUDE[consumeadapterservlong](../../includes/consumeadapterservlong-md.md)]启用适配器客户端来检索操作的元数据。 适配器还生成的编程项目，可以使用编程解决方案中。 有关详细信息[!INCLUDE[addadapterservreflong](../../includes/addadapterservreflong-md.md)]， [!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)]，并[!INCLUDE[consumeadapterservlong](../../includes/consumeadapterservlong-md.md)]，请参阅[连接到 SQL Server 在 Visual Studio 中使用 SQL 适配器](../../adapters-and-accelerators/adapter-sql/connect-to-sql-server-in-visual-studio-using-the-sql-adapter.md)。  
  
 [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]使用 ADO.NET 与 SQL Server 数据库进行通信。 可以使用[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]以以下方式与 SQL Server 数据库进行通信：  
  
- 通过开发 BizTalk 应用程序。 有关详细信息，请参阅[开发 BizTalk 应用程序](../../adapters-and-accelerators/adapter-sql/develop-biztalk-applications-using-the-sql-adapter.md)。  
  
- 通过使用[!INCLUDE[firstref_btsWinCommFoundation](../../includes/firstref-btswincommfoundation-md.md)]服务模型。 有关详细信息，请参阅[开发应用程序使用 WCF 服务模型](../../adapters-and-accelerators/adapter-sql/develop-sql-applications-using-the-wcf-service-model.md)。  
  
- 通过使用 WCF 通道模型。 有关详细信息，请参阅[开发应用程序使用 WCF 通道模型](../../adapters-and-accelerators/adapter-sql/develop-sql-applications-using-the-wcf-channel-model.md)。  
  
## <a name="in-this-section"></a>本节内容  
  
-   [适配器如何连接到 SQL Server？](https://msdn.microsoft.com/library/dd788114.aspx) 
  
-   [原理适配器图面上的 SQL Server 元数据是什么？](https://msdn.microsoft.com/library/dd787941.aspx)  
  
-  [哪些操作可以是执行使用适配器？](https://msdn.microsoft.com/library/cc185219(v=bts.10).aspx)  
  
-   [通过 SQL 适配器支持哪些操作](../../adapters-and-accelerators/adapter-sql/what-operations-are-supported-by-the-sql-adapter.md)  
  
## <a name="see-also"></a>请参阅  
 [了解用于 SQL Server 的 BizTalk 适配器](../../adapters-and-accelerators/adapter-sql/understand-biztalk-adapter-for-sql-server.md)