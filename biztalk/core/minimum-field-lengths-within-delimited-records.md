---
title: 分隔记录中的最小字段长度 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 24272d0d-34c8-487a-9334-683c65c159b8
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f7e30f3bcb6b26a13dfd964eb59796dcdee56237
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65324681"
---
# <a name="minimum-field-lengths-within-delimited-records"></a>分隔记录中的最小字段长度
根据定义，位置记录中的字段都定义为具有特定的确切长度。 分隔记录中的字段还可以定义为具有最小长度。 此特性定义的 **[填充字符的最小长度**的属性**Field 元素**并**字段属性**节点。  

 提供一个非零值时**填充字符的最小长度**属性，平面文件组装器将确定与字段关联的数据字符数是否小于设置**填充字符的最小长度**属性，将使用相关的填充字符以组成一个不同之处。  

 之前或之后的数据字符基于的设置将添加填充字符**理由**针对字段的属性。 当**理由**属性设置为**左侧**，为满足最小长度所需的所有填充字符将都添加数据字符之后。 当**理由**属性设置为**右**，为满足最小长度所需的所有填充字符将都添加到数据字符之前。  

 提供一个非零值时**填充字符的最小长度**属性，平面文件拆装器将检查的开头或结尾 (根据设置**理由**属性) 的字段值存在相关的填充字符，并且如果有，填充字符将被放弃并不会出现在所构造的等效 XML 消息。  

## <a name="see-also"></a>请参阅  
- [字段注意事项](../core/field-considerations.md)   
- **对齐 （平面文件架构的节点属性）** 和**填充字符 （平面文件架构的节点属性） 的最小长度** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]
