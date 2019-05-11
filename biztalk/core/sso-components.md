---
title: SSO 组件 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- passwords, synchronizing [SSO]
- SSO, components
- SSO, password synchronization
- SSO, sub-services
ms.assetid: e29e68df-f770-4220-a9f8-cb9323403017
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 9e7e00ad4dfb82d2c6e16c45a09c4f452b33081b
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65401762"
---
# <a name="sso-components"></a>SSO 组件
企业单一登录 (SSO) 服务的子服务如下所示：  
  
-   **映射。** 此组件将用户帐户在 Windows 系统中的用户帐户映射的后端系统中。  
  
-   **查找。** 此组件将在后端系统中查找 SSO 数据库中的用户凭据。 这是 SSO 运行时组件。  
  
-   **管理。** 此组件管理关联应用程序和每个关联应用程序的映射。  
  
-   **Secret.** 此组件生成主密钥，并在系统中将其分发给其他 SSO 服务器。 它只是活动的单一登录服务器充当在主密钥服务器上。  
  
-   **密码同步。** 此组件可以简化管理 SSO 数据库中，并保留密码各个用户目录间保持同步。  
  
## <a name="see-also"></a>请参阅  
 [SSO Server](../core/sso-server.md)   
 [安装 SSO](../core/installing-sso.md)