---
title: EDI 支持 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 1d4f50a9-fc55-400c-a63c-40b697425fea
caps.latest.revision: 25
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 79b1c7ba658d3f7921fb0a96b25c06d18e45e81d
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65350211"
---
# <a name="edi-support-in-biztalk-server"></a>BizTalk Server 中的 EDI 支持
EDI 内置于 BizTalk Server，安装和配置 BizTalk Server 时是一个可选组件。 
  
## <a name="feature-set-comparison-chart"></a>功能集比较表  
 下表显示了 BizTalk Server 附带的 EDI 支持。
  
|功能|注释|  
|---|---|
|事务集级别的 ISA 段修改| 创建特定于事务集的协议|  
|ISA11:  美国或其他标准类型| |  
|ISA12:  交换控制版本| |  
|ISA13:  交换控制编号 （递增编号）| |  
|ISA15:  测试或生产| |  
|文档/事务级别的 GS 段修改| |  
|GS 发送方/接收方 Id 可以是不同于 ISA| |  
|入站的文档 Id 不同于 ISA & GS 出站 Id| |  
|GS01:  若要更改的文档类型的功能| |  
|GS04:  日期 （格式更改功能）|包含用于选择 CCYYMMDD 和 YYMMDD 格式的 UI|  
|GS05:  时间 （格式更改功能）|包含用于选择 HHMM、 HHMMSS 和 HHMMSSdd 格式的 UI|  
|GS06:  更改控制编号| |  
|GS07:  机构代码| |  
|GS08:  能够插入标准版本| |  
|用于重写在运行时的 EDI 信封功能| |  
|自定义 EDI 架构| |  
|组织/参与方设置|创建单独的参与方和协议。 此外创建协议模板为基础。|  
|通过文档定义路由 EDI 文档| |  
|自动发送 997 向贸易合作伙伴|特定于业务配置文件配置|  
|可靠消息传送通过 997 实现的出站 EDI| |  
|EDIFACT 支持|支持为 D93 到 D05 ISO 9735 4.1 版|  
|X12 支持|2040 到 5030|  
|HIPAA 支持| Microsoft BizTalk Accelerator for HIPAA (BTAHIPAA) 作为本机 EDI 功能的一部分|  
|删除/代码列表枚举器的功能|使用 Visual Studio/BizTalk 编辑器|  
|AS2    Send/Receive| AS2 是多文件附件支持、 文件名保存支持和互操作性的 Drummond 认证。|  
|AS2 文件名称保存| |  
|AS2 可靠消息传送| |  
|出站批处理 （累积在单个事务中的多个事务类型）|为每个业务配置文件支持多个批处理配置|  
|入站批处理 – 交换 XML （保留传入批交换） 或根据配置选项的事务集 XML|此外支持入站解除，交换拆分为单独的事务集 Xml|  
|交换及事务集生成和验证在 Visual Studio 中的设计时| |  
|TA1 （技术确认） 生成和协调| |  
|可选的 EDI 和 XSD 验证标志| |  
|GS 级别的文档格式/定义| |  
  
## <a name="see-also"></a>请参阅  
 [EDI 标准支持](../core/edi-standards-support.md)   
 [EDI 文档架构支持](../core/edi-document-schema-support.md)   
 [EDI 字符集支持](../core/edi-character-set-support.md)