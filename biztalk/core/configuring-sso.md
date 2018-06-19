---
title: 配置 SSO |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- SSO, command line utilities
- configuring, SSO
- SSO, interfaces
- SSOConfig [SSO]
- SSO, configuring
- SSOClient [SSO]
- SSO, tools
- SSOManage [SSO]
ms.assetid: 6f755735-9b48-4771-beec-ced844f3d532
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: d729633717d709a83c10e9b50c55791029902010
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22233037"
---
# <a name="configuring-sso"></a>配置 SSO
可以通过使用命令行实用工具、用户界面工具或者 COM 或 Microsoft .NET 接口来配置企业单一登录。  
  
## <a name="sso-command-line-utilities"></a>SSO 命令行实用工具  
 您可以使用三种不同的命令行实用工具来执行企业单一登录任务：  
  
 **SSOConfig。** SSO 管理员可使用该工具来配置 SSO 数据库和管理主密钥。  
  
> [!NOTE]
>  配置向导创建 SSO 数据库和主密钥服务器。  
  
 **SSOManage。** SSO 管理员、SSO 关联管理员和应用程序管理员可使用该工具来更新 SSO 数据库，以添加、删除和管理应用程序，管理用户映射，以及为关联应用程序用户设置凭据。 某些操作只能由 SSO 管理员来执行；或者只能由 SSO 管理员和 SSO 关联管理员来执行。 可由应用程序管理员执行的所有操作都可由 SSO 管理员和 SSO 关联管理员来执行。  
  
 **SSOClient。** 单一登录用户可以使用该工具来管理自己的用户映射以及设置自己的凭据。  
  
 有关 SSO 帐户的详细信息，请参阅[SSO 用户组](../core/sso-user-groups.md)。  
  
## <a name="sso-ui-tools"></a>SSO 用户界面工具  
 **企业 SSO mmc 管理单元。** SSO 管理员、SSO 关联管理员和应用程序管理员可使用该工具来更新 SSO 数据库，添加、删除和管理应用程序，管理用户映射，以及为关联应用程序用户设置凭据。 只能由 SSO administrators，可以执行某些操作，或仅通过 SSO 管理员和 SSO affiliate 管理员。 可以执行的应用程序管理员的所有操作还可以都执行的 SSO Administrators 和 SSO Affiliate Administrators。  
  
 **SSO 客户端实用工具。** 最终用户可使用该用户界面工具来管理自己映射以及设置自己的凭据。  
  
## <a name="sso-com-and-net-interfaces"></a>SSO COM 和 .NET 接口  
 企业单一登录提供有 COM 和 .NET 编程接口，使您能够创建自定义组件和创建脚本以便对 SSO 系统进行管理。  
  
## <a name="see-also"></a>另请参阅  
 [SSO 组件](../core/sso-components.md)