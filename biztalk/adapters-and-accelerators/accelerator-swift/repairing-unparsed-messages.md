---
title: "修复未分析的消息 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- unparsed messages
- repairing messages, unparsed messages
- messages, unparsed messages
ms.assetid: cc061243-3539-4407-a096-71a3feded1c5
caps.latest.revision: "4"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: de427afc854bf782f69a8c0428a874c61ffb5c4f
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="repairing-unparsed-messages"></a>修复未分析的消息
如果[!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]反汇编程序无法分析一条消息，则可以修复该消息。 因此在执行[!INCLUDE[btsInpathNoVersion](../../includes/btsinpathnoversion-md.md)]中的窗体[!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]MRSR 站点。 但是，[!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]处理该消息以不同的方式从修复后的消息 XML 或 BRE 验证失败。  
  
 如果消息或批处理失败分析，[!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]将磁带标记为[!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]_Failed = True，分析错误计数大于 0。 消息正文一直保持平面文件形式，保存的 XML 包装中。 如果修复规则设置为允许的处理分析失败，消息是发送到使用未分析的窗体的处理的未分析收件箱。  
  
 没有为所有用户和所有部门，只有一个未分析的收件箱因为[!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]可能不可以访问与消息有关的任何数据，而非原始接收位置。 因此，若要修复未分析的消息，用户必须具有修复功能，必须与所有部门中的修复角色相关联。  
  
 [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]在 Unparsed 的文本区域中显示未分析的消息[!INCLUDE[btsInpathNoVersion](../../includes/btsinpathnoversion-md.md)]窗体。 若要更正分析问题，可以输入或删除根据需要的字符。 它提交后，消息提取从 XML 包装器，并通过 SWIFT 接收管道重新提交。 如果分析成功，[!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]处理消息，就像任何其他消息。  
  
 [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]不处理具有固定通过完整修复工作流未分析的消息。 [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]将其发送未验证和未批准。 当修复后未分析的消息进行签名，然后提交它，[!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]不会调用 BRE 验证或检查部门，但直接向发送管道发送消息。 如果该管道无法处理该消息，[!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]将其发送到修复过程。  
  
 此过程，可更正来自另一个系统的格式不正确消息。 但是，在更正分析问题时应小心。 当[!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]处理未分析的消息，不会验证消息。 未分析的修复未定义为一个角色，因此，任何人都可以执行此过程。 由于未分析的消息不属于任何部门，提供对它们的访问的唯一安全是未分析的收件箱上的 Acl。 [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]也不会保留原始接收未分析的消息的位置作为消息的上下文属性。  
  
 你可以编写自定义验证要修复后未分析消息上执行。 你还可以编写订阅将修复后未分析的消息发送到原始文件管道。  
  
 对于未分析消息上工作的修复机制，你需要将 EnvelopeUnparsedMessage.xsd 架构添加到包含消息架构的程序集。 有关详细信息，请参阅[部署 A4SWIFT 架构](../../adapters-and-accelerators/accelerator-swift/deploying-a4swift-schemas.md)。