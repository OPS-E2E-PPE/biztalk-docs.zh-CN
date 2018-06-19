---
title: 步骤 5： 升级架构属性 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- message enrichment tutorial, pomoted properties
- promoted properties
- schemas, promoted properties
ms.assetid: cb51cece-1b65-4ba2-b8e6-ce8b6694cdb6
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 91d68ece5bedf7ec46a6d5ede7efc6878fa972fc
ms.sourcegitcommit: 3fc338e52d5dbca2c3ea1685a2faafc7582fe23a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/01/2017
ms.locfileid: "26004470"
---
# <a name="step-5-promote-schema-properties"></a>步骤 5： 升级架构中的属性
在此步骤中，升级架构中的属性，以便[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]业务流程可以引用在后续步骤中创建这些属性值。 升级是一种机制，用于引用消息实例内的某个特定值，并使其能够[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]组件，例如业务流程或基于内容的路由目的。 此外，已提升的属性是可见的[!INCLUDE[btsCoName](../../includes/btsconame-md.md)]IntelliSense 中的表达式编辑器[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]。  
  
> [!NOTE]
>  [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]审核和日志记录功能，使用 BizTalk 运行状况和活动跟踪 (HAT) 工具可以跟踪仅提升的架构属性。  
  
### <a name="to-promote-schema-properties"></a>若要升级架构中的属性  
  
1.  在解决方案资源管理器下**BTAHL7 项目**，双击**DoorBell.xsd**节点以打开该架构。  
  
2.  右键单击**FirstName**字段元素中，依次指向**Promote**，然后单击**快速升级**。  
  
3.  单击**确定**属性架构添加到项目。  
  
    > [!NOTE]
    >  [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]添加的图标橙色圆圈**FirstName**元素，，该值指示元素已被提升。  
  
4.  重复上述步骤以提升的以下字段元素：  
  
    -   **MiddleName**  
  
    -   **LastName**  
  
    -   **SSN**  
  
    > [!IMPORTANT]
    >  务必要注意如社会保障号 (SSN) 会导致该升级一个患者 ID (PID)[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]来跟踪该属性用于通过系统每个入站消息。 这种情况下的副作用是消息跟踪数据库将患者 Ssn 的副本。 这可能会造成重大的安全问题。 你必须保护小心地使用此数据存储，或者可以完全避免 PID 数据在升级。  
  
     有关跟踪升级的架构元素所基于的文档的详细信息，请参阅有关运行状况和活动跟踪信息的 BizTalk Server 帮助。  
  
 继续执行[步骤 6： 验证架构](../../adapters-and-accelerators/accelerator-hl7/step-6-validate-the-schemas.md)。  
  
## <a name="see-also"></a>另请参阅  
 [消息充实教程](../../adapters-and-accelerators/accelerator-hl7/message-enrichment-tutorial.md)