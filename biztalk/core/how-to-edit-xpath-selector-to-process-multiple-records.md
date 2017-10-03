---
title: "如何编辑 XPath 选择器来处理多个记录 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- Business Rules Framework, editing multiple records
- Business Rules Framework, code samples
- Business Rules Framework, programming
ms.assetid: ef7e1f8d-2e29-4cef-b558-0090648bffc0
caps.latest.revision: "8"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 34c9b45e3fce9f4ad5730d7f03d2a568b3701742
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-edit-xpath-selector-to-process-multiple-records"></a>如何编辑 XPath 选择器以处理多个记录
单独的子 TypedXmlDocuments 时创建 TypedXmlDocument 断言引擎;请参阅[断言](../core/assert.md)。 引擎将根据规则中定义的 XPath 选择器决定创建哪些子 TypedXmlDocument。 在编辑器中生成规则时，XPath 选择器的值默认为事实浏览器的“XML 架构”选项卡中所选节点之上的那个节点。 相对于所选节点的父节点，XPath 字段的值默认为所选节点本身。  
  
 在某些情况下，您可能希望自定义编辑器在生成规则时创建的默认 XPath。 假设存在以下示例 XML 文档：  
  
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
  
 假设您希望生成计算每个 Orderline 的 Total 值的规则。 该规则应与下面所列相似：  
  
 IF 1==1  
  
 然后**/order/Orderline/**总 = (**/顺序/Orderline/Hat/**成本 + **/顺序/Orderline/Shirt/**成本)  
  
 XPath 的粗体部分表示选择器部分，其余部分表示字段 XPath。 这些都是编辑器生成的默认值。 但是，运行此策略将导致创建 6 个对象：2 个 Orderline 对象、2 个 Hat 对象和 2 个 Shirt 对象。 Orderline 总计值将针对 Hat 对象和 Shirt 对象的每个组合来进行计算，并始终设置为同一值，该值源自上次执行规则所得的结果。 该规则将触发 8 次。 然而，这并不是本方案的预期结果。  
  
 一种解决方案是按如下所示编辑 XPath 值：  
  
 IF 1==1  
  
 然后**/order/Orderline/**总 = (**/order/Orderline/**Hat/成本 + **/order/Orderline/**Shirt/成本)  
  
 所有三个字段的选择器 XPath 值均已设置为同一 /Order/Orderline 值，并且字段 XPath 值也已进行相应的编辑。 这是在“XML 架构”选项卡中选择节点后，通过更改“属性”窗口中的 XPath 选择器和 XPath 字段值来完成的。该操作应在将字段拖到规则参数中之前完成。  
  
 如果执行包含此更改的策略，则会根据每个 Orderline 内 Shirt 节点和 Hat 节点的 Cost 值正确计算出该 Orderline 的 Total 值。