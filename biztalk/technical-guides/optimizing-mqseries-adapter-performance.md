---
title: "优化 MQSeries 适配器性能 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 1a46455c-a8d2-4427-99bb-4e3c6dbd9566
caps.latest.revision: "6"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 0d4a2bd1f2cfa338d31fd574879d73249d74d08b
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="optimizing-mqseries-adapter-performance"></a>优化 MQSeries 适配器性能
使用时可以提高性能的以下设置配置 MQSeries 适配器。  
  
## <a name="adjust-the-value-for-the-mqseries-receive-adapter-polling-threads"></a>调整值，用于 MQSeries 接收适配器轮询线程  
 增加为指定的值**线程**中**MQSeries 传输属性**时将 MQSeries 适配器配置为接收位置。 增加此属性从默认值 2 5 的值将显著提高从该处可以接收消息使用 MQSeries 适配器的速率。  
  
## <a name="disable-transaction-support-on-mqseries-receive-locations-where-not-required"></a>禁用事务支持 MQSeries 上的接收位置不需要  
 MQSeries 适配器事务支持会产生很大的开销。 如果事务支持不是一项业务要求，设置**事务支持**中的值**MQSeries 传输属性**对话框中的默认值从**是**到**否**。  
  
## <a name="disable-ordered-delivery-of-messages-on-the-mqseries-adapter-when-not-required"></a>禁用时不需要的 MQSeries 适配器上的消息的有序的传递  
 启用此属性将强制执行有序的消息传递，因为它们是从接收或发送到 MQSeries 队列，但会影响性能。 启用有序的传递时，消息传送的运行时将使用单个线程从给定的 MQSeries 队列接收消息。 如果有序的消息传递，则不业务要求，然后执行更改的默认值**Ordered**中的属性**MQSeries 传输属性**对话框中设置为**否排序**。  
  
## <a name="see-also"></a>另请参阅  
 [优化 BizTalk Server 性能](../technical-guides/optimizing-biztalk-server-performance.md)