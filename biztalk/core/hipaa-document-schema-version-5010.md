---
title: HIPAA 文档架构版本 5010 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 62e50964-66e1-4ed9-a1a1-68556b13b024
caps.latest.revision: 15
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 0a3d1aafd346a75c4968f436b2d04f12ae987d2b
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65344370"
---
# <a name="hipaa-document-schema-version-5010"></a>HIPAA 文档架构版本 5010
美国部门的运行状况和公众服务部 (HHS) 宣布使用版本 5010 替换当前的 HIPAA 版本 4010A1 2009 年 1 月 16 日，一条最终规则。 版本 5010 HIPAA 标准的包括结构化，前面的内容，技术中的改进和数据内容。 这些改进将减少和消除数据方面的多义性问题，同时满足几个以前未满足的业务需求。 BizTalk Server 提供对 HIPAA 版本 5010 的支持。  

> [!NOTE]
>  BizTalk Server 继续支持 HIPAA 版本 4010A1。  

## <a name="hipaa-5010-version-support"></a>HIPAA 5010 版本支持  
 作为的一部分引入了以下更改[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]的 HIPAA 5010 的支持：  

- **新的替换架构**:HIPAA 版本 5010 在早期版本 4010A1 上引入了以下新替换架构。 EDI 架构的压缩，然后在可执行文件，将交付[!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]XSD_Schema\EDI\MicrosoftEdiXSDTemplates.exe。 MicrosoftEdiXSDTemplates.exe 执行时，将 HIPAA 5010 架构到[!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]XSD_Schema\EDI\HIPAA\5010 文件夹。  


  |  GS08/ST03   | 设置 Id (ST01) |                       Description                       |
  |--------------|----------------|---------------------------------------------------------|
  |  005010X279  |      270       |   资格、 保险范围或收益查询-请求    |
  |  005010X279  |      271       | 资格、 保险范围或保险赔偿信息-响应 |
  |  005010X212  |      276       |           医疗保健索赔状态-请求            |
  |  005010X212  |      277       |           医疗保健索赔状态-响应           |
  |  005010X217  |      278       |   医疗保健服务审核 – 请求和响应    |
  |  005010X218  |      820       |                    工资扣缴                    |
  |  005010X220  |      834       |    医疗保健福利登记和维护    |
  |  005010X221  |      835       |              医疗保健索赔付款               |
  |  005010X222  |      837       |           医疗保健索赔-职业           |
  | 005010X223A1 |      837       |          医疗保健索赔-机构           |
  | 005010X224A1 |      837       |              医疗保健索赔-牙科              |


- **对 ST03 字段的支持**:版本 5010 要求非 835 （医疗保健索赔付款所有事务集在存在 ST03。 ST03 用于标识事务集的版本。 ST03 允许单个组内事务集的不同版本。 GS08 上，ST03 优先中标识事务集版本。 您可以编写和提升 ST03 为上下文属性的 EDI 属性架构命名空间下，并基于 ST03 路由消息。  

- **对组内的相似事务集的支持**:X12 标准提供事务集和组，称为 ST01-GS01 映射之间的映射。 此映射用于验证单个组 (GS-GE) 中结據相似事务集。 对于 HIPAA，这意味着职业、 机构和牙科 837 索赔现在可以在单个组中出现。  

- **对 icd-10 的支持**:电子事务代码集用于传输医疗保健数据。 版本 5010 可使用国际疾病分类 (icd-10) 代码集，它不支持的早期版本 4010A1。 Icd-10 用于识别的各种诊断和索赔单、 相关的事务和临床报告中的过程。 使用 icd-10 的优点包括患者服务、 诊断、 治疗信息和更全面的质量数据报告上更准确的数据。  

- **5010 997 中的新字段**:-现成的 BizTalk server 引入了三个新的可选字段即 AK103、 AK203 和 AK41.3 时，提供了 997 功能确认架构。 EDI 引擎都能够处理的传入 5010 997 消息包含这些字段，但将不会生成传出 997 确认基于新的架构。  

  出现在其中 X12_R 数据类型的元素不会检查其最小和最大长度的 HIPAA 4010A1 架构的已知的问题。 在 BizTalk Server 中修复此问题和 HIPAA 5010 架构验证的最小和最大长度为 X12_R 数据类型的元素。  

## <a name="see-also"></a>请参阅  
 [BizTalk Server 中的 HIPAA 支持](../core/hipaa-support-in-biztalk-server.md)   
 [拆分 HIPAA 子文档](../core/splitting-hipaa-subdocuments.md)