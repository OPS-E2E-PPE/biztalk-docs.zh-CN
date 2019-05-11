---
title: 删除使用规则验证 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- policies, deleting rules
- rules
ms.assetid: b2b0dabf-8f99-4b85-95da-6bbf3e79ad41
caps.latest.revision: 11
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: cb3747ca3cf950ecb7897ff9e77b9d46950296e0
ms.sourcegitcommit: d27732e569b0897361dfaebca8352aa97bb7efe1
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/10/2019
ms.locfileid: "65530225"
---
# <a name="removing-usage-rule-validation"></a>删除使用规则验证
SWIFT 标准中定义并强制实施使用规则[!INCLUDE[A4SWIFT_CurrentVersion_FirstRef](../../includes/a4swift-currentversion-firstref-md.md)]特定于每种消息类型的业务策略。 这些使用规则是可用于提供额外的字段的验证的指南。 与不同的是网络验证规则，这是必需的您可以选择不需要使用规则的消息类型。 如果是这样，您可以执行以下任一操作：  

-   可以删除特定的业务规则强制执行消息类型验证策略的使用情况规则。  

    > [!IMPORTANT]
    >  从策略中删除一个规则将其永久删除。  

-   如果您不想要强制实施任何使用规则，可以取消部署消息类型的验证策略。  

### <a name="to-remove-a-rule-from-a-policy"></a>若要从策略中删除规则  

1.  在文本编辑器中，（如记事本） 打开的验证策略，你想要更改，例如，在 MT103_Validation_Policy *\<驱动器\>*: files\ Microsoft BizTalk Accelerator for SWIFT \<版本\>消息 Pack\SWIFT Messages\A4SWIFT SRG\<版本\>\Category 1\MT103。  

2.  删除规则节点，不想，然后保存策略。  

3.  使用业务规则引擎部署向导来发布和部署策略。  

    > [!NOTE]
    >  您也可以通过创建策略的复制、 删除特定的规则，并将部署已修改的策略验证策略中删除规则。 取消部署策略的上一版本。  

    > [!NOTE]
    >  在业务规则编辑器中，不能从已发布或已部署的策略中删除规则。  

### <a name="to-remove-the-policy-for-a-message-type"></a>若要删除的消息类型的策略  

1. 单击**启动**，依次指向**程序**，指向**Microsoft**[!INCLUDE[btsBizTalkServer2006r3ui](../../includes/btsbiztalkserver2006r3ui-md.md)]，然后单击**业务规则编辑器**。  

2. 在策略浏览器中对于消息类型，例如，MT103_Validation_Policy 查找已部署的验证策略。  

3. 右键单击该策略，单击**Undeploy**，单击**删除**，然后单击**是**。
