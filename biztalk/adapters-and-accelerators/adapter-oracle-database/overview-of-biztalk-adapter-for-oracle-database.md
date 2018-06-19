---
title: 用于 Oracle 数据库的 BizTalk Adapter 概述 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- adapter, overview
- ODP.NET
- Oracle Data Provider for .NET 2.0
ms.assetid: 852b8f82-ab34-45b8-ad7f-263d719a87f9
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 7b874b5523256342a4e8ae14b2c475ede11fe279
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22214205"
---
# <a name="overview-of-biztalk-adapter-for-oracle-database"></a>用于 Oracle 数据库的 BizTalk Adapter 的概述
[!INCLUDE[adapteroracle](../../includes/adapteroracle-md.md)]公开作为 WCF 服务的 Oracle 数据库。 适配器客户端可以通过交换 SOAP 消息与适配器执行对 Oracle 数据库的操作。 适配器使用 WCF 消息，并且相应 ODP.NET 调用来执行该操作。 适配器回客户端的 SOAP 消息的形式，从 Oracle 数据库中返回响应。  
  
 [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]曲面描述元数据的 Oracle 数据库项目 （表、 函数、 过程等） 的结构的 SOAP 消息的 WSDL 形式。 [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]使用[!INCLUDE[addadapterservreflong](../../includes/addadapterservreflong-md.md)]， [!INCLUDE[consumeadapterservlong](../../includes/consumeadapterservlong-md.md)]，和[!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)]才能使适配器客户端检索操作的元数据并在编程解决方案中生成可用的编程项目。  
  
 [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]使用 Oracle 数据提供程序的.NET (ODP.NET) 与 Oracle 数据库通信。 你可以使用[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]与 Oracle 数据库通信通过以下方式：  
  
-   通过开发 BizTalk 应用程序。 请参阅[开发 BizTalk 应用程序](../../core/develop-your-biztalk-applications.md)有关详细信息。  
  
-   通过使用[!INCLUDE[firstref_btsWinCommFoundation](../../includes/firstref-btswincommfoundation-md.md)]服务模型。 请参阅[开发 Oracle 数据库应用程序使用 WCF 服务模型](../../adapters-and-accelerators/adapter-oracle-database/develop-oracle-database-applications-using-the-wcf-service-model.md)有关详细信息。  
  
-   通过使用 WCF 通道模型。 请参阅[开发 Oracle 数据库应用程序使用 WCF 通道模型](../../adapters-and-accelerators/adapter-oracle-database/develop-oracle-database-applications-using-the-wcf-channel-model.md)有关详细信息。  
  
## <a name="in-this-section"></a>本节内容  
  
-   [适配器如何连接到 Oracle 数据库？](https://msdn.microsoft.com/library/cc185360(v=bts.10).aspx)  
  
-   [原理适配器图面 Oracle 元数据是什么？](https://msdn.microsoft.com/library/cc185310(v=bts.10).aspx)  
  
-   [哪些操作可以是执行使用适配器？](https://msdn.microsoft.com/library/cc185259(v=bts.10).aspx)  
  
-   [如何执行适配器处理事务？](https://msdn.microsoft.com/library/dd788428.aspx)  
  
-   [Oracle 数据库中的 LOB 数据类型的流式处理支持](../../adapters-and-accelerators/adapter-oracle-database/streaming-support-for-lob-data-types-in-oracle-database.md)  
  
-   [Oracle 数据库适配器支持何种操作](../../adapters-and-accelerators/adapter-oracle-database/what-operations-are-supported-by-the-oracle-database-adapter.md)  
  
## <a name="see-also"></a>另请参阅  
 [了解 Biztalk 适配器用于 Oracle 数据库](../../adapters-and-accelerators/adapter-oracle-database/understand-the-biztalk-adapter-for-oracle-database.md)