---
title: 如何管理 BizTalk Server Administrators 组 |Microsoft Docs
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
ms.openlocfilehash: a7b22fff1ff8216021ba11038d5ee275f4dd0bb4
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65336714"
---
# <a name="how-to-manage-the-biztalk-server-administrators-group"></a>如何管理 BizTalk Server Administrators 组
BizTalk Server Administrators 组具有执行管理任务所需的最少权限。 将用户添加到 BizTalk Server Administrators 组，以便他们可以通过使用 BizTalk Server 管理控制台或 WMI 提供程序执行管理任务。 您还用户从组中删除 BizTalk Server 管理员不再需要使用 BizTalk Server 管理控制台或 WMI 提供程序执行管理任务时。  
  
## <a name="prerequisites"></a>先决条件  
 必须是要执行此过程的 Administrators 或 Domain Admins 组的成员。  
  
### <a name="to-add-users-to-the-local-biztalk-server-administrators-group"></a>若要将用户添加到本地 BizTalk Server Administrators 组  
  
1.  单击**启动**，依次指向**管理工具**，然后单击**计算机管理**。  
  
2.  展开**系统工具**，展开**本地用户和组**，然后单击**组**文件夹。 详细信息窗格中显示该文件夹的内容。  
  
3.  在详细信息窗格中，单击**BizTalk Server Administrators**。  
  
4.  上**操作**菜单，依次指向**的所有任务**，然后单击**将添加到组**。  
  
5.  在中**BizTalk Server Administrators 属性**对话框中，单击**添加**。  
  
6.  在中**查找**列表中，选择你的域或计算机名称。  
  
7.  在列表中包含的用户和计算机与域或在步骤 6 中所选的计算机关联，选择要添加，请单击用户帐户**外**，然后单击**确定**。  
  
8.  单击**确定**以关闭**BizTalk Server Administrators 属性**对话框。  
  
### <a name="to-remove-users-from-local-the-biztalk-server-administrators-group"></a>若要从本地 BizTalk Server Administrators 组中删除用户  
  
1.  单击**启动**，依次指向**管理工具**，然后单击**计算机管理**。  
  
2.  展开**系统工具**，展开**本地用户和组**，然后单击**组**文件夹。 详细信息窗格中显示该文件夹的内容。  
  
3.  在详细信息窗格中，单击**BizTalk Server Administrators**。  
  
4.  上**操作**菜单上，单击**属性**。  
  
5.  在中**BizTalk Server Administrators 属性**对话框中，选择的用户的帐户是你想要删除，并单击**删除**。  
  
6.  单击“确定” 。  
  
### <a name="to-add-users-to-the-domain-biztalk-server-administrators-group"></a>若要将用户添加到域 BizTalk Server Administrators 组  
  
1.  登录到其中的 SQL Server 数据库联接使用域管理员帐户的域控制器上。  
  
2.  单击**启动**，依次指向**所有程序**，指向**管理工具**，然后单击**Active Directory 用户和计算机**到启动**Active Directory 用户和计算机**控制台。  
  
    1.  在控制台树中，单击包含你想要将成员添加的 BizTalk Server Administrators 组的文件夹。  
  
    2.  在细节窗格中，右键单击 BizTalk Server Administrators 组，然后单击**属性**。  
  
    3.  上**成员**选项卡上，单击**添加**。  
  
    4.  在中**输入要选择的对象名称**，键入用户的名称，然后单击**确定**。  
  
### <a name="to-remove-users-from-the-domain-biztalk-server-administrators-group"></a>若要从域 BizTalk Server Administrators 组中删除用户  
  
1.  登录到域控制器的 SQL 数据库联接使用域管理员帐户。  
  
2.  单击**启动**，依次指向**所有程序**，指向**管理工具**，然后单击**Active Directory 用户和计算机**到启动**Active Directory 用户和计算机**控制台。  
  
    1.  在控制台树中，单击包含你想要将成员添加的 BizTalk Server Administrators 组的文件夹。  
  
    2.  在细节窗格中，右键单击 BizTalk Server Administrators 组，然后单击**属性**。  
  
    3.  上**成员**选项卡上，单击你想要删除，然后单击的成员**删除**。  
  
    4.  单击“确定” 。  
  
## <a name="see-also"></a>请参阅  
 [管理 BizTalk Server 安全性](../core/managing-biztalk-server-security.md)   
 [管理主机和服务帐户](../core/managing-hosts-and-service-accounts.md)   
 [管理 Windows 组和用户帐户的最佳实践](../core/best-practices-for-managing-windows-groups-and-user-accounts.md)   
 [Windows 组和 BizTalk Server 中的用户帐户](../core/windows-groups-and-user-accounts-in-biztalk-server.md)   
 [管理 Windows 组和用户帐户](../core/managing-windows-groups-and-user-accounts.md)