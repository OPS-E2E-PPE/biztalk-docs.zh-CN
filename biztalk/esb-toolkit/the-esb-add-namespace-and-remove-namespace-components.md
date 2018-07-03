---
title: ESB 添加 Namespace 和删除 Namespace 组件 |Microsoft Docs
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
ms.openlocfilehash: ef25458cdf578930f46bdb702feb283a171d1529
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36971422"
---
# <a name="the-esb-add-namespace-and-remove-namespace-components"></a>ESB 添加 Namespace 和删除 Namespace 组件
许多公司已在标准仍在不断涌现，并且文档共享尚不普遍的时间的 XML 技术的早期采用者。 因此，它们并没有严格执行包括唯一的根命名空间，这通常这种情况今天的要求。  
  
 但是，Microsoft BizTalk Server 会执行文档标识基于根节点命名空间和根节点名称的组合，因此具有根节点没有命名空间的文档很难正确识别如果多个不同的文档类型使用相同的根节点名称。  
  
 添加 Namespace 和删除 Namespace 组件，从而在接收时向文档添加命名空间并从文档中删除命名空间，它们提供之前解决此问题。 因此，文档可以位于默认命名空间中 （或多个不同的文档类型通用的命名空间中） 时发送和接收，但驻留在暂时性唯一的根命名空间内的 ESB 和 BizTalk 的处理过程。  
  
 组件也是有用的集成，而不是 XML 架构定义中使用文档类型定义 (DTD) 或使用旧无法创建包含的根命名空间的文档的 XML 分析器的旧式系统时。  
  
## <a name="installation"></a>安装  
 自动安装 ESB 核心安装**添加 Namespace**并**删除 Namespace** BizTalk Server 管道组件文件夹中的组件。  
  
## <a name="how-it-works"></a>其工作原理  
 添加 Namespace 组件将指定的命名空间添加到 XML 文档。 该组件可以向文档添加单个命名空间。 在文档已具有根节点命名空间中使用添加 Namespace 组件不受支持的方案，因为单个唯一的命名空间是所有所需。  
  
 组件不识别命名空间，不会保留任何命名空间值。 但是，添加 Namespace 组件将请求的消息的现有命名空间中的命名空间进行比较，并且只是返回到管道的原始消息，如果它们匹配。  
  
 开发人员将添加 Namespace 组件包括在接收管道或发送管道，并设置相应的属性。 在运行时执行以下验证：  
  
- **Xpath**属性或**NamespaceBase**属性必须包含值。  
  
- **分隔符**属性可以包含有效的字符 (如**/** 或**\\**) 或空字符串。  
  
- **NamespacePrefix**属性值不能为保留值之一 (**ns0**到**ns6**) 并且必须是字母数字。  
  
  利用这些规则的任何变体导致组件在运行时引发异常，挂起消息 (标记为**挂起 – 可恢复**)，并写入 Windows 应用程序事件日志中的条目。  
  
  删除 Namespace 组件从 XML 文档中删除所有根命名空间。 该组件可以从单个文档中删除的命名空间的数量受可用于在处理期间保存当前节点的物理内存。 但是，该组件使用标准 BizTalk Server 2009 管道消息流式处理进程，并且将仅在文档中的当前节点加载到内存而不是加载整个文档。  
  
  删除 Namespace 组件还重新编码到指定的编码的文档 (**ascii，unicode/utf16**或**utf8**)，并可以删除字节顺序标记 (BOM) 从一开始的流，如果必填。  
  
## <a name="using-the-add-namespace-and-remove-namespace-components"></a>使用添加 Namespace 和删除 Namespace 组件  
 开发人员可以使用任何以下情况下添加 Namespace 组件：  
  
- 入站的消息已没有根命名空间。  
  
- 入站的消息使用的数据元素或属性的数据来描述消息类型。  
  
- 描述消息类型的数据将一致，可使用 XPath 查询。  
  
  添加 Namespace 和删除 Namespace 组件可以位于任何接收管道或发送管道的阶段。 可以链接在必要情况下，此类像使用删除 Namespace 组件后面跟着添加 Namespace 组件来更改文档的根命名空间组件的实例。  
  
  如果有多个接收位置，需要使用这些组件，可以创建单个管道，并使用 BizTalk Server 组件配置来设置组件属性发送的每个实例或接收管道"每个实例"。 使用 BizTalk Server 2009，您可以设置属性在管道的每个实例基础，这意味着，您可以重用单个管道，跨多个接收位置和也许有每个实例的不同组件属性。 这是使管理员可以使用 BizTalk Server 管理控制台，而无需更改代码或重新部署的更改的运行时设置。  
  
## <a name="component-properties"></a>组件属性  
 添加 Namespace 组件公开五个公共属性：  
  
-   **NamespacePrefix**。 这是前缀的命名空间之间插入**xmlns:** 部分，在以下等号 （=）。 若要避免使用标准 BizTalk 架构命名空间前缀的冲突，应避免使用值**ns0**通过**ns9**。  
  
-   **NamespaceBase**。 这是将前缀中的值生成的结果的命名空间的静态部分**分隔符**并**Xpath**属性。  
  
-   **ExtractionNodeXPath**。 这是解析为包含你想要在命名空间的生成部分使用的元素或属性值的文档中的单个元素的 XPath 语句。  
  
-   **Xpath**。 这是一个管道 (**&#124;** ) 用来提取每个组件的组合到一起以形成命名空间的 XPath 查询的分隔的列表。  
  
-   **分隔符**。 这是要使用的命名空间段之间的分隔符。 最常见的值为正斜杠 (**/** )，但如果需要，能为空字符串。  
  
> [!NOTE]
>  所有 XML 节点，如元素和属性名称都均区分大小写。  
  
 删除 Namespace 组件公开两个公共属性：  
  
- **编码**。 这是编码输出消息，以下值之一： **ascii，unicode/utf16**或**utf8**。  
  
- **RemoveByteOrderMark**。 这是一个布尔属性，指示组件是否应删除的字节顺序标记 (通常**0xEFBB、 0xBFFFFE，** 或**0xFEFF**) 从 XML 文档流的开始位置。  
  
  有关如何使用这些组件的示例，请参阅[安装和运行 Namespace 组件示例](../esb-toolkit/installing-and-running-the-namespace-component-sample.md)。