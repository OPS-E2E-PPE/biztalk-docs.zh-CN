---
title: "验证消息 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- messages, verifying
- verifying, messages
ms.assetid: df2b72bb-4dc1-4fdd-8f63-35fc73a12151
caps.latest.revision: "6"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 0f2fdc186e93bd182b3021a3ef8fc258cee59923
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/28/2017
---
# <a name="verifying-a-message"></a>验证消息
本部分介绍如何验证已修复的消息。  
  
### <a name="to-verify-a-message"></a>若要验证消息  
  
1.  在 Internet Explorer 中，打开 http://localhost/sites/bassite MRSR 网站。  
  
2.  在主页窗口中，单击**文档**。  
  
3.  在文档窗口中，在**文档库**，单击  **\<*部门名称*\>_Verifier * *。  
  
4.  在验证窗口中，单击**收件箱**。  
  
5.  在验证收件箱窗口中，依次指向此消息的标题，单击消息标题中，右侧的箭头，然后单击**在 Microsoft Office InfoPath 中编辑**。  
  
6.  在**文件下载**对话框中，单击**打开**。  
  
7.  中的当前角色： RekeyVerify 窗格[!INCLUDE[btsOfficeNoVersion](../../includes/btsofficenoversion-md.md)] [!INCLUDE[btsInpathNoVersion](../../includes/btsinpathnoversion-md.md)] 2007年窗口中，单击**错误**。 查看中显示任何错误**Parse 和 XML 验证错误**框和**BRE 验证错误**框。  
  
8.  在[!INCLUDE[btsInpathNoVersion](../../includes/btsinpathnoversion-md.md)]窗体中，滚动到错误的位置并验证是否已更正错误。 你可以看到原始错误为通过单击**错误**中当前的角色： RekeyVerify 窗格中，和一个错误窗格中查看该错误。 你还可以通过单击比较消息的修复和已修复版本**消息详细信息**中当前的角色： RekeyVerify 窗格。  
  
9. 若要确保将验证消息，请单击**验证**中当前的角色： RekeyVerify 窗格中，然后单击**Validate 消息**。  
  
    > [!NOTE]
    >  当前角色中的消息验证下的结果窗格中： RekeyVerify 窗格将显示你需要重新生成密钥的消息中的所有字段。 [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]将标记中使用红色星号消息窗格中的这些字段。  
  
10. 到消息窗格标有红色星号 （指示在提交之前，必须重新生成数据） 中的所有字段中重新生成数据的密钥。  
  
    > [!NOTE]
    >  可以向消息字段重新生成的密钥显示你需要的数据，通过单击**消息详细信息**中当前的角色： RekeyVerify 窗格中，并滚动到字段的原始消息。 这是 true，除非其中一个原始消息中中的重新生成密钥字段中了验证错误在这种情况下，你需要修复字段，当你重新生成密钥。  
  
11. 单击**验证**中**当前角色： RekeyVerify**窗格中，，然后单击**Validate 消息**。 验证结果窗格中显示的消息**消息无效**。  
  
12. 单击**提交**中[!INCLUDE[btsOfficeNoVersion](../../includes/btsofficenoversion-md.md)] [!INCLUDE[btsInpathNoVersion](../../includes/btsinpathnoversion-md.md)] 2007年窗口。  
  
    > [!NOTE]
    >  当你单击**提交**，[!INCLUDE[btsInpathNoVersion](../../includes/btsinpathnoversion-md.md)]对消息执行 XML 验证。 如果未成功验证，则必须修复验证错误，然后继续。  
  
13. 在提交消息对话框中，单击**接受**具有接受的更改提交已验证的消息。 单击**拒绝**具有拒绝的更改提交消息。 单击**取消**若要取消提交并返回到该表单。  
  
    > [!NOTE]
    >  如果你接受消息更改，[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]对消息执行 BRE 验证。  
  
    > [!NOTE]
    >  如果您拒绝消息更改，[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]将消息返回至工作流的第一个阶段 （创建或修复） 并将重置修复工作流。  
  
14. 在用于选择要对表单进行签名的证书数字签名向导页上，选择你想要使用表单 （为验证程序创建的证书），进行签名的证书，然后单击**下一步**。  
  
    > [!NOTE]
    >  若要验证其有效性的数字签名，请单击**数字签名**上**工具**菜单上，单击你想要验证，，然后单击的数字签名**查看签名的表单**. 如果你需要添加为此角色的另一个签名，因此在执行[!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]管理控制台。  
  
15. 在用于输入注释数字签名向导页上，单击**完成**。  
  
16. 在验证窗体数字签名向导页上，验证将对进行签名的消息正确。 单击**查看证书**如果你想要验证是否正在使用正确的签名。 单击**我已在签名之前验证此内容**，然后单击**登录**。  
  
17. 在验证数字签名窗口中，单击**关闭**。  
  
18. 在提交成功对话框中，单击**确定**。  
  
19. 关闭[!INCLUDE[btsInpathNoVersion](../../includes/btsinpathnoversion-md.md)]窗口。  
  
20. 在 MRSR 站点中，单击**文档和列表**。 如果你单击**接受**接受这些更改的步骤 13 中，验证\<部门名称\>_Approve 文档库包含刚刚修改的消息。 如果您已经有打开的文档和列表窗口，请单击**刷新**上**视图**菜单。 如果你单击**拒绝**拒绝步骤 13 中的更改，请确认*\<计算机名称\>*_Outbox 文档库包含刚刚修改的消息。