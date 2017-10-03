---
title: "TIBCO 集合限制 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: TIBCO Rendezvous, limitations
ms.assetid: 8e210457-2887-43f9-a249-be1daa6ee4eb
caps.latest.revision: "4"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 717188e42450d13dee92364cd9c673aaaf48eaf6
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="tibco-rendezvous-limitations"></a>TIBCO Rendezvous 限制
在 TIBCO Rendezvous 中，不能保证字段名的唯一性。 如果 TIBCO Rendezvous 消息包含两个相同的名称字段，则结果 XML 无效。  
  
 其他限制包括：  
  
-   未提供字段排序功能。  
  
-   根据 TIBCO Rendezvous 文档，使用者名称中不会使用非打印的字符；但是仍可能使用这样的字符。 用于 TIBCO Rendezvous 的 BizTalk 适配器不支持包含这些字符的使用者名称。  
  
-   不支持与后台程序的安全连接。  
  
-   不支持自定义数据类型。  
  
-   传输端不支持经过验证的消息。  
  
## <a name="see-also"></a>另请参阅  
 [TIBCO 会合概念](../core/tibco-rendezvous-concepts.md)   
 [入门](../core/getting-started-with-biztalk-adapter-for-tibco-rendezvous.md)