---
title: "连接到 SQL Server 和 SQL 适配器一起使用 Windows 身份验证 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 45c54b2a-e056-496f-9f10-f19b6a3ca1a6
caps.latest.revision: "12"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: db7d0cbe07155d09085091d995b524b3058c0bf0
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="connect-to-sql-server-using-windows-authentication-with-the-sql-adapter"></a>连接到 SQL Server 和 SQL 适配器一起使用 Windows 身份验证
[!INCLUDE[adaptersql_md](../../includes/adaptersql-md.md)]使适配器客户端以使用 Windows 身份验证来建立与 SQL Server 的连接。 若要使用 Windows 身份验证，适配器客户端必须输入一个空的用户名和密码。 

若要连接到 SQL Server 使用 Visual Studio 中的 Windows 身份验证，请参阅[连接到使用适配器服务外接程序使用的 Visual Studio 中的 SQL Server](../../adapters-and-accelerators/adapter-sql/connect-to-sql-server-in-visual-studio-using-the-consume-adapter-service-add-in.md)。  
  
 若要启用适配器客户端使用 Windows 身份验证来连接到 SQL Server，请运行 SQL Server 的计算机上的用户启用 Windows 身份验证。  

> [!TIP]
> 如果你的 SQL Server 上未安装 SQL Server Management Studio，则可以[下载 SQL Server Management Studio (SSMS)](https://docs.microsoft.com/sql/ssms/download-sql-server-management-studio-ssms)，并将其安装。 
 
## <a name="add-the-user-in-sql-server"></a>在 SQL Server 中添加用户  
  
1.  打开 SQL Server Management Studio。 在**连接到服务器**，选择**数据库引擎**，输入你的 SQL**服务器名称**，并输入管理员凭据以连接到服务器。  

    选择“连接”。
  
2.  在**对象资源管理器**，展开 SQL Server，展开**安全**，右键单击**登录名**，然后选择**新登录名**。  
  
3.  有关**登录名**，输入中的 Windows 用户名`domain\username`格式。  

    > [!NOTE]
    >* 在与 BizTalk 一起使用此适配器，然后输入，登录名是主机实例帐户的标识。  
    >
    >* 在.NET 代码中使用此适配器，然后你输入的登录名时该进程的标识。
  
4.  选择**用户映射**（左的窗格）。 选择要与用户相关联的数据库。 典型的 BizTalk 用户应将关联到下列数据库： 

* BizTalkDTADb
* BizTalkMgmtDb
* BizTalkMsgBoxDb
* BTAHL7
* SSODB

5. 在**数据库角色成员身份**框中，选择**db_owner**所有 BizTalk 数据库。  

    > [!NOTE]
    > [服务器和 SQL Server 中的数据库角色](https://msdn.microsoft.com/library/bb669065.aspx)在角色上提供有用的信息。 
  
6.  单击“确定”保存更改。
  
 已将用户添加后，用户可以连接并对使用 SQL Server 进行身份验证[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]、 日志记录使用空白用户名和密码。  



## <a name="see-also"></a>另请参阅  
 [创建与 SQL Server 的连接](../../adapters-and-accelerators/adapter-sql/create-a-connection-to-sql-server.md)