---
title: 添加 A4SWIFT 用户和更新 Windows 组 |Microsoft 文档
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
ms.openlocfilehash: ce3fbf2f3b78b13205b43989c2b0c03909dec392
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22209925"
---
# <a name="adding-a4swift-users-and-updating-windows-groups"></a>添加 A4SWIFT 用户和更新 Windows 组
创建和安装适用于消息修复和新提交角色的证书之后，你必须创建[!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]用户并添加[!INCLUDE[btsWinNoVersion](../../includes/btswinnoversion-md.md)]到组的用户。  
  
 **摘要**  
  
 创建消息修复和新提交用户并添加到本地或域帐户[!INCLUDE[btsWinNoVersion](../../includes/btswinnoversion-md.md)]用户组，，如下所示：  
  
-   在[!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]管理控制台中，你需要创建任意多个用户与你消息修复和新提交进程的工作流阶段角色。 将不同的证书与每个这些用户相关联。  
  
-   使用[!INCLUDE[btsWinNoVersion](../../includes/btswinnoversion-md.md)]计算机管理实用工具，添加创建，修复，每个本地用户验证，或批准 A4SWIFT 用户到一条消息。  
  
-   使用[!INCLUDE[btsWinNoVersion](../../includes/btswinnoversion-md.md)]计算机管理实用程序添加到 BizTalk 服务 BizTalk 组服务的登录为字段中列出的本地用户[!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]用户组。  
  
    > [!NOTE]
    >  有关详细信息[!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]用户和角色，请参阅[创建部门和适用于消息修复和新提交角色](../../adapters-and-accelerators/accelerator-swift/creating-departments-and-roles-for-message-repair-and-new-submission.md)。  
  
### <a name="to-add-user-accounts-to-the-a4swift-users-group"></a>若要将用户帐户添加到 A4SWIFT 用户组  
  
1.  单击**启动**，指向**所有程序**，指向**管理工具**，然后单击**计算机管理**。  
  
2.  在**计算机管理**对话框中，在左窗格中，展开**本地用户和组**，然后单击**组**。  
  
3.  在**计算机管理**对话框中，在右窗格中，双击**A4SWIFT 用户**。  
  
4.  在**A4SWIFT 用户属性**对话框中，单击**添加**。  
  
5.  在**选择用户、 计算机或组**对话框中，在**输入要选择的对象名称**窗格中，键入创建、 修复、 验证，或批准一条消息，本地用户的名称，然后单击**确定**。  
  
6.  对于每个本地用户创建、 修复、 验证，或批准一条消息重复步骤 5。  
  
7.  在 A4SWIFT 用户属性对话框中，单击**确定**。  
  
8.  在计算机管理对话框中，在左窗格中，展开服务和应用程序，，然后单击服务。 在右窗格中，单击**BizTalk 服务 BizTalk 组**。 请注意有关的登录为列中列出的用户**BizTalk 服务 BizTalk 组**。  
  
9. 在左窗格中**计算机管理**对话框框中，展开**本地用户和组**，然后单击**组**。 双击**A4SWIFT 用户**。 确保日志作为列中列出的用户**BizTalk 服务 BizTalk 组**属于**A4SWIFT 用户**组。 否则，请添加到该用户**A4SWIFT 用户**组。  
  
10. 注销服务器，然后重新登录。