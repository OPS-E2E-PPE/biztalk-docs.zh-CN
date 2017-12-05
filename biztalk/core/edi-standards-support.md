---
title: "EDI 标准支持 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: c2ef14c5-5f12-40e2-93d7-59b5c5a0d641
caps.latest.revision: "27"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ebb7ab3abb9a4bc547d920614e1a1839a85c593b
ms.sourcegitcommit: 3fc338e52d5dbca2c3ea1685a2faafc7582fe23a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/01/2017
---
# <a name="edi-standards-support"></a>EDI 标准支持
BizTalk Server 提供四个编码标准的设计和运行时支持。 下表列出了编码标准并详细信息的链接。  
  
|编码标准|行业细分市场|References|  
|-----------------------|----------------------|----------------|  
|取消/EDIFACT|常规行业|[标准网站](http://go.microsoft.com/fwlink/?LinkId=77532)（负载参考）<br /><br /> [编码规则](http://go.microsoft.com/fwlink/?LinkId=77534)每 ISO 9735 4.1|  
|X12|常规行业|[标准网站](http://go.microsoft.com/fwlink/?LinkID=28673)<br /><br /> [规范开发](http://go.microsoft.com/fwlink/?LinkId=77535)|  
|EANCOM|零售|[标准网站](http://go.microsoft.com/fwlink/?LinkId=92861)|  
|HIPAA X12N|健康保健|[HIPAA 实现指南](http://go.microsoft.com/fwlink/?LinkId=77541)<br /><br /> [HIPAA 规范](http://go.microsoft.com/fwlink/?LinkId=77542)|  
  
> [!NOTE]
>  EANCOM 架构是 EDIFACT 的子集。 EANCOM 遵循 EDIFACT 遵循的相同的编码规则。  
  
> [!NOTE]
>  KEDIFACT 是单独的标准，但严格基于 EDIFACT 标准。  
  
## <a name="x12-and-edifact"></a>X12 和 EDIFACT  
 两种标准，ANSI X12 和取消/EDIFACT，构成超过 90%的所有全局交换的 EDI 消息：  
  
-   取消/EDIFACT EDI 国际消息标准 (管理、 商业和贸易 EDI) 开发的将继续由美国国家/地区经济佣金欧洲 (取消/ECE) 来维护。 该标准也简称为 EDIFACT。  
  
-   X12 EDI U.S. 消息标准由美国国家标准协会 (ANSI) 设立的公认标准委员会 (ASC) X12 委员会制定并继续维护。  
  
 EDIFACT 很大程度上基于美国X12 标准。 这两个 EDI 标准在结构方面十分相似。 不同点包括：  
  
-   结构元素在这两个标准中的名称不同。 例如，交换控制标头在 X12 中为 ISA 数据元素，而在 EDIFACT 中为 UNB 数据元素。  
  
-   很多事务集在这两个标准之间存在映射关系，但事务集在这两个标准中具有不同的名称。 例如，采购订单在 X12 中为 850 事务集，而在 EDIFACT 中为 ORDERS 事务集。  
  
-   EDIFACT 具有用于设置结构元素（如分隔符和十进制符号）的可选标头段 UNA，可替代管道中定义的默认值。  
  
-   X12 具有两个确认（名为 TA1 的技术确认和名为 997 的功能确认），而 EDIFACT 具有一个名为 CONTRL 的全面确认。  
  
-   X12 建议使用 ASCII 编码，而 EDIFACT 建议使用 UTF8 编码。  
  
 BizTalk Server 支持 KEDIFACT (朝鲜 EDIFACT) 标准。 KEDIFACT 遵循 UN/EDIFACT 的消息实现指南，因此在很大程度上是以 EDIFACT 为基础。 但是，KEDIFACT 和 X12/EDIFACT 之间存在差异。 KEDIFACT 使用若干特定于 KEDIFACT 的 EDI 架构，并使用 KECA 代码页。  
  
## <a name="hipaa"></a>HIPAA  
 BizTalk 服务器支持 X12 处理，而 BizTalk Server 由于 HIPAA 处理是处理 X12 的派生，支持 HIPAA 处理。 如果你看到对 X12 支持本文档中的引用，则它也适用于 HIPAA 处理中。  
  
 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 提供了特定于 HIPAA 的更多支持：  
  
-   一组 4010A1 版本的 HIPAA 文档架构。 BizTalk Server 中的 EDI 和 HIPAA 文档架构的详细信息，请参阅[EDI 文档架构](../core/edi-document-schemas.md)。  
  
-   一组 5010 版本的 HIPAA 文档架构。 有关详细信息，请参阅[HIPAA 文档架构版本 5010](../core/hipaa-document-schema-version-5010.md)。  
  
-   HIPAA 子文档拆分。 有关详细信息，请参阅[拆分 HIPAA 子文档](../core/splitting-hipaa-subdocuments.md)。  
  
-   测试 WEDI 代码段的前两个级别的支持： X12 语法完整性和要求[HIPAA 实施指南](http://go.microsoft.com/fwlink/?LinkId=77541)。  
  
 BizTalk Server 提供 HIPAA 支持作为本机 BizTalk Server EDI 功能的一部分。 有关详细信息，请参阅[BizTalk Server 中的 EDI 支持](../core/edi-support-in-biztalk-server2.md)。  
  
## <a name="eancom"></a>EANCOM  
 BizTalk Server 支持 EDIFACT 处理，并 BizTalk Server 由于 EANCOM 处理 EDIFACT 处理的派生，支持 EANCOM 处理。 本文档中所有提及支持 EDIFACT 的部分也支持 EANCOM 处理。  
  
 BizTalk Server 提供额外的 EANCOM 特定支持：  
  
-   一组 EAN94、EAN97 和 EAN02 版本的 EANCOM 文档架构。 BizTalk Server 中的 EDI 和 EANCOM 文档架构的详细信息，请参阅[EDI 文档架构](../core/edi-document-schemas.md)。  
  
## <a name="see-also"></a>另请参阅  
 [EDI 消息结构](../core/edi-message-structure.md)   
 [EDI 文档架构](../core/edi-document-schemas.md)