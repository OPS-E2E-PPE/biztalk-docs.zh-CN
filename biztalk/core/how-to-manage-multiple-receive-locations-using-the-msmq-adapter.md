---
title: 如何管理多个接收位置使用 MSMQ 适配器 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
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
caps.latest.revision: 15
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 3b46ab60e3e5073c7c487ffb530dbc0407b0444f
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65384709"
---
# <a name="how-to-manage-multiple-receive-locations-using-the-msmq-adapter"></a>如何管理多个接收位置使用 MSMQ 适配器
若要提高性能，MSMQ 适配器是多线程。 如果有多个接收位置，可能不有足够的线程可用于所有接收位置。 这会妨碍某些接收位置提取消息。 有三种方法来解决此问题：  
  
-   添加到您的计算机的 BizTalk 主机，并划分的主机之间的接收位置。 添加主机使更多的线程可用于接收位置。  
  
-   设置**串行处理**属性设置为`True`上每个接收位置。 将属性设置为`True`分配到每个线程的单个接收位置。 这将使更多可用的线程池中。 但是，这可能还会导致性能降低。  
  
-   修改注册表以增加 MSMQ 适配器接收处理程序是可用于该主机的线程数。 有关详细信息请参阅**修改主机的 CLR 宿主线程值**一部分[配置参数会影响适配器性能的](../core/configuration-parameters-that-affect-adapter-performance.md)。  
  
## <a name="see-also"></a>请参阅  
 [配置 MSMQ 适配器](../core/configuring-the-msmq-adapter.md)