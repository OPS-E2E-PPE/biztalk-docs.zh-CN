---
title: "可选节点 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- testing, BizTalk Mapper
- maps, testing
- testing, maps
- BizTalk Mapper, testing
- maps, optional nodes
ms.assetid: 7dcd203e-fb23-438a-87d1-42323acd87cc
caps.latest.revision: "6"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 96cf7d8b22ee8469a7e52dba7bbad899209c5274
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="optional-nodes"></a>可选的节点
使用可选节点将导致在测试映射时出现警告。 在以下两种情况中源节点可能会被视为可选节点：  
  
-   实际的记录或字段是可选的。  
  
-   源记录或源字段是必需的，但是其父级、祖父级或更高级别的层次是可选的。  
  
 可能存在这样的情况，源架构中的记录和字段是可选的，但目标架构却需要相应的记录或字段。  
  
 在这两种可能的情况，测试你的代码图生成中的某个警告**输出**窗口。 此外，输出数据将不包含目标节点。  
  
## <a name="see-also"></a>另请参阅  
 [测试映射](../core/testing-maps.md)