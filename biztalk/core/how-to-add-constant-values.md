---
title: 如何添加常量值 |Microsoft Docs
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
ms.openlocfilehash: 6510c278be4f64814dd690d275e42c6739587e4e
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65387239"
---
# <a name="how-to-add-constant-values"></a>如何添加常量值
在测试映射时，有时想要在测试过程中设置的使用的常数值。  
  
## <a name="set-constant-values-for-nodes-in-the-source-or-destination-schema-trees"></a>设置常量节点中的源或目标架构树  
  
1. 在源或目标架构树中选择的记录或字段。  
  
2. 在属性窗口中**常规**类别中，使用**值**属性输入所选的记录或字段的值。  
  
   > [!NOTE]
   >  只能将一个值关联的记录与及其**内容**属性设置为**纯文本**或**混合**。  
  
   在源架构中，如果将节点**值**属性设置为**\<空\>**，源架构生成的实例消息包含为相应的空值节点。  
  
   有时，不使用目标架构中的所有字段，即一些目标架构中的字段不含有任何传入链接。 在这种情况下，测试映射操作将引发错误，则**验证测试映射输入**或**验证测试映射输出**属性设置为**True**。 若要避免这种情况下的测试映射错误，请设置**值**为常量值节点的属性或**\<空\>**。 使用**\<空\>** 如果您不想要设置任意数据的未使用的目标架构字段。  
  
## <a name="see-also"></a>请参阅  
[验证和测试映射](../core/how-to-configure-map-validation-and-test-parameters.md)