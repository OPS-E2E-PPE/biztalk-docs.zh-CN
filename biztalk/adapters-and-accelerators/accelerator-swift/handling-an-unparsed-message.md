---
title: 处理未分析的消息 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- unparsed messages
- messages, unparsed messages
ms.assetid: c6a67ff3-3295-489f-9d5f-fb35b2bf8b19
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 77478326c3f2f457c5b88b4234d8087ec512215b
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65377497"
---
# <a name="handling-an-unparsed-message"></a>处理未分析的消息
本部分介绍如何处理未分析的消息。 与不同的验证失败的消息，不能修复一条消息的[!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]无法分析。 消息修复和新提交显示消息和分析错误的性质，并使您能够打印消息或将其保存到本地文件。 然后可以发出警报将消息发送到分析失败的特定特性的实体。  

### <a name="to-handle-an-unparsed-message"></a>若要处理未分析的消息  

1. 在 Internet Explorer 中，打开你的 MRSR 站点置于 http://localhost/sites/bassite 。  

2. 在主页窗口中，单击**文档**。  

3. 在文档窗口中下,**文档库**，单击**Unparsed**。  

4. 在未分析的窗口中，单击**收件箱**。  

5. 在未分析的收件箱窗口中，点的消息，未不分析，请单击该消息，右侧的箭头，然后单击**在 Microsoft Office InfoPath 中编辑**。  

6. SWIFT 加速器在窗格中，单击**错误**。  

7. 在分析和 XML 验证错误窗格中，读取分析错误。  

8. 在未分析消息窗格中，查看消息。  

   > [!NOTE]
   >  如果你想要打印的未分析消息窗格中，该邮件**文件**菜单上，单击**打印**。  
   > 
   > [!NOTE]
   >  如果你想要在该消息保存到本地文件，在未分析消息窗格中，**文件**菜单上，单击**另存为**。 在中**另存为**对话框中**中保存**下拉列表中，转到你想要保存的文件中，然后单击文件夹**确定**。 [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)] 以 XML 格式保存该消息。  

9. 在未分析消息窗格中，进行必要的更改，然后单击**提交**。  

    > [!NOTE]
    >  无法验证已修复未分析的消息。  

10. 在提交消息对话框中，单击**Accept**若要接受的更改提交修复后的消息，请单击**拒绝**以拒绝所做的更改，或单击**取消**取消提交和返回到该窗体中。  

11. 如果单击了**Accept**或**拒绝**在步骤 11 中，在数字签名向导页上，选择你想要用于登录窗体 （为 repairer 创建证书），该证书，然后单击**下一步**。  

    > [!NOTE]
    >  若要验证数字签名的有效性，请单击**数字签名**上**工具**菜单中，单击你想要验证，，然后单击的数字签名**查看签名窗体**.  

    > [!NOTE]
    >  执行的任何角色的任何用户可以提交它们修复未分析的消息。  

12. 在用于输入注释数字签名向导页上，单击**完成**。  

13. 在验证窗体数字签名向导页上，验证签名的消息正确。 单击**查看证书**如果你想要验证是否使用正确的签名。 单击**我已在签名之前验证此内容**，然后单击**登录**。  

14. 在验证数字签名窗口中，单击**关闭**。  

15. 在提交成功对话框中，单击**确定**。  

16. 关闭[!INCLUDE[btsInpathNoVersion](../../includes/btsinpathnoversion-md.md)]窗口。
