---
title: 创建与 SQL Server 的连接 |Microsoft 文档
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
ms.openlocfilehash: c3b87b4141c9e14c680d8100a7c505dda0a0093c
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22225397"
---
# <a name="create-a-connection-to-sql-server"></a>创建与 SQL Server 的连接
[!INCLUDE[adaptersql](../../includes/adaptersql-md.md)]是[!INCLUDE[firstref_btsWinCommFoundation](../../includes/firstref-btswincommfoundation-md.md)]自定义绑定。 在这种情况下，它使到 SQL Server 数据库通过 WCF 终结点地址的通信。 在 WCF 中，终结点地址将标识服务的网络位置，并通常表示为统一资源标识符 (URI)。 [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]表示此位置作为连接 URI，其中包含属性的[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]用于建立与 SQL Server 数据库的连接。 必须指定连接 URI 时你：  
  
-   创建通道工厂或通道侦听器使用 WCF 通道模型或当你创建使用 WCF 服务模型的 WCF 客户端或服务主机。  
  
-   创建中的物理端口绑定[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]解决方案。  
  
-   使用[!INCLUDE[addadapterservreflong](../../includes/addadapterservreflong-md.md)]生成 WCF 客户端类或 WCF 服务模型解决方案的 WCF 服务接口。  
  
-   使用[!INCLUDE[consumeadapterservlong](../../includes/consumeadapterservlong-md.md)]检索消息架构从[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]BizTalk Server 解决方案。  
  
-   使用 ServiceModel 元数据实用工具 (svcutil.exe) 生成 WCF 客户端类或 WCF 服务模型解决方案的 WCF 服务接口。  
  
 本部分中的主题介绍如何之间建立连接[!INCLUDE[adaptersql](../../includes/adaptersql-md.md)]和通过为您提供了 SQL Server 数据库：  
  
-   有关连接属性和 SQL Server 连接 URI 的结构信息。  
  
-   演示如何通过使用指定连接 URI 的主题的链接[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]。  
  
-   有关连接到 SQL Server 使用 Windows 身份验证的信息。  
  
  
  
## <a name="see-also"></a>另请参阅  
[开发 SQL 应用程序](../../adapters-and-accelerators/adapter-sql/develop-your-sql-applications.md)