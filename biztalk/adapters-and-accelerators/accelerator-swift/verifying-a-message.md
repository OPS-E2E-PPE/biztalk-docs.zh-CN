---
title: 验证消息 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- messages, verifying
- verifying, messages
ms.assetid: df2b72bb-4dc1-4fdd-8f63-35fc73a12151
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 4cff0cb63f88bf2b69dc01862bf8257864c00d54
ms.sourcegitcommit: d27732e569b0897361dfaebca8352aa97bb7efe1
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/10/2019
ms.locfileid: "65529647"
---
# <a name="verifying-a-message"></a>验证消息
本部分介绍如何验证已修复的消息。  

### <a name="to-verify-a-message"></a>若要验证消息  

1. 在 Internet Explorer 中，打开你的 MRSR 站点置于 http://localhost/sites/bassite 。  

2. 在主页窗口中，单击**文档**。  

3. 在文档窗口中下,**文档库**，单击 **\<*部门名称*\>_Verifier**。  

4. 在确认窗口中，单击**收件箱**。  

5. 在验证收件箱窗口中，依次指向的消息的标题，请单击消息标题右侧的箭头，然后单击**在 Microsoft Office InfoPath 中编辑**。  

6. 在中**文件下载**对话框中，单击**打开**。  

7. 中的当前角色：RekeyVerify 窗格[!INCLUDE[btsOfficeNoVersion](../../includes/btsofficenoversion-md.md)] [!INCLUDE[btsInpathNoVersion](../../includes/btsinpathnoversion-md.md)] 2007年窗口中，单击**错误**。 查看任何错误中所示**分析和 XML 验证错误**框和**BRE 验证错误**框。  

8. 在[!INCLUDE[btsInpathNoVersion](../../includes/btsinpathnoversion-md.md)]窗体中，滚动到错误的位置并验证是否已更正错误。 可以看到原始错误已通过单击**错误**当前角色中：RekeyVerify 窗格中，并在其中一个错误窗格中查看该错误。 此外可以通过单击比较消息的修复和已修复版本**消息的详细信息**当前角色中：RekeyVerify 窗格。  

9. 若要确保将验证该消息，请单击**验证**当前角色中：RekeyVerify 窗格中，然后单击**验证消息**。  

   > [!NOTE]
   >  在当前角色中的消息验证下的结果窗格中：RekeyVerify 窗格指示需要重新生成密钥的消息中的所有字段。 [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)] 将标记中红色的星号消息窗格中的这些字段。  

10. 在消息窗格 （指示在提交之前，必须重新生成数据） 以红色星号标记中的所有字段中重新生成数据。  

    > [!NOTE]
    >  您可以通过单击所需的数据显示消息字段中重新生成密钥**消息的详细信息**当前角色中：RekeyVerify 窗格中，并滚动到该字段的原始消息。 这是 true，除非其中一个原始消息中的重新生成密钥字段中的验证错误时出现这种情况下您必须重新生成它时修复该字段。  

11. 单击**验证**中**当前角色：RekeyVerify**窗格中，，然后单击**验证消息**。 验证结果窗格中显示消息**该消息是否有效**。  

12. 单击**提交**中[!INCLUDE[btsOfficeNoVersion](../../includes/btsofficenoversion-md.md)] [!INCLUDE[btsInpathNoVersion](../../includes/btsinpathnoversion-md.md)] 2007年窗口。  

    > [!NOTE]
    >  当您单击**提交**，[!INCLUDE[btsInpathNoVersion](../../includes/btsinpathnoversion-md.md)]对消息执行 XML 验证。 如果验证不成功，必须修复验证错误，然后继续。  

13. 在提交消息对话框中，单击**接受**可以将已验证的消息提交已接受的更改。 单击**拒绝**可以将消息提交已拒绝的更改。 单击**取消**取消提交并返回到该表单。  

    > [!NOTE]
    >  如果接受消息更改，[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]对消息执行 BRE 验证。  
    > 
    > [!NOTE]
    >  如果拒绝消息更改，则[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]该消息返回给工作流的第一个阶段 （创建或修复） 并将重置修复工作流。  

14. 在用于选择证书来签署该窗体数字签名向导页上，选择你想要用于登录窗体 （为验证程序创建的证书），该证书，然后单击**下一步**。  

    > [!NOTE]
    >  若要验证数字签名的有效性，请单击**数字签名**上**工具**菜单中，单击你想要验证，，然后单击的数字签名**查看签名窗体**. 如果需要添加此角色的另一个签名，此，请在[!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]管理控制台。  

15. 在用于输入注释数字签名向导页上，单击**完成**。  

16. 在验证窗体数字签名向导页上，验证签名的消息正确。 单击**查看证书**如果你想要验证是否使用正确的签名。 单击**我已在签名之前验证此内容**，然后单击**登录**。  

17. 在验证数字签名窗口中，单击**关闭**。  

18. 在提交成功对话框中，单击**确定**。  

19. 关闭[!INCLUDE[btsInpathNoVersion](../../includes/btsinpathnoversion-md.md)]窗口。  

20. 在 MRSR 站点中，单击**文档和列表**。 如果单击了**Accept**为接受步骤 13 中的更改，请确认\<部门名称\>_Approve 文档库中包含的消息，只需修改。 如果已打开文档和列表窗口，单击**刷新**上**视图**菜单。 如果单击了**拒绝**为拒绝步骤 13 中的更改，请确认*\<计算机名称\>*_Outbox 文档库中包含的消息，只需修改。
