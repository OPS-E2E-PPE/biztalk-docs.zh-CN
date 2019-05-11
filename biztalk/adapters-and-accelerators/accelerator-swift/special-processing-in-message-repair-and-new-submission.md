---
title: 消息修复和新提交中的特殊处理 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
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
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: be98399ec9af6d3f513cfe27147d0a5b5c4a81c7
ms.sourcegitcommit: d27732e569b0897361dfaebca8352aa97bb7efe1
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/10/2019
ms.locfileid: "65530006"
---
# <a name="special-processing-in-message-repair-and-new-submission"></a>消息修复和新提交中的特殊处理
[!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]消息修复和新提交功能使客户能够开发企业实现。 功能支持以下特殊处理：  
  
-   重新生成密钥验证  
  
-   特定于部门的工作流支持 (有关详细信息，请参阅[修复消息和提交新消息](../../adapters-and-accelerators/accelerator-swift/repairing-messages-and-submitting-new-messages.md)。)  
  
-   输入作为 BIC 11 BIC 12 数据  
  
-   BIC 字段的项作为一个字符串  
  
-   修复和重新提交的分析故障 (有关详细信息，请参阅[修复未分析消息](../../adapters-and-accelerators/accelerator-swift/repairing-unparsed-messages.md)。)  
  
-   通过使用保存命令保存正在进行中的修复  
  
-   使用另存为命令创建一个新的模板  
  
## <a name="rekey-verification"></a>重新生成密钥验证  
 对于许多金融机构，检查工作的主要方式是第二个人员重新生成事务的最重要的字段。 此操作将验证第二个用户具有读取和理解，这些字段中的数据。 [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)] 提供用于消息修复或在其中创建了此功能[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]。  
  
 如果重新生成密钥步骤是必需的[!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]出要将向用户显示该窗体中重新生成的字段的空白。 [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)] 仍在任务窗格中，显示原始消息的内容，因此输入数据时，验证程序可以使用这些内容。 验证程序不应更改在消息中，其他字段，因为这可能会使更改而无需验证。 相反，验证人应拒绝消息修复，如果需要进行其他更改。  
  
 在重新生成密钥步骤之后,[!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]的修复结果重新生成密钥的结果进行比较。 它仅在具有已重新生成，在按字段的基础的字段上执行此比较。 如果基于字符的字符不同意的两个版本，必须再次修复消息。 [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)] 指示存在密钥验证不匹配，并将错误添加到消息的错误集合一部分。 输入验证器的数据不会保存。  
  
 下的 MRSR 文件夹 MrsrXpathConfig.xml 文件中指定要将重新生成的字段[!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]文件夹。 此文件包含要进行重新生成的字段和字段的 xpath 组成的名称/值对。 可以自定义此文件可以更改哪些字段将重新生成为每个消息。 要将重新生成的字段通常是那些表示与消息内容相关的最重要日期的事务，并在事务量的货币。  
  
 消息修复和新提交中的所有验证步骤涉及都到重新生成密钥验证。 在审批者执行建立直通连接，验证。  
  
## <a name="entry-of-bic-12-data-as-bic-11"></a>输入作为 BIC 11 BIC 12 数据  
 [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)] 适合于需要一条消息的逻辑终端 (LT) 地址中的其他字符。 LT 地址包含仅有 11 个字符的数据，但 SWIFT 联盟访问 (SAA) 需要 LT 字段位置 9 中具有"X"。 此额外的字符到 SAA 指示它应选择正确的 LT.  
  
 LT 地址用于查找网络上进行消息传输。 它可以包含在 SWIFTBound 消息 （基本标头块的 l T 地址字段） 或输入的应用程序标头块中的目标地址字段的两个字段，在从 SWIFT 消息的两个字段 (基本标头块的 l T 地址字段或LT 地址中的输出应用程序标头块中的消息输入引用）。  
  
 创建或修复一条消息，或重新生成该字段的密钥作为验证的一部分时，用户必须输入仅 11 个字符。 即使在修复或重新生成密钥有 12 个字符 T，用户必须输入仅 11 个字符。 [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)] 将插入的第 12 个字符，并验证 12 个字符字段。 [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)] 验证针对 BIC 加上数据库中的地址的 11 个字符 l T 地址。  
  
## <a name="entry-of-bic-fields-as-one-string"></a>BIC 字段作为一个字符串的条目  
 可以单个字段中输入 BIC[!INCLUDE[btsInpathNoVersion](../../includes/btsinpathnoversion-md.md)]窗体。 BIC 包含四个子字段，其中每个具有子字段[!INCLUDE[btsInpathNoVersion](../../includes/btsinpathnoversion-md.md)]窗体。 到单个字段中，输入完整的 BIC 字符串后[!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]填充每四个子字段。  
  
## <a name="saving-repairs-in-progress"></a>正在保存修复  
 如果需要中断修复，可以将一条消息在其当前状态保存回修复收件箱。 通过使用保存命令检查消息中执行此操作。 你可以关闭[!INCLUDE[btsInpathNoVersion](../../includes/btsinpathnoversion-md.md)]窗体并检查消息更高版本，或其他人可以查看它继续修复。 消息的历史记录指示在保存操作，并第二个 repairer 可以看到您执行了修复。  
  
 您可以执行另存为命令在用户的本地计算机上，其当前状态中存储一条消息。 这会将此签出给了另存为执行的用户的消息。 用户可以关闭[!INCLUDE[btsInpathNoVersion](../../includes/btsinpathnoversion-md.md)]窗体并返回更高版本才能完成修复，但另一个用户不能签出该消息并修复它。  
  
## <a name="creating-a-new-template"></a>创建新模板  
 在创建新消息时，可以通过执行另存为命令来创建新的模板。 这使您可以打开现有模板，将数据添加到字段，并创建新模板基于现有模板包含的其他数据。 使用新名称保存模板并有权访问 MRSR 站点中的新消息文件夹的任何人都可以创建基于模板的新消息。 必须将模板保存到 MRSR 站点将基于模板向消息提交[!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]。 否则为将发生错误，或者你将无法再打开窗体。