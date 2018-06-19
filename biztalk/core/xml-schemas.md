---
title: XML 架构 |Microsoft 文档
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
ms.openlocfilehash: 86760d50b729419f31ba8186033181e0d03ad14c
ms.sourcegitcommit: 3fc338e52d5dbca2c3ea1685a2faafc7582fe23a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/01/2017
ms.locfileid: "26008094"
---
# <a name="xml-schemas"></a>XML 架构
XML 架构描述了以 XML 表示的业务文档。 由于 Microsoft BizTalk Server 使用 XML 作为其规范表示形式的业务文档，入站和出站文档不需要进行任何变换。 可以只使用在所有架构中都可用的一组基本属性在 BizTalk 编辑器中创建 XML 架构，并且不需要启用任何架构编辑器扩展。  
  
 有几种方法可以在其中创建 BizTalk Server 中的 XML 架构。 其中包括：  
  
-   **创建新的架构**。 此架构创建方法涉及向 BizTalk 项目中添加新架构。 在**解决方案资源管理器**，右键单击 BizTalk 项目，单击**添加**，单击**新项**，然后单击**架构**。 通过将各种节点添加架构树视图中，生成架构的结构。  
  
-   **结合其他架构中创建新的架构，**。 对于实际情况中的复杂架构，您可能更希望使用其他现有架构中提供的类型来为消息生成架构。 通过使用导入、包括和重新定义架构的 XML 架构定义 (XSD) 语言概念，可以利用在其他架构中已定义的类型。 有关结合使用多个架构的详细信息，请参阅[架构，使用其他架构](../core/schemas-that-use-other-schemas.md)。  
  
-   **从实例消息生成架构**。 只要特定的实例消息是由格式正确的 XML 组成，就可以生成对应于该实例消息的 XML 架构。 使用**添加生成的项的 *\<BizTalk 项目名称\>*** 对话框中，通过单击访问**添加生成的项**上**项目**菜单上，若要执行此类型的架构生成操作。  
  
    > [!NOTE]
    >  此类生成操作只能用于生成 XML 架构，而不能用于生成属性架构或平面文件架构。  
  
-   **从较旧的架构规范语言的架构迁移到 XSD**。 可以从开发的使用以 XML 数据简化 (XDR) 格式存储架构的 BizTalk Server 的早期版本的架构的 BizTalk Server 中生成 XML 架构。 有关如何将较旧的 XDR 架构迁移到 BizTalk Server 使用的 XSD 格式的详细信息，请参阅[架构迁移从以前版本的 BizTalk Server](../core/schema-migration-from-previous-versions-of-biztalk-server.md)。  
  
     还可以从使用文档类型定义 (DTD) 语法表示的文档架构生成基于 XSD 的 XML 架构。  
  
     使用**添加生成的项的 *\<BizTalk 项目名称\>*** 对话框中，通过单击访问**添加生成的项**上**项目**菜单上，若要执行此类型的架构生成操作。  
  
    > [!NOTE]
    >  这些类型的生成操作只能用于生成 XML 架构，而不能用于生成属性架构或平面文件架构。  
  
 无论使用哪一种架构创建方法，都需要进一步修改架构，以便该架构可为其对应的实例消息提供足够完整的说明。 若要开始，这些任务，请参阅[管理架构节点内](../core/managing-the-nodes-within-a-schema.md)，[设置节点属性](../core/how-to-set-node-properties.md)，和[使用现有节点](../core/working-with-existing-nodes.md)。  
  
## <a name="see-also"></a>另请参阅  
 [不同类型的 BizTalk 架构](../core/different-types-of-biztalk-schemas.md)