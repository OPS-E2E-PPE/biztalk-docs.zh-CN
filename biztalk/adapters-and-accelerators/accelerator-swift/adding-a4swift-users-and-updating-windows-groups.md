---
title: 添加 A4SWIFT 用户和更新 Windows 组 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- user accounts, Windows groups
- Windows groups, user accounts
- user accounts, creating
- Windows groups, updating
- updating Windows groups
- A4SWIFT, creating user accounts
ms.assetid: ddc54457-6499-402c-9cc2-f7b17bbc255f
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: bb276c069a86d060c319f960e666210691b69056
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36973326"
---
# <a name="adding-a4swift-users-and-updating-windows-groups"></a>添加 A4SWIFT 用户和更新 Windows 组
创建和安装为消息修复和新提交的角色的证书后，必须创建[!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]用户，并添加[!INCLUDE[btsWinNoVersion](../../includes/btswinnoversion-md.md)]用户到组。  
  
 **摘要**  
  
 创建消息修复和新提交用户并添加到本地或域帐户[!INCLUDE[btsWinNoVersion](../../includes/btswinnoversion-md.md)]用户组，请按如下所示：  
  
- 在[!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]管理控制台中，需要创建消息修复和新提交过程的工作流阶段中有角色尽可能多的用户。 将不同的证书与每个这些用户相关联。  
  
- 使用[!INCLUDE[btsWinNoVersion](../../includes/btswinnoversion-md.md)]计算机管理实用程序，添加每个本地用户都创建，修复，验证，或审核到 A4SWIFT 用户消息。  
  
- 使用[!INCLUDE[btsWinNoVersion](../../includes/btswinnoversion-md.md)]计算机管理实用程序添加到 BizTalk 服务 BizTalk 组服务的登录方式字段中列出的本地用户[!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]用户组。  
  
  > [!NOTE]
  >  有关详细信息[!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]用户和角色，请参阅[创建部门和角色用于消息修复和新提交](../../adapters-and-accelerators/accelerator-swift/creating-departments-and-roles-for-message-repair-and-new-submission.md)。  
  
### <a name="to-add-user-accounts-to-the-a4swift-users-group"></a>若要将用户帐户添加到 A4SWIFT 用户组  
  
1.  单击**启动**，依次指向**所有程序**，指向**管理工具**，然后单击**计算机管理**。  
  
2.  在中**计算机管理**对话框中，在左窗格中，展开**本地用户和组**，然后单击**组**。  
  
3.  在中**计算机管理**对话框中，在右窗格中，双击**A4SWIFT 用户**。  
  
4.  在中**A4SWIFT 用户属性**对话框中，单击**添加**。  
  
5.  在中**选择用户、 计算机或组**对话框中**输入要选择的对象名称**窗格中，键入创建、 修复、 验证，或批准一条消息的本地用户的名称，然后单击**确定**。  
  
6.  重复步骤 5 为每个本地用户创建、 修复、 验证，或审核消息。  
  
7.  在 A4SWIFT 用户属性对话框中，单击**确定**。  
  
8.  在计算机管理对话框中的的左窗格中，展开服务和应用程序，，然后单击服务。 在右窗格中，单击**BizTalk 服务 BizTalk 组**。 请注意日志为列中列出的用户**BizTalk 服务 BizTalk 组**。  
  
9. 在左窗格中**计算机管理**对话框框中，展开**本地用户和组**，然后单击**组**。 双击**A4SWIFT 用户**。 确保日志作为列中列出的用户**BizTalk 服务 BizTalk 组**属于**A4SWIFT 用户**组。 如果没有，请将添加到该用户**A4SWIFT 用户**组。  
  
10. 注销服务器，然后重新登录。