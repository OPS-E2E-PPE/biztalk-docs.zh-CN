---
title: SSO 映射 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- maps [SSO]
- maps [SSO], creating
- SSO, maps
ms.assetid: b44f7a0c-595c-49dc-9d75-2e76f29dca88
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 98b44a1a9e8be3b275a4dd328c70323d79eb8a54
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22277237"
---
# <a name="sso-mappings"></a>SSO 映射
在企业单一登录 (SSO) 管理员或 SSO 关联管理员定义关联应用程序时，该管理员可以将其定义为具有单项映射的应用程序或具有组映射的应用程序。  
  
## <a name="individual-mappings"></a>单项映射  
 使用 SSO 单项映射，管理员和用户可以在 Windows 用户与他们对应的非 Windows 凭据之间创建一对一映射。 在使用单项映射时，用户可以管理他们自己的映射。 SSO 系统可维护用户的 Windows 帐户与该用户的非 Windows 帐户间的一对一关系。  
  
 Windows 最终用户可以为单项类型的应用程序创建和管理他们自己的映射。 同一关联应用程序可以用作 Windows 启动的 SSO 类型应用程序和主机启动的 SSO 类型应用程序。  
  
> [!IMPORTANT]
>  只能为 Windows 域帐户创建映射。 无法映射本地帐户。  
  
> [!NOTE]
>  在使用单项映射时，只有用户本人才可以获得其个人帐户的凭据。  
  
## <a name="group-mapping"></a>组映射  
 SSO 组映射由从 Windows 组指向关联应用程序中的单个帐户的映射组成，该 Windows 组包含多个 Windows 用户。  
  
 也可以为 SSO 应用程序用户角色指定多个帐户。 所指定的每个帐户均可与外部帐户关联。 例如，您可以将域组帐户映射到 EXTERNALUSER1，并将个人域帐户映射到 EXTERNALUSER2。 如果同一用户具有多个映射，则使用 SSO 应用程序用户顺序中的第一个映射。  
  
 只有应用程序管理员、SSO 关联管理员或 SSO 管理员才可以创建或管理组映射。  
  
 不能为 Windows 启动的 SSO 和主机启动的 SSO 指定相同的组应用程序。  
  
> [!IMPORTANT]
>  只能为 Windows 域帐户创建映射。 无法映射本地帐户。  
  
> [!IMPORTANT]
>  在使用组映射时，组成员可以获得组映射的凭据信息。  
  
## <a name="see-also"></a>另请参阅  
 [管理用户映射](../core/managing-user-mappings.md)   
 [SSO 关联应用程序](../core/sso-affiliate-applications.md)