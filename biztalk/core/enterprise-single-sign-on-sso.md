---
title: 企业单一登录 (SSO) |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- SSO, about SSO
- SSO
ms.assetid: beab96f7-f026-4ae1-8462-a165ad76bbec
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 1dee56153e9eca7112ac0323bbfd604c3d062e86
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65349290"
---
# <a name="enterprise-single-sign-on-sso"></a>企业单一登录 (SSO)
企业单一登录 (SSO) 提供的服务来存储和传输加密用户凭据跨本地和网络边界，其中包括域边界。 SSO 将凭据存储在 SSO 数据库中。 由于 SSO 提供了一个泛型单一登录解决方案，中间件应用程序和自定义适配器可以利用 SSO 来安全地存储和传输整个环境的用户凭据。 最终用户无需记住的不同应用程序不同的凭据。  
  
 单一登录系统包含 SSO 数据库、 主密钥服务器和一个或多个单一登录服务器。  
  
 SSO 系统包含*关联应用程序*管理员定义的。 *关联应用程序*是表示系统或如主机、 后端系统或业务线应用程序的子系统的逻辑实体连接到使用企业单一登录。 每个关联应用程序具有多个用户映射;例如，它具有在 Active Directory 中用户的凭据和其对应的 RACF 凭据之间的映射。  
  
 SSO 数据库是存储有关关联应用程序，以及所有关联的所有应用程序的加密的用户凭据的信息的 SQL Server 数据库。  
  
 *主密钥服务器*是存储主密钥的企业单一登录服务器。 中的所有其他单一登录服务器系统从主密钥服务器获取主密钥。  
  
 SSO 系统还包含一个或多个 SSO 服务器。 这些服务器的 Microsoft Windows 和后端凭据之间进行映射，并查找 SSO 数据库中的凭据。 管理员使用它们来维护 SSO 系统。  
  
 完整信息在企业单一登录，请参阅[了解 SSO](../core/understanding-sso.md)。  
  
## <a name="see-also"></a>请参阅  
 [运行时体系结构](../core/runtime-architecture.md)