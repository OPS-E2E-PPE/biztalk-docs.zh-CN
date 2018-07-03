---
title: 可选节点 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- testing, BizTalk Mapper
- maps, testing
- testing, maps
- BizTalk Mapper, testing
- maps, optional nodes
ms.assetid: 7dcd203e-fb23-438a-87d1-42323acd87cc
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 91fe82709df36b374d8744e2060798074835b891
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36994086"
---
# <a name="optional-nodes"></a>可选节点
使用可选节点将导致在测试映射时出现警告。 在以下两种情况中源节点可能会被视为可选节点：  
  
- 实际的记录或字段是可选的。  
  
- 源记录或源字段是必需的，但是其父级、祖父级或更高级别的层次是可选的。  
  
  可能存在这样的情况，源架构中的记录和字段是可选的，但目标架构却需要相应的记录或字段。  
  
  在这种可能的情况，测试您的映射生成中的警告**输出**窗口。 此外，输出数据将不包含目标节点。  
  
## <a name="see-also"></a>请参阅  
 [测试映射](../core/testing-maps.md)