---
title: "HIPAA 文档架构版本 5010 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 62e50964-66e1-4ed9-a1a1-68556b13b024
caps.latest.revision: "15"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 24d1528d5c35c15e777ce1540d42ea4b7066cea2
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="hipaa-document-schema-version-5010"></a>HIPAA 文档架构版本 5010
美国部门的运行状况和公共服务部 (HHS) 宣布当前 HIPAA 版本 4010A1 替换版本 5010 上 2009 年 1 月 16 日的最后一个规则。 5010 新版 HIPAA 标准包括结构，前面的内容，技术中的改进和数据内容。 这些改进将减少，并消除数据中的多义性，同时还解决了几个以前不符合的业务需求。 [!INCLUDE[prague](../includes/prague-md.md)]提供对 HIPAA 版本 5010 支持。  
  
> [!NOTE]
>  [!INCLUDE[prague](../includes/prague-md.md)] 继续支持 HIPAA 版本 4010A1。  
  
## <a name="hipaa-5010-version-support"></a>HIPAA 5010 版本支持  
 为了让 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 支持 HIPAA 5010，引入了以下更改：  
  
-   **新替换架构**: 5010 引入了以下新替换架构，通过早期版本 4010A1 HIPAA 版本。 压缩并传递可执行文件中的 EDI 架构[!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]XSD_Schema\EDI\MicrosoftEdiXSDTemplates.exe。 在执行时，MicrosoftEdiXSDTemplates.exe 内存放 HIPAA 5010 架构转换[!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]XSD_Schema\EDI\HIPAA\5010 文件夹。  
  
    |GS08/ST03|集 ID (ST01)|Description|  
    |----------------|----------------------|-----------------|  
    |005010X279|270|资格、范围或收益查询 - 请求|  
    |005010X279|271|资格、保险范围或保险赔偿信息 - 响应|  
    |005010X212|276|医疗保健索赔状态 - 请求|  
    |005010X212|277|医疗保健索赔状态 - 响应|  
    |005010X217|278|医疗保健服务审核 – 请求和响应|  
    |005010X218|820|工资扣缴|  
    |005010X220|834|医疗保健福利登记和维护|  
    |005010X221|835|医疗保健索赔付款|  
    |005010X222|837|医疗保健索赔 - 职业|  
    |005010X223A1|837|医疗保健索赔 - 机构|  
    |005010X224A1|837|医疗保健索赔 - 牙科|  
  
-   **支持 ST03 字段**： 版本 5010 规定所有事务中的是否存在 ST03 设置而非 835 (卫生保健声明 Payment(s))。 ST03 用于标识事务集的版本。 ST03 允许单个组中存在不同版本的事务集。 在识别事务集版本上，ST03 优先于 GS08。 您可以在 EDI 属性架构命名空间下编写和提升 ST03 为上下文属性，并基于 ST03 路由消息。  
  
-   **为组中的类似的事务集支持**: X12 标准提供事务设置和组，称为 ST01 GS01 映射之间的映射。 此映射用于验证可以在单个组 (GS-GE) 中合并的相似事务集。 对于 HIPAA，这意味着职业、机构和牙科 837 索赔现在可以出现在单个组内。  
  
-   **支持 ICD 10**： 电子事务代码集用于的医疗保健数据传输。 版本 5010 可使用国际疾病分类 (ICD-10) 代码集，它在早期版本 4010A1 中是不受支持的。 ICD-10 用于识别索赔单、相关事务和临床报告中的各种诊断和手续。 使用 ICD-10 的优点有：可提供有关患者服务、诊断、治疗信息的更准确的数据，以及更全面的质量数据报告。  
  
-   **5010 997 中的新字段**: 997 功能确认架构提供的的现成通过[!INCLUDE[prague](../includes/prague-md.md)]引入了即 AK103、 AK203 和 AK41.3 的三个新可选字段。 EDI 引擎是能够处理传入 5010 997 消息中包含这些字段，但将不会生成传出 997 确认基于新的架构。  
  
 先前存在一个 HIPAA 4010A1 架构的已知问题，即不会检查 X12_R 数据类型元素的最小和最大长度。 在 [!INCLUDE[prague](../includes/prague-md.md)] 中，此问题已得到解决，现在 HIPAA 5010 架构会验证 X12_R 数据类型元素的最小和最大长度。  
  
## <a name="see-also"></a>另请参阅  
 [BizTalk Server 中的 HIPAA 支持](../core/hipaa-support-in-biztalk-server.md)   
 [拆分 HIPAA 子文档](../core/splitting-hipaa-subdocuments.md)