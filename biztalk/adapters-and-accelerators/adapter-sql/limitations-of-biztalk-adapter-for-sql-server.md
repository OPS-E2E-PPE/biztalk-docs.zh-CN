---
title: 适用于 SQL Server 的 BizTalk 适配器的限制 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 5a19b109-a6b7-452f-a544-48627fa52f36
caps.latest.revision: 15
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 195701e4bba469a7faaab36a5ae1636c5abca5f4
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36967382"
---
# <a name="limitations-of-biztalk-adapter-for-sql-server"></a>适用于 SQL Server 的 BizTalk 适配器的限制
以下已知的限制[!INCLUDE[adaptersql](../../includes/adaptersql-md.md)]:  
  
- [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]不支持在 SQL Server 数据库中创建的同义词。 有关 SQL Server 中的同义词功能的信息，请参阅[ http://go.microsoft.com/fwlink/?LinkId=120111 ](http://go.microsoft.com/fwlink/?LinkId=120111)。  
  
- 如果您更改运行的计算机的系统时间[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]主机，时间不会自动更新中[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]主机。 这可能导致不正确的行为使用的接收端口的入站操作[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]。 解决此问题，必须重新启动主机实例的接收端口后已更改运行它的计算机的系统时间。  
  
- 如果在存储过程的参数名称包含 127 或多个字符，则无法执行存储的过程使用[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]。 这是因为 ADO.NET 的限制。  
  
- WSDL[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]时转换为代理生成、 公开为 System.DateTime DateTimeOffset 列。 此数据类型不能存储时区信息。 因此，适配器将发送到代理的任何日期/时间值将转换为.NET 应用程序中的本地时间。 如果您想要保留的时区信息，则必须更改您的代理服务器而不是 System.DateTime 使用字符串类型的接口。 然后，使用 XmlConvert.ToDateTimeOffset 创建 Sytstem.DateTimeOffset 对象，可以存储时区信息。  
  
## <a name="see-also"></a>请参阅  
 [了解适用于 SQL Server 的 BizTalk 适配器](../../adapters-and-accelerators/adapter-sql/understand-biztalk-adapter-for-sql-server.md)