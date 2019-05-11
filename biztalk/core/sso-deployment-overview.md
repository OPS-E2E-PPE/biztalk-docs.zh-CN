---
title: SSO 部署概述 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- SSO, deploying example
- SSO, deploying
- deploying, SSO
- SSO, multiple computers
- examples, deploying
ms.assetid: 6eccee26-c392-41fe-97fb-3afe1685540f
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c942bf7f7fd0853164e2cf2b8fdadbfced2fe33d
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65401754"
---
# <a name="sso-deployment-overview"></a>SSO 部署概述
在此示例中的系统部署在三个域，其中包含以下计算机：  
  
 **域 ORCH.com**  
  
- ORCH 域控制器  
  
- HIS1，HISSO 服务器  
  
- HIS2，主密钥服务器  
  
- 在 HIS3，管理数据库  
  
  **Domain SQL.com**  
  
- SQL 域控制器  
  
- SQL2，SSO 数据库  
  
  **域 HIS.com**  
  
- 他的域控制器  
  
- HIS4 数据库  
  
  定义此部署的关键点是按如下所示：  
  
- 域 ORCH.com 和域 SQL.com 具有双向选择信任关系。  
  
- 域 ORCH.com 配置为本机[!INCLUDE[btsWinSvr2k8](../includes/btswinsvr2k8-md.md)]或[!INCLUDE[btsWinSvr2k8R2](../includes/btswinsvr2k8r2-md.md)]功能级别。  
  
- 所有 SSO 服务在 ORCH.com 域用户帐户 (Orch\SSOSvcUser) 都运行。 用户配置为在 SQL.com 域的 SQL2 计算机上具有访问权限。 用户配置的协议转换和约束委派在 ORCH.com 域中。  
  
- 另一个 ORCH.com 域用户 (Orch\TestAppUser) 来运行测试程序设置。 此用户也被配置为协议转换和约束委派。  
  
## <a name="see-also"></a>请参阅  
 [部署过程](../core/deployment-process.md)