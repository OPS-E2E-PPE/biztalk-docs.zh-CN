---
title: 修复未分析的消息 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- unparsed messages
- repairing messages, unparsed messages
- messages, unparsed messages
ms.assetid: cc061243-3539-4407-a096-71a3feded1c5
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: fd9e2a19e875df1d666d8a6a72ba92f39b7cc2c4
ms.sourcegitcommit: d27732e569b0897361dfaebca8352aa97bb7efe1
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/10/2019
ms.locfileid: "65530039"
---
# <a name="repairing-unparsed-messages"></a>修复未分析的消息
如果[!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]拆装器不能分析一条消息，则可以修复该消息。 此，请在[!INCLUDE[btsInpathNoVersion](../../includes/btsinpathnoversion-md.md)]中的窗体[!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]MRSR 站点。 但是，[!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]处理该消息以不同的方式从修复后的消息的 XML 或 BRE 验证失败。  
  
 如果消息或批失败分析过程中，[!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]将磁带标记为[!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]_Failed = True，分析错误计数大于 0。 消息正文将保留在平面文件窗体中，保存的 XML 包装器中。 如果修复规则设置为允许分析失败的处理，则会将消息发送到使用未分析的窗体处理的未分析的收件箱。  
  
 没有为所有用户和所有部门，只有一个未分析的收件箱因为[!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]可能不具有访问消息有关的任何数据，而不是原始接收位置。 因此，若要修复未分析的消息，用户必须修复功能并且必须与所有部门中的修复角色相关联。  
  
 [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)] Unparsed 的文本区域中显示的未分析的消息[!INCLUDE[btsInpathNoVersion](../../includes/btsinpathnoversion-md.md)]窗体。 若要更正分析问题，可能会输入或删除根据需要的字符。 提交后，将消息从 XML 包装器提取，并通过 SWIFT 接收管道重新提交。 如果分析成功，[!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]像任何其他消息处理的消息。  
  
 [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)] 不会处理未分析的消息具有固定通过完全修复工作流。 [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)] 将其发送出未验证和未批准。 当已修复未分析的消息进行签名，并提交它，[!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]不会调用 BRE 验证或检查部门，但该消息将直接发送到发送管道。 如果该管道无法处理该消息，[!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]将其发送到修复过程。  
  
 此过程使您能够更正来自另一个系统的格式不正确的消息。 但是，在更正分析问题时应小心。 当[!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]处理未分析的消息，不会验证消息。 未分析的修复未定义为一个角色，因此，任何人都可以执行此过程。 由于未分析的消息不属于任何部门，提供上对其进行访问的唯一安全是未分析的收件箱中的 Acl。 [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)] 也不会保留原始接收消息的上下文属性作为未分析消息的位置。  
  
 您可以编写自定义验证要在已修复未分析消息上执行。 此外可以编写要向原始文件管道发送已修复未分析的消息的订阅。  
  
 若要运行未分析的消息上的修复机制，需要将 EnvelopeUnparsedMessage.xsd 架构添加到包含消息架构的程序集。 有关详细信息，请参阅[部署 A4SWIFT 架构](../../adapters-and-accelerators/accelerator-swift/deploying-a4swift-schemas.md)。