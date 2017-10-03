---
title: "使用自定义文本的字符进行编码时 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: a69dffe1-3fb2-4902-a9a2-093f3ea7b11f
caps.latest.revision: "4"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 002bccd7c0ed00192f42f9ef478097409d698ddb
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="encoding-characters-using-free-text"></a>使用自定义文本的字符进行编码
从开始[!INCLUDE[bts2013r2](../../includes/bts2013r2-md.md)]，可以在字段或段中使用"FreeText"。 不分析"FreeText"字段/段中的数据。  
  
## <a name="what-you-need-to-know"></a>你需要知道  
  
||行为|示例|  
|-|--------------|-------------|  
|~: 重复分隔符|在字段中，重复 （~） 将被视为重复分隔符。 非空闲段中重复 （~） 将被视为重复分隔符。 在可用的段中，重复 （~） 视为普通，不新重复的一部分。|在下面的示例中，帧是免费的段。 它可以具有任何以任意文本形式的字符包括 ~。 任何其他重复 （~） 不被视为重复分隔符，而是被视为可用的文本内容。 验证成功，即使可用段的子级可非重复和包含重复 （~）。 帧示例：<br /><br /> **帧 &#124;Foo & ^ &#124;Foo & ^ &#124;Foo & ^ &#124;Foo （& a) ^ ~ Foo & ^ &#124;Foo & ^ &#124;Foo & ^ &#124;Foo & ^**<br /><br /> 在以下示例中，EVN4 定义为普通因为它包含 *&^* 。 当"&#124;"在遇到分隔符，则它将被视为当前的自定义文本的末尾。 EVN 示例：<br /><br /> **EVN （#124; &#124; &#124;) #124;Foo & ^ Foo （& a) ^ Foo （& a) ^ Foo & ^ Foo （& a) ^ &#124; &#124;**<br /><br /> 在以下示例中，EVN5 的第一个子级定义为普通因为它包含 *&* 。 当"^"在遇到分隔符，则它将被视为当前的自定义文本的末尾。 EVN5 示例：<br /><br /> **EVN （#124; &#124; &#124;) #124;&#124;Foo 和 Foo & Foo & Foo & Foo & ^5.2 &#124;**<br /><br /> 在下面的示例中，5.2.1 章和 5.2.2 不能有任何分隔符为免费的文本，即使它指 FreeText 架构中。 5.2.1 章和 5.2.2 示例：<br /><br /> **EVN （#124; &#124; &#124;) #124;&#124;Foo1 ^5.2.1 章 5.2.2 &#124;**<br /><br /> 在下面的示例中，假定 EVN4 可以重复，并且是免费的文本的类型。 *Foo1 & ^*将被视为第一个重复和*Foo2 & ^*将被视为第二个重复。 如果 EVN4 不是可重复 (MaxOccurs = 1)，则验证将失败，如果它包含 ~，即使它是免费的文本类型 （如在非自定义文本字段的情况下）。 EVN4 示例：<br /><br /> **EVN （#124; &#124; &#124;) #124;Foo1 （& a) ^ ~ Foo2 & ^ &#124; &#124;**|  
|&#124;: 字段分隔符|可用的段的段标记后面缺少的字段分隔符，如果验证成功。|在以下示例中，帧是免费的文本类型。 可以启动免费的文本内容，帧段标记中，有无后立即"&#124;"字段分隔符。 这两个示例成功：<br /><br /> **FREabc** <br /> **帧 &#124; abc**<br /><br /> 在以下示例中，验证成功：<br /><br /> 输入的消息到 DASM:**帧 &#124; abcd**<br />输出从 DASM:  **\<SegmentData > &#124; abcd\</SegmentData >**<br />ASM 的输出：**帧 &#124; abcd**<br /><br /> 输入的消息到 DASM: **FREabcd**<br />输出从 DASM:  **\<SegmentData > abcd\</SegmentData >**<br />ASM 的输出： **FREabcd**|  
|父-子可选|父-子可选的验证规则仍适用。|假定父级是可选的其某个子级是必需的然后：<br /><br /> -如果没有任何其他的子级和必需的子不会填充，消息验证成功。<br />-如果填充了至少一个子级，则应还填充的必需子。 否则，消息验证将失败。<br /><br /> 在下面的示例中，为可选字段 1。 其*1.a*子是可选的是免费的文本类型。 其*1.b*子是必需的：<br /><br /> **xyz &#124;1.a^1.b &#124; 2**<br /><br /> 在下面的示例消息中， *dfssdf**&**sdf*视为单个元素-1.a。 分析器检查 1.b 是否存在。 当*&#124;*是达到，假定未填充 1.b 和消息验证失败：<br /><br /> **xyz &#124; dfssdf & sdf &#124; 2**|  
|MSH、 FSH 和 BSH 段|对于所有字段，自定义文本将被忽略。 这些段对应于标头部分。 像通常一样，即使它们被定义为普通，会发生验证。||  
|\\： 转义字符|如果有偶数个元素中的"\"，验证将成功 （即使它们不是连续的）。 如果有奇数数目，验证将失败。 对于非自定义文本字段继续相同的行为。 与自定义文本字段，没有任何验证的数量;它视为可用的文本内容。||  
  
 [消息分隔符](../../adapters-and-accelerators/accelerator-hl7/message-delimiters.md)提供有关这些示例中的分隔符详细信息。  
  
## <a name="using-free-text"></a>使用自定义文本  
  
1.  在 Visual Studio 中的项目，打开架构。  
  
2.  右键单击记录，选择**插入架构节点**，选择**子字段元素**。  
  
3.  在属性中，选择**数据类型**，然后选择**普通 (SimpleType)**。  
  
## <a name="see-also"></a>另请参阅  
 [处理 HL7 消息](../../adapters-and-accelerators/accelerator-hl7/processing-hl7-messages.md)