---
title: 消息编码 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- messages, encodings
- messages, code samples
- encoding [messages]
- code samples
ms.assetid: 360638c0-4094-428f-a7c7-306a5f95a6bf
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 013df4d29604e6dd7ce6d2e486612be303cc5898
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "37007086"
---
# <a name="message-encodings"></a>消息编码
不是只需按顺序 for HL7 有用定义消息的语义。 一旦确定消息内容，该标准包括说明如何表示实际接口中的内容。 也就是说，必须指定"消息编码"。 HL7 版本 2 支持两种形式的消息编码、 自定义基于分隔符的编码和 XML 编码。  
  
 HL7 选择原始基于分隔符的编码以减少的尽可能多的消息的大小。 例如，如果比较结果中的分隔符分隔到一组固定的位置中定位的每个元素的结构元素的数据结构，基于分隔符的结构是） 消息不包含一些元素和 b） 某些更经济实惠元素不填充所有允许的空间。 在基于分隔符的结构中的唯一开销是分隔符本身。  
  
 原始 HL7 编码定义五个分隔符，用来在 MSH 段中声明的每条消息。 这些警报表示：  
  
- 段  
  
- 字段  
  
- 组件  
  
- 子组件  
  
- （的字段、 组件或子组件） 重复  
  
  请注意，因为分隔符是编码的一个基本方面，您必须先定义。 结果之一就不是可以是任何子子分隔符。 有时，此限制会产生令人遗憾的影响上新的数据类型的设计。  
  
  在 2003 年 6 月，HL7 发布 HL7 版本 2、 编码的 XML 语法、 发行版 1。 此标准定义 HL7 版本 2.3.1 和 2.4 消息的备用编码规则，并提供一种机制用于确定备用的编码规则的后续 HL7 2.X 版本。 从本质上讲，这个新的标准版本 2.3.1 和于 V2.4 的抽象消息、 段、 字段和数据类型的定义 XML 元素标记，并创建用于定义所需的标准为版本 2 的后续版本创建的任何新结构标记的规则。 定义此标准的过程就会导致一系列版本 2.4 和 2.5 中的改进。 发生这种情况是因为创建 XML 标记会导致需要解决基础标准中的某些长期以来二义性。 这样，创建） 定义明确的消息结构代码，以指示触发事件，b） 重复组的抽象消息段已正式标识和指定，与关联的抽象消息中的变体和 c) 本地定义的数据类型，CM 已替换为更具体的类型。  
  
  例如，下面是使用传统的竖线分隔格式的简单的确认消息：  
  
```  
MSH|^~\&|LAB|767543|ADT|767543|199003141304-0500||ACK^^ACK|XX3657|P|2.4  
MSA|AR|ZZ9380  
ERR|PID^1^16^103&Table value not found&HL70357  
```  
  
 与此相反，下面是相同的消息表示为 XML 文档：  
  
```  
<ACK  
xmlns="urn:hl7-org:v2xml"  
xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance"  
xsi:schemaLocation="urn:hl7-org:v2xml ACK.xsd">  
   <MSH>  
      <MSH.1>|</MSH.1>  
      <MSH.2>^~\&</MSH.2>  
      <MSH.3>  
         <HD.1>LAB</HD.1>  
      </MSH.3>  
      <MSH.4>  
         <HD.1>767543</HD.1>  
      </MSH.4>  
      <MSH.5>  
         <HD.1>ADT</HD.1>  
      </MSH.5>  
      <MSH.6>  
         <HD.1>767543</HD.1>  
      </MSH.6>  
      <MSH.7>  
         <TS.1>199003141304-0500</TS.1>  
      </MSH.7>  
      <MSH.9>  
         <MSG.1>ACK</MSG.1>  
         <MSG.3>ACK</MSG.3>  
      </MSH.9>  
      <MSH.10>XX3657</MSH.10>  
      <MSH.11>  
         <PT.1>P</PT.1>  
      </MSH.11>  
      <MSH.12>  
         <VID.1>2.4</VID.1>  
      </MSH.12>  
   </MSH>  
   <MSA>  
      <MSA.1>AR</MSA.1>  
      <MSA.2>ZZ9380</MSA.2>  
   </MSA>  
   <ERR>  
      <ERR.1>  
         <ELD.1>PID</ELD.1>  
         <ELD.2>1</ELD.2>  
         <ELD.3>16</ELD.3>  
         <ELD.4>  
            <CE.1>103</CE.1>  
            <CE.2>Table value not found</CE.2>  
            <CE.3>HL70357</CE.3>  
         </ELD.4>  
      </ERR.1>  
   </ERR>  
</ACK>  
```  
  
 Microsoft BizTalk Accelerator for HL7 的以下函数 ([!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]) 支持这些要求：  
  
-   分隔的管道和 XML 编码的支持。  
  
-   支持 XML 和管道之间的转换的分隔的编码。  
  
## <a name="see-also"></a>请参阅  
 [处理 HL7 消息](../../adapters-and-accelerators/accelerator-hl7/processing-hl7-messages.md)   
 [消息处理](../../adapters-and-accelerators/accelerator-hl7/message-processing.md)   
 [使用 HL7 2.X 架构](../../adapters-and-accelerators/accelerator-hl7/using-hl7-2-x-schemas.md)