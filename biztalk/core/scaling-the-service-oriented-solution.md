---
title: 缩放服务面向解决方案 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- scaling, service solutions
- service solution tutorial, scaling
ms.assetid: 6c22a68d-03e7-4174-b612-0e2246aa9413
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 3026664d3a365630c93bf1c61d7cf635fdd9dc31
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22269173"
---
# <a name="scaling-the-service-oriented-solution"></a>缩放服务面向解决方案
若要扩展解决方案以支持更高的吞吐量，同时保持较短的消息延迟时间，则需要使用该解决方案的内联版本。 内联解决方案在与后端系统进行交互时将绕过 MessageBox 数据库。  
  
 也可以添加 BizTalk Server 处理服务器来运行业务流程。 这样会降低每台服务器的使用率，从而可以迅速处理新的请求。 还可以扩展 MessageBox 服务器，以便该服务器具有足够的能力处理消息吞吐量。  
  
 但是，如果具有多个 MessageBox 数据库，则面向服务的体系结构解决方案不会从中受益。 如有多个 MessageBox，则要求使用分布式事务处理协调器 (DTC) 事务。 这些事务会延长总的消息延迟时间。  
  
 通过取消用于添加 MQSeries 标头信息的管道组件，可以缩短响应时间。 有关详细信息，请参阅[实现突出显示的服务面向解决方案](../core/implementation-highlights-of-the-service-oriented-solution.md)。  
  
## <a name="see-also"></a>另请参阅  
 [面向开发的服务解决方案](../core/developing-a-service-oriented-solution.md)