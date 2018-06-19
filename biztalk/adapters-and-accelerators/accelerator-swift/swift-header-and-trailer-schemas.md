---
title: SWIFT 标头和预告片架构 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- trailer schemas
- schemas, headers
- schemas, trailers
- header schemas
ms.assetid: 82cd33d4-6bbb-4124-9506-fd35b5dca8a4
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c8f3cb45e14a7c7e900fc26a4cbc8fcfb5d7b66e
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22214573"
---
# <a name="swift-header-and-trailer-schemas"></a>SWIFT 标头和预告片架构
[!INCLUDE[btsCoName](../../includes/btsconame-md.md)][!INCLUDE[A4SWIFT_CurrentVersion_FirstRef](../../includes/a4swift-currentversion-firstref-md.md)]提供 SWIFT 标头和尾的架构。 A4SWIFT 已合并这些到各种 FIN 消息的交换架构。 如果你想要创建一个自定义的 SWIFT FIN 格式样式消息类型 （例如，N98 消息），你可以将标头和尾架构合并到你自己的格式。  
  
 SWIFT 标头架构 (SWIFT Header.xsd) 包含以下格式：  
  
-   基本的标头  
  
-   应用程序标头 （选择的输入或输出）  
  
-   用户标头  
  
-   从文本块分隔符  
  
 基本的标头包含有关消息的源信息。 应用程序标头包含有关消息类型和消息的目标的信息。 SWIFT 拆装器接收管道中的消息类型的解析取决于相应的应用程序标头中的字段的内容。 用户标头是可选的并包含特殊的处理指令。  
  
> [!NOTE]
>  几种消息类型具有基于字段 119 用户标头中的内容的变量格式。 这些是 A4SWIFT 中的"双向消息类型"。 A4SWIFT 反汇编程序使用在结合字段 119 的内容应用程序标头中的消息类型选择消息实例的相应架构。  
  
 *SWIFT 用户手册*，FIN 服务中的 SWIFT 文档的一部分介绍了所有这些标头。  
  
 文本块的开头为"{4:"跟回车符和换行符。 文本块的开头是必需的。  
  
 为了容纳处理 （分析和验证） 包含仅 SWIFT 的交换的交换的架构中的所有标头和尾块的块 4，被标记为可选。 这偏离基本标头块 1 和 2 的应用程序标头块是必需的 SWIFT FIN 规范。 这使你能够使用交换架构来处理不需要标头的消息。 例如，如果接受通过 FileAct 接收的消息时，批处理标头可能包含的消息，以及常见的消息类型的源。  
  
 运行时架构 DLL 还包括标头架构。 A4SWIFT 安装部署运行时架构 DLL 和 A4SWIFT 属性架构。 如果你需要使用你自己的标头进行处理，可以定义和部署自定义标头架构，并将提升用于消息解析适当的属性。 如果这样做，你将还需要指定 SWIFT 反汇编程序 (DASM) 到新的标头。 自定义标头架构不应有和 SWIFT 标头的架构相同的文档类型安装在运行时架构 DLL 中已部署该 A4SWIFT。 请务必更改架构命名空间，和 / 或根节点名称。  
  
 SWIFT 尾部架构 (**SWIFT Trailer.xsd**) 包含以下格式：  
  
-   结束分隔符的文本块  
  
-   用户拖车安排 （用户和系统信息）  
  
-   系统拖车安排  
  
 结束分隔符的文本块是"-}"。 电影预告片块开头"{5:"。 电影预告片块的内容包括用户信息 （校验和、 消息身份验证、 专有身份验证等） 和系统信息 （延迟的消息、 消息引用、 可能的重复消息和等等）。 拖车安排添加 SWIFT 还提供分隔的第三个块"{s:"。 *SWIFT 用户手册*，在"FIN 服务说明"下详细地介绍了块 5 的内容。 A4SWIFT 不会验证内容块 s。  
  
 实际的 FIN 接口或 SWIFT 网络追加拖车安排。 如果消息包含尾部 A4SWIFT 收到消息时，A4SWIFT 会带来的尾部，并显示消息。 如果消息不包含尾部 A4SWIFT 收到消息时，A4SWIFT 不会引发错误。 作为标头，与所有预告片项，包括块本身，是可选的 A4SWIFT 中。  
  
## <a name="see-also"></a>另请参阅  
 [使用架构](../../adapters-and-accelerators/accelerator-swift/working-with-schemas.md)