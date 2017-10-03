---
title: "创建使用 BizTalk 编辑器的架构 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 03fac91b-5b67-4baf-968c-294c525d3018
caps.latest.revision: "9"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: fb9e4c6496f43a9602ad56bc0e095d98f2da90d9
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="create-schemas-using-biztalk-editor"></a>使用 BizTalk 编辑器创建架构

## <a name="overview"></a>概述
BizTalk 编辑器是在 Microsoft 内部运行的工具[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]环境。 您可以使用它来创建、编辑和管理要用于应用程序的架构。 BizTalk 编辑器使用其自己的分层记录和字段的图形系统来表示实例消息的结构，并使用 XML 架构定义 (XSD) 语言存储其定义的架构。 不论实例消息以何种格式进行交换都是如此。 例如，假设您要与贸易合作伙伴交换平面文件。 当 BizTalk Server 处理这些平面文件时，它会将这些平面文件转换为符合 BizTalk 编辑器中所定义的 XSD 架构的 XML 格式，以及进行相反转换。  
  
 使用 BizTalk 编辑器创建的架构可以用于已编排为业务流程的业务程序，如下图所示：  
  
 ![](../core/media/ebiz-dev-busprcsh.gif "ebiz_dev_busprcsh")  
  
 组装器和拆装器也可使用架构以将实例消息从一种格式翻译成另一种格式，例如，在平面文件格式与 XML 之间。 此外，架构还在实例消息转换中起着非常重要的作用，即实例消息中的数据可用于构造具有不同结构的实例消息。 而新的实例消息可能与原始实例消息在语义上是相同的（例如，采购订单的不同表示形式），或它们的类型可能不同但相关，在新的实例消息的内容中需要原始实例消息中的部分或所有数据。  
  
 之所以将所有实例消息翻译成符合 XSD 架构的 XML 格式，一个重要原因是为了简化消息从一种结构转换成另一种结构的过程。 尽管消息结构在语法上存在差异，但它们通常在语义上是相同的。 例如，您与您的贸易合作伙伴可能会以不同方式构建采购订单，但这些采购订单所包含的基本信息是相同的，这样它们才能自动地在格式间进行转换。 通过首先将所有实例消息转换成由对应的 XSD 架构控制的 XML 格式，这些实例消息就可以在 XML 格式和非 XML 格式之间进行翻译，并可从一种 XML 结构转换成另一种结构。 有关实例消息转换和实例消息转换之间的区别的详细信息，请参阅[数据转换](../core/data-transformation.md)。  
  
 在 Microsoft Visual Studio 环境中，BizTalk 编辑器的辅助工具为 BizTalk 映射器。 在使用 BizTalk 编辑器创建定义两个相关实例消息的结构和格式的架构后，可以使用 BizTalk 映射器以图形方式定义如何将符合某种架构的实例消息（源实例消息和架构）转换成符合另一种架构的实例消息（目标实例消息和架构）。 此类转换的规范是使用可扩展样式表语言转换 (XSLT) 实现的，并作为文件（称为映射）进行保存。 BizTalk 映射程序有关的概念性和程序性信息，请参阅[创建地图使用 BizTalk 映射程序](../core/creating-maps-using-biztalk-mapper.md)。 有关 BizTalk 映射程序属性和 functoid 的参考信息，请参阅**映射属性引用**和**Functoid 引用**[!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]。  
  
 使用 BizTalk 编辑器，可以打开未包含任何结构的空架构、打开现有的 XSD 架构、和从非 XSD 源中生成架构。 从非 XSD 源中生成架构时，BizTalk 编辑器将解释该源的结构，并生成作为其 XSD 表示形式的架构。 您可以编辑显示在 BizTalk 编辑器架构树视图中的任何记录和字段，然后将结构另存为 BizTalk 架构。  
  
 有关使用 BizTalk 编辑器的键盘快捷方式的信息，请参阅[BizTalk 编辑器键盘快捷键](../core/biztalk-editor-keyboard-shortcuts.md)。  
  
## <a name="next-steps"></a>后续步骤
  
-   [规划架构创建](../core/planning-for-schema-creation.md)  
  
-   [有关实例消息](../core/about-instance-messages.md)  
  
-   [有关架构](../core/about-schemas.md)  
  
-   [使用 BizTalk 编辑器](../core/using-biztalk-editor.md)  
  
-   [创建架构](../core/creating-schemas.md)  
  
-   [创建架构使用 BizTalk 平面文件架构向导](../core/creating-schemas-using-biztalk-flat-file-schema-wizard.md)  
  
-   [测试架构](../core/testing-schemas.md)  
  
-   [扩展 BizTalk 编辑器](../core/extending-biztalk-editor.md)  
  
-   [创建架构时的注意事项](../core/considerations-when-creating-schemas.md)  
  
-   [架构生成和验证已知的问题](../core/known-issues-with-schema-generation-and-validation.md)