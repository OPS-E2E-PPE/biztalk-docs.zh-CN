---
title: 步骤 5：升级架构属性 |Microsoft Docs
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
ms.openlocfilehash: fa148fee56ae62d5c14112c850f16b4d9ae3cf53
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65288068"
---
# <a name="step-5-promote-schema-properties"></a>步骤 5：升级架构属性
在此步骤中，提升架构属性，以便[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]业务流程可以引用在后续步骤中创建这些属性值。 升级是一种机制，用于引用消息实例中的特定值，并使其可以访问[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]组件，例如业务流程或基于内容的路由目的。 此外，升级的属性情况下是可见的表达式编辑器中的 Microsoft IntelliSense [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]。  
  
> [!NOTE]
>  [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] 审核和使用 BizTalk 运行状况与活动跟踪 (HAT) 工具的日志记录功能可以跟踪仅升级的架构属性。  
  
### <a name="to-promote-schema-properties"></a>若要升级架构属性  
  
1. 在解决方案资源管理器下**BTAHL7 项目**，双击**DoorBell.xsd**节点以打开该架构。  
  
2. 右键单击**FirstName**字段元素中，依次指向**Promote**，然后单击**快速升级**。  
  
3. 单击**确定**属性架构添加到项目。  
  
   > [!NOTE]
   >  [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)] 向的图标添加一个橙色圆**FirstName**元素，指示已升级元素。  
  
4. 重复上述步骤以升级以下字段元素：  
  
   -   **MiddleName**  
  
   -   **LastName**  
  
   -   **SSN**  
  
   > [!IMPORTANT]
   >  务必要注意如社会安全号码 (SSN) 会导致该升级患者 ID (PID)[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]来跟踪该属性为每个入站消息通过系统。 这种情况下的副作用是消息跟踪数据库将患者 Ssn 的副本。 这可能会造成重大的安全问题。 必须保护小心地使用此数据存储区或完全避免的 PID 数据升级。  
  
    有关跟踪基于升级的架构元素的文档的详细信息，请参阅有关运行状况与活动跟踪的信息的 BizTalk Server 帮助。  
  
   请继续执行[步骤 6:验证架构](../../adapters-and-accelerators/accelerator-hl7/step-6-validate-the-schemas.md)。  
  
## <a name="see-also"></a>请参阅  
 [消息充实教程](../../adapters-and-accelerators/accelerator-hl7/message-enrichment-tutorial.md)