---
title: EDI 支持 |Microsoft 文档
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
ms.openlocfilehash: 04cd9c14b9c3663bdf332155cc9824e1681ca7a6
ms.sourcegitcommit: 32f380810b90b70e5df7be72a6a14988a747868e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/28/2018
ms.locfileid: "29710292"
---
# <a name="edi-support-in-biztalk-server"></a>BizTalk Server 中的 EDI 支持
EDI 是内置于 BizTalk Server 中，安装和配置 BizTalk Server 时，一个可选组件。 
  
## <a name="feature-set-comparison-chart"></a>功能集比较表  
 下表显示了包含与 BizTalk Server EDI 支持。
  
|功能|注释|  
|---|---|
|在事务集 ISA 段修改| 创建 TransactionSet 特定协议|  
|ISA11︰ 美国或其他标准类型| |  
|ISA12︰ 交换控件版本| |  
|ISA13︰ 交换控制编号 （递增数）| |  
|ISA15︰ 测试或生产| |  
|文档/事务级别的 GS 段修改| |  
|GS 发送者/接收者 Id 可以是不同于 ISA| |  
|入站文档 Id 不同于 ISA 和 GS 出站 Id| |  
|GS01︰ 能够更改文档的类型| |  
|GS04︰ 日期 （能够更改格式）|包含用于为 CCYYMMDD 和 YYMMDD 选择格式的 UI|  
|GS05︰ 时间 （能够更改格式）|包含用于选择 HHMM、 HHMMSS，和 HHMMSSdd 格式的 UI|  
|GS06︰ 更改控制编号| |  
|GS07︰ 代理代码| |  
|GS08︰ 能够将放入标准版本| |  
|在运行时覆盖 EDI 信封的能力| |  
|自定义的 EDI 架构| |  
|组织/参与方设置|创建单独的方和协议。 此外创建基于模板的协议。|  
|通过文档定义路由的 EDI 文档| |  
|自动向贸易合作伙伴发送 997|配置特定于业务配置文件|  
|可靠消息传递通过 997 的出站 EDI| |  
|EDIFACT 支持|每个 ISO 9735 v4.1 支持到 D05 D93|  
|X12 支持|2040 到 5030|  
|HIPAA 支持| Microsoft BizTalk 快捷键的 HIPAA (BTAHIPAA) 作为本机 EDI 功能的一部分|  
|枚举器/代码列表删除功能|使用 Visual Studio/BizTalk 编辑器|  
|AS2 发送/接收| AS2 适用于多文件附件支持、 文件名保留支持和互操作性 Drummond 认证。|  
|AS2 文件名称保存| |  
|AS2 可靠消息传递| |  
|（累积单个事务中的多个事务类型） 的出站批处理|对于每个业务配置文件支持多个批处理配置|  
|入站批处理 – 交换 XML （保留将传入的批处理交换） 或基于配置选项的事务设置 XML|此外支持入站-debatching，即，拆分成单个事务设置 Xml 的交换|  
|交换和事务设置生成和验证在 Visual Studio 中的设计时| |  
|TA1 (技术 ACK) 生成和对帐| |  
|可选的 EDI 和 XSD 验证标志| |  
|文档的格式定义，可在 GS 级别| |  
  
## <a name="see-also"></a>另请参阅  
 [EDI 标准支持](../core/edi-standards-support.md)   
 [EDI 文档架构支持](../core/edi-document-schema-support.md)   
 [EDI 字符集支持](../core/edi-character-set-support.md)