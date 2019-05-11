---
title: 配置 SSO |Microsoft Docs
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
ms.openlocfilehash: 19825ec6f420b8ec3e30f5dead09ad1d901503f8
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65355194"
---
# <a name="configuring-sso"></a>配置 SSO
使用命令行实用程序、 用户界面工具，或者 COM 或 Microsoft.NET 接口可以配置企业单一登录。  
  
## <a name="sso-command-line-utilities"></a>SSO 命令行实用程序  
 使用三个不同的命令行实用程序来执行企业单一登录任务：  
  
 **SSOConfig。** 若要配置 SSO 数据库以及管理主密钥 SSO 管理员可使用。  
  
> [!NOTE]
>  配置向导创建 SSO 数据库和主密钥服务器。  
  
 **SSOManage。** 启用 SSO 管理员、 SSO 关联管理员和应用程序管理员，若要更新 SSO 数据库，添加、 删除和管理应用程序、 管理用户映射，并为关联应用程序用户设置凭据。 只能由 SSO 管理员，可以执行一些操作，或只能由 SSO 管理员和 SSO 关联管理员。 此外可以通过 SSO Administrators 和 SSO Affiliate Administrators 执行应用程序管理员可以执行的所有操作。  
  
 **SSOClient。** 启用单一登录的用户来管理其自己的用户映射以及设置自己的凭据。  
  
 有关 SSO 帐户的详细信息，请参阅[SSO 用户组](../core/sso-user-groups.md)。  
  
## <a name="sso-ui-tools"></a>SSO 用户界面工具  
 **企业 SSO mmc 管理单元。** 启用 SSO 管理员、 SSO 关联管理员和应用程序管理员，若要更新 SSO 数据库、 添加、 删除和管理应用程序、 管理用户映射，以及为关联应用程序用户设置凭据。 只能由 SSO 管理员，可以执行一些操作，或只能由 SSO 管理员和 SSO 关联管理员。 此外可以通过 SSO Administrators 和 SSO Affiliate Administrators 执行应用程序管理员可以执行的所有操作。  
  
 **SSO 客户端实用工具。** 使最终用户能够管理自己映射以及设置自己的凭据使用 UI 工具。  
  
## <a name="sso-com-and-net-interfaces"></a>SSO COM 和.NET 接口  
 企业单一登录提供 COM 和.NET 编程接口，使您能够创建自定义组件，以及创建脚本以促进 SSO 系统的管理。  
  
## <a name="see-also"></a>请参阅  
 [SSO 组件](../core/sso-components.md)