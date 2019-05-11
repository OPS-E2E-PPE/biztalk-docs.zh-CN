---
title: 优化 MQSeries 适配器性能 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 1a46455c-a8d2-4427-99bb-4e3c6dbd9566
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 1ba12a46e17c8c521afef62e7c0ad5a9f51afe35
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65291427"
---
# <a name="optimizing-mqseries-adapter-performance"></a>优化 MQSeries 适配器性能
使用以下设置时，可以增加性能配置 MQSeries 适配器。  
  
## <a name="adjust-the-value-for-the-mqseries-receive-adapter-polling-threads"></a>将值调整为 MQSeries 接收适配器轮询线程  
 增加为指定的值**线程**中**MQSeries 传输属性**时配置 MQSeries 适配器接收位置。 增加此属性的默认值为 2 从 5 的值将极大地缩短从该处可以接收消息使用 MQSeries 适配器的速率。  
  
## <a name="disable-transaction-support-on-mqseries-receive-locations-where-not-required"></a>禁用事务支持，在 MQSeries 接收位置在不需要  
 MQSeries 适配器的事务支持会产生很大的开销。 如果事务支持不是一项业务要求，设置**支持事务**中的值**MQSeries 传输属性**对话框中的默认值从**是**到**否**。  
  
## <a name="disable-ordered-delivery-of-messages-on-the-mqseries-adapter-when-not-required"></a>禁用 MQSeries 适配器时不是必需的适配器上的消息按序的的送达  
 启用此属性将强制执行按序的送达消息，因为从接收或发送到 MQSeries 队列，但会影响性能。 启用按序的送达后，消息传送的运行时将使用一个线程从给定的 MQSeries 队列接收消息。 如果按序送达消息不是一项业务要求，则执行更改的默认值**Ordered**属性中的**MQSeries 传输属性**对话框中为其设置为**否排序**。  
  
## <a name="see-also"></a>请参阅  
 [优化 BizTalk Server 性能](../technical-guides/optimizing-biztalk-server-performance.md)