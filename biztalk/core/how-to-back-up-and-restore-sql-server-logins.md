---
title: 如何备份和还原 SQL Server 登录名 |Microsoft Docs
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
ms.openlocfilehash: 87634ca9e9f8bbd3cc7508ce0bcfe54e5154ca0f
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65387111"
---
# <a name="how-to-back-up-and-restore-sql-server-logins"></a>如何备份和还原 SQL Server 登录名
备份和还原与 BizTalk Server 相关联的 SQL Server 登录名。  
  
## <a name="biztalk-server-sql-server-security-logins"></a>BizTalk Server SQL Server 安全登录  
 下面列出的 SQL Server 安全登录名是与 BizTalk Server 相关联。 您可能必须与已创建的 BizTalk Server 应用程序相关联的其他登录名。 需要备份的登录名并将其还原时将 BizTalk Server 数据库移动到新的服务器或 SQL Server 的新实例。  
  
-   BizTalk Application Users  
  
-   BizTalk Isolated Host Users  
  
-   BizTalk Server Administrators  
  
-   BizTalk Server Operators  
  
-   SSO Administrators  

## <a name="prerequisites"></a>先决条件  
您必须是属于**管理员**上 SQL Server 备份和还原登录的安全角色。  
  
## <a name="back-up-a-login-using-a-script"></a>备份使用脚本的登录名  
  
1.  打开 SQL Server Management Studio。  
  
2.  展开**安全**，然后展开的列表**登录名**。  
  
3.  右键单击你想要创建备份脚本，然后选择登录的名**编写登录脚本为**。  
  
4.  选择**创建到**，然后选择其中一个**新查询编辑器窗口**，**文件**，或**剪贴板**以选择脚本目标。 通常情况下，目标是文件，并且 **.sql**扩展。  
  
5.  每个登录名要编写脚本重复步骤 3 中的此过程。 到的列表，请参阅 BizTalk Server 相关的登录名，以确定需要脚本的登录名。  
  
## <a name="restore-a-login-from-a-script"></a>从脚本还原登录名  
  
1.  打开 SQL Server Management Studio。  
  
2.  上**文件**菜单中，**打开**包含脚本登录名的文件。  
  
3.  执行脚本以创建登录名。