---
title: "在 Jdearglist 中设置字符串理由 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- jdearglist.txt, setting string justification
- strings, configuring
- strings, right-justified
ms.assetid: 1c9b013a-839d-45f1-9da0-c96fd45b25e5
caps.latest.revision: "6"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: daecf4101ebf5dc8964562dc7f385d41279a3401
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="setting-string-justification-in-jdearglist"></a>在 Jdearglist 中设置字符串对齐
若要在 JD Edwards OneWorld jdearglist.txt 文件中将某些字符串参数配置为右对齐（并且向左填充），您必须知道要访问哪一个业务函数；尤其必须了解要调用业务函数中的哪些字段。  
  
 您必须先更新该 jdearglist.txt，然后在业务流程中生成绑定（架构）。 更新 jdearglist.txt 文件的说明所述[处理字符串值](../core/handling-string-values1.md)。  
  
 如果在审核日志中收到 jdearglist.txt 警告消息，则是通知您缺少 jdearglist.txt。 如果运行 SalesOrder 或 PurchaseOrder 业务函数，您的路径中必须具有该文件，否则它将不会运行。  
  
## <a name="see-also"></a>另请参阅  
 [管理 BizTalk 适配器用于博士 Edwards OneWorld](../core/administering-biztalk-adapter-for-jd-edwards-oneworld.md)