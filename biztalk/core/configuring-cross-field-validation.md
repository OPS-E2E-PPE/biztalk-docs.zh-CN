---
title: 配置跨字段验证 |Microsoft Docs
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
ms.openlocfilehash: 6cd14497f08bf085c1a93122baa00875ad714cc1
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65391346"
---
# <a name="configuring-cross-field-validation"></a>配置跨字段验证
本主题介绍如何启用 EDI 编码消息中的事务集数据元素上的跨字段/段验证。 若要执行此操作，需要执行两个设置：  
  
-   设置 EDI 架构的批注中的跨字段验证标志。 对于 X12 或 HIPAA 架构，这是**X12ConditionDesignator_Check**标志。 对于 EDIFACT 架构，则**EdifactDependencyRule_Check**标志。  
  
-   启用的协议属性中的 EDI 类型验证。  
  
## <a name="prerequisites"></a>先决条件  
 必须以成员的身份登录[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]Administrators 组。  
  
### <a name="configuring-cross-field-validation"></a>配置跨字段验证  
  
1. 在 BizTalk 编辑器中打开您的架构。  
  
2. 对于 X12 或 HIPAA 架构，找到**X12ConditionDesignator_Check**中架构的 appinfo 部分批注中的标志。 将其设置为**是**。  
  
   > [!NOTE]
   >  设置为将标记 X12ConditionDesignator_Check**是**无法执行从 BizTalk 架构编辑器。 设置该标记，你必须打开记事本或类似的文本编辑器中编辑和保存该架构文件 (.xsd)。  
  
3. 对于 EDIFACT 架构，找到**EdifactDependencyRule_Check**中架构的 appinfo 部分批注的标志。 将其设置为**是**。  
  
4. 对于该架构适用段，指定关系条件 （x12 和 HIPAA） 或依赖规则 (EDIFACT) 的应用。 有关详细信息，请参阅[跨字段-段验证](../core/cross-field-segment-validation.md)。  
  
   > [!NOTE]
   >  为 EDI 架构中的某个段被输入跨字段验证条件或规则。 如果针对数据元素，而不是一个段中，输入跨字段验证规则[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]执行架构验证时，会生成一个警告。  
  
5. 在中**验证**页 (下**事务集设置**部分) 的单向协议选项卡**协议属性**相关协议的对话框请确保**EDI 类型验证**选择属性。  
  
## <a name="see-also"></a>请参阅  
 [开发 EDI 架构](../core/developing-edi-schemas.md)