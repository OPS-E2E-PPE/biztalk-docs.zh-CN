---
title: 修复消息 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- repairing messages
ms.assetid: 3a61b73b-5433-4249-b580-6194ccb4aebc
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f9edb8f9cc3c5db67e75ff47125e0d58891a5173
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36992038"
---
# <a name="repairing-a-message"></a>修复消息
本部分介绍如何修复未通过验证的消息。  

### <a name="to-repair-a-message"></a>若要修复消息  

1. 在 Internet Explorer 中，打开你的 MRSR 站点置于http://localhost/sites/bassite。  

2. 在主页窗口中，单击**文档**。  

3. 在文档窗口中下,**文档库**，单击 **\<*部门名称*\>**_**Repairer**.  

4. 在中\<*部门名称*\>_Repair 窗口中，单击**收件箱**。  

5. 在收件箱窗口中，指向的消息的标题，单击消息标题右侧的箭头，然后单击**在 Microsoft Office InfoPath 中编辑**。  

6. SWIFT 加速器窗格中的[!INCLUDE[btsOfficeNoVersion](../../includes/btsofficenoversion-md.md)] [!INCLUDE[btsInpathNoVersion](../../includes/btsinpathnoversion-md.md)] 2007年窗口中，确保**错误**处于选中状态。 查看任何错误中所示**分析和 XML 验证错误**， **BRE 验证错误**，并**运行时错误**框。  

7. 在[!INCLUDE[btsInpathNoVersion](../../includes/btsinpathnoversion-md.md)]窗体中，滚动到的位置错误，并更正该错误。 如果 XML 验证错误，将以红色突出显示该错误。  

   > [!NOTE]
   >  不中用红色突出显示 BRE 验证错误[!INCLUDE[btsInpathNoVersion](../../includes/btsinpathnoversion-md.md)]窗体。 BRE 验证错误的详细信息，请参阅[SWIFT 错误代码](../../adapters-and-accelerators/accelerator-swift/swift-error-codes.md)。  
   > 
   > [!NOTE]
   >  如果错误发生在伴随下拉列表的字段，你将不能以查看导致了错误的原始值。 该字段将显示"选择"，而不是原始值。 从下拉列表中选择适当的值。  

8. 若要确保将验证该消息，请单击**验证**当前角色中： 修复窗格中，然后依次**验证消息**。 验证是否显示结果窗格**该消息是否有效**。  

9. 在中[!INCLUDE[btsOfficeNoVersion](../../includes/btsofficenoversion-md.md)] [!INCLUDE[btsInpathNoVersion](../../includes/btsinpathnoversion-md.md)] 2007年窗口中，单击**提交**。  

   > [!NOTE]
   >  当您单击**提交**，[!INCLUDE[btsInpathNoVersion](../../includes/btsinpathnoversion-md.md)]对消息执行 XML 验证。 如果验证不成功，必须修复验证错误，然后继续。  

10. 在提交消息对话框中，单击**Accept**若要接受的更改提交修复后的消息，请单击**拒绝**以拒绝所做的更改，或单击**取消**取消提交和返回到该窗体中。  

    > [!NOTE]
    >  如果接受消息更改，[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]对消息执行 BRE 验证。  
    > 
    > [!NOTE]
    >  如果在修复阶段中，拒绝消息更改，则[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]将消息路由到 MessageBox，并发布到事件查看器读取的错误"无法重置到工作流中的第一个阶段。"。  

11. 如果单击了**Accept**或**拒绝**在步骤 10 中，在**数字签名向导**页上，选择你想要用于登录窗体的证书 (证书，对于创建 repairer），然后单击**下一步**。  

    > [!NOTE]
    >  若要验证数字签名的有效性，请单击**数字签名**上**工具**菜单中，单击你想要验证，，然后单击的数字签名**查看签名窗体**.  

12. 在输入的注释为数字签名向导页上，单击**完成**。  

13. 在验证窗体数字签名向导页上，验证签名的消息和您的签名正确。 单击**我已在签名之前验证此内容**，然后单击**登录**。  

14. 在验证数字签名窗口中，单击**关闭**。  

15. 在提交成功对话框中，单击**确定**。  

16. 关闭[!INCLUDE[btsInpathNoVersion](../../includes/btsinpathnoversion-md.md)]窗口。  

17. 在 MRSR 站点中，单击**文档**。 如果单击了**Accept**为接受步骤 11 中的更改，请确认*\<部门名称\>*_ReKeyVerify 文档库中包含的消息，只需修复。 如果单击了**拒绝**要拒绝步骤 11 中的更改，请验证 A4SWIFT_Outbox 文档库包含刚刚修改的消息。
