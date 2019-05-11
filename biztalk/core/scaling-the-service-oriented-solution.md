---
title: 扩展面向服务的解决方案 |Microsoft Docs
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
ms.openlocfilehash: 895b0ad325e9dce4086c90bccf932f73226780e1
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65308911"
---
# <a name="scaling-the-service-oriented-solution"></a>扩展面向服务的解决方案
若要扩展解决方案以支持更高的吞吐量，同时保持低消息延迟要求使用该解决方案的内联版本。 内联解决方案与后端系统进行交互时，会绕过 MessageBox 数据库。  
  
 此外可以添加 BizTalk Server 处理服务器来运行业务流程。 这将减少每个服务器的使用率，以便可以快速处理新请求。 此外可以纵向 MessageBox 服务器，以便有足够的额外容量来处理消息吞吐量。  
  
 但是，面向服务的体系结构解决方案不会不受益于具有多个 MessageBox 数据库。 多个 Messagebox 需要分布式的事务处理协调器 (DTC) 事务。 这些事务会延长总的消息延迟时间。  
  
 可以添加 MQSeries 标头信息的管道组件，从而缩短响应时间。 有关详细信息，请参阅[实现面向服务的解决方案的重点](../core/implementation-highlights-of-the-service-oriented-solution.md)。  
  
## <a name="see-also"></a>请参阅  
 [开发面向服务的解决方案](../core/developing-a-service-oriented-solution.md)