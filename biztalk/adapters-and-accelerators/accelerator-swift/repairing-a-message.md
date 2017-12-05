---
title: "修复消息 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: repairing messages
ms.assetid: 3a61b73b-5433-4249-b580-6194ccb4aebc
caps.latest.revision: "6"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 4489e463257f811fe2c71efea49880940751c66a
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/28/2017
---
# <a name="repairing-a-message"></a>修复消息
本部分介绍如何修复未通过验证的消息。  
  
### <a name="to-repair-a-message"></a>若要修复一条消息  
  
1.  在 Internet Explorer 中，打开 http://localhost/sites/bassite MRSR 网站。  
  
2.  在主页窗口中，单击**文档**。  
  
3.  在文档窗口中，在**文档库**，单击  **\<*部门名称*\>**_**Repairer * *。  
  
4.  在\<*部门名称*\>_Repair 窗口中，单击**收件箱**。  
  
5.  在收件箱窗口中，指向此消息的标题，单击消息标题中，右侧的箭头，然后单击**在 Microsoft Office InfoPath 中编辑**。  
  
6.  在 SWIFT 快捷键窗格中的[!INCLUDE[btsOfficeNoVersion](../../includes/btsofficenoversion-md.md)] [!INCLUDE[btsInpathNoVersion](../../includes/btsinpathnoversion-md.md)] 2007年窗口中，确保**错误**选择。 查看中显示任何错误**Parse 和 XML 验证错误**， **BRE 验证错误**，和**运行时错误**框。  
  
7.  在[!INCLUDE[btsInpathNoVersion](../../includes/btsinpathnoversion-md.md)]窗体中，滚动到的位置错误，并更正错误。 如果这是 XML 验证错误，将以红色突出显示错误。  
  
    > [!NOTE]
    >  未在中以红色突出显示 BRE 验证错误[!INCLUDE[btsInpathNoVersion](../../includes/btsinpathnoversion-md.md)]窗体。 有关 BRE 验证错误的详细信息，请参阅[SWIFT 错误代码](../../adapters-and-accelerators/accelerator-swift/swift-error-codes.md)。  
  
    > [!NOTE]
    >  如果错误发生在字段伴随下拉列表中，你将不能以查看导致错误的原始值。 该字段将显示"选择"，而不是原始值。 从下拉列表中选择适当的值。  
  
8.  若要确保将验证消息，请单击**验证**中当前的角色： 修复窗格中，并依次**Validate 消息**。 验证结果窗格中显示**消息无效**。  
  
9. 在[!INCLUDE[btsOfficeNoVersion](../../includes/btsofficenoversion-md.md)] [!INCLUDE[btsInpathNoVersion](../../includes/btsinpathnoversion-md.md)] 2007年窗口中，单击**提交**。  
  
    > [!NOTE]
    >  当你单击**提交**，[!INCLUDE[btsInpathNoVersion](../../includes/btsinpathnoversion-md.md)]对消息执行 XML 验证。 如果未成功验证，则必须修复验证错误，然后继续。  
  
10. 在提交消息对话框中，单击**接受**要接受的更改提交修复后的消息，请单击**拒绝**以拒绝所做的更改，或单击**取消**取消提交并返回到窗体中。  
  
    > [!NOTE]
    >  如果你接受消息更改，[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]对消息执行 BRE 验证。  
  
    > [!NOTE]
    >  如果您在修复阶段中，拒绝消息更改[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]将消息路由到 MessageBox，并发送到事件查看器读取错误"无法重置到工作流中的第一个阶段。"。  
  
11. 如果你单击**接受**或**拒绝**在步骤 10 中，在**数字签名向导**页上，选择你想要用于对表单进行签名的证书 (证书你为创建 repairer），然后单击**下一步**。  
  
    > [!NOTE]
    >  若要验证其有效性的数字签名，请单击**数字签名**上**工具**菜单上，单击你想要验证，，然后单击的数字签名**查看签名的表单**.  
  
12. 在用于输入注释数字签名向导页上，单击**完成**。  
  
13. 在验证窗体数字签名向导页上，验证将对进行签名的消息和签名正确。 单击**我已在签名之前验证此内容**，然后单击**登录**。  
  
14. 在验证数字签名窗口中，单击**关闭**。  
  
15. 在提交成功对话框中，单击**确定**。  
  
16. 关闭[!INCLUDE[btsInpathNoVersion](../../includes/btsinpathnoversion-md.md)]窗口。  
  
17. 在 MRSR 站点中，单击**文档**。 如果你单击**接受**若要接受步骤 11 中的更改，请确认*\<部门名称\>*_ReKeyVerify 文档库包含仅修复的消息。 如果你单击**拒绝**若要拒绝步骤 11 中的更改，请验证 A4SWIFT_Outbox 文档库包含刚刚修改的消息。