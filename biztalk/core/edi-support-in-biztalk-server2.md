---
title: "在 BizTalk Server2 EDI 支持 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 1d4f50a9-fc55-400c-a63c-40b697425fea
caps.latest.revision: "25"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 6162276e5e394bd17b75825535ddaf097a7f589c
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="edi-support-in-biztalk-server"></a>BizTalk Server 中的 EDI 支持
不同的 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 版本通过以下不同的功能和组件来支持 EDI：  
  
|发行版本|提供 EDI 支持的组件/功能|  
|---|---|  
|[!INCLUDE[btsbiztalkserver2006r2](../includes/btsbiztalkserver2006r2-md.md)]和所有更高版本|本机 EDI 功能|  
|[!INCLUDE[btsBizTalkServer2006](../includes/btsbiztalkserver2006-md.md)]|基本 EDI 适配器|  
|[!INCLUDE[btsBizTalkServer2004](../includes/btsbiztalkserver2004-md.md)]|基本 EDI 适配器|  
|[!INCLUDE[btsBizTalkServer2002](../includes/btsbiztalkserver2002-md.md)]|本机 EDI 功能|  
  
## <a name="feature-set-comparison-chart"></a>功能集比较表  
 下表显示了在 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 发行版中，EDI 组件/功能提供的 EDI 支持。 “Y”表示功能受支持；“N”表示功能不受支持。  
  
|功能|[!INCLUDE[btsBizTalkServer2000](../includes/btsbiztalkserver2000-md.md)] - [!INCLUDE[btsBizTalkServer2002](../includes/btsbiztalkserver2002-md.md)]|[!INCLUDE[btsBizTalkServer2004](../includes/btsbiztalkserver2004-md.md)] - [!INCLUDE[btsBizTalkServer2006](../includes/btsbiztalkserver2006-md.md)]|[!INCLUDE[btsbiztalkserver2006r2](../includes/btsbiztalkserver2006r2-md.md)]|BizTalk Server 2009|BizTalk Server 2010|注释|  
|---|---|---|---|---|---|---|  
|在事务集 ISA 段修改|是|否|是|是|是|在 [!INCLUDE[btsbiztalkserver2006r2](../includes/btsbiztalkserver2006r2-md.md)] 和更高版本中，通过创建特定于事务集的协议提供支持。|  
|ISA11： 美国或其他标准类型|是|否|是|是|是|-|  
|ISA12： 交换控件版本|是|否|是|是|是|-|  
|ISA13： 交换控制编号 （递增数）|是|否|是|是|是|-|  
|ISA15： 测试或生产|是|否|是|是|是|-|  
|文档/事务级别的 GS 段修改|是|否|是|是|是|-|  
|GS 发送者/接收者 Id 可以是不同于 ISA|是|否|是|是|是|-|  
|入站文档 Id 不同于 ISA 和 GS 出站 Id|是|否|是|是|是|-|  
|GS01： 能够更改文档的类型|是|否|是|是|是|-|  
|GS04： 日期 （能够更改格式）|否|否|是|是|是|[!INCLUDE[btsbiztalkserver2006r2](../includes/btsbiztalkserver2006r2-md.md)] 和更高版本包含用于选择 CCYYMMDD 和 YYMMDD 格式的 UI|  
|GS05： 时间 （能够更改格式）|否|否|是|是|是|[!INCLUDE[btsbiztalkserver2006r2](../includes/btsbiztalkserver2006r2-md.md)] 和更高版本包含用于选择 HHMM、HHMMSS 和 HHMMSSdd 格式的 UI|  
|GS06： 更改控制编号|是|否|是|是|是|-|  
|GS07： 代理代码|是|否|是|是|是|-|  
|GS08： 能够将放入标准版本|是|否|是|是|是|-|  
|在运行时覆盖 EDI 信封的能力|否|否|否|是|是|-|  
|自定义的 EDI 架构|是|否|是|是|是|-|  
|组织/参与方设置|是|Y（最低）|是|是|是|[!INCLUDE[btsbiztalkserver2006r2](../includes/btsbiztalkserver2006r2-md.md)] 和 BizTalk Server 2009 可以创建不以模板为基础的参与方。<br /><br /> BizTalk Server 2010 和更高版本通过分隔参与方和协议来重新对此进行建模。 允许创建不以模板为基础的协议。|  
|通过文档定义路由的 EDI 文档|是|-|是|是|是|-|  
|自动 997 的向贸易合作伙伴|是|是|是|是|是|在 [!INCLUDE[btsbiztalkserver2006r2](../includes/btsbiztalkserver2006r2-md.md)] 和 BizTalk Server 2009 中，通过特定于参与方的配置提供支持<br /><br /> 在 BizTalk Server 2010 和更高版本中，通过特定于业务配置文件的配置提供支持。|  
|可靠消息传递通过 997 的出站 EDI|是|是|是|是|是|-|  
|EDIFACT 支持|是|Y（最低）|是|是|是|在 [!INCLUDE[btsbiztalkserver2006r2](../includes/btsbiztalkserver2006r2-md.md)] 和更高版本中提供支持（按照 ISO 9735 4.1 版，为 D93 到 D05）。|  
|X12 支持|是|Y（最低）|是|是|是|在 [!INCLUDE[btsbiztalkserver2006r2](../includes/btsbiztalkserver2006r2-md.md)] 和更高版本中提供支持（2040 到 5030）|  
|HIPAA 支持|否|Y（在 [!INCLUDE[btsBizTalkServer2006](../includes/btsbiztalkserver2006-md.md)] 中）|是|是|是|中支持[!INCLUDE[btsBizTalkServer2006](../includes/btsbiztalkserver2006-md.md)]作为 Microsoft BizTalk Accelerator for HIPAA (BTAHIPAA) 3.3。 在 [!INCLUDE[btsbiztalkserver2006r2](../includes/btsbiztalkserver2006r2-md.md)] 和更高版本中作为本机 EDI 功能的一部分提供支持。|  
|删除/codelists 枚举器的功能|是|否|是|是|是|在 [!INCLUDE[btsbiztalkserver2006r2](../includes/btsbiztalkserver2006r2-md.md)] 和更高版本中，通过 Visual Studio/BizTalk 编辑器提供支持|  
|AS2 发送/接收|否|否|是|是|是|在 BizTalk Server 2009 及更高版本，AS2 是 Drummond 认证为多文件附件支持、 文件名保留支持和互操作性。|  
|AS2 文件名称保存|否|否|否|是|是|-|  
|AS2 可靠消息传递|否|否|否|是|是|-|  
|可以迁移[!INCLUDE[btsBizTalkServer2002](../includes/btsbiztalkserver2002-md.md)]到 EDI 存储库的自定义 XDR EDI 架构|-|否|否|否|否|必须将基本 EDI 应用程序迁移到 [!INCLUDE[btsbiztalkserver2006r2](../includes/btsbiztalkserver2006r2-md.md)] 或 BizTalk Server 2009，然后使用“参与方迁移工具”将应用程序迁移到 BizTalk Server 2010 和更高版本。|  
|（累积单个事务中的多个事务类型） 的出站批处理|否|否|是|是|是|BizTalk Server 2009 和更高版本支持用于每个业务配置文件的多个批处理配置。|  
|入站批处理 – 交换 XML （保留将传入的批处理交换） 或基于配置选项的事务设置 XML|否|否|是|是|是|在 [!INCLUDE[btsbiztalkserver2006r2](../includes/btsbiztalkserver2006r2-md.md)] 和更高版本中，这是对入站解除批处理（即将交换拆分为单独的事务集 Xml）支持的补充|  
|交换和事务设置生成和验证在 Visual Studio 中的设计时|否|否|是|是|是|-|  
|TA1 (技术 ACK) 生成和对帐|否|否|是|是|是|-|  
|可选的 EDI 和 XSD 验证标志|否|否|是|是|是|-|  
|文档的格式定义，可在 GS 级别|否|否|是|是|是|-|  
  
## <a name="see-also"></a>另请参阅  
 [EDI 标准支持](../core/edi-standards-support.md)   
 [EDI 文档架构支持](../core/edi-document-schema-support.md)   
 [EDI 字符集支持](../core/edi-character-set-support.md)