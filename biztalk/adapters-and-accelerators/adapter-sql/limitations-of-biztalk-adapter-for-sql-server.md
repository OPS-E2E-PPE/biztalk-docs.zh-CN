---
title: "SQL Server 的 BizTalk Adapter 限制 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 5a19b109-a6b7-452f-a544-48627fa52f36
caps.latest.revision: "15"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c5a80990a9e3f417b64a06d8823300d53b2c4f3b
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="limitations-of-biztalk-adapter-for-sql-server"></a>BizTalk Adapter for SQL Server 的限制
以下已知的限制[!INCLUDE[adaptersql](../../includes/adaptersql-md.md)]:  
  
-   [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]不支持在 SQL Server 数据库中创建的同义词。 有关 SQL Server 中的同义词的信息，请参阅[http://go.microsoft.com/fwlink/?LinkId=120111](http://go.microsoft.com/fwlink/?LinkId=120111)。  
  
-   如果你更改运行的计算机的系统时间[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]主机，时间不会自动更新中[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]主机。 这可能导致不正确的行为使用接收端口的入站操作[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]。 一种解决方法，你必须重新启动后已更改运行它的计算机的系统时间已接收端口的主机实例。  
  
-   如果存储过程中的参数名包含 127 或多个字符，则无法执行存储的过程使用[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]。 这是由于 ADO.NET 的限制。  
  
-   WSDL[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]时转换为代理生成、 公开 System.DateTime 的 DateTimeOffset 列。 此数据类型不能存储时区信息。 因此，该适配器将发送到代理的任何日期/时间值将转换为.NET 应用程序中的本地时间。 如果您想要保留时区信息，则必须更改你的代理服务器来代替 System.DateTime 字符串类型的接口。 然后，使用 XmlConvert.ToDateTimeOffset 创建 Sytstem.DateTimeOffset 对象，可以存储的时区信息。  
  
## <a name="see-also"></a>另请参阅  
 [理解 SQL Server 的 BizTalk Adapter](../../adapters-and-accelerators/adapter-sql/understand-biztalk-adapter-for-sql-server.md)