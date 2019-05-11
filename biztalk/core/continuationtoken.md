---
title: ContinuationToken |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 2d4911fc-c6fb-4628-9177-bd723d4d8ebc
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a5509fe9ec6b4d1966af84e56ca1b1571ebc3f55
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65390267"
---
# <a name="continuationtoken"></a>ContinuationToken
使用继续标记来关联 BAM 基础结构中各种不同的信息。 请考虑一个业务流程来构造以下类型的消息：  
  
- 根据采购订单号标识的采购订单  
  
- 由销售订单号标识的销售订单  
  
- 由发货订单号标识的发货订单  
  
  在此过程中，有三个重要的标识符： 采购订单 ID、 销售订单 ID 和发货订单 id。 每个这些标识符向原始订单生存期内发出信号的重要事件，但无法直接关联。 若要跟踪与采购订单相关的事件，必须标识各消息间共有的信息来帮助准确地关联事件的 BAM 跟踪基础结构。  
  
## <a name="format"></a>格式  
 继续标记包含一个表达式元素和一个或多个操作：  
  
```  
<ic:ContinuationToken>  
  <ic:Expression>  
    <!-- Operations -->  
  </ic:Expression>  
</ic:ContinuationToken>  
```  
  
## <a name="remarks"></a>备注  
 ContinuationToken 表达式中不允许以下常见运算：  
  
- And  
  
- 等于  
  
  [WF/WCF 中的运算部分标头应具有相似的图表和其他图表根据]  
  
## <a name="example"></a>示例  
 在此示例中，WF 流程的继续标记检索从工作流使用`GetWorkflowProperty`。 此处，开发人员决定通过使用自定义代码，可能因为确定继续标记的过程只是涉及到两个或三个表达式，并可能依赖外部数据的工作流中的连续符提供支持。  
  
```  
<ic:ContinuationToken>  
  <ic:Expression>  
    <wf:Operation Name="GetWorkflowProperty">  
      <wf:Argument>ContinuationToken</wf:Argument>  
    </wf:Operation>  
  </ic:Expression>  
</ic:ContinuationToken>  
```  
  
 您可以选择提供新 WF 或 WCF 应用程序中类似的功能，或者，如果令牌十分容易使用表达式运算创建的则可以避免编写额外代码。  
  
 下面的示例通过使用建立为 WCF 流程的继续标记**XPath**操作从当前消息中检索信用卡卡号和**常量**和**串联**操作前面加上"CID_"字符串检索到的号码：  
  
```  
<ic:ContinuationToken>  
  <ic:Expression>  
    <ic:Operation Name="Constant">  
      <ic:Argument>CID_</ic:Argument>  
    </ic:Operation>  
    <wcf:Operation Name="XPath">  
      <wcf:Argument>//Purchase/Payment/CreditCardNumber</wcf:Argument>  
    </wcf:Operation>  
    <ic:Operation Name="Concatenate" />  
  </ic:Expression>  
</ic:ContinuationToken>  
```  
  
## <a name="see-also"></a>请参阅  
 [侦听器 OnEvent 元素](../core/interceptor-onevent-element.md)