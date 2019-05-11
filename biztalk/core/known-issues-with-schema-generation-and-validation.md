---
title: 使用架构生成和验证的已知问题 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: df1eaa6c-0d3e-4aec-9de0-8b9817b7bb97
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f76e8043519672e5fe5b39bc9ce75b71dc0e95d3
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65380705"
---
# <a name="known-issues-with-schema-generation-and-validation"></a>架构生成和验证的已知的问题
本主题提供有关使用架构生成和验证的已知问题的信息。  
  
## <a name="an-instance-message-generated-for-a-positional-record-with-tags-could-be-incorrect"></a>使用标记的位置记录生成的实例消息可能不正确  
 对于位置记录，标记可以在字段中，也可以跨两个字段。 在任一情况下，生成的实例将无效，并将失败分析引擎中的分析阶段。  
  
 如果标记不是任何子级 （子记录或子字段） 的一部分，将不会出现此问题。  
  
 若要解决此问题，包括为架构中的默认标记的实际值。 在 BizTalk 编辑器的平面文件扩展功能，可以设置**固定值**或**默认值**的相应位置字段具有标记的值的属性。  
  
## <a name="an-instance-message-generated-for-a-field-with-some-restrictions-may-not-pass-validation"></a>有一些限制条件的字段生成的实例消息可能无法通过验证  
 从包含一个或多个架构生成实例消息时**Field 元素**并**字段属性**具有使用限制机制，如派生的数据类型的节点当**模式**使用属性时，生成的此类字段的示例数据可能不符合要求的限制，从而防止使用相同的架构从该实例消息的验证成功它生成。  
  
## <a name="an-instance-message-generated-for-a-schema-that-contains-an-infinite-loop-may-not-be-valid"></a>包含一个无限循环的架构生成实例消息可能不是有效的。  
 包含与节点的循环引用时，您的架构可以包含无限循环**最小出现次数**属性值大于或等于一，实质上阻止终止条件。 实例消息的生成将人为终止，以便生成操作可以完成，但生成的实例消息因此将不符合从其生成的架构。 此类架构通常是可疑的。  
  
## <a name="validation-of-xml-instance-fails-for-document-schema-which-has-the-target-namespacehttpwwww3orgxml1998namespace"></a>验证 XML 实例的失败的文档架构目标命名空间 ="<http://www.w3.org/XML/1998/namespace>"  
 超链接"<http://www.w3.org/XML/1998/namespace>"是保留的命名空间，其前缀应为"XML"。 您可以手动编辑为"XML"前缀。

## <a name="see-also"></a>另请参阅
这些属性的更多详细信息[!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]。
