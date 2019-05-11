---
title: 创建连接到 SQL Server |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 44a03b2c-55b5-49a0-92cc-6f017720d34a
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: bbf9a791ba404f1890becc81cfcc545df2cb3f78
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65369882"
---
# <a name="create-a-connection-to-sql-server"></a>创建与 SQL Server 的连接
[!INCLUDE[adaptersql](../../includes/adaptersql-md.md)]是[!INCLUDE[firstref_btsWinCommFoundation](../../includes/firstref-btswincommfoundation-md.md)]自定义绑定。 在这种情况下，它使到 SQL Server 数据库通过 WCF 终结点地址的通信。 在 WCF 中，终结点地址标识服务的网络位置，并通常都表示为统一资源标识符 (URI)。 [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]表达此位置作为一个连接 URI，其中包含属性的[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]用于建立与 SQL Server 数据库的连接。 必须指定连接 URI 时您：  
  
- 创建通道工厂或通道侦听器使用的 WCF 通道模型或创建 WCF 客户端或服务主机使用 WCF 服务模型时。  
  
- 创建中的一个物理端口绑定[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]解决方案。  
  
- 使用[!INCLUDE[addadapterservreflong](../../includes/addadapterservreflong-md.md)]生成 WCF 客户端类或 WCF 服务模型解决方案的 WCF 服务接口。  
  
- 使用[!INCLUDE[consumeadapterservlong](../../includes/consumeadapterservlong-md.md)]来检索从消息架构[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]BizTalk Server 解决方案。  
  
- 使用 ServiceModel 元数据实用工具工具 (svcutil.exe) 生成 WCF 客户端类或 WCF 服务模型解决方案的 WCF 服务接口。  
  
  在本部分中的主题介绍如何建立之间的连接[!INCLUDE[adaptersql](../../includes/adaptersql-md.md)]和，它可以提供与 SQL Server 数据库：  
  
- 有关连接属性和 SQL Server 连接 URI 的结构信息。  
  
- 演示如何通过使用指定连接 URI 的主题的链接[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]。  
  
- 有关连接到 SQL Server 使用 Windows 身份验证的信息。  
  
  
  
## <a name="see-also"></a>请参阅  
[开发 SQL 应用程序](../../adapters-and-accelerators/adapter-sql/develop-your-sql-applications.md)