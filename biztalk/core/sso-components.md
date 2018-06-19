---
title: SSO 组件 |Microsoft 文档
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
ms.openlocfilehash: c1111f1a0dfac47412ae28b58f93ddc51e1f562b
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22276469"
---
# <a name="sso-components"></a>SSO 组件
企业单一登录 (SSO) 服务的子服务如下所示：  
  
-   **映射。** 此组件将 Windows 系统的用户帐户中的用户帐户映射后端系统中。  
  
-   **查找。** 此组件后端系统中查找的 SSO 数据库中的用户凭据。 这是 SSO 运行时组件。  
  
-   **管理。** 此组件管理关联应用程序和每个关联应用程序的映射。  
  
-   **机密。** 此组件生成主密钥并将其分发给其他 SSO 服务器中，在系统中。 仅在充当主密钥服务器上单一登录服务器上活动。  
  
-   **密码同步。** 此组件，来简化管理 SSO 数据库中，并保持密码同步在用户的目录。  
  
## <a name="see-also"></a>另请参阅  
 [SSO 服务器](../core/sso-server.md)   
 [安装 SSO](../core/installing-sso.md)