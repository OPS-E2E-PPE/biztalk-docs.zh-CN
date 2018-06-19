---
title: 在博士 Edwards OneWorld 适配器中设置字符串理由 |Microsoft 文档
description: 更新 jdearglist 文件以在 BizTalk Server 业务流程中使用博士 Edwards OneWorld 适配器
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 1c9b013a-839d-45f1-9da0-c96fd45b25e5
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 70b32d0106d95a1970b480e32dfa47a81ebf98ca
ms.sourcegitcommit: dd7c54feab783ae2f8fe75873363fe9ffc77cd66
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/07/2017
ms.locfileid: "24012996"
---
# <a name="set-string-justification-in-jdearglist"></a>在 Jdearglist 中设置字符串理由

## <a name="overview"></a>概述
若要在 JD Edwards OneWorld jdearglist.txt 文件中将某些字符串参数配置为右对齐（并且向左填充），您必须知道要访问哪一个业务函数；尤其必须了解要调用业务函数中的哪些字段。  
  
 您必须先更新该 jdearglist.txt，然后在业务流程中生成绑定（架构）。 更新 jdearglist.txt 文件的说明所述[处理字符串值](../core/handling-string-values1.md)。  
  
 如果在审核日志中收到 jdearglist.txt 警告消息，则是通知您缺少 jdearglist.txt。 如果运行 SalesOrder 或 PurchaseOrder 业务函数，您的路径中必须具有该文件，否则它将不会运行。  
  
## <a name="see-also"></a>另请参阅  
[使用 BizTalk Server 异常处理](using-biztalk-server-exception-handling1.md)