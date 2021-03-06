---
title: 消息批处理 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 5f893d16-2670-4463-9a89-6f5be912a045
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 78222848258ea4c1840b645c1357bceb49c0ac14
ms.sourcegitcommit: d27732e569b0897361dfaebca8352aa97bb7efe1
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/10/2019
ms.locfileid: "65531168"
---
# <a name="message-batches"></a>消息批
当您的适配器具有一组需要一次处理的消息时，你应执行批处理这些消息，以优化性能。 以编程方式，消息批是具有关联的操作的消息的集合。 通过对批中的消息进行分组，而不是逐个提交每个消息，你可以优化资源和处理任务的使用。 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 使用批处理执行：  

- 在许多消息范围内分摊交易成本。  

- 通过减少数据库的内部数量的增加速度往返。  

- 更有效地使用[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]以异步方式处理消息的线程池。  

  批是原子工作单元。 也就是说，在它的所有操作都成功，或在它的所有操作都失败。 如果在批处理中的一个操作成功，但另一个操作失败，构成批的所有操作都将都失效，必须重新提交消息。 这意味着适配器必须一批失败的响应中的三个操作：  

- 确定失败的消息。  

- 确定应如何处理失败的消息。  

- 重新提交未失败的消息。
