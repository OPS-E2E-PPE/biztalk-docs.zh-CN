---
title: 如何编辑 XPath 选择器以处理多个记录 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- Business Rules Framework, editing multiple records
- Business Rules Framework, code samples
- Business Rules Framework, programming
ms.assetid: ef7e1f8d-2e29-4cef-b558-0090648bffc0
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 826158471dbff3116df55a00f653740ab183e2d7
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65338053"
---
# <a name="how-to-edit-xpath-selector-to-process-multiple-records"></a>如何编辑 XPath 选择器以处理多个记录
单独的子 Typedxmldocument 时，会创建将 TypedXmlDocument 添加到引擎中;请参阅[Assert](../core/assert.md)。 在引擎确定哪些子 Typedxmldocument 创建基于在规则中定义的 XPath 选择器。 生成在编辑器中的规则时，XPath 选择器值默认为事实浏览器中的 XML 架构选项卡中选择的节点上方的节点。 XPath 字段值默认为所选节点本身，相对于其父节点。  
  
 在某些情况下您可能想要自定义默认的生成规则时创建编辑器的 XPath。 假定下面的示例 XML 文档。  
  
```  
<Order>  
   <Orderline>  
      <Hat style="Baseball">                        
         <Cost>10</Cost>  
      </Hat>  
      <Shirt color="Black">  
         <Cost>20</Cost>  
      </Shirt>  
      <Total></Total>  
   </Orderline>  
   <Orderline>  
      <Hat style="Bowler">                        
         <Cost>20</Cost>  
      </Hat>  
      <Shirt color="Red">  
         <Cost>20</Cost>  
      </Shirt>  
      <Total></Total>  
   </Orderline>  
</Order>  
```  
  
 假设你想要生成的规则，计算每个 Orderline 总计值。 你的规则如以下所示。  
  
 IF 1==1  
  
 然后<strong>/o/Orderline/</strong>总 = (<strong>顺序/Orderline/Hat/</strong>成本 + <strong>顺序/Orderline/Shirt/</strong>成本)  
  
 Xpath 的粗体部分表示选择器部分，其余部分表示字段 XPath。 这些是编辑器生成的默认值。 运行此策略，但是，将导致创建 6 个对象-2 个 Orderline 对象、 2 个 Hat 对象和 2 个 Shirt 对象。 将为 Hat 和 Shirt 对象的每个组合计算 Orderline 总计和总计将始终设置为相同的值，该值源自上次执行规则。 该规则将触发 8 次。 这是不是为想在此方案中。  
  
 一种解决方案是编辑 XPath 值是按如下所示。  
  
 IF 1==1  
  
 然后<strong>/o/Orderline/</strong>总 = (<strong>/o/Orderline/</strong>Hat/成本 + <strong>/o/Orderline/</strong>Shirt/成本)  
  
 所有三个字段的选择器 XPath 值已设置为同一 /Order/Orderline 值并相应地编辑的字段 XPath 值。 这是通过在 XML 架构选项卡中选择节点时更改属性窗口中的 XPath 选择器和 XPath 字段值。这应在将字段拖动到规则参数之前完成。  
  
 执行此更改的策略将导致每个 Orderline 基于该 Orderline 内 Shirt 和 Hat 节点的 Cost 值正确计算出的总计值。