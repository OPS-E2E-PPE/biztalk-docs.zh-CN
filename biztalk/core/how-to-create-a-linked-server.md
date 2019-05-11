---
title: 如何创建链接的服务器 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- servers, linking for backups
- backing up, linking servers
ms.assetid: 7d4aba3d-77c0-4cdf-8547-71e821ce34a1
caps.latest.revision: 26
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 3ddb25ae58ee7adddd936f4904a131d4064a608f
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65385572"
---
# <a name="how-to-create-a-linked-server"></a>如何创建链接服务器
当[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]安装在分布式拓扑中，属于 BizTalk 组的数据库存在在多个[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]。 可以备份整个 BizTalk 环境从 BizTalk 管理服务器之前，必须配置链接的服务器连接到每个远程服务器。 链接的服务器是 OLE DB 数据源中使用[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]分布式查询。  
  
 备份和还原过程中，备份的一部分[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]作业将自动创建链接的服务器。 如有必要，但是，可以手动创建链接的服务器使用此过程。  
  
 此外可以使用创建链接的服务器*sp_addlinkedserver*存储过程。 有一些与此操作关联的安全注意事项。 使用 sp_addlinkedserver 创建链接的服务器后，您将所有本地登录名的映射到新的链接服务器默认情况下。 若要控制对链接服务器的访问*sp_droplinkedsvrlogin*过程应该用于删除全局登录映射后, 跟*sp_addlinkedsvrlogin*将映射到的所需的登录帐户新建链接的服务器。 在使用 sp_addlinkedsvrlogin 时，建议您设置@useself参数 = TRUE。 这样可以避免将嵌入到您的 SQL 脚本的用户名和密码。  

> [!TIP]
> 这些步骤可能随时间变化。 我们建议引用[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]文档，网址[创建链接服务器](https://docs.microsoft.com/sql/relational-databases/linked-servers/create-linked-servers-sql-server-database-engine)。
  
## <a name="prerequisites"></a>先决条件  
  
- 是的成员的帐户登录[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] **sysadmin**固定的服务器角色  
  
- 创建本地[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]登录名。 在以下步骤中，此帐户映射到登录名在[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]，将链接到。 
  
## <a name="create-a-linked-server"></a>创建链接的服务器
  
1. 打开**SQL Server Management Studio**，输入你的本地名称[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]，然后选择**Connect**。  
  
2. 展开**Server 对象**，右键单击**链接服务器**，然后选择**新建链接服务器**。  

   若要查看**Server 对象**，连接到本地内部[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]。 然后， **Server 对象**应显示。
  
3. 在中**链接服务器**文字框中，输入的完整网络名称[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]你想要链接到。  
  
   > [!NOTE]
   >  此过程通常是指要为远程服务器链接到的服务器。 这只是为了方便，以指示本地服务器的链接 （"远程"） 服务器的关系。  
  
4. 下**服务器类型**，选择**SQL Server**。  
  
5. 在左窗格中，选择“安全性” 。 

   在此步骤中，你创建的本地帐户映射到远程服务器登录名。 选项包括： 
    
   | | | 
   |---|---|
   | **可使用登录名的当前安全上下文** | 在域环境中，用户通常使用其域登录名连接。 由于登录的域帐户的安全上下文映射到你创建的本地帐户，此选项可能是最佳。|
   | **使用此安全上下文建立连接** | 当用户连接到本地 SQL Server 使用 SQL Server 登录名时，则此选项可能是最佳。 然后输入登录名和密码的帐户链接的服务器上。 |


6. 选择**添加**，并输入以下命令： 

   1. 下**本地登录名**，选择你创建的本地帐户。 
   2. 检查**Impersonate**如果远程服务器上还存在本地登录名。 
   3. 或者，如果将本地登录名映射到远程[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]登录名，输入**远程用户**名称并**远程密码**的远程服务器登录名。  
  
      > [!NOTE]
      >  若要使用模拟，您[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]配置和登录帐户必须满足委派要求。 请参阅[委派配置链接服务器](https://msdn.microsoft.com/library/ms189580.aspx)的更多详细信息。  

7. 在左窗格中，选择**服务器选项**。 设置**RPC**并**RPC Out**参数**True**，然后选择**确定**。 
 
> [!TIP]
> 有关详细信息和建议创建链接的服务器时使用 includig`sp_addlinkedserver`存储 procedcure，请参阅[创建链接服务器](https://docs.microsoft.com/sql/relational-databases/linked-servers/create-linked-servers-sql-server-database-engine)。

  
## <a name="see-also"></a>请参阅  
 [有关备份和还原的高级信息](../core/advanced-information-about-backup-and-restore1.md)