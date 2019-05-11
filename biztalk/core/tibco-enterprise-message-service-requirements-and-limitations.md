---
title: TIBCO Enterprise Message Service 要求和限制 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 6e4c022c-e6a8-4ac5-b998-b0465002a31e
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 94a0adbc67dfb78eef97876d65b4da50a343efce
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65379844"
---
# <a name="tibco-enterprise-message-service-requirements-and-limitations"></a>TIBCO Enterprise Message Service 要求和限制

## <a name="system-requirements"></a>系统要求  
包含与 TIBCO Enterprise Message Service 包括客户端 SDK （使用 TIBCO EMS C# API）。 用于 TIBCO EMS 的 BizTalk 适配器使用此 API 与 TIBCO EMS 进行通信。  
  
## <a name="add-the-api-to-the-gac"></a>将 API 添加到 GAC  
 用于 TIBCO EMS 的 BizTalk 适配器要求 TIBCO EMS C# API，TIBCO。EMS.dll，若要添加到全局程序集缓存 (GAC)。 适配器触发异常并记录相应的消息，如果未安装此程序集。  
  
1. 将复制到 TIBCO EMS C #API 你[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]计算机。  
  
2. 将目录更改为 C# API 文件，TIBCO 的位置。EMS。DLL。  
  
    在默认安装中，此 DLL 的路径是 c:\tibco\ems\clients\cs\TIBCO。EMS。DLL。  
  
3. 在命令提示符下键入：  
  
    `C:\bin> gacutil /i TIBCO.EMS.dll`  
  
    TIBCO。EMS.dll 现在显示 gac。  
  
    若要查看 GAC 列表中，在控制面板中，打开**管理工具**，打开**Microsoft.NET Framework X.XConfiguration**，然后单击**程序集缓存**。  
  
## <a name="limitations"></a>限制  
 用于 TIBCO Enterprise Message Service 的 BizTalk 适配器使用 TIBCO。EMS.dll 与 TIBCO Enterprise Message Service 进行通信。 使用 TIBCO EMS C# API 时，应考虑以下限制：  
  
-   消息压缩，允许 TIBCO EMS 客户端将以压缩形式的消息发送到 EMS，不是可用于 C# API。  
  
-   适配器与服务器之间的消息加密不可用与 C# API。 C# API 不允许 SSL 加密使用 OpenSSL 库。  
  
-   C# API 不支持用于 EMS 的管理 API。  
  
-   无法发送或接收使用 BizTalk TIBCO EMS 适配器的消息大于 50 MB 的大小。 超出此大小，在环境体验 System.OutOfMemoryException 异常。  
  
## <a name="see-also"></a>请参阅  
 [规划和体系结构](../core/planning-and-architecture16.md)