---
title: 使用 Multi-order 项 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- JD Edwards OneWorld adapters, multiple calls
- JD Edwards OneWorld adapters, multi-order numbers
- multiple edit line calls [JD Edwards OneWorld adapters]
- adapters [JD Edwards OneWorld adapters], multi-order numbers
- multi-order numbers [JD Edwards OneWorld adapters]
- adapters [JD Edwards OneWorld adapters], multiple calls
ms.assetid: 207ea92c-03f7-4117-8414-eb174e659d26
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 939a9d7564cf586dd989eb20d65ec3105d7533a9
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65396794"
---
# <a name="using-multi-order-items"></a>使用 Multi-order 项
由于 JD Edwards OneWorld API 的结构，如果想要在 BizTalk Server 上使用 multi-order 成员，必须在业务流程中创建多个编辑行调用，以将这些行项目添加到业务流程中。 例如，一个 multi-order 项目可能包含带有单个订单编号的标头，以及包括多个项目订单（如 Toy 1EA、Gloves 2EA）的详细信息。  
  
 若要使用多个编辑行调用，则由 BizTalk Server 开发人员负责开发这些调用的结构。 开发人员应该在业务流程中创建一个内部循环来实现这些调用。  
  
 JD Edwards OneWorld 系统支持多个编辑行调用，但该 API 不支持此功能。 如果您正在查看编辑行方法的结构，它是一个平滑的结构而不是一个序列。 因此，您必须在每次想要插入行项目时调用此函数。  
  
## <a name="see-also"></a>请参阅  
 [规划和体系结构](../core/planning-and-architecture17.md)