---
title: 相关文档 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- queries [BAM], document references
- definition files [BAM], related documents
- Query Builder [BAM portal], viewing details
- document references [BAM]
- Query Builder [BAM portal], document references
- queries [BAM], viewing details
ms.assetid: 9c5f2175-fe7c-40ec-910d-1ac5c8142045
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 56338d268bac6568f8e175b6e70da202715fd7a8
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "37006727"
---
# <a name="related-documents"></a>相关的文档
查询结果详细信息的“相关文档”区域显示与活动相关的引用文档的列表。 文档可以是任何类型，包括 CAD 图像。WAV 文件或采购订单。 例如，“采购订单”活动通常将“采购订单”作为基本文档类型。 列表将包含采购订单的链接。  
  
## <a name="adding-document-references"></a>添加文档引用  
 在以下两种方式生成相关文档的列表：  
  
- 开发您的跟踪配置文件时您将一个文档引用 URL 节点包含的活动树中，然后将其映射从包含指向物理文档的引用的源。  
  
- 集成开发人员以编程方式填充通过调用自定义应用程序的列表。  
  
  定义使用其中一种方法的文档引用将添加中的某一行\<activityname\>_References 表与文档位置。  
  
  如果已执行这些任务任一，**相关文档**区域将为空。  
  
## <a name="see-also"></a>请参阅  
 [跟踪配置文件编辑器](../core/tracking-profile-editor.md)