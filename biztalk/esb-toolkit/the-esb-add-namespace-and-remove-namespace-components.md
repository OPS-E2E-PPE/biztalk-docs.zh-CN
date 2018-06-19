---
title: ESB 添加 Namespace 和删除 Namespace 组件 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 21df1b21-b73c-4e31-a234-49a1a6b53cc7
caps.latest.revision: 2
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 2bcbe519cfd8c6796569da4de87f59fa6a16d8a8
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22296245"
---
# <a name="the-esb-add-namespace-and-remove-namespace-components"></a>ESB 添加 Namespace 和删除 Namespace 组件
许多公司已在时间仍已新兴标准，文档共享已不常见的 XML 技术的早期采用者。 因此，它们未不严格强制包括唯一的根命名空间，这通常这种情况今天的要求。  
  
 但是，Microsoft BizTalk Server 执行文档标识基于的根节点命名空间和根节点名称的组合，因此根节点没有命名空间的文档难以正确标识如果多个不同的文档类型使用的相同的根节点名称。  
  
 添加 Namespace 和删除 Namespace 组件通过使其能够在到达时向文档中添加命名空间以及能够从文档中删除命名空间，然后将他们传送解决此问题。 因此，文档可以位于默认命名空间中 （或共有多种不同的文档类型的命名空间中） 时发送和接收但位于暂时性唯一的根命名空间中的 ESB 和 BizTalk 中的处理过程。  
  
 组件也是有用的集成，而不是 XML 架构定义中使用文档类型定义 (DTD) 或使用不能创建包含的根命名空间的文档的旧 XML 分析器的旧系统时。  
  
## <a name="installation"></a>安装  
 自动安装 ESB 核心安装**添加 Namespace**和**删除 Namespace** BizTalk Server 管道组件文件夹中的组件。  
  
## <a name="how-it-works"></a>它是如何工作  
 添加 Namespace 组件将指定的命名空间添加到 XML 文档。 组件可以将单个命名空间添加到文档。 在已有的根节点命名空间的文档中使用添加 Namespace 组件不受支持的方案，因为单个唯一的命名空间是所有所需。  
  
 组件是不识别命名空间，并且不会保留的任何命名空间值。 但是，添加 Namespace 组件将请求的消息的现有命名空间中的命名空间进行比较，并只是返回到管道原始消息，如果它们匹配。  
  
 开发人员将添加 Namespace 组件包括在接收管道或发送管道，并设置适当的属性。 在运行时执行以下验证：  
  
-   **Xpath**属性或**NamespaceBase**属性必须包含一个值。  
  
-   **分隔符**属性只能包含有效字符 (如 **/** 或 **\\** ) 或空字符串。  
  
-   **NamespacePrefix**属性值不能是保留的值之一 (**ns0**到**ns6**) 并且必须是字母数字。  
  
 利用这些规则的任何变体导致要引发运行时异常时，挂起消息的组件 (标记为**挂起 – 可恢复**)，并写入 Windows 应用程序事件日志中的条目。  
  
 删除 Namespace 组件从 XML 文档中移除所有的根命名空间。 该组件，可移除单个文档的命名空间的数量受可用于在处理过程中保存当前节点的物理内存的约束。 但是，该组件使用标准的 BizTalk Server 2009 管道消息流式处理进程，并且将仅在文档中的当前节点加载到内存而不是加载整个文档。  
  
 删除 Namespace 组件还重新会编码到指定的编码的文档 (**ascii、 unicode/utf16**或**utf8**)，并可以删除字节顺序标记 (BOM) 从开始处流，如果必填。  
  
## <a name="using-the-add-namespace-and-remove-namespace-components"></a>使用添加 Namespace 和删除 Namespace 组件  
 在任何以下情况下，开发人员可以使用添加 Namespace 组件：  
  
-   入站的消息具有没有根命名空间。  
  
-   入站的消息使用元素数据或属性数据来描述消息类型。  
  
-   描述消息类型的数据将一致，可使用 XPath 查询。  
  
 添加 Namespace 和删除 Namespace 组件可以驻留在任何阶段接收管道或发送管道。 你可以链接组件必要情况下，如就像使用跟添加 Namespace 组件删除 Namespace 组件来更改文档的根命名空间的实例。  
  
 如果你有多个接收需要的这些组件使用的位置，你可以创建单个管道，并使用 BizTalk Server 组件配置设置的发送每个实例的组件属性，或接收管道"每个实例"。 使用 BizTalk Server 2009，您可以设置属性管道为每个实例运行，这意味着，你可以重用单个管道，在多个接收位置，并且可能有每个实例的不同的组件属性。 这是运行时设置，使管理员能够进行无需更改代码或重新部署中使用 BizTalk Server 管理控制台的更改。  
  
## <a name="component-properties"></a>组件属性  
 添加 Namespace 组件公开五个公共属性：  
  
-   **NamespacePrefix**。 此为前缀的命名空间，之间插入**xmlns:** 部分，并在以下等号 （=）。 若要避免与标准 BizTalk 架构命名空间前缀的冲突，应避免使用值**ns0**通过**ns9**。  
  
-   **NamespaceBase**。 这是将前缀中的值生成的结果的命名空间的静态部分**分隔符**和**Xpath**属性。  
  
-   **ExtractionNodeXPath**。 这是可解析为包含你想要的命名空间的生成部分使用的元素或属性值的文档中的单个元素的 XPath 语句。  
  
-   **Xpath**。 这是一种管道 (**&#124;** ) 分隔的 XPath 查询用于提取每个组合到一起以形成命名空间的组件列表。  
  
-   **分隔符**。 这是要使用的命名空间段之间的分隔符。 最常用的值为正斜杠 ( **/**  )，但如果需要，也可以是一个空字符串。  
  
> [!NOTE]
>  所有的 XML 节点，如元素和属性名称区分大小写。  
  
 删除 Namespace 组件公开两个公共属性：  
  
-   **编码**。 这是输出消息，下列值之一的编码： **ascii、 unicode/utf16**或**utf8**。  
  
-   **RemoveByteOrderMark**。 这是布尔值属性，该值指示组件是否应删除的字节顺序标记 (通常**0xEFBB、 0xBFFFFE，** 或**0xFEFF**) 从 XML 文档流的开始位置。  
  
 有关如何使用这些组件的示例，请参阅[安装和运行 Namespace 组件示例](../esb-toolkit/installing-and-running-the-namespace-component-sample.md)。