---
title: "SSO 服务器 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- Master Secret server, tasks
- Master Secret server, SSO
- servers, SSO
- SSO, servers
- SSO, Master Secret server
ms.assetid: 40240d6b-b7d1-48fb-b750-be0e380d52e3
caps.latest.revision: "8"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 37f2f24911a0336a734125436d97dbce6f9e0b77
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="sso-server"></a>SSO 服务器
企业单一登录 (SSO) 服务器可以执行任何以下任务：  
  
-   **用作主密钥服务器。** 主密钥服务器保留持久化的副本的主密钥，或密钥，用于加密 SSO 系统中的所有凭据。 尽管主密钥服务器可以充当查找和管理的服务器，建议使用此服务器仅充当出于安全原因主密钥服务器。 主密钥服务器执行函数的详细信息，请参阅[主密钥服务器](../core/master-secret-server.md)。  
  
-   **执行管理操作。** SSO 管理员可以使用任何单一登录服务器以执行管理任务，例如管理关联应用程序、 设置用户凭据和管理用户映射。  
  
-   **执行查找操作。** SSO 服务器使用的运行时组件来查找用户凭据。  
  
-   **发出并兑换票证。** SSO 服务器还发出并兑换 SSO 票证。  
  
-   **密码同步。** 你可以创建和管理 SSO 服务器上的密码同步适配器。  
  
## <a name="see-also"></a>另请参阅  
 [使用 SSO](../core/using-sso.md)   
 [安装 SSO](../core/installing-sso.md)