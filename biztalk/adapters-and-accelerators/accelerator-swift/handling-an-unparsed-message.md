---
title: "处理未分析的消息 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- unparsed messages
- messages, unparsed messages
ms.assetid: c6a67ff3-3295-489f-9d5f-fb35b2bf8b19
caps.latest.revision: "4"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 4b7683a598169b8ece75788584e8bb9b3c7f4861
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="handling-an-unparsed-message"></a>处理未分析的消息
本部分介绍如何处理未分析的消息。 与不同的是未通过验证的消息，不能修复一条消息，[!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]无法分析。 消息修复和新提交显示消息和分析错误的性质，并允许你打印消息或将其保存到本地文件。 然后，你可以警报将邮件发送给分析失败的特定性质的实体。  
  
### <a name="to-handle-an-unparsed-message"></a>以处理未分析的消息  
  
1.  在 Internet Explorer 中，打开 http://localhost/sites/bassite MRSR 网站。  
  
2.  在主页窗口中，单击**文档**。  
  
3.  在文档窗口中，在**文档库**，单击**Unparsed**。  
  
4.  在未分析的窗口中，单击**收件箱**。  
  
5.  在未分析的收件箱窗口中，依次指向未不分析，请单击邮件中，右侧的箭头，然后单击的消息**在 Microsoft Office InfoPath 中编辑**。  
  
6.  在 SWIFT 快捷键窗格中，单击**错误**。  
  
7.  在分析和 XML 验证错误窗格中，读取了分析错误。  
  
8.  在未分析消息窗格中，查看消息。  
  
    > [!NOTE]
    >  如果你想要在上打印消息，在未分析消息窗格中，**文件**菜单上，单击**打印**。  
  
    > [!NOTE]
    >  如果你想要将消息保存到本地文件，在未分析消息窗格中，在**文件**菜单上，单击**另存为**。 在**另存为**对话框中，在**将保存在**下拉列表中，移动到你想要保存在中，该文件，然后单击的文件夹**确定**。 [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]以 XML 格式保存消息。  
  
9. 在未分析消息窗格中，进行必要的更改，然后单击**提交**。  
  
    > [!NOTE]
    >  无法验证您已修复未分析的消息。  
  
10. 在提交消息对话框中，单击**接受**要接受的更改提交修复后的消息，请单击**拒绝**以拒绝所做的更改，或单击**取消**取消提交并返回到窗体中。  
  
11. 如果你单击**接受**或**拒绝**在步骤 11 中，在数字签名向导页上，选择你想要使用表单 （为 repairer 创建的证书），进行签名的证书，然后单击**下一步**。  
  
    > [!NOTE]
    >  若要验证其有效性的数字签名，请单击**数字签名**上**工具**菜单上，单击你想要验证，，然后单击的数字签名**查看签名的表单**.  
  
    > [!NOTE]
    >  执行任何角色的任何用户可以提交它们已修复未分析的消息。  
  
12. 在用于输入注释数字签名向导页上，单击**完成**。  
  
13. 在验证窗体数字签名向导页上，验证将对进行签名的消息正确。 单击**查看证书**如果你想要验证是否正在使用正确的签名。 单击**我已在签名之前验证此内容**，然后单击**登录**。  
  
14. 在验证数字签名窗口中，单击**关闭**。  
  
15. 在提交成功对话框中，单击**确定**。  
  
16. 关闭[!INCLUDE[btsInpathNoVersion](../../includes/btsinpathnoversion-md.md)]窗口。