---
title: 确保适配器安全的最佳做法 |Microsoft Docs
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
ms.openlocfilehash: ea93206c296df5c1930e699500aeba8fda253b75
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65358152"
---
# <a name="best-practices-for-securing-adapters"></a>确保适配器安全的最佳实践
本主题提供了适配器安全性的最佳做法的列表。  
  
 **在您的计算机; 上未安装不受信任的适配器仅使用经认证的适配器开发合作伙伴。**  
  
 **在默认适配器架构中存储敏感的客户数据。**  
  
 只在部署适配器之后，应配置用户名和密码信息。 这可确保信息获取存储在 SSO 数据库。 有关 SSO 数据库的详细信息，请参阅[使用 SSO](../core/using-sso.md)。  
  
 **授予用于提取和存放文件使用的文件和 EDI 适配器的共享文件夹 （接收文件夹和发送文件夹） 上的以下权限：**  
  
- **接收文件夹**  
  
   文件适配器的接收文件夹上的接收位置进行配置。 可在接收处理程序配置 EDI 适配器的接收文件夹。 在文件系统级别上，提取该文件的 BizTalk 主机服务帐户应具有以下权限：  
  
  - 列出文件夹 / 读取数据  
  
  - 删除子文件夹和文件  
  
    如果接收文件夹位于网络共享上，必须在文件共享级别上授予以下权限：  
  
  - 提取该文件的 BizTalk 主机服务帐户必须具有完全控制权限。  
  
  - [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理员必须具有用于故障排除的完全控制权限。  
  
  - 外部用户或程序文件放到此位置必须具有写入权限。  
  
- **发送文件夹**  
  
   发送文件夹中的文件和 EDI 适配器的发送端口上进行配置。  
  
  - BizTalk 主机或主机文件拖至此处的服务帐户必须具有写入权限。  
  
  - [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理员必须具有完全控制权限。  
  
  - 外部用户或提取文件的程序必须具有读取权限。  
  
  **将添加到 BTS_HOST_USERS SQL 角色运行 EDI 服务在其下的用户帐户。**  
  
  这是必需的以便你可以获取 BizTalk 资源管理器对象管理 (OM) 访问权限，而无需管理权限。 若要执行此操作，添加到 BTS_HOST_USERS 角色中的 BizTalk 管理数据库，BizTalkMgmtDb"EDI Subsystem Users"。  
  
  若要添加到 SQL Server 2005 上的 BTS_HOST_USERS 角色的"EDI Subsystem Users"，请完成以下步骤：  
  
1. 启动从 SQL Server Management Studio**开始，程序，Microsoft SQL Server 2008**。  
  
2. 连接到托管 BizTalk 管理数据库的 SQL 服务器。  
  
3. 展开对象资源管理器中的此服务器。  
  
4. 展开**数据库**，然后展开 BizTalk 管理数据库。  
  
5. 展开**安全**，展开**角色**，然后单击以选择**数据库角色**  
  
6. 在细节窗格中，右键单击 BTS_HOST_USERS 角色，然后单击**属性**。  
  
7. 在 BTS_HOST_USERS 对话框中，单击**外**，单击**浏览**，然后选中要将其添加的 EDI Subsystem Users 组旁边的框。  
  
    如果 EDI Subsystem Users 组不存在要添加的用户的列表中，必须向 BizTalk 管理数据库将 EDI Subsystem Users 组添加为新的数据库用户。 若要将 EDI Subsystem Users 组添加为新的数据库用户，完成 SQL Server Management Studio 中的以下步骤：  
  
   1.  展开 BizTalk 管理数据库。  
  
   2.  展开**安全**。  
  
   3.  右键单击**用户**然后单击**新用户**。  
  
   4.  单击文本框旁边的省略号 （...） 按钮**登录名**以显示**选择登录名**对话框。  
  
   5.  单击浏览按钮，输入**EDI Subsystem Users**组，然后依次**确定。** 如果出现提示**找到多个对象**对话框中，选择**EDI Subsystem Users**登录名并单击**确定**。  
  
   6.  上**数据库用户-新建**对话框中输入**EDI Subsystem Users**有关**用户名**文本框中，单击**确定**。  
  
   **添加到 EDI Subsystem Users 组运行 BizTalk 服务的用户帐户。**  
  
   请按照下列步骤将 BizTalk 服务的用户帐户添加到 EDI Subsystem Users 组。  
  
-   **如果 BizTalk Server 配置为使用域组：**  
  
    1.  登录到域中的 Windows Server 计算机。  
  
    2.  单击**启动**，单击**所有程序**，单击**管理工具**，然后单击**Active Directory 用户和计算机**。  
  
        > [!NOTE]
        >  必须具有相应的域级权限，才能修改中的对象**Active Directory 用户和计算机**接口。  
  
    3.  单击此项可展开域容器，然后单击以展开**用户**容器。  
  
    4.  双击**EDI Subsystem Users**组，以显示此组的属性。  
  
    5.  单击**成员**选项卡**EDI Subsystem Users**组对话框。  
  
    6.  单击**添加**按钮将为 BizTalk 服务的用户帐户添加到此组。  
  
    7.  单击“确定” 。  
  
-   **如果 BizTalk Server 配置为使用本地组：**  
  
    1.  登录到 BizTalk Server。  
  
    2.  单击**启动**，单击**所有程序**，单击**管理工具**，然后单击**计算机管理**。  
  
    3.  单击此项可展开**系统工具**，单击此项可展开**本地用户和组**，并单击以展开**组**。  
  
    4.  双击**EDI Subsystem Users**组，以显示此组的属性。  
  
    5.  单击**添加**按钮将 BizTalk 服务的用户帐户添加到此组。  
  
    6.  单击“确定” 。