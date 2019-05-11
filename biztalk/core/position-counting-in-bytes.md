---
title: 以字节为单位计算位置 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 5cf666ec-d15e-4d2d-9df9-49189f352c65
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 5801987517d66147a9c8110c945b8fdff84bc88b
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65396219"
---
# <a name="position-counting-in-bytes"></a>以字节为单位计算位置

## <a name="overview"></a>概述

可以使用**数**的属性**架构**节点： 

* 指定如何值为输入**位置长度**并**位置偏移量**解释位置记录内的各字段的属性
* 指定如何值为输入**标记偏移量**解释为位置记录本身的属性

默认情况下，这些值被解释为字符数。 但当**数**属性设置为**True**，这些值被解释为字节数。  
  
 设置**数**属性设置为**True**可能需要处理多字节字符时设置 （MBCS 或 DBCS） 数据，或当平面文件消息源自 SAP、 大型机或其他系统，可能数以字节为单位的位置。  
  
 使用字符进行编码的字节数是变量，并可能会导致一些问题有关确定字段边界时，计算字段长度以字节为单位可能很复杂。 当平面文件拆装器对平面文件中这种情况下时，它会尝试以使相应的解析决策基于自身使用的字符编码的了解。  
  
 此类型的解析决策示例涉及 MBCS 字符编码中的前导字节。 前导字节是已知字节值，用于开始的多字节字符编码和其应永远不会出现在其自己。 指定使用字节而不是字符字段的长度时, 的情况下可能会出现在其中找到的字段中的最后一个字节是前导字节，不能构成完整字符本身。 在这种情况下，平面文件拆装器将字符视为就在前导字节之前为前一个字段中的最后一个字符并开始分析下一个字段开头的前导字节。  

这些属性的更多详细信息[!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]。 
  
## <a name="see-also"></a>请参阅  
 [位置记录注意事项](../core/positional-record-considerations.md)   
