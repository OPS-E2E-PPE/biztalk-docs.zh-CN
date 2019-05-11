---
title: 标记分隔记录中的处理 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 568eb804-bea5-46d4-8547-8bc30b87156c
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 3b2c9a792eb498c1bb7bf45ccd4f42110169c17c
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65291660"
---
# <a name="tag-handling-in-delimited-records"></a>分隔记录中的标记处理

## <a name="overview"></a>概述
分隔的记录可以包含的已知字符序列，称为一个标记，它可用于消除从另一个记录的一种类型的歧义。 这样，平面文件拆装器以便正确标识适当**记录**中包含正确解析平面文件记录所需的信息的架构的节点。  

 可以使用**标记标识符**属性可指定分隔记录中的标记。 与不同的位置记录中的标记，分隔记录中的标记必须出现在分隔记录的开头，并记录转换为其等效的 XML 格式时永远不会自动包含在数据。  

## <a name="see-also"></a>请参阅  
- [分隔记录注意事项](../core/delimited-record-considerations.md)   
- **标记标识符 （平面文件架构的节点属性）** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]
