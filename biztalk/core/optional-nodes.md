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
ms.openlocfilehash: bbab14a66f0ac88f32e945bf7b9c738eb419b654
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65323399"
---
# <a name="optional-nodes"></a>可选节点
使用可选节点会在测试映射时生成警告。 有在其中一个源节点可能会被视为可选的两个条件：  
  
- 实际的记录或字段是可选的。  
  
- 源记录或字段是必需的但父级、 祖父级和更高级别的层次结构是可选的。  
  
  您可能会存在这样的情况的记录和源架构中的字段是可选的但目标架构所需的相应记录或字段。  
  
  在这种可能的情况，测试您的映射生成中的警告**输出**窗口。 此外，输出数据将不包括目标节点。  
  
## <a name="see-also"></a>请参阅  
 [测试映射](../core/testing-maps.md)