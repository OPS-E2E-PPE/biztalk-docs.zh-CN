---
title: "SSO 部署概述 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- SSO, deploying example
- SSO, deploying
- deploying, SSO
- SSO, multiple computers
- examples, deploying
ms.assetid: 6eccee26-c392-41fe-97fb-3afe1685540f
caps.latest.revision: "8"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f88afb52f1db1263112732e70befb2ab95e6b135
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="sso-deployment-overview"></a>SSO 部署概述
本示例中的系统部署在三个域中，包含以下计算机：  
  
 **域 ORCH.com**  
  
-   ORCH 域控制器  
  
-   HIS1，HISSO 服务器  
  
-   HIS2，主密钥服务器  
  
-   HIS3，管理数据库  
  
 **域 SQL.com**  
  
-   SQL 域控制器  
  
-   SQL2，SSO 数据库  
  
 **域 HIS.com**  
  
-   HIS 域控制器  
  
-   HIS4 数据库  
  
 定义此部署的要点如下：  
  
-   域 ORCH.com 和域 SQL.com 具有双向选择信任关系。  
  
-   域 ORCH.com 配置为本机 [!INCLUDE[btsWinSvr2k8](../includes/btswinsvr2k8-md.md)] 或 [!INCLUDE[btsWinSvr2k8R2](../includes/btswinsvr2k8r2-md.md)] 功能级别。  
  
-   所有 SSO 服务都以 ORCH.com 域用户帐户 (Orch\SSOSvcUser) 运行。 该用户被配置为具有对 SQL.com 域中的 SQL2 计算机的访问权限。 为该用户配置在 ORCH.com 域中的协议转换和约束委托。  
  
-   设置另外一个 ORCH.com 域用户 (Orch\TestAppUser) 来运行测试程序。 并为该用户配置协议转换和约束委托。  
  
## <a name="see-also"></a>另请参阅  
 [部署过程](../core/deployment-process.md)