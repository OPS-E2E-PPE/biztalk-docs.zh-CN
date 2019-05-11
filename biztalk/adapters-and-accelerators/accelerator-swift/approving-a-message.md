---
title: 审核消息 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- messages, approving
- approving messages
ms.assetid: e6abfef3-aab2-470e-a7a7-a6d091ffba53
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 481a0cab00152f947e17b57a92fc9cf0df84c06a
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65378867"
---
# <a name="approving-a-message"></a>审核消息
本部分描述如何批准一条消息，已修复和验证。  

### <a name="to-approve-a-message"></a>若要批准一条消息  

1. 在 Internet Explorer 中，打开你的 MRSR 站点置于 http://localhost/sites/bassite 。  

2. 在主页窗口中，单击**文档**。  

3. 在文档窗口中下,**文档库**，单击 **\<*部门名称*\>_Approver**。  

4. 在中\<部门名称\>_Approver 窗口中，单击**收件箱**。  

5. 在收件箱窗口中，指向的消息的标题，单击消息标题右侧的箭头，然后单击**在 Microsoft Office InfoPath 中编辑**。  

6. SWIFT 加速器窗格中的[!INCLUDE[btsOfficeNoVersion](../../includes/btsofficenoversion-md.md)] [!INCLUDE[btsInpathNoVersion](../../includes/btsinpathnoversion-md.md)] 2007年窗口中，单击**错误**。 查看任何错误中所示**分析和 XML 验证错误**框中， **BRE 验证错误**框中，并且**运行时错误**框。  

7. 在[!INCLUDE[btsInpathNoVersion](../../includes/btsinpathnoversion-md.md)]窗体中，滚动到错误的位置并验证是否已更正错误。 可以看到原始错误已通过单击**错误**当前角色中：批准窗格中，并在其中一个错误窗格中查看该错误。 此外可以通过单击比较消息的修复和已修复版本**消息的详细信息**当前角色中：批准窗格。  

8. 若要确保将验证该消息，请单击**验证**当前角色中：批准窗格中，然后依次**验证消息**。 验证结果窗格中显示消息**该消息是否有效**。  

9. 如果已对该文档中的更改批准[!INCLUDE[btsOfficeNoVersion](../../includes/btsofficenoversion-md.md)] [!INCLUDE[btsInpathNoVersion](../../includes/btsinpathnoversion-md.md)] 2007年窗口中，单击**提交**。  

   > [!NOTE]
   >  当您单击**提交**，[!INCLUDE[btsInpathNoVersion](../../includes/btsinpathnoversion-md.md)]对消息执行 XML 验证。 如果验证不成功，必须修复验证错误，然后继续。  

10. 在提交消息对话框中，单击**接受**提交已批准的消息与接受更改。 单击**拒绝**可以将消息提交已拒绝的更改。 单击**取消**取消提交并返回到该表单。  

    > [!NOTE]
    >  如果接受消息更改，[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]对消息执行 BRE 验证。  
    > 
    > [!NOTE]
    >  如果拒绝消息更改，则[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]该消息返回给工作流的第一个阶段 （创建或修复） 并将重置修复工作流。  

11. 在用于选择证书来签署该窗体数字签名向导页上，选择你想要使用表单 （为审批者创建的证书） 进行签名的证书。 单击**查看证书**如果你想要验证是否使用正确的签名。 单击“下一步” 。  

    > [!NOTE]
    >  若要验证数字签名的有效性，请单击**数字签名**上**工具**菜单中，单击你想要验证，，然后单击的数字签名**查看签名窗体**. 您还可以查看哪些角色已签名的表单之前 （窗体进行签名者必须一次每个工作流） 通过单击**数字签名**上**工具**菜单。 如果需要添加此角色的另一个签名，此，请在[!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]管理控制台。  

12. 在用于输入注释数字签名向导页上，单击**完成**。  

13. 在验证窗体数字签名向导页上，验证签名的消息正确。 单击**查看证书**如果你想要验证是否使用正确的签名。 单击**我已在签名之前验证此内容**，然后单击**登录**。  

14. 在验证数字签名窗口中，单击**关闭**。  

15. 在提交成功对话框中，单击**确定**。  

16. 关闭[!INCLUDE[btsInpathNoVersion](../../includes/btsinpathnoversion-md.md)]窗口。  

17. 在[!INCLUDE[btsWinNoVersion](../../includes/btswinnoversion-md.md)]资源管理器中，打开设置以接收所发送的消息的文件夹。 验证该文件夹包含已批准的消息。 若要验证已修复消息的文本编辑器中打开的邮件。
