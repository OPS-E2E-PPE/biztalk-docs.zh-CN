---
title: 如何备份和还原 SQL Server 登录名 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 847c3a3d-0d97-415b-893e-4ba173085bae
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 54fa6a51a27f82add8a96c613e36f5ed7ce88e87
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22248549"
---
# <a name="how-to-back-up-and-restore-sql-server-logins"></a>如何备份和还原 SQL Server 登录名
备份和还原与 BizTalk Server 关联的 SQL Server 登录名。  
  
## <a name="biztalk-server-sql-server-security-logins"></a>BizTalk Server SQL Server 安全登录  
 下面列出了与 BizTalk Server 关联的 SQL Server 安全登录。 你可能有更多的登录与所创建的 BizTalk Server 应用程序相关联。 将 BizTalk Server 数据库移动到新服务器或 SQL Server 的新实例时，需要备份和还原此登录。  
  
-   BizTalk Application Users  
  
-   BizTalk Isolated Host Users  
  
-   BizTalk Server Administrators  
  
-   BizTalk Server Operators  
  
-   SSO Administrators  

## <a name="prerequisites"></a>先决条件  
您必须是属于**管理员**上 SQL Server 在备份和还原登录名的安全角色。  
  
## <a name="back-up-a-login-using-a-script"></a>备份使用脚本的登录名  
  
1.  打开**SQL Server Management Studio**。  
  
2.  展开**安全**，，然后展开的列表**登录名**。  
  
3.  右键单击你想要创建的备份脚本，然后选择的登录名**脚本以用户身份登录**。  
  
4.  选择**创建到**，然后选择其中一个**新查询编辑器窗口**，**文件**，或**剪贴板**若要为脚本选择一个目标。 通常情况下，目标是为此文件 **.sql**扩展。  
  
5.  对于要生成脚本的每个登录，从步骤 3 重复此过程。 请参考与 BizTalk Server 相关的登录名列表，以确定你需要为哪些登录名编写脚本。  
  
## <a name="restore-a-login-from-a-script"></a>从脚本中还原一个登录名  
  
1.  打开**SQL Server Management Studio**。  
  
2.  上**文件**菜单上，**打开**包含已编写脚本的登录名的文件。  
  
3.  执行该脚本以创建登录。