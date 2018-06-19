---
title: EPM 线程池大小设置 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 9e170e76-5151-4306-9473-5b68e815219a
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 54afa88b51876d0ee56f548f263be1b00c37967a
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22271133"
---
# <a name="setting-the-epm-threadpool-size"></a>设置 EPM 线程池大小
本主题说明如何设置为终结点管理器 (EPM) 的线程池大小。  
  
 上**高级**选项卡中**主机属性**对话框中，没有名为的属性**每个 CPU 线程的最大数量的消息传递引擎**。 有关访问此对话框中的说明，请参阅[如何创建新的主机](../core/how-to-create-a-new-host.md)。 使用此属性来控制的消息传递引擎用于处理消息的进程线程池的大小。 默认值为此属性为 20，这意味着消息引擎将为每个服务器上的 CPU 使用不能超过 20 个线程。  
  
 由于消息批处理池中的每个线程处理，调整的值**每个 CPU 线程的最大数量的消息传递引擎**可以通过更改服务器上的资源使用率的 dynamics 影响性能。 有关线程池的工作原理的详细信息，请参阅[使用 BizTalk Messaging Engine](../core/using-the-biztalk-messaging-engine.md)。  
  
 测试表明，在其中 CPU 或 SQL Server 过度使用的情况下，减少的值**每个 CPU 线程的最大数量的消息传递引擎**可能会导致吞吐量净的性能收益。 例如，在其中 MessageBox 数据库服务器表现出 CPU 的情况下利用率高于 90%或 SQL 锁等待时间将提升超过 500-1000 毫秒，减少池中的线程数会减少对 SQL 进行的所有连接服务器，这会导致消息处理更高效。 在某些情况下，将设置最大线程池大小的值低 2 可能会导致显著提高吞吐量提升。  
  
## <a name="recommendation"></a>建议  
 在优化的 BizTalk Server 安装，建议你精细优化为设置的值**每个 CPU 线程的最大数量的消息传递引擎**。  尝试减少 MessageBox 数据库服务器的使用率，请考虑减小此属性的值。  
  
 当 BizTalk server 或 MessageBox 数据库服务器不高利用率，并应用额外的负载不会导致更高的吞吐量时，请尝试增加的值**每个 CPU 线程的最大数量的消息传递引擎**若要利用使用不足的资源。  
  
## <a name="see-also"></a>另请参阅  
 [如何创建新的主机](../core/how-to-create-a-new-host.md)   
 [使用 BizTalk 消息传送引擎](../core/using-the-biztalk-messaging-engine.md)