---
title: "使用 InfoPath 窗体来修复消息或提交新消息 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- creating, messages
- InfoPath forms, verifying messages
- submitting, messages
- InfoPath forms, repairing messages
- Bank Identifier Code (BIC)
- messages, submitting
- messages, repairing
- unparsed messages
- repairing messages, unparsed messages
- messages, unparsed messages
- messages, modifying
- messages, InfoPath forms
- modifying, messages
- messages, approving
- repairing messages, InfoPath forms
- messages, creating
- approving messages
- messages, verifying
- verifying, messages
ms.assetid: fb1a885f-fb01-42be-88bc-f68715f689f7
caps.latest.revision: "7"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f89959b1900ce03717f2bb28efda7651c5008e7c
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="using-an-infopath-form-to-repair-a-message-or-submit-a-new-message"></a>使用 InfoPath 窗体来修复消息或提交新消息
若要修复、 验证、 批准，或创建一条消息，在工作[!INCLUDE[btsInpathNoVersion](../../includes/btsinpathnoversion-md.md)]内打开的窗体[!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]MRSR Web 站点。 MRSR 站点包含[!INCLUDE[btsInpathNoVersion](../../includes/btsinpathnoversion-md.md)]窗体中的为每种消息类型和[!INCLUDE[btsInpathNoVersion](../../includes/btsinpathnoversion-md.md)]未分析的消息的窗体。 消息修复和新的提交将需要修复、 验证或审批的消息发送到相应的 MRSR 文档库，你可以打开它。  
  
 当在 MRSR 文档库中，打开邮件[!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]显示[!INCLUDE[btsInpathNoVersion](../../includes/btsinpathnoversion-md.md)]填充的消息数据的窗体。 执行内部操作[!INCLUDE[btsInpathNoVersion](../../includes/btsinpathnoversion-md.md)]窗体中，可用于处理在标记的字段，从下拉列表中 （如果适用），选择值并查看字段是必需还是可选的数据。 [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]确保消息修复和新的提交过程是安全的通过提交的要求的域帐户和使用证书的签名。  
  
 若要执行的操作中消息[!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]MRSR 站点，必须部署[!INCLUDE[btsInpathNoVersion](../../includes/btsinpathnoversion-md.md)]窗体中的为该消息类型。 这将加载[!INCLUDE[btsInpathNoVersion](../../includes/btsinpathnoversion-md.md)]消息到模板文档库所需的窗体。  
  
## <a name="repairing-a-message"></a>修复消息  
 若要修复、 验证、 批准，或创建一条消息，在从 MRSR SharePoint 站点内打开的 InfoPath 窗体中工作。 要修复的消息会被发布 MRSR 站点中。 消息修复和新的提交将需要修复、 验证或审批的消息发送到相应 MRSR 站点文档库，你可以打开它。  
  
 在 MRSR 站点文档库中打开一条消息时，A4SWIFT 显示填充的消息数据的 InfoPath 窗体。 执行内部 InfoPath 窗体，可用于处理在标记的字段，从下拉列表中 （如果适用），选择值并查看字段是必需还是可选的数据的操作。 A4SWIFT 可确保在消息修复和新的提交过程是安全的通过提交的要求的域帐户和使用证书的签名。  
  
 若要执行 MRSR 站点上一条消息的操作，你必须部署该消息类型的 InfoPath 窗体。 这将加载到模板文档库中消息所需的 InfoPath 窗体。  
  
## <a name="verifying-a-message"></a>验证消息  
 修复工作流可以包括验证阶段。 在此阶段，repairer 已修复了一条消息后, 一个验证程序验证消息中的修复正确。 若要执行此操作，你可以打开中的消息[!INCLUDE[btsInpathNoVersion](../../includes/btsinpathnoversion-md.md)]从窗体\<部门名称 > _RekeyVerify 文档库中你 MRSR 的站点，并验证到消息所做的修复是否正确。 你必须还重新生成密钥数据到需要重新生成密钥的某些字段。 所有的验证阶段需要重新生成密钥，尽管你可以自定义的字段 （如果有的话） 都需要将重新生成。 有关重新生成密钥验证的详细信息，请参阅[消息修复和新的提交中的特殊处理](../../adapters-and-accelerators/accelerator-swift/special-processing-in-message-repair-and-new-submission.md)。  
  
 包含所有可能的阶段的工作流包括一个或多个验证阶段。 但是，工作流不必包括验证阶段。  
  
## <a name="approving-a-message"></a>批准一条消息  
 修复工作流可以包括的批准阶段。 在此阶段中，验证程序已验证到一条消息或在新消息中，数据修复后审批者直观地验证消息中的修复正确。 请注意批准阶段包含 visual 验证时，将验证阶段包含的重新生成密钥验证。  
  
## <a name="accepting-or-rejecting-the-changes-to-a-message"></a>接受或拒绝对一条消息的更改  
 在完成一个阶段之后, 创建者、 repairer、 验证程序或审批者可以可以接受更改、 取消所做的更改，或拒绝所做的更改。 如果提交成功，则接受将该消息移动到下一个阶段。 拒绝拒绝的更改将提交消息。 取消将取消提交过程中，并且消息保留在其当前阶段。  
  
 如果您拒绝中验证的消息或批准阶段，[!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]将消息返回到为该工作流定义的第一个阶段 （创建或修复）。 工作流重置，因此任何 repairer 可以修复消息。 如果工作流的第一个阶段会拒绝该消息，修复业务流程会将消息发布到 MessageBox 用适当的提升属性。 你可以编写自定义的处理程序，来处理这些消息。 有关详细信息，请参阅[为拒绝的消息创建自定义处理程序](../../adapters-and-accelerators/accelerator-swift/creating-a-custom-handler-for-rejected-messages.md)。  
  
 如果在创建或修复阶段中，拒绝消息[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]挂起消息，并且你将收到错误消息:"无法重置到工作流中的第一个阶段。"  
  
## <a name="repairing-an-unparsed-message"></a>修复未分析的消息  
 如果由于分析错误，导致失败的消息[!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]将消息路由到 MRSR 站点中的未分析的文档库。 与未通过验证，当你双击消息，消息[!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]显示[!INCLUDE[btsInpathNoVersion](../../includes/btsinpathnoversion-md.md)]填充的消息数据的窗体。 修复从窗体中的消息。 当您提交消息，[!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]直接向发件箱，而不验证或审批发送消息。 有关详细信息，请参阅[修复未分析消息](../../adapters-and-accelerators/accelerator-swift/repairing-unparsed-messages.md)。  
  
## <a name="creating-and-submitting-a-new-message"></a>创建和提交新消息  
 你可以创建新的消息中[!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]MRSR 站点显示新消息窗体、 输入数据，并将其提交。 有关详细信息，请参阅[创建和提交新消息](../../adapters-and-accelerators/accelerator-swift/creating-and-submitting-a-new-message.md)。  
  
 若要创建新的消息，你必须部署该消息类型的新邮件窗体。 这将加载到的文档库中创建以包含新消息窗体消息所需的 XML 格式。  
  
 当从默认新消息窗体中创建一条消息时，字段均不填充，需将所有字段中输入数据。 你可以预先窗体中的字段填充，打开消息、 输入数据，然后运行保存的与从 MRSR 站点中的文件菜单命令。 你可以为提供[!INCLUDE[btsInpathNoVersion](../../includes/btsinpathnoversion-md.md)]构成不同的名称，并且将其保存到不同的文档库。  
  
## <a name="looking-up-a-bic"></a>查找 BIC  
 中工作时[!INCLUDE[btsInpathNoVersion](../../includes/btsinpathnoversion-md.md)]窗体中[!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]MRSR 站点，你可能需要输入 Bank 标识符代码 (BIC)。 [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]提供了可用于查找 BIC 一个实用工具。 在[!INCLUDE[btsInpathNoVersion](../../includes/btsinpathnoversion-md.md)]窗体中，在窗体的右窗格中单击 BIC 查找。 此时将显示用于基于时银行名称，或反之 BIC 搜索的窗体。 这会搜索的 Bicplus 表[!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]数据库。 Bicplus 表的详细信息，请参阅[启用验证 Bank 标识符代码的](../../adapters-and-accelerators/accelerator-swift/enabling-validation-of-bank-identifier-codes.md)和[管理 A4SWIFT 数据库中的 Bicplus 表](../../adapters-and-accelerators/accelerator-swift/managing-the-bicplus-table-in-the-a4swift-database.md)。