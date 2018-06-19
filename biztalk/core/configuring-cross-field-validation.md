---
title: 配置跨字段验证 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 8f0c6ae8-0b8a-4826-9dfb-bf27e5ff7fa6
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 4bde88ac82d69cdaa0dec7513e294953b7164b56
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22233645"
---
# <a name="configuring-cross-field-validation"></a>配置跨字段验证
本主题介绍如何对 EDI 编码消息中的事务集数据元素启用跨字段/段验证。 为此，你需要执行两个设置：  
  
-   设置 EDI 架构的批注中的跨字段验证标志。 对于 X12 或 HIPAA 架构，这是**X12ConditionDesignator_Check**标志。 对于 EDIFACT 架构，这是**EdifactDependencyRule_Check**标志。  
  
-   在协议属性中启用 EDI 类型验证。  
  
## <a name="prerequisites"></a>先决条件  
 你必须以 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理员组成员的身份登录。  
  
### <a name="configuring-cross-field-validation"></a>配置跨字段验证  
  
1.  在 BizTalk 编辑器中打开你的架构。  
  
2.  对于 X12 或 HIPAA 架构，查找**X12ConditionDesignator_Check**中的应用程序信息部分中的架构批注的标志。 将其设置为**是**。  
  
    > [!NOTE]
    >  设置标志 X12ConditionDesignator_Check**是**无法执行从 BizTalk 架构编辑器。 若要设置该标记，必须在记事本或类似的文本编辑器中打开它并进行编辑，然后保存架构文件 (.xsd)。  
  
3.  对于 EDIFACT 架构，查找**EdifactDependencyRule_Check**批注中的架构的 appinfo 部分中的标志。 将其设置为**是**。  
  
4.  对于适用的架构段，指定适用的关系条件（X12 和 HIPAA）或依赖规则 (EDIFACT)。 有关详细信息，请参阅[交叉字段段验证](../core/cross-field-segment-validation.md)。  
  
    > [!NOTE]
    >  跨字段验证条件或规则是针对 EDI 架构中的段输入的。 如果针对数据元素（而非段）输入跨字段验证规则，[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 将在执行架构验证时生成警告。  
  
5.  在**验证**页 (下**事务设置设置**部分) 的单向协议选项卡**协议属性**相关协议的对话框中请确保**EDI 类型验证**选择属性。  
  
## <a name="see-also"></a>另请参阅  
 [开发 EDI 架构](../core/developing-edi-schemas.md)