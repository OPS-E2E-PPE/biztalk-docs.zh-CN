---
title: 连接到 SQL Server 与 SQL 适配器使用 Windows 身份验证 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 45c54b2a-e056-496f-9f10-f19b6a3ca1a6
caps.latest.revision: 12
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: fa19a836d4465b96b663dd4abc5f89500b37e338
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36973638"
---
# <a name="connect-to-sql-server-using-windows-authentication-with-the-sql-adapter"></a>连接到 SQL Server 与 SQL 适配器使用 Windows 身份验证
[!INCLUDE[adaptersql_md](../../includes/adaptersql-md.md)]使适配器客户端能够使用 Windows 身份验证建立与 SQL Server 的连接。 若要使用 Windows 身份验证，适配器客户端必须输入的空用户名和密码。 

若要连接到 SQL Server 使用 Visual Studio 中的 Windows 身份验证，请参阅[连接到 SQL Server 在 Visual Studio 中使用适配器服务外接程序使用](../../adapters-and-accelerators/adapter-sql/connect-to-sql-server-in-visual-studio-using-the-consume-adapter-service-add-in.md)。  
  
 若要启用适配器客户端使用 Windows 身份验证来连接到 SQL Server，请运行 SQL Server 的计算机上的用户启用 Windows 身份验证。  

> [!TIP]
> 如果在 SQL Server 上未安装 SQL Server Management Studio，你可以[下载 SQL Server Management Studio (SSMS)](https://docs.microsoft.com/sql/ssms/download-sql-server-management-studio-ssms)，并将其安装。 
 
## <a name="add-the-user-in-sql-server"></a>在 SQL Server 中添加用户  
  
1.  打开 SQL Server Management Studio。 在中**连接到服务器**，选择**数据库引擎**，输入 SQL**服务器名称**，并输入管理员凭据以连接到服务器。  

    选择“连接”。
  
2.  在中**对象资源管理器**，展开 SQL 服务器，展开**安全**，右键单击**登录名**，然后选择**新登录名**。  
  
3.  有关**登录名**，输入中的 Windows 用户名`domain\username`格式。  

    > [!NOTE]
    >* 使用此适配器时 BizTalk 使用，您输入的登录名是主机实例帐户的标识。  
    >
    >* 使用此适配器时的.NET 代码中，您输入的登录名是该进程的标识。
  
4.  选择**用户映射**（左的窗格）。 选择要将与用户相关联的数据库。 典型的 BizTalk 用户应与以下数据库相关联： 

* BizTalkDTADb
* BizTalkMgmtDb
* BizTalkMsgBoxDb
* BTAHL7
* SSODB

5. 在中**数据库角色成员身份**框中，选择**db_owner**的所有 BizTalk 数据库。  

    > [!NOTE]
    > [服务器和 SQL Server 中的数据库角色](https://msdn.microsoft.com/library/bb669065.aspx)角色上提供有用信息。 
  
6. 单击“确定”保存更改。
  
   添加用户后，用户可以连接并进行身份验证与 SQL Server 使用[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]、 日志记录使用空白用户名和密码。  



## <a name="see-also"></a>请参阅  
 [创建与 SQL Server 的连接](../../adapters-and-accelerators/adapter-sql/create-a-connection-to-sql-server.md)