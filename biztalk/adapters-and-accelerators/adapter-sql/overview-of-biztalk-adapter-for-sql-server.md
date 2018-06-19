---
title: 用于 SQL Server 的 BizTalk Adapter 概述 |Microsoft 文档
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
ms.openlocfilehash: 40d0c1fd3ce3a9f07367b7cc75ffeeb98f84b119
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22222741"
---
# <a name="overview-of-biztalk-adapter-for-sql-server"></a>用于 SQL Server 的 BizTalk Adapter 的概述
[!INCLUDE[adaptersql](../../includes/adaptersql-md.md)]公开作为 WCF 服务的 SQL Server 数据库。 适配器客户端可以通过交换 SOAP 消息与适配器执行 SQL Server 数据库上的操作。 适配器使用 SOAP 消息，并且相应的 ADO.NET 调用来执行该操作。 适配器回客户端的 SOAP 消息的形式从 SQL Server 数据库返回响应。  
  
 [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]曲面元数据 （如表、 视图和过程） 的 SQL Server 数据库中的项目。  此元数据描述窗体的 Web 服务描述语言 (WSDL) 中的 SOAP 消息的结构。 [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]使用[!INCLUDE[addadapterservreflong](../../includes/addadapterservreflong-md.md)]， [!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)]，和[!INCLUDE[consumeadapterservlong](../../includes/consumeadapterservlong-md.md)]才能使适配器客户端检索操作的元数据。 适配器还编程解决方案中生成可用的编程项目。 有关详细信息[!INCLUDE[addadapterservreflong](../../includes/addadapterservreflong-md.md)]， [!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)]，和[!INCLUDE[consumeadapterservlong](../../includes/consumeadapterservlong-md.md)]，请参阅[连接到使用 SQL 适配器的 Visual Studio 中的 SQL Server](../../adapters-and-accelerators/adapter-sql/connect-to-sql-server-in-visual-studio-using-the-sql-adapter.md)。  
  
 [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]使用 ADO.NET 与 SQL Server 数据库进行通信。 你可以使用[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]可通过以下方式与 SQL Server 数据库进行通信：  
  
-   通过开发 BizTalk 应用程序。 有关详细信息，请参阅[开发 BizTalk 应用程序](../../adapters-and-accelerators/adapter-sql/develop-biztalk-applications-using-the-sql-adapter.md)。  
  
-   通过使用[!INCLUDE[firstref_btsWinCommFoundation](../../includes/firstref-btswincommfoundation-md.md)]服务模型。 有关详细信息，请参阅[开发应用程序使用 WCF 服务模型](../../adapters-and-accelerators/adapter-sql/develop-sql-applications-using-the-wcf-service-model.md)。  
  
-   通过使用 WCF 通道模型。 有关详细信息，请参阅[开发应用程序使用 WCF 通道模型](../../adapters-and-accelerators/adapter-sql/develop-sql-applications-using-the-wcf-channel-model.md)。  
  
## <a name="in-this-section"></a>本节内容  
  
-   [适配器如何连接到 SQL Server？](https://msdn.microsoft.com/library/dd788114.aspx) 
  
-   [原理适配器图面 SQL 服务器元数据是什么？](https://msdn.microsoft.com/library/dd787941.aspx)  
  
-  [哪些操作可以是执行使用适配器？](https://msdn.microsoft.com/library/cc185219(v=bts.10).aspx)  
  
-   [哪些操作受 SQL 适配器](../../adapters-and-accelerators/adapter-sql/what-operations-are-supported-by-the-sql-adapter.md)  
  
## <a name="see-also"></a>另请参阅  
 [理解 SQL Server 的 BizTalk Adapter](../../adapters-and-accelerators/adapter-sql/understand-biztalk-adapter-for-sql-server.md)