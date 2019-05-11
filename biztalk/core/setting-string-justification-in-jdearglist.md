---
title: 在 JD Edwards OneWorld 适配器中设置字符串对齐 |Microsoft Docs
description: 更新 jdearglist 文件以在 BizTalk Server 业务流程中使用 JD Edwards OneWorld 适配器
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
ms.openlocfilehash: 8f33941e997315a5e91e5c99f4e6dc4bd0d2b7aa
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65393247"
---
# <a name="set-string-justification-in-jdearglist"></a>在 Jdearglist 中设置字符串对齐

## <a name="overview"></a>概述
若要配置某些字符串参数，右对齐 （并且向左填充） 在 JD Edwards OneWorld jdearglist.txt 文件中，您必须知道你想要访问; 哪些业务函数具体而言，您必须知道你想要调用业务函数中的哪些字段。  
  
 在业务流程中生成的绑定 （架构） 之前，必须更新 jdearglist.txt。 用于更新 jdearglist.txt 文件的说明所述[处理字符串值](../core/handling-string-values1.md)。  
  
 如果审核日志中收到 jdearglist.txt 警告消息，它将通知您缺少指定 jdearglist.txt。 如果运行 SalesOrder 或 PurchaseOrder 业务函数，该文件必须在你的路径，或它将无法工作。  
  
## <a name="see-also"></a>请参阅  
[使用 BizTalk Server 异常处理](using-biztalk-server-exception-handling1.md)