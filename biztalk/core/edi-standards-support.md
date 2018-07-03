---
title: EDI 标准支持 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: c2ef14c5-5f12-40e2-93d7-59b5c5a0d641
caps.latest.revision: 27
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ebb4d85b4972991054914baea2014b6d268a24eb
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "37007126"
---
# <a name="edi-standards-support"></a>EDI 标准支持
BizTalk Server 提供的四个编码标准的设计和运行时支持。 下表列出了使用的详细信息的链接的编码标准。  
  
|编码标准|行业细分市场|References|  
|-----------------------|----------------------|----------------|  
|UN/EDIFACT|常规行业|[标准网站](http://go.microsoft.com/fwlink/?LinkId=77532)（有效负载参考）<br /><br /> [编码规则](http://go.microsoft.com/fwlink/?LinkId=77534)根据 ISO 9735 4.1|  
|X12|常规行业|[标准网站](http://go.microsoft.com/fwlink/?LinkID=28673)<br /><br /> [规范开发](http://go.microsoft.com/fwlink/?LinkId=77535)|  
|EANCOM|零售|[标准网站](http://go.microsoft.com/fwlink/?LinkId=92861)|  
|HIPAA X12N|健康保健|[HIPAA 实施指南](http://go.microsoft.com/fwlink/?LinkId=77541)<br /><br /> [HIPAA 规范](http://go.microsoft.com/fwlink/?LinkId=77542)|  
  
> [!NOTE]
>  EANCOM 架构是 EDIFACT 的子集。 EANCOM 遵循相同的编码规则 EDIFACT 后面。  
  
> [!NOTE]
>  KEDIFACT 是一个单独的标准，但严格基于 EDIFACT 标准。  
  
## <a name="x12-and-edifact"></a>X12 和 EDIFACT  
 这两个标准，ANSI X12 和 UN/EDIFACT，构成所有 EDI 交换的消息的全球超过 90%:  
  
- UN/EDIFACT EDI 国际消息标准 (针对管理、 商务和贸易的 EDI) 开发的并继续由联合国经济委员会欧洲 (UN/ECE) 来维护。 该标准也简称为 EDIFACT。  
  
- X12 EDI U.S. 消息标准由美国国家标准协会 (ANSI) 设立的公认标准委员会 (ASC) X12 委员会制定并继续维护。  
  
  EDIFACT 很大程度上基于美国的X12 标准。 这两个 EDI 标准在结构方面十分相似。 不同点包括：  
  
- 结构元素在这两个标准中的名称不同。 例如，交换控制标头在 X12 中为 ISA 数据元素，而在 EDIFACT 中为 UNB 数据元素。  
  
- 很多事务集在这两个标准之间存在映射关系，但事务集在这两个标准中具有不同的名称。 例如，采购订单在 X12 中为 850 事务集，而在 EDIFACT 中为 ORDERS 事务集。  
  
- EDIFACT 具有用于设置结构元素（如分隔符和十进制符号）的可选标头段 UNA，可替代管道中定义的默认值。  
  
- X12 具有两个确认（名为 TA1 的技术确认和名为 997 的功能确认），而 EDIFACT 具有一个名为 CONTRL 的全面确认。  
  
- X12 建议使用 ASCII 编码，而 EDIFACT 建议使用 UTF8 编码。  
  
  BizTalk Server 支持 KEDIFACT (韩国 EDIFACT) 标准。 KEDIFACT 遵循 UN/EDIFACT 的消息实现指南，因此在很大程度上是以 EDIFACT 为基础。 但是，KEDIFACT 和 X12/EDIFACT 之间存在差异。 KEDIFACT 使用若干特定于 KEDIFACT 的 EDI 架构，并使用 KECA 代码页。  
  
## <a name="hipaa"></a>HIPAA  
 BizTalk Server 支持 X12 处理，而由于 HIPAA 处理由 x12 处理派生而来，BizTalk Server 支持 HIPAA 处理。 请参阅本文档中支持对 X12 引用，其中也适用于 HIPAA 处理。  
  
 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 提供了特定于 HIPAA 的更多支持：  
  
- 一组 4010A1 版本的 HIPAA 文档架构。 在 BizTalk Server 中的 EDI 和 HIPAA 文档架构的详细信息，请参阅[EDI 文档架构](../core/edi-document-schemas.md)。  
  
- 一组 5010 版本的 HIPAA 文档架构。 有关详细信息，请参阅[HIPAA 文档架构版本 5010](../core/hipaa-document-schema-version-5010.md)。  
  
- HIPAA 子文档拆分。 有关详细信息，请参阅[拆分 HIPAA 子文档](../core/splitting-hipaa-subdocuments.md)。  
  
- 支持 WEDI SNIP 测试的前两个级别： X12 语法完整性和要求[HIPAA 实施指南](http://go.microsoft.com/fwlink/?LinkId=77541)。  
  
  BizTalk Server 提供 HIPAA 支持作为本机 BizTalk Server EDI 功能的一部分。 有关详细信息，请参阅[BizTalk Server 中的 EDI 支持](../core/edi-support-in-biztalk-server2.md)。  
  
## <a name="eancom"></a>EANCOM  
 BizTalk Server 支持 EDIFACT 处理，由于 EANCOM 处理由 EDIFACT 处理派生而来，BizTalk Server 支持 EANCOM 处理。 本文档中所有提及支持 EDIFACT 的部分也支持 EANCOM 处理。  
  
 BizTalk Server 提供了其他特定于 EANCOM 的支持：  
  
-   一组 EAN94、EAN97 和 EAN02 版本的 EANCOM 文档架构。 在 BizTalk Server 中的 EDI 和 EANCOM 文档架构的详细信息，请参阅[EDI 文档架构](../core/edi-document-schemas.md)。  
  
## <a name="see-also"></a>请参阅  
 [EDI 消息结构](../core/edi-message-structure.md)   
 [EDI 文档架构](../core/edi-document-schemas.md)