---
title: 如何管理 BizTalk Server Administrators 组 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- BizTalk Administrators group, user accounts
- BizTalk Administrators group
- user accounts, BizTalk Administrators group
- Windows Management Instrumentation (WMI), administering
- BizTalk Administrators group, privileges
- security, BizTalk Administrators group
- Administration Console [BizTalk Server], security
- Administration Console [BizTalk Server], administering
- BizTalk Administrators group, about BizTalk Administrators group
ms.assetid: 60ea689b-0b93-4fcc-b49c-6436e7be473f
caps.latest.revision: 18
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 2fe92c9c43ccef242d8c14b5f1aa48e0b1a8d852
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22254749"
---
# <a name="how-to-manage-the-biztalk-server-administrators-group"></a>如何管理 BizTalk Server Administrators 组
BizTalk Server 管理员组具有执行管理任务所需的最低权限。 您可以使用 BizTalk Server 管理控制台或 WMI 提供程序将用户添加到 BizTalk Server Administrators 组中，以便用户可以执行管理任务。 当不再需要用户执行管理任务时，也可以使用 BizTalk Server 管理控制台或 WMI 提供程序将用户从 BizTalk Server Administrators 组中删除。  
  
## <a name="prerequisites"></a>先决条件  
 此过程必须由 Administrators 组或域 Admins 组的成员来执行。  
  
### <a name="to-add-users-to-the-local-biztalk-server-administrators-group"></a>向本地 BizTalk Server Administrators 组中添加用户  
  
1.  单击**启动**，指向**管理工具**，然后单击**计算机管理**。  
  
2.  展开**系统工具**，展开**本地用户和组**，然后单击**组**文件夹。 该文件夹的内容将出现在详细信息窗格中。  
  
3.  在详细信息窗格中，单击**BizTalk Server Administrators**。  
  
4.  上**操作**菜单上，指向**所有任务**，然后单击**将添加到组**。  
  
5.  在**BizTalk 服务器管理员属性**对话框中，单击**添加**。  
  
6.  在**查找**列表中，选择你的域或计算机名称。  
  
7.  在列表中包含的用户和计算机与域或在步骤 6 中所选的计算机关联，选择要添加，请单击的用户帐户**添加**，然后单击**确定**。  
  
8.  单击**确定**关闭**BizTalk 服务器管理员属性**对话框。  
  
### <a name="to-remove-users-from-local-the-biztalk-server-administrators-group"></a>从本地 BizTalk Server Administrators 组中删除用户  
  
1.  单击**启动**，指向**管理工具**，然后单击**计算机管理**。  
  
2.  展开**系统工具**，展开**本地用户和组**，然后单击**组**文件夹。 该文件夹的内容将出现在详细信息窗格中。  
  
3.  在详细信息窗格中，单击**BizTalk Server Administrators**。  
  
4.  上**操作**菜单上，单击**属性**。  
  
5.  在**BizTalk 服务器管理员属性**对话框中，选择的用户的帐户是你想要删除，，然后单击**删除**。  
  
6.  单击 **“确定”**。  
  
### <a name="to-add-users-to-the-domain-biztalk-server-administrators-group"></a>向域 BizTalk Server Administrators 组中添加用户  
  
1.  使用域 Admins 帐户登录到与 SQL Server 数据库联接的域控制器。  
  
2.  单击**启动**，指向**所有程序**，指向**管理工具**，然后单击**Active Directory 用户和计算机**到启动**Active Directory 用户和计算机**控制台。  
  
    1.  在控制台树中，单击要向其中添加成员的 BizTalk Server Administrators 组所在的文件夹。  
  
    2.  在细节窗格中，右键单击 BizTalk Server Administrators 组中，，然后单击**属性**。  
  
    3.  上**成员**选项卡上，单击**添加**。  
  
    4.  在**输入要选择的对象名称**，键入用户的名称，然后单击**确定**。  
  
### <a name="to-remove-users-from-the-domain-biztalk-server-administrators-group"></a>从域 BizTalk Server 管理员组中删除用户  
  
1.  使用域 Admins 帐户登录到与 SQL 数据库联接的域控制器。  
  
2.  单击**启动**，指向**所有程序**，指向**管理工具**，然后单击**Active Directory 用户和计算机**到启动**Active Directory 用户和计算机**控制台。  
  
    1.  在控制台树中，单击要向其中添加成员的 BizTalk Server Administrators 组所在的文件夹。  
  
    2.  在细节窗格中，右键单击 BizTalk Server Administrators 组中，，然后单击**属性**。  
  
    3.  上**成员**选项卡上，单击你想要删除，，然后单击的成员**删除**。  
  
    4.  单击 **“确定”**。  
  
## <a name="see-also"></a>另请参阅  
 [管理 BizTalk Server 安全性](../core/managing-biztalk-server-security.md)   
 [管理主机和服务帐户](../core/managing-hosts-and-service-accounts.md)   
 [管理 Windows 组和用户帐户的最佳做法](../core/best-practices-for-managing-windows-groups-and-user-accounts.md)   
 [Windows 组和 BizTalk Server 中的用户帐户](../core/windows-groups-and-user-accounts-in-biztalk-server.md)   
 [管理 Windows 组和用户帐户](../core/managing-windows-groups-and-user-accounts.md)