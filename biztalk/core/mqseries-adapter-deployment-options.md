---
title: MQSeries 适配器部署选项 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- MQSeries adapters, deploying
- deploying, MQSeries adapters
ms.assetid: d9380aff-40ea-419b-88e2-1e2ec3f023cb
caps.latest.revision: 12
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 18d2791b62478b1927772149f3f5d54f3cb5f618
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65264420"
---
# <a name="mqseries-adapter-deployment-options"></a>MQSeries 适配器部署选项
MQSeries 适配器为您提供了极其灵活地配置硬件。 有三个主要模式的使用：  
  
-   BizTalk Server、 适配器和 MQSeries Server for Windows 在同一计算机上。  
  
-   BizTalk Server 和上一台计算机和 MQSeries Server for Windows （包括 MQSAgent） 连接到一个或多个运行 MQSeries 服务器的其他计算机的第二个计算机上的适配器。  
  
-   多个不同的计算机上组的适配器和 MQSeries 服务器 （包括 MQSAgent） 中的 BizTalk Server 安装。  
  
-   如果群集 MQSeries Server 和 MQSeries 队列管理器，该适配器的功能正确。  
  
    > [!NOTE]
    >  MQSAgent COM + 应用程序不应在这种情况下群集。 相反，在群集的两个节点应具有的 MQSAgent COM + 应用程序安装和配置。 在此方案中，如果 MQSAgent COM + 应用程序停止时，从客户端的下一个调用将重新启动它。  
  
## <a name="see-also"></a>请参阅  
 [使用 MQSeries 适配器](../core/using-the-mqseries-adapter.md)