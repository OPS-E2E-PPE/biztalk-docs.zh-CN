---
title: "连接到 SAP 系统使用适配器 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- connection URI
- adapters, connecting to an SAP system
- connection string
ms.assetid: d506a948-5f4a-420b-a404-508824683099
caps.latest.revision: "6"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 75f8c4b8650b2c81b3b82bf520958646e20da380
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="connect-to-an-sap-system-using-the-adapter"></a>连接到 SAP 系统使用适配器
[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]要求适配器客户端提供连接字符串，调用统一资源标识符 (URI) 以连接到 SAP 系统的连接。 通过连接 URI 适配器客户端可以指定要连接到外部系统的连接参数。有关连接 URI 的详细信息，请参阅[创建与 SAP 系统的连接](../../adapters-and-accelerators/adapter-sap/create-a-connection-to-the-sap-system.md)。  
  
 请确保您遵守安全指导原则建立与 SAP 系统的连接时。 有关安全指导原则的详细信息，请参阅[保护 SAP 应用程序](../../adapters-and-accelerators/adapter-sap/secure-your-sap-applications.md)。
  
## <a name="how-many-connections-can-the-adapter-open-to-the-sap-system"></a>多少个连接可以适配器打开到 SAP 系统？  
 默认情况下，SAP 系统启用客户端打开 100 个连接到 SAP 系统。 但是，你可以运行 SAP 系统，以增大对连接数限制的计算机上设置环境变量。 有关详细信息，请参阅[与 SAP 适配器故障排除操作问题](../../adapters-and-accelerators/adapter-sap/troubleshoot-operational-issues-with-the-sap-adapter.md)。  
  
## <a name="see-also"></a>另请参阅  
 [为 mySAP Business Suite 的 BizTalk 适配器的体系结构概述](../../adapters-and-accelerators/adapter-sap/architecture-overview-of-the-biztalk-adapter-for-mysap-business-suite.md)