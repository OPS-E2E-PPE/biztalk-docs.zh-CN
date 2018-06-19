---
title: 如何添加常量值 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: f46bf66e-caf2-4352-930f-c3c43a5717c3
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 9d7ea539b778cc382991e82841dec45db5316f18
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/28/2017
ms.locfileid: "25969715"
---
# <a name="how-to-add-constant-values"></a>如何添加常量值
在测试映射时，有时您会希望设置一些在测试期间使用的常数值。  
  
## <a name="set-constant-values-for-nodes-in-the-source-or-destination-schema-trees"></a>常量中的设置值节点的源或目标架构树  
  
1.  在源架构树或目标架构树中选择记录或字段。  
  
2.  在属性窗口中，在**常规**类别中，使用**值**属性输入一个值为选定的记录或字段。  
  
    > [!NOTE]
    >  只能将一个值关联的记录与其**内容**属性设置为**纯文本**或**混合**。  
  
 源架构，如果你设置中的节点**值**属性**\<空\>**，源架构生成的实例消息包含为相应的空值节点。  
  
 有时，您并未使用目标架构中的全部字段，即，目标架构中的某些字段将不含有任何传入链接。 在这种情况下，该测试映射操作将引发错误，条件是**验证测试映射输入**或**验证测试映射输出**属性设置为**True**。 若要避免这种情况下的测试映射错误，设置**值**为不变值节点的属性或**\<空\>**。 使用**\<空\>** 如果你不想要设置未使用的目标架构字段的任意数据。  
  
## <a name="see-also"></a>另请参阅  
[验证和测试映射](../core/how-to-configure-map-validation-and-test-parameters.md)