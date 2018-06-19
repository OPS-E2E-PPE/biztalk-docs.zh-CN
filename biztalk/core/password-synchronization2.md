---
title: 密码 Synchronization2 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- SSO, passwords
- passwords, synchronizing [SSO]
- managing [SSO], synchronizing passwords
- Password Synchronization [SSO]
- Password Synchronization [SSO], about Password Synchronization
- SSO database, passwords
ms.assetid: 6d4970e0-ac73-4fca-ab8f-6c8a6f3a6ec0
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b9c12bc9ff5190fe0a76c92b1cfee2233b9d206a
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22264357"
---
# <a name="password-synchronization"></a>密码同步
密码同步的用途是简化 SSO 数据库的管理，使密码在用户目录中保持同步。  
  
 这两个任务是通过使用密码同步适配器来实现的，本部分中的主题介绍了用于创建和管理这些适配器的命令行实用工具。  
  
 有三种类型的密码同步子功能。  
  
 第一种类型是**到外部的 Windows** (例如，到 RACF 的 Active Directory)。 在此方案中，将捕获对 Windows 用户的密码所做的更改，并将其发送到指定用来从域控制器接收密码更改的企业 SSO 服务器。 然后，该服务器将密码更改转发到外部系统，SSO 数据库中的映射会与外部系统中所做的更改保持同步。  
  
 第二种类型是**Windows-完全同步到外部**。 在此方案中，将捕获外部系统中的密码，并将其发送到指定用来执行密码同步的企业单一登录服务器，随后该服务器将更新 SSO 数据库中的密码，并同时更新 Active Directory 中 Windows 用户的密码。  
  
 第三种类型是**外部的 Windows-部分同步**。 在此方案中，将捕获外部系统中的密码，并将其发送到指定用来执行密码同步的企业单一登录服务器，随后该服务器将更新 SSO 数据库中的密码。  
  
## <a name="in-this-section"></a>本节内容  
  
-   [如何安装密码同步](../core/how-to-install-password-synchronization.md)  
  
-   [如何管理密码同步](../core/how-to-administer-password-synchronization.md)  
  
-   [如何配置密码同步](../core/how-to-configure-password-synchronization.md)  
  
-   [如何管理密码同步](../core/how-to-manage-password-synchronization.md)