---
title: SSO 映射 |Microsoft Docs
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
ms.openlocfilehash: 5debd3e1dcf1ee0e45d421e777006d247a6da84f
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65258613"
---
# <a name="sso-mappings"></a>SSO 映射
当企业单一登录 (SSO) 管理员或 SSO 关联管理员定义关联应用程序时，管理员可以将其定义为具有单项映射的应用程序或使用组映射的应用程序。  
  
## <a name="individual-mappings"></a>单项映射  
 SSO 单项映射，管理员和用户可创建 Windows 用户和其相应的非 Windows 凭据之间的一对一映射。 在使用单项映射时，用户可以管理他们自己的映射。 SSO 系统会维护有关用户的 Windows 帐户和用户的非 Windows 帐户的一对一关系。  
  
 Windows 最终用户可以创建和管理他们自己的映射的各个类型的应用程序。 同一关联应用程序可充当 Windows 启动的 SSO 和主机启动的 SSO 类型应用程序。  
  
> [!IMPORTANT]
>  可以仅为 Windows 域帐户创建映射。 无法映射本地帐户。  
  
> [!NOTE]
>  使用单项映射时，只有用户可以获取其个人帐户的凭据。  
  
## <a name="group-mapping"></a>组映射  
 将 Windows 组，其中包含多个 Windows 用户，映射到关联应用程序中的单个帐户包含 SSO 组映射。  
  
 此外可以指定为 SSO 应用程序用户角色的多个帐户。 指定每个帐户可以与外部帐户相关联。 例如，可以将域组帐户映射到 EXTERNALUSER1，并将个人域帐户到 EXTERNALUSER2。 如果同一用户具有多个映射，则使用 SSO 应用程序用户顺序的第一个映射。  
  
 只有应用程序管理员、 SSO 关联管理员或 SSO 管理员可以创建或管理组映射。  
  
 不能指定同一组应用程序的 Windows 启动的 SSO 和主机启动的 SSO。  
  
> [!IMPORTANT]
>  可以仅为 Windows 域帐户创建映射。 无法映射本地帐户。  
  
> [!IMPORTANT]
>  当你使用组映射时，组的成员可以获得组映射的凭据信息。  
  
## <a name="see-also"></a>请参阅  
 [管理用户映射](../core/managing-user-mappings.md)   
 [SSO 关联应用程序](../core/sso-affiliate-applications.md)