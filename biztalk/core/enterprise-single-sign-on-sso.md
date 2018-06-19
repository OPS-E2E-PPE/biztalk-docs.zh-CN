---
title: 企业单一登录 (SSO) |Microsoft 文档
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
ms.openlocfilehash: 2f6cbc5f514d13cd8457cd9417be5ea5b78408e6
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22240149"
---
# <a name="enterprise-single-sign-on-sso"></a>企业单一登录 (SSO)
使用企业单一登录 (SSO) 提供的服务，可以跨本地和网络边界（包括域边界）存储和传输加密的用户凭据。 SSO 将凭据存储在 SSO 数据库中。 由于 SSO 提供了通用的单一登录解决方案，因此中间件应用程序和自定义适配器可以利用 SSO 来跨环境安全地存储和传输用户凭据。 最终用户不必为不同的应用程序记住不同的凭据。  
  
 单一登录系统由以下部分组成：SSO 数据库、主密钥服务器以及一个或多个单一登录服务器。  
  
 SSO 系统包含*affiliate 应用程序*管理员定义的。 *Affiliate 应用程序*是表示系统或如主机、 后端系统或业务线应用程序的子系统的逻辑实体连接到使用企业单一登录。 每个关联应用程序都具有多个用户映射；例如，关联应用程序具有 Active Directory 中的用户凭据与其对应的 RACF 凭据之间的映射。  
  
 SSO 数据库是存储有关关联应用程序，以及所有关联的所有应用程序的加密的用户凭据的信息的 SQL Server 数据库。  
  
 *主密钥服务器*是企业单一登录服务器，它将存储主密钥。 系统中的其他所有单一登录服务器都从主密钥服务器中获取主密钥。  
  
 SSO 系统还包含一个或多个 SSO 服务器。 这些服务器在 Microsoft Windows 凭据与后端凭据之间进行映射，并在 SSO 数据库中查找凭据。 管理员可使用这些服务器来维护 SSO 系统。  
  
 有关更完整查看在企业单一登录，请参阅[了解 SSO](../core/understanding-sso.md)。  
  
## <a name="see-also"></a>另请参阅  
 [运行时体系结构](../core/runtime-architecture.md)