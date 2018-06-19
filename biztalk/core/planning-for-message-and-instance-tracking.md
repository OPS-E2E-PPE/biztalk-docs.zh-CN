---
title: 规划消息和跟踪的实例 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- HAT, planning
- planning, HAT
ms.assetid: 69b0d30e-77df-4847-9a59-6dd806152b71
caps.latest.revision: 13
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 506dcd8342b016b325544f63f95c76c87dcc0772
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22263557"
---
# <a name="planning-for-message-and-instance-tracking"></a>规划消息和实例跟踪
应当在计划阶段确定需要跟踪的信息，以便在部署项目后可以设置跟踪选项并限制跟踪的数据量，从而仅为您提供所需的信息。  
  
 建议您不要跟踪所有消息，因为每次访问消息时，BizTalk Server 消息与服务器实例跟踪都将生成另一个副本。 例如，可以通过仅跟踪特定的端口来缩小范围。 这样有助于最大限度地提高系统性能并保持数据库不乱。  
  
## <a name="see-also"></a>另请参阅  
 [管理和跟踪体系结构](../core/management-and-tracking-architecture.md)