---
title: XML 架构 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 1ec364e7-866d-4164-be91-be75a40ce878
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f46a4ed9f834d09993dfa2edb48b3e875b0f3699
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65298401"
---
# <a name="xml-schemas"></a>XML 架构
XML 架构描述了在 XML 中表示的业务文档。 由于 Microsoft BizTalk Server 使用 XML 作为其规范表示形式的业务文档，入站和出站文档不需要任何转换。 可以在 BizTalk 编辑器中使用仅可在所有架构，且不需要启用任何架构编辑器扩展属性的基本集创建 XML 架构。  
  
 有几种方法可在其中创建 BizTalk Server 中的 XML 架构。 这些问题包括：  
  
- **创建新架构**。 此架构创建方法涉及向 BizTalk 项目中添加新架构。 在中**解决方案资源管理器**，右键单击 BizTalk 项目，单击**添加**，单击**新项**，然后单击**架构**。 通过添加多个节点在架构树视图中生成的架构的结构。  
  
- **创建新的架构，结合其他架构**。 对于现实生活中的复杂架构，则更有可能使用其他现有架构中提供的类型生成您的消息的架构。 通过使用导入的 XML 架构定义 (XSD) 语言概念，包括和重新定义架构，您可以充分利用已在其他架构中定义的类型。 有关将多个架构一起使用的详细信息，请参阅[使用其他架构的](../core/schemas-that-use-other-schemas.md)。  
  
- **从实例消息生成架构**。 可以生成对应于特定的实例消息，只要该实例消息包含格式正确的 XML 的 XML 架构。 使用**添加生成的项-  *\<BizTalk 项目名称\>*** 对话框中，通过单击来访问**添加生成的项**上**项目**菜单中，若要执行此类型的架构生成操作。  
  
  > [!NOTE]
  >  此类型的生成操作只能用于生成 XML 架构、 不是属性架构或平面文件架构。  
  
- **将架构从旧的架构规范语言迁移到 XSD**。 可以从已通过使用以前版本的 BizTalk Server，以 XML 数据缩减 (XDR) 格式存储架构开发的架构的 BizTalk Server 中生成 XML 架构。 有关如何将旧 XDR 架构迁移到 BizTalk Server 使用的 XSD 格式的详细信息，请参阅[从以前版本的 BizTalk Server 迁移架构](../core/schema-migration-from-previous-versions-of-biztalk-server.md)。  
  
   此外可以生成基于 XSD 从使用文档类型定义 (DTD) 语法表示的文档架构的 XML 架构。  
  
   使用**添加生成的项-  *\<BizTalk 项目名称\>*** 对话框中，通过单击来访问**添加生成的项**上**项目**菜单中，若要执行此类型的架构生成操作。  
  
  > [!NOTE]
  >  这些类型的生成操作只能用于生成 XML 架构、 不是属性架构或平面文件架构。  
  
  无论您使用的架构创建方法将继续通过修改架构，以便它提供了其相应的实例消息的足够完整的说明。 若要开始这些任务，请参阅[管理节点架构中](../core/managing-the-nodes-within-a-schema.md)，[设置节点属性](../core/how-to-set-node-properties.md)，并[使用现有节点](../core/working-with-existing-nodes.md)。  
  
## <a name="see-also"></a>请参阅  
 [不同类型的 BizTalk 架构](../core/different-types-of-biztalk-schemas.md)