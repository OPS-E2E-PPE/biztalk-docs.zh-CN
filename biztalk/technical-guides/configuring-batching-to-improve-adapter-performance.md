---
title: 配置批处理以优化适配器性能 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 65589925-af94-45f1-b501-37c21618b2cf
caps.latest.revision: 2
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c5276c6a979783a5ab6a5e4d73573eec95cabd25
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65244053"
---
# <a name="configuring-batching-to-improve-adapter-performance"></a>配置批处理以优化适配器性能
适配器处理的批方式，可以显著影响性能。 由于没有与每个事务相关联的固定的延迟，应尝试通过组合多个到单个批处理操作的事务数量降至最低。  
  
 如果您要提交到消息[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]分批情况下，不限制批处理大小仅基于消息计数。 例如，如果批大小为 2，并且适配器获取的四个消息大小为 4 KB，8 KB，1 MB 和 5 MB 分别将是第一批大小的 12 KB 的文件和第二个批处理将的大小为 6 MB。 BizTalk 消息引擎按顺序处理单个批次中的所有消息，因为第二个批处理在此示例中将速度远远低于第一批进行处理。 此操作的效果是降低的吞吐量。  
  
 若要处理此问题，我们建议你批处理的基于消息计数和批处理 （即，批大小以字节为单位） 中的字节总数。 针对总字节数没有最佳数量。 但是，在正常处理方案中，如果批大小超过 1 mb 以内，首先将遇到较差的并发性和吞吐量。  
  
 适配器通常处理的生产环境中具有不同大小的消息。 传入消息的大小很可能差别很大。 因此，始终使用消息计数和总字节数来生成批。