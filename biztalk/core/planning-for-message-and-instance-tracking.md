---
title: 规划消息和实例跟踪 |Microsoft Docs
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
ms.openlocfilehash: a56fa045c8da355b3e47f58b8b0ae9ace59b5067
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65395682"
---
# <a name="planning-for-message-and-instance-tracking"></a>规划消息和实例跟踪
应在规划阶段确定需要跟踪，以便部署项目后你可以设置跟踪选项并限制为您提供所需的信息的跟踪数据量的信息。  
  
 我们建议您不要跟踪所有消息，因为每次访问消息，BizTalk Server 消息与服务器实例跟踪将生成另一个副本。 例如，可以通过跟踪特定端口来缩小范围。 这有助于您的系统性能最大化并保持数据库整洁。  
  
## <a name="see-also"></a>请参阅  
 [管理和跟踪体系结构](../core/management-and-tracking-architecture.md)