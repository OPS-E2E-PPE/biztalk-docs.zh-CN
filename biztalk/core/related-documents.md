---
title: "相关文档 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- queries [BAM], document references
- definition files [BAM], related documents
- Query Builder [BAM portal], viewing details
- document references [BAM]
- Query Builder [BAM portal], document references
- queries [BAM], viewing details
ms.assetid: 9c5f2175-fe7c-40ec-910d-1ac5c8142045
caps.latest.revision: "10"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 5b87f0d31010a8bf80e09c59f05f2f9302a510e2
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/28/2017
---
# <a name="related-documents"></a>相关的文档
查询结果详细信息的“相关文档”区域显示与活动相关的引用文档的列表。 文档可以是任何类型，包括 CAD 映像。WAV 文件或采购订单。 例如，“采购订单”活动通常将“采购订单”作为基本文档类型。 该列表将包含采购订单的链接。  
  
## <a name="adding-document-references"></a>文档中添加引用  
 在两种方式之一生成相关文档的列表：  
  
-   当你开发跟踪配置文件时包括文档引用 URL 节点在内的活动树中，并且然后将其映射从包含指向物理文档的引用的源。  
  
-   集成开发人员以编程方式填充的列表，通过调用自定义应用程序。  
  
 定义使用这些方法之一的文档引用将添加中的行\<activityname\>_References 表与文档位置。  
  
 如果已执行这些任务任一，**相关文档**区域为空。  
  
## <a name="see-also"></a>另请参阅  
 [跟踪配置文件编辑器](../core/tracking-profile-editor.md)