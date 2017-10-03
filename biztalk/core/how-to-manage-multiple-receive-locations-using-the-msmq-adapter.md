---
title: "如何管理多个接收位置使用 MSMQ 适配器 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- MSMQ adapters, receive locations
- MSMQ adapters, threads
- receive locations, multiple
- threads
- receive locations, MSMQ adapters
- receive locations, threads
- configuring [MSMQ adapters], receive locations
ms.assetid: 5b2ee043-bcc9-443b-84b0-df7f487159eb
caps.latest.revision: "15"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 72438551d2ecab09b918808d43e7d7de6d600677
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-manage-multiple-receive-locations-using-the-msmq-adapter"></a>如何使用 MSMQ 适配器管理多个接收位置
为了提高性能，MSMQ 适配器提供了多线程功能。 如果您具有许多接收位置，则可能会没有足够的线程用于所有接收位置。 这会妨碍某些接收位置对消息的提取。 解决这一问题有以下三种方法：  
  
-   向您的计算机添加多个 BizTalk 主机，并将各接收位置划分给这些主机。 添加主机可为接收位置提供更多线程。  
  
-   设置**串行处理**属性`True`上每个接收位置。 将属性设置为`True`将分配给每个线程单个接收位置。 这样池中可用的线程就会增多。 不过，这也可能会导致性能降低。  
  
-   修改注册表以增加 MSMQ 适配器接收处理程序的主机可使用的线程数。 有关详细信息请参阅**修改主机的 CLR 承载线程值**部分[配置参数会影响适配器性能](../core/configuration-parameters-that-affect-adapter-performance.md)。  
  
## <a name="see-also"></a>另请参阅  
 [配置 MSMQ 适配器](../core/configuring-the-msmq-adapter.md)