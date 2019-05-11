---
title: 使用 BizTalk 编辑器创建架构 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 03fac91b-5b67-4baf-968c-294c525d3018
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b32b4667e0f9777ccf21f26fdfc38a2d12946998
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65389886"
---
# <a name="create-schemas-using-biztalk-editor"></a>使用 BizTalk 编辑器创建架构

## <a name="overview"></a>概述
BizTalk 编辑器是在 Microsoft 内部运行的工具[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]环境。 可以使用它来创建、 编辑和管理与你的应用程序使用的架构。 BizTalk 编辑器使用分层记录和字段的自有图形系统来表示实例消息的结构，并使用 XML 架构定义 (XSD) 语言来存储它定义的架构。 这是而不考虑在其中交换实例消息的格式，则返回 true。 例如，假设您与贸易合作伙伴交换平面文件。 当 BizTalk Server 处理这些平面文件，它将其转换到和从符合 XSD 架构定义在 BizTalk 编辑器中的 XML 格式。  
  
 下图中所示，可以安排好的业务流程内使用使用 BizTalk 编辑器创建的架构。  
  
 ![](../core/media/ebiz-dev-busprcsh.gif "ebiz_dev_busprcsh")  
  
 架构还用于通过组装器和拆装器将实例消息从一种格式，如翻译平面文件格式和 XML 之间。 架构还在实例消息转换，其中的实例消息中的数据用于构造具有不同结构的实例消息中发挥重要作用。 新的实例消息可能是语义上等效，如采购订单的不同表示形式也可能是需要部分或全部在其内容中的原始实例消息中的数据的实例消息的不同但相关类型。  
  
 有关将所有实例消息都翻译成符合 XSD 架构的 XML 格式的一个重要原因是为了简化将消息从一种结构转换为另一种结构的过程。 消息结构通常是其语法差异尽管在语义上等效的。 例如，您和您的贸易合作伙伴可能会以不同的方式，构建采购订单，但它们所包含的基本信息是相同的这样它们自动来回转换。 第一个，则将所有实例消息转换为相应的 XSD 架构控制的 XML 格式，可以 XML 和非 XML 格式之间来回转换和从一种 XML 结构转换为另一个实例消息。 实例消息翻译与实例消息转换之间的差别的详细信息，请参阅[数据转换](../core/data-transformation.md)。  
  
 Microsoft Visual Studio 环境中的辅助工具向 BizTalk 编辑器为 BizTalk 映射器。 使用 BizTalk 编辑器创建定义的结构和相关的实例消息的对格式的架构后，使用 BizTalk 映射器以图形方式定义如何将符合某种架构的实例消息 (源实例消息和架构） 转换为符合另一个架构 （目标实例消息和架构） 的实例消息。 此类转换的规范使用可扩展样式表语言转换 (XSLT) 实现的并保存为文件称为的映射。 有关 BizTalk 映射器的概念性和程序性信息，请参阅[创建映射使用 BizTalk 映射器](../core/creating-maps-using-biztalk-mapper.md)。 有关 BizTalk 映射器属性和 functoid 的参考信息，请参阅**映射属性参考**并**Functoid 参考**[!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]。  
  
 使用 BizTalk 编辑器中，您可以打开未包含任何结构的空架构，可以打开现有的 XSD 架构，也可以从非 XSD 源生成架构。 当从非 XSD 源生成架构时，BizTalk 编辑器将解释源的结构，并生成是它的 XSD 表示形式的架构。 您可以编辑的任何记录和显示在 BizTalk 编辑器架构树视图中，字段，然后将结构保存为 BizTalk 架构。  
  
 有关使用 BizTalk 编辑器的键盘快捷方式的信息，请参阅[BizTalk 编辑器键盘快捷方式](../core/biztalk-editor-keyboard-shortcuts.md)。  
  
## <a name="next-steps"></a>后续步骤
  
-   [规划架构创建](../core/planning-for-schema-creation.md)  
  
-   [关于实例消息](../core/about-instance-messages.md)  
  
-   [关于架构](../core/about-schemas.md)  
  
-   [使用 BizTalk 编辑器](../core/using-biztalk-editor.md)  
  
-   [创建架构](../core/creating-schemas.md)  
  
-   [使用“BizTalk 平面文件架构向导”创建架构](../core/creating-schemas-using-biztalk-flat-file-schema-wizard.md)  
  
-   [测试架构](../core/testing-schemas.md)  
  
-   [扩展 BizTalk 编辑器](../core/extending-biztalk-editor.md)  
  
-   [创建架构时的注意事项](../core/considerations-when-creating-schemas.md)  
  
-   [架构生成和验证的已知问题](../core/known-issues-with-schema-generation-and-validation.md)