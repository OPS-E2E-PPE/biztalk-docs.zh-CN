---
title: 用于 Oracle 数据库的 BizTalk 适配器概述 |Microsoft Docs
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
ms.openlocfilehash: 0d6629672ac1bbfdd5e0bc4e01cee37c5d71d137
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "37005174"
---
# <a name="overview-of-biztalk-adapter-for-oracle-database"></a>用于 Oracle 数据库的 BizTalk 适配器概述
[!INCLUDE[adapteroracle](../../includes/adapteroracle-md.md)]公开为 WCF 服务的 Oracle 数据库。 适配器客户端可以通过交换 SOAP 消息与适配器执行对 Oracle 数据库的操作。 适配器使用 WCF 消息并调用相应 ODP.NET 来执行该操作。 适配器返回到 SOAP 消息的窗体中的客户端，并将响应返回从 Oracle 数据库。  
  
 [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]的 Oracle 数据库项目 （表、 函数、 过程等） 的图面元数据描述结构的 SOAP 消息的 WSDL 格式。 [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]使用[!INCLUDE[addadapterservreflong](../../includes/addadapterservreflong-md.md)]， [!INCLUDE[consumeadapterservlong](../../includes/consumeadapterservlong-md.md)]，和[!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)]启用适配器客户端来检索操作的元数据，并在生成的编程项目，可以使用编程解决方案中。  
  
 [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]使用 Oracle 数据提供程序的.NET (ODP.NET) 与 Oracle 数据库进行通信。 可以使用[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]以以下方式与 Oracle 数据库进行通信：  
  
- 通过开发 BizTalk 应用程序。 请参阅[开发 BizTalk 应用程序](../../core/develop-your-biztalk-applications.md)有关详细信息。  
  
- 通过使用[!INCLUDE[firstref_btsWinCommFoundation](../../includes/firstref-btswincommfoundation-md.md)]服务模型。 请参阅[开发 Oracle 数据库应用程序使用 WCF 服务模型](../../adapters-and-accelerators/adapter-oracle-database/develop-oracle-database-applications-using-the-wcf-service-model.md)有关详细信息。  
  
- 通过使用 WCF 通道模型。 请参阅[开发 Oracle 数据库应用程序使用 WCF 通道模型](../../adapters-and-accelerators/adapter-oracle-database/develop-oracle-database-applications-using-the-wcf-channel-model.md)有关详细信息。  
  
## <a name="in-this-section"></a>本节内容  
  
-   [适配器如何连接到 Oracle 数据库？](https://msdn.microsoft.com/library/cc185360(v=bts.10).aspx)  
  
-   [原理适配器图面上的 Oracle 元数据是什么？](https://msdn.microsoft.com/library/cc185310(v=bts.10).aspx)  
  
-   [哪些操作可以是执行使用适配器？](https://msdn.microsoft.com/library/cc185259(v=bts.10).aspx)  
  
-   [原理适配器处理事务是什么？](https://msdn.microsoft.com/library/dd788428.aspx)  
  
-   [Oracle 数据库中的 LOB 数据类型的流支持](../../adapters-and-accelerators/adapter-oracle-database/streaming-support-for-lob-data-types-in-oracle-database.md)  
  
-   [哪些操作支持的 Oracle 数据库适配器](../../adapters-and-accelerators/adapter-oracle-database/what-operations-are-supported-by-the-oracle-database-adapter.md)  
  
## <a name="see-also"></a>请参阅  
 [了解用于 Oracle 数据库的 Biztalk 适配器](../../adapters-and-accelerators/adapter-oracle-database/understand-the-biztalk-adapter-for-oracle-database.md)