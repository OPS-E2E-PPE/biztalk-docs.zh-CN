---
title: 连接到 SAP 系统使用的适配器 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- connection URI
- adapters, connecting to an SAP system
- connection string
ms.assetid: d506a948-5f4a-420b-a404-508824683099
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 5b8c470d294124826d79903fcdf6eef54303f646
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65373670"
---
# <a name="connect-to-an-sap-system-using-the-adapter"></a>连接到 SAP 系统使用的适配器
[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]要求适配器客户端提供连接字符串，调用统一资源标识符 (URI) 来连接到 SAP 系统的连接。 使用一个连接 URI，适配器客户端可以指定连接参数，以连接到外部系统。有关连接 URI 的详细信息，请参阅[创建连接到 SAP 系统](../../adapters-and-accelerators/adapter-sap/create-a-connection-to-the-sap-system.md)。  
  
 请确保符合安全指导原则建立与 SAP 系统的连接时。 有关安全指导原则的详细信息，请参阅[保护 SAP 应用程序](../../adapters-and-accelerators/adapter-sap/secure-your-sap-applications.md)。
  
## <a name="how-many-connections-can-the-adapter-open-to-the-sap-system"></a>多少个连接可以适配器打开到 SAP 系统？  
 默认情况下，SAP 系统启用客户端打开 100 个连接到 SAP 系统。 但是，您可以运行 SAP 系统以提高对连接数的限制的计算机上设置环境变量。 有关详细信息，请参阅[SAP 适配器的故障排除操作问题](../../adapters-and-accelerators/adapter-sap/troubleshoot-operational-issues-with-the-sap-adapter.md)。  
  
## <a name="see-also"></a>请参阅  
 [用于 mySAP Business Suite 的 BizTalk 适配器的体系结构概述](../../adapters-and-accelerators/adapter-sap/architecture-overview-of-the-biztalk-adapter-for-mysap-business-suite.md)