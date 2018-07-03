---
title: SWIFT 标头和尾部架构 |Microsoft Docs
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
ms.openlocfilehash: a639199a35f2e122d221ada618aa17cc52f510ec
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36998286"
---
# <a name="swift-header-and-trailer-schemas"></a>SWIFT 标头和尾部架构
Microsoft[!INCLUDE[A4SWIFT_CurrentVersion_FirstRef](../../includes/a4swift-currentversion-firstref-md.md)]提供 SWIFT 标头和尾部架构。 A4SWIFT 已合并到各种 FIN 消息的交换架构。 如果你想要创建一个自定义的 SWIFT FIN 格式样式消息类型 （例如，N98 消息），您可以将标头和尾部架构合并到您自己的格式。  
  
 SWIFT 标头架构 (SWIFT Header.xsd) 包含以下格式：  
  
- 基本的标头  
  
- 应用程序标头 （选择的输入或输出）  
  
- 用户标头  
  
- 从开始分隔符的文本块  
  
  基本的标头包含有关消息的源的信息。 应用程序标头包含有关消息类型和消息的目标信息。 SWIFT 反汇编程序的接收管道中的消息类型的解决方法取决于相应的应用程序标头中的字段的内容。 用户标头是可选的并包含特殊的处理指令。  
  
> [!NOTE]
>  几种消息类型具有变量格式基于字段 119 用户标头中的内容。 这些是在 A4SWIFT 中的"双消息类型"。 A4SWIFT 拆装器中的字段 119 内容与一起使用的应用程序标头中使用消息类型选择相应的架构的消息实例。  
  
 *SWIFT 用户手册*，这是查找服务的 SWIFT 文档的一部分介绍了所有这些标头。  
  
 文本块的开头是"{4:"后跟回车符和换行符。 文本块的开头是必需的。  
  
 为了适应处理 （分析和验证） 包含仅 SWIFT 的交换的交换架构中的所有标头和尾部块的块 4，标记为可选。 这背离基本标头块 1 和 2 的应用程序标头块是必需的 SWIFT FIN 规范。 这使您可以使用交换架构来处理不需要标头的消息。 例如，如果接受通过 FileAct 接收的消息，批处理标头可能包含消息，以及常见的消息类型的源。  
  
 运行时架构 DLL 还包括标头架构。 A4SWIFT 安装部署的运行时架构 DLL 和 A4SWIFT 属性架构。 如果您需要使用你自己的标头进行处理，可以定义和部署自定义标头架构，并将升级消息解析为相应的属性。 如果这样做，还需要指定到 SWIFT 反汇编程序 (DASM) 的新标头。 自定义标头架构不应具有 SWIFT 标头架构的文档类型相同的 A4SWIFT 安装已部署在运行时架构 DLL 中。 请务必更改架构命名空间或根节点名称。  
  
 SWIFT 尾部架构 (**SWIFT Trailer.xsd**) 包含以下格式：  
  
- 结束的分隔符的文本块  
  
- 用户尾部 （用户和系统信息）  
  
- 系统尾部  
  
  文本块的结束分隔符是"--}"。 尾部块开头"{5:"。 尾部块的内容包括用户信息 （校验和、 消息身份验证、 专有身份验证等） 和系统信息 （延迟的消息、 消息引用，可能的重复消息等）。 添加的 SWIFT 尾部还提供第三个块中，分隔"{s:"。 *SWIFT 用户手册*，在"查找服务说明"下详细地介绍了块 5 的内容。 A4SWIFT 不会验证内容块 s。  
  
  实际 FIN 接口或 SWIFT 网络将追加尾部。 如果消息中包含尾部 A4SWIFT 接收消息时，A4SWIFT 携带消息尾部。 如果消息不包含尾部 A4SWIFT 接收消息时，A4SWIFT 不会引发错误。 作为使用标头，所有尾部项，包括块本身是可选的 A4SWIFT 中。  
  
## <a name="see-also"></a>请参阅  
 [处理架构](../../adapters-and-accelerators/accelerator-swift/working-with-schemas.md)