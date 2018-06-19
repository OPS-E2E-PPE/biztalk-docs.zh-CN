---
title: 保护适配器的最佳实践 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- adapters, security
- best practices, adapters
- adapters, permissions
- security, adapters
- permissions, adapters
- best practices, security
- adapters, best practices
ms.assetid: 004e1a01-b316-4eee-967f-5a806431de2b
caps.latest.revision: 25
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 86abbba06e851b9b289b29cd7fbbf01b3af292a7
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22233293"
---
# <a name="best-practices-for-securing-adapters"></a>确保适配器安全的最佳实践
本主题提供了适配器安全性最佳实践的列表。  
  
 **在你的计算机; 上未安装不受信任的适配器仅使用经认证的适配器开发合作伙伴。**  
  
 **在默认适配器架构中存储敏感的客户数据。**  
  
 应当只在部署适配器之后才配置用户名和密码信息。 这样可以确保将信息存储在 SSO 数据库中。 SSO 数据库有关的详细信息，请参阅[使用 SSO](../core/using-sso.md)。  
  
 **授予用于选取并删除使用的文件和 EDI 适配器文件的共享文件夹 （接收文件夹和发送文件夹） 上的以下权限：**  
  
-   **接收文件夹**  
  
     文件适配器的接收文件夹可在接收位置上进行配置。 EDI 适配器的接收文件夹可在接收处理程序上进行配置。 提取文件的 BizTalk 主机的服务帐户应在文件系统级别具有以下权限：  
  
    -   列出文件夹/读取数据  
  
    -   删除子文件夹和文件  
  
     如果接收文件夹位于网络共享上，则必须在文件共享级别授予以下权限：  
  
    -   提取文件的 BizTalk 主机的服务帐户必须具有“完全控制”权限。  
  
    -   [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理员必须具有“完全控制”权限，才能进行故障排除。  
  
    -   将文件存放到此位置的外部用户或程序必须具有写权限。  
  
-   **发送文件夹**  
  
     文件适配器和 EDI 适配器的发送文件夹可在发送端口上进行配置。  
  
    -   BizTalk 主机或在将文件存放在此处的主机的服务帐户必须具有写权限。  
  
    -   [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理员必须具有“完全控制”权限。  
  
    -   提取文件的外部用户或程序必须具有读权限。  
  
 **添加在其下 EDI 服务运行到 BTS_HOST_USERS SQL 角色的用户帐户。**  
  
 此项为必需操作，以便可在不具有管理权限的情况下获取 BizTalk 浏览器对象管理 (OM) 访问权限。 若要执行此操作，请将“EDI Subsystem Users”添加到 BizTalk 管理数据库 (BizTalkMgmtDb) 的 BTS_HOST_USERS 角色中。  
  
 若要在 SQL Server 2005 上将“EDI Subsystem Users”添加到 BTS_HOST_USERS 角色中，请完成以下步骤：  
  
1.  启动 SQL Server Management Studio 从**开始时，程序，Microsoft SQL Server 2008**。  
  
2.  连接到 BizTalk 管理数据库所在的 SQL Server。  
  
3.  展开对象资源管理器中的此服务器。  
  
4.  展开**数据库**，然后展开 BizTalk 管理数据库。  
  
5.  展开**安全**，展开**角色**，然后单击以选择**数据库角色**  
  
6.  在细节窗格中，右键单击 BTS_HOST_USERS 角色，然后单击**属性**。  
  
7.  在 BTS_HOST_USERS 对话框中，单击**添加**，单击**浏览**，，然后检查 EDI 子系统用户组以将其添加旁边的框。  
  
     如果 EDI Subsystem Users 组没有显示在要添加的用户列表中，则必须将 EDI Subsystem Users 组作为新数据库用户添加到 BizTalk 管理数据库中。 若要将 EDI 子系统用户组添加为新的数据库用户，完成 SQL Server Management Studio 中的以下步骤：  
  
    1.  展开 BizTalk 管理数据库。  
  
    2.  展开**安全**。  
  
    3.  右键单击**用户**单击**新用户**。  
  
    4.  单击文本框旁边的省略号 （…） 按钮**登录名**以显示**选择登录名**对话框。  
  
    5.  单击浏览按钮，输入**EDI 子系统用户**分组，并依次**确定。** 如果系统提示提供**找到多个对象**对话框中，选择**EDI 子系统用户**登录名和单击**确定**。  
  
    6.  上**数据库用户-新**对话框中，输入**EDI 子系统用户**为**用户名**文本框中，单击**确定**。  
  
 **添加在其下 BizTalk 服务运行到 EDI 子系统 Users 组的用户帐户。**  
  
 请按照下列步骤将 BizTalk 服务的用户帐户添加到 EDI 子系统用户组。  
  
-   **如果 BizTalk Server 配置为使用域组：**  
  
    1.  登录到域中的 Windows Server 计算机。  
  
    2.  单击**启动**，单击**所有程序**，单击**管理工具**，然后单击**Active Directory 用户和计算机**。  
  
        > [!NOTE]
        >  你必须具有相应域级别权限，才能修改中的对象**Active Directory 用户和计算机**接口。  
  
    3.  单击以展开域容器并单击以展开**用户**容器。  
  
    4.  双击**EDI 子系统用户**组以显示为此组的属性。  
  
    5.  单击**成员**选项卡**EDI 子系统用户**组对话框。  
  
    6.  单击**添加**按钮将为 BizTalk 服务的用户帐户添加到此组。  
  
    7.  单击 **“确定”**。  
  
-   **如果 BizTalk Server 配置为使用本地组：**  
  
    1.  登录到 BizTalk Server。  
  
    2.  单击**启动**，单击**所有程序**，单击**管理工具**，然后单击**计算机管理**。  
  
    3.  单击以展开**系统工具**，单击以展开**本地用户和组**，并单击以展开**组**。  
  
    4.  双击**EDI 子系统用户**组以显示为此组的属性。  
  
    5.  单击**添加**按钮将 BizTalk 服务的用户帐户添加到此组。  
  
    6.  单击 **“确定”**。