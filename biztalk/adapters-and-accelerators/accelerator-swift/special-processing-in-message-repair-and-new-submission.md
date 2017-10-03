---
title: "特殊处理消息修复和新的提交中 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- repairing messages, rekey verification
- repairing messages, process flow
- rekey verification
- repairing messages
- messages, templates
- messages, rekey verification
- BIC fields
- templates, messages
- BIC-12 data
- messages, process flow
- BIC-11 data
ms.assetid: 0ab729e3-4b67-47d3-84c9-f016318a4c41
caps.latest.revision: "4"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 1d77d518b080fd84b874c9bb79dedd5173d0a78b
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="special-processing-in-message-repair-and-new-submission"></a>在消息修复和新提交的特殊处理
[!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]消息修复和新功能使客户能够开发企业实现的提交。 功能支持以下特殊处理：  
  
-   重新生成密钥验证  
  
-   部门特定工作流支持 (有关详细信息，请参阅[修复消息和提交新消息](../../adapters-and-accelerators/accelerator-swift/repairing-messages-and-submitting-new-messages.md)。)  
  
-   输入作为 BIC 11 BIC 12 数据  
  
-   BIC 字段的项作为一个字符串  
  
-   修复并重新提交的分析失败 (有关详细信息，请参阅[修复未分析消息](../../adapters-and-accelerators/accelerator-swift/repairing-unparsed-messages.md)。)  
  
-   正在保存修复，通过使用保存命令  
  
-   通过使用另存为命令创建新模板  
  
## <a name="rekey-verification"></a>重新生成密钥验证  
 对于许多金融机构中，检查工作的主要方式是供第二个用户事务的最重要的字段重新生成密钥。 此操作将验证的第二个用户具有读取和理解，这些字段中的数据。 [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]提供的消息修复或在其中创建了此功能[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]。  
  
 如果重新生成密钥步骤是必需的[!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]出要向用户显示的形式将重新生成的字段的空白。 [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]仍在任务窗格中，显示原始消息的内容，因此在输入数据时，验证程序可以使用这些内容。 验证程序不应更改在消息中，其他字段，因为这可能允许更改而无需验证。 相反，验证程序应拒绝消息修复，如果需要进行其他更改。  
  
 在重新生成密钥步骤中，完成之后[!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]使用修复结果重新加密操作的结果进行比较。 它只能在具有已重新生成，基于按字段的字段上执行这种比较。 如果基于字符的字符不一致的两个版本，则必须再次修复消息。 [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]指示存在密钥验证不匹配，并将错误添加到消息的错误集合部分。 输入由验证程序的数据不会保存。  
  
 下的 MRSR 文件夹中 MrsrXpathConfig.xml 文件中指定要将重新生成的字段[!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]文件夹。 此文件包含要将重新生成的字段和字段到 xpath 组成的名称/值对。 你可以自定义此文件可更改的字段将为每个消息重新生成。 要将重新生成的字段通常是那些表示最重要日期与消息内容，关联的事务，并在事务量的货币。  
  
 在消息修复和新提交的所有验证步骤都涉及重新生成密钥验证。 使其不可见验证通过审批者执行。  
  
## <a name="entry-of-bic-12-data-as-bic-11"></a>输入作为 BIC 11 BIC 12 数据  
 [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]还包含一条消息的逻辑终端 (LT) 地址中的其他字符的需求。 LT 地址包含仅有 11 个字符的数据，但 SWIFT 联盟访问 (SAA) 需要 LT 字段，才能在位置 9 中具有"X"。 向 SAA 指示此额外的字符，它应选择正确的 LT.  
  
 LT 地址用于通过 FIN 网络进行传输的消息。 可在两个字段的 SWIFTBound 消息 （基本标头块的 LT 地址字段） 或输入的应用程序标头块中的目标地址字段中包含和 SWIFT 的消息的两个字段中 (基本标头块的 LT 地址字段或LT 地址的消息输入参考中的输出应用程序标头块）。  
  
 在创建或修复一条消息，或重新字段验证的一部分生成密钥时，用户必须输入仅 11 个字符。 即使修复或重新生成密钥 LT 具有 12 个字符，则用户必须输入仅 11 个字符。 [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]插入第 12 个字符，并验证 12 个字符字段。 [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]验证针对 BIC 加上数据库中的地址的 11 个字符 LT 地址。  
  
## <a name="entry-of-bic-fields-as-one-string"></a>作为一个字符串 BIC 字段的项  
 你可以输入有关 BIC 成单个字段[!INCLUDE[btsInpathNoVersion](../../includes/btsinpathnoversion-md.md)]窗体。 BIC 包含四个子字段，其中每个有子字段[!INCLUDE[btsInpathNoVersion](../../includes/btsinpathnoversion-md.md)]窗体。 到单个字段中，输入完整的 BIC 字符串后[!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]填充每四个个子字段。  
  
## <a name="saving-repairs-in-progress"></a>正在保存修复  
 如果你需要以中断修复，你可以在其当前状态回修复收件箱来保存消息。 通过使用保存命令来检查消息中执行此操作。 你可以关闭[!INCLUDE[btsInpathNoVersion](../../includes/btsinpathnoversion-md.md)]窗体并检查消息更高版本，或其他人可以查看它继续修复。 消息的历史记录指示保存操作和第二个 repairer 就可以看到你执行修复。  
  
 你可以执行的另存为命令来将一条消息存储在用户的本地计算机上，其当前状态。 签出到另存为执行的用户消息仍会保留。 用户可以关闭[!INCLUDE[btsInpathNoVersion](../../includes/btsinpathnoversion-md.md)]窗体并返回更高版本以完成修复，但另一个用户无法签出该消息并将其修复。  
  
## <a name="creating-a-new-template"></a>创建新模板  
 在创建新消息时，你可以通过执行另存为命令创建新的模板。 这使您要打开现有模板，将数据添加到字段，然后创建新模板基于现有模板包含的其他数据。 使用新名称保存该模板并有权访问新的消息文件夹 MRSR 站点中的任何人都可以创建基于模板的新消息。 必须将模板保存到 MRSR 站点提交根据模板消息[!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]。 否则为将发生错误或你将不能打开窗体。