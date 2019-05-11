---
title: 设置 EPM 线程池的大小 |Microsoft Docs
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
ms.openlocfilehash: 0eeb755b7fbee5939510e9e3fae0bb8868f91611
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65393236"
---
# <a name="setting-the-epm-threadpool-size"></a>设置 EPM 线程池的大小
本主题说明如何设置为终结点管理器 (EPM) 的线程池大小。  
  
 上**高级**选项卡**主机属性**对话框中，还有一个名为属性**每 CPU 的最大数量的消息引擎线程**。 有关访问此对话框中的说明，请参阅[如何创建新的主机](../core/how-to-create-a-new-host.md)。 使用此属性来控制消息引擎使用来处理消息的进程线程池的大小。 默认值为 20，这意味着消息引擎将为每个 CPU 的服务器上使用不超过 20 个线程。  
  
 由于消息批通过在池中每个线程处理，因此调整的值**每 CPU 的最大数量的消息引擎线程**可以通过更改在服务器上的资源利用率的动态会影响性能。 有关线程池的工作原理的详细信息，请参阅[使用 BizTalk 消息引擎](../core/using-the-biztalk-messaging-engine.md)。  
  
 测试表明，在其中 CPU 或 SQL Server 过度的情况下，减小值的**每 CPU 的最大数量的消息引擎线程**可能会导致吞吐量的净增加。 例如，在其中 MessageBox 数据库服务器表现出 CPU 的情况下利用率高于 90%或 SQL 锁等待时间提升超过 500-1000 毫秒，减少池中的线程数将减少对 SQL 进行的所有连接服务器，这会导致更有效的消息处理。 在某些情况下，将最大线程池大小设置为值低 2 可能会导致可测量吞吐量提升。  
  
## <a name="recommendation"></a>建议  
 在优化时 BizTalk Server 安装，建议您调整为设置的值**每 CPU 的最大数量的消息引擎线程**。  当您尝试减少 MessageBox 数据库服务器的使用率时，请考虑减少此属性的值。  
  
 当 BizTalk server 或 MessageBox 数据库服务器的利用率不高，并应用其他负载不会导致更高的吞吐量时，请尝试增加的值**每 CPU 的最大数量的消息引擎线程**若要充分利用未充分利用资源。  
  
## <a name="see-also"></a>请参阅  
 [如何创建新的主机](../core/how-to-create-a-new-host.md)   
 [使用 BizTalk 消息引擎](../core/using-the-biztalk-messaging-engine.md)