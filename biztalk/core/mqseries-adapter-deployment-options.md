---
title: "MQSeries 适配器部署选项 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- MQSeries adapters, deploying
- deploying, MQSeries adapters
ms.assetid: d9380aff-40ea-419b-88e2-1e2ec3f023cb
caps.latest.revision: "12"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b88fa674c38df8b31c1954234846fd3939ed8568
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="mqseries-adapter-deployment-options"></a>MQSeries 适配器部署选项
使用 MQSeries 适配器可在配置硬件时提供很大的灵活性。 至少有三个主要使用模式：  
  
-   BizTalk Server、适配器和 MQSeries Server for Windows 位于同一计算机上。  
  
-   BizTalk Server 和适配器位于同一计算机上，MQSeries Server for Windows（包括 MQSAgent）位于第二台计算机上，后者连接到一台或多台运行 MQSeries 服务的其他计算机。  
  
-   一个组中的多个 BizTalk Server 安装和适配器，MQSeries 服务器（包括 MQSAgent）位于不同的计算机上。  
  
-   如果群集 MQSeries 服务器和 MQSeries 队列管理器，适配器能正常工作。  
  
    > [!NOTE]
    >  在这种情况下，不应对 MQSAgent COM+ 应用程序进行群集。 而群集的两个节点都应安装并配置 MQSAgent COM+ 应用程序。 在此方案中，如果 MQSAgent COM+ 应用程序停止运行，则下一次从客户端中进行调用时将启动该程序。  
  
## <a name="see-also"></a>另请参阅  
 [使用 MQSeries 适配器](../core/using-the-mqseries-adapter.md)