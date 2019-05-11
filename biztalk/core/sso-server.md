---
title: SSO Server | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- Master Secret server, tasks
- Master Secret server, SSO
- servers, SSO
- SSO, servers
- SSO, Master Secret server
ms.assetid: 40240d6b-b7d1-48fb-b750-be0e380d52e3
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 7a17d3ad69ab18e9d1916f5a7cf2907021d7d54c
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65398980"
---
# <a name="sso-server"></a>SSO 服务器
企业单一登录 (SSO) 服务器可以执行任何以下任务：  
  
-   **主密钥服务器的功能。** 主密钥服务器保留持久化的副本的主密钥，或密钥，用于加密在 SSO 系统中的所有凭据。 尽管在主密钥服务器可充当用于查找和管理的服务器，建议使用此服务器仅充当主密钥服务器出于安全原因。 主密钥服务器执行这些函数的详细信息，请参阅[主密钥服务器](../core/master-secret-server.md)。  
  
-   **执行管理操作。** SSO 管理员可以使用任何单一登录服务器来执行管理任务，例如管理关联应用程序设置的用户凭据，以及管理用户映射。  
  
-   **执行查找操作。** SSO 服务器使用的运行时组件要查找的用户凭据。  
  
-   **颁发并兑换票证。** SSO 服务器还颁发并兑换 SSO 票证。  
  
-   **密码同步。** 您可以创建和管理 SSO 服务器上的密码同步适配器。  
  
## <a name="see-also"></a>请参阅  
 [使用 SSO](../core/using-sso.md)   
 [安装 SSO](../core/installing-sso.md)