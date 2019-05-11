---
title: 使用 InfoPath 表单修复消息或提交新消息 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
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
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: d2f8c9ecb2ef1e4181cabc6b5ac35b2e13058a36
ms.sourcegitcommit: d27732e569b0897361dfaebca8352aa97bb7efe1
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/10/2019
ms.locfileid: "65529636"
---
# <a name="using-an-infopath-form-to-repair-a-message-or-submit-a-new-message"></a>使用 InfoPath 表单修复消息或提交新消息
修复、 验证、 批准或创建一条消息，您从事[!INCLUDE[btsInpathNoVersion](../../includes/btsinpathnoversion-md.md)]中打开的窗体[!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]MRSR Web 站点。 MRSR 站点包含[!INCLUDE[btsInpathNoVersion](../../includes/btsinpathnoversion-md.md)]每种消息类型的窗体和[!INCLUDE[btsInpathNoVersion](../../includes/btsinpathnoversion-md.md)]未分析的消息的窗体。 消息修复和新提交将需要修复、 验证或批准的消息发送到相应的 MRSR 文档库，您可以打开它。  
  
 当在 MRSR 文档库中，打开一条消息时[!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]显示[!INCLUDE[btsInpathNoVersion](../../includes/btsinpathnoversion-md.md)]填充消息数据的窗体。 执行内部操作[!INCLUDE[btsInpathNoVersion](../../includes/btsinpathnoversion-md.md)]窗体，使你能够操作中标记的字段中，选择值，从下拉列表中 （如果适用），以及查看一个字段是必需还是可选的数据。 [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)] 确保消息修复和新提交过程的安全性通过提交要求的域帐户和使用证书的签名。  
  
 若要执行的操作中的消息[!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]MRSR 站点，必须部署[!INCLUDE[btsInpathNoVersion](../../includes/btsinpathnoversion-md.md)]该消息类型的窗体。 这将加载[!INCLUDE[btsInpathNoVersion](../../includes/btsinpathnoversion-md.md)]消息到模板文档库所需的窗体。  
  
## <a name="repairing-a-message"></a>修复消息  
 若要修复、 验证、 审核或创建一条消息，在从 MRSR SharePoint 站点内打开的 InfoPath 窗体中工作。 要修复的消息发布 MRSR 站点中。 消息修复和新提交将需要修复、 验证或批准的消息发送到相应 MRSR 站点文档库中，您可以打开它。  
  
 当在 MRSR 站点文档库中打开一条消息时，A4SWIFT 显示 InfoPath 窗体使用的消息数据填充。 执行内部 InfoPath 窗体，使你能够操作中标记的字段中，选择值，从下拉列表中 （如果适用），以及查看一个字段是必需还是可选的数据的操作。 A4SWIFT 确保消息修复和新提交过程的安全性通过提交要求的域帐户和使用证书的签名。  
  
 若要在 MRSR 站点中执行上一条消息的操作，必须部署该消息类型的 InfoPath 窗体。 这将加载到模板文档库所需的消息在 InfoPath 窗体。  
  
## <a name="verifying-a-message"></a>验证消息  
 修复工作流可以包含验证阶段。 在此阶段，repairer 已修复一条消息后, 一个验证程序验证消息中的修复正确。 若要执行此操作，打开中的消息[!INCLUDE[btsInpathNoVersion](../../includes/btsinpathnoversion-md.md)]从窗体\<部门名称\>_RekeyVerify 文档库中 MRSR 站点，并验证对消息所做的修复是否正确。 此外必须重新数据生成到需要重新生成密钥的某些字段。 所有验证阶段都需要重新生成密钥，尽管你可以自定义的字段 （如果有） 需要进行重新生成。 有关重新生成密钥验证的详细信息，请参阅[消息修复和新提交中的特殊处理](../../adapters-and-accelerators/accelerator-swift/special-processing-in-message-repair-and-new-submission.md)。  
  
 包含所有可能的阶段的工作流包括一个或多个验证阶段。 但是，工作流不需要包括验证阶段。  
  
## <a name="approving-a-message"></a>审核消息  
 修复工作流可以包含审批阶段。 在此阶段，一个验证程序已验证的一条消息或在新消息中，数据修复后审批者直观地验证消息中的修复正确。 请注意，重新生成密钥验证的包含验证阶段时审批阶段包含 visual 验证。  
  
## <a name="accepting-or-rejecting-the-changes-to-a-message"></a>接受或拒绝对一条消息的更改  
 在完成一个阶段之后, 创建者、 repairer、 验证程序或审批者可以接受所做的更改、 取消所做的更改，或拒绝所做的更改。 如果提交成功，则接受将消息移到下一个阶段。 拒绝将消息提交已拒绝的更改。 取消取消提交过程中，并将消息保留在其当前阶段。  
  
 如果您拒绝中验证的消息或批准阶段，[!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]该消息返回给该工作流定义的第一个阶段 （创建或修复）。 工作流重置，因此任何 repairer 可以修复该消息。 如果工作流的第一个阶段会拒绝该消息，修复业务流程将消息发布到 MessageBox 中具有适当的升级属性。 您可以编写一个自定义处理程序来处理这些消息。 有关详细信息，请参阅[为被拒绝消息创建自定义处理程序](../../adapters-and-accelerators/accelerator-swift/creating-a-custom-handler-for-rejected-messages.md)。  
  
 如果在创建或修复阶段中，拒绝消息，则[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]挂起消息，并收到错误消息："无法重置到工作流中的第一个阶段。"  
  
## <a name="repairing-an-unparsed-message"></a>修复未分析的消息  
 如果由于分析错误，导致失败的消息[!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]将消息路由到 MRSR 站点中的未分析的文档库。 与双击的消息，则验证，失败的消息一样[!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]显示[!INCLUDE[btsInpathNoVersion](../../includes/btsinpathnoversion-md.md)]填充消息数据的窗体。 修复从窗体中的消息。 当您提交消息，[!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]直接向发件箱中而无需验证或批准发送消息。 有关详细信息，请参阅[修复未分析消息](../../adapters-and-accelerators/accelerator-swift/repairing-unparsed-messages.md)。  
  
## <a name="creating-and-submitting-a-new-message"></a>创建和提交新消息  
 可以创建中的新消息[!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]MRSR 站点由显示新消息窗体、 输入数据，并将其提交。 有关详细信息，请参阅[创建和提交新消息](../../adapters-and-accelerators/accelerator-swift/creating-and-submitting-a-new-message.md)。  
  
 若要创建新的消息，必须部署该消息类型的新邮件窗体。 这将加载到文档库中创建包含新消息窗体的消息所需的 XML 格式。  
  
 从默认新消息窗体中创建一条消息，没有任何字段会填充，无需在所有字段中输入数据。 您可以预窗体中的字段填充通过打开一条消息，输入数据，然后运行保存的与 MRSR 站点中的文件菜单命令。 您可以为[!INCLUDE[btsInpathNoVersion](../../includes/btsinpathnoversion-md.md)]窗体的不同名称，并将其保存到不同的文档库。  
  
## <a name="looking-up-a-bic"></a>查找 BIC  
 您从事[!INCLUDE[btsInpathNoVersion](../../includes/btsinpathnoversion-md.md)]中的窗体[!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]MRSR 站点，您可能需要输入银行标识符代码 (BIC)。 [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)] 提供了可用于查找 BIC 实用程序。 在[!INCLUDE[btsInpathNoVersion](../../includes/btsinpathnoversion-md.md)]窗体中，在窗体的右窗格中单击 BIC 查找。 这会显示用于搜索基于银行名称，或反之 BIC 的窗体。 这会搜索的 Bicplus 表[!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]数据库。 Bicplus 表的详细信息，请参阅[启用验证的银行标识代码](../../adapters-and-accelerators/accelerator-swift/enabling-validation-of-bank-identifier-codes.md)并[管理 Bicplus 表 A4SWIFT 数据库中](../../adapters-and-accelerators/accelerator-swift/managing-the-bicplus-table-in-the-a4swift-database.md)。