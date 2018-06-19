---
title: 管理 Windows 组和用户帐户的最佳实践 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- best practices, Windows groups
- authenticating, best practices
- Windows groups, security
- best practices, user accounts
- best practices, security
- security, best practices
- user accounts, security
- authenticating, security
- Windows groups, best practices
- best practices, authenticating
- user accounts, best practices
- hosts, security
- hosts, best practices
- best practices, hosts
ms.assetid: 0c4a141e-97ce-434a-8e45-a56c634bbd6c
caps.latest.revision: 16
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 71f7560e3867bf290f20e0f2f49a740d7298131b
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22231221"
---
# <a name="best-practices-for-managing-windows-groups-and-user-accounts"></a>管理 Windows 组和用户帐户的最佳实践
本部分包含了管理 Windows 组和用户帐户的安全性时的最佳实践和提示。  
  
-   **使用服务帐户与主机实例所需的最小权限**  
  
     为了确保 BizTalk Server 环境的安全性，建议您使用具有运行主机实例时所需的最低权限的服务帐户。 有关服务帐户要求的最小特权的详细信息，请参阅[访问控制和数据安全](../core/access-control-and-data-security.md)。  
  
-   **使用不同的用户组来指定受信任的身份验证和非受信任的主机**  
  
     为了确保不受信任验证主机比受信任验证主机拥有更少的权限，每个主机必须使用不同的服务帐户。  
  
-   **为每个 BizTalk 主机使用不同的用户组**  
  
     为了使各主机间的安全边界最大，建议对 BizTalk 组中每个 BizTalk 主机使用不同的 Windows 用户组。  
  
-   **从 BizTalk Server Administrators 组中删除安装用户**  
  
     在具有本地组的单台计算机上安装 BizTalk Server 时，系统会自动将执行 BizTalk Server 交互式安装的用户添加到 BizTalk Server Administrators 组。 这使该用户可以使用配置管理器来配置 BizTalk Server。  
  
     如果安装 BizTalk Server 的用户将来不需要对 BizTalk Server 进行管理，则建议在配置完 BizTalk Server 之后将该用户从 BizTalk Server Administrators 组中删除。  
  
## <a name="see-also"></a>另请参阅  
 [管理 BizTalk Server 安全性](../core/managing-biztalk-server-security.md)