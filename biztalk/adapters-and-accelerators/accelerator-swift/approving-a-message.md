---
title: "批准消息 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- messages, approving
- approving messages
ms.assetid: e6abfef3-aab2-470e-a7a7-a6d091ffba53
caps.latest.revision: "5"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 0b5b77ca46be2e6a3fb4c882947eb47829f591ed
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="approving-a-message"></a>批准一条消息
本部分描述如何批准已修复且已验证的消息。  
  
### <a name="to-approve-a-message"></a>批准一条消息  
  
1.  在 Internet Explorer 中，打开 http://localhost/sites/bassite MRSR 网站。  
  
2.  在主页窗口中，单击**文档**。  
  
3.  在文档窗口中，在**文档库**，单击  **\<*部门名称*> _Approver * *。  
  
4.  在\<部门名称 > _Approver 窗口中，单击**收件箱**。  
  
5.  在收件箱窗口中，指向此消息的标题，单击消息标题中，右侧的箭头，然后单击**在 Microsoft Office InfoPath 中编辑**。  
  
6.  在 SWIFT 快捷键窗格中的[!INCLUDE[btsOfficeNoVersion](../../includes/btsofficenoversion-md.md)] [!INCLUDE[btsInpathNoVersion](../../includes/btsinpathnoversion-md.md)] 2007年窗口中，单击**错误**。 查看中显示任何错误**Parse 和 XML 验证错误**框中， **BRE 验证错误**框中，与**运行时错误**框。  
  
7.  在[!INCLUDE[btsInpathNoVersion](../../includes/btsinpathnoversion-md.md)]窗体中，滚动到错误的位置并验证是否已更正错误。 你可以看到原始错误为通过单击**错误**中当前的角色： 批准窗格中，并在其中一个错误窗格中查看该错误。 你还可以通过单击比较消息的修复和已修复版本**消息详细信息**中当前的角色： 批准窗格。  
  
8.  若要确保将验证消息，请单击**验证**中当前的角色： 批准窗格中，并依次**Validate 消息**。 验证结果窗格中显示的消息**消息无效**。  
  
9. 如果你已在中进行到文档中，更改的批准[!INCLUDE[btsOfficeNoVersion](../../includes/btsofficenoversion-md.md)] [!INCLUDE[btsInpathNoVersion](../../includes/btsinpathnoversion-md.md)] 2007年窗口中，单击**提交**。  
  
    > [!NOTE]
    >  当你单击**提交**，[!INCLUDE[btsInpathNoVersion](../../includes/btsinpathnoversion-md.md)]对消息执行 XML 验证。 如果未成功验证，则必须修复验证错误，然后继续。  
  
10. 在提交消息对话框中，单击**接受**具有接受的更改提交已批准的消息。 单击**拒绝**具有拒绝的更改提交消息。 单击**取消**若要取消提交并返回到该表单。  
  
    > [!NOTE]
    >  如果你接受消息更改，[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]对消息执行 BRE 验证。  
  
    > [!NOTE]
    >  如果您拒绝消息更改，[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]将消息返回至工作流的第一个阶段 （创建或修复） 并将重置修复工作流。  
  
11. 在用于选择要对表单进行签名的证书数字签名向导页上，选择你想要使用表单 （为审批者创建的证书） 进行签名的证书。 单击**查看证书**如果你想要验证是否正在使用正确的签名。 单击 **“下一步”**。  
  
    > [!NOTE]
    >  若要验证其有效性的数字签名，请单击**数字签名**上**工具**菜单上，单击你想要验证，，然后单击的数字签名**查看签名的表单**. 你还可以看到哪些角色具有签名的表单以前 （窗体进行签名被人猜出一次每个工作流） 通过单击**数字签名**上**工具**菜单。 如果你需要添加为此角色的另一个签名，因此在执行[!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]管理控制台。  
  
12. 在用于输入注释数字签名向导页上，单击**完成**。  
  
13. 在验证窗体数字签名向导页上，验证将对进行签名的消息正确。 单击**查看证书**如果你想要验证是否正在使用正确的签名。 单击**我已在签名之前验证此内容**，然后单击**登录**。  
  
14. 在验证数字签名窗口中，单击**关闭**。  
  
15. 在提交成功对话框中，单击**确定**。  
  
16. 关闭[!INCLUDE[btsInpathNoVersion](../../includes/btsinpathnoversion-md.md)]窗口。  
  
17. 在[!INCLUDE[btsWinNoVersion](../../includes/btswinnoversion-md.md)]资源管理器中，打开设置以接收发送的消息的文件夹。 验证该文件夹包含已批准的消息。 若要验证已修复消息的文本编辑器中打开的邮件。