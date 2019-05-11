---
title: 如何使用 ENTSSO 管理代理 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 9c89b494-db12-4d2a-a030-6acd34489cab
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e5316fc279ea7dc0c29038ffefb1b16770bf6469
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65383348"
---
# <a name="how-to-use-the-entsso-management-agent"></a>如何使用 ENTSSO 管理代理
此版本的企业单一登录 (SSO) 包含管理代理 (MA) 的 Microsoft Identity Integration Server (MIIS)，其中将企业 SSO 与 MIIS 的帐户同步功能集成起来。 这样，MIIS 管理员来管理 SSO 数据库中的 SSO 映射。  
  
 在企业 SSO 之间创建映射的 Windows 域帐户 (*域名 \ 用户名*) 和外部凭据。 如果为外部数据源具有 Active Directory 管理代理和管理代理 (示例：RACF MA)，可以使用企业 SSO MA (ENTSSO MA) 来管理 SSO 数据库中的映射。 ENTSSO MA 是*基于呼叫的导出*仅管理代理。  
  
 在三个独立的部分中配置管理代理：  
  
- 配置文件 (ENTSSO.xml)  
  
- MIIS 用户界面  
  
- ENTSSO 用户界面  
  
  在本部分中的主题介绍配置过程。  
  
## <a name="in-this-section"></a>本节内容  
  
-   [配置 XML 文件](../core/configuring-the-xml-file.md)  
  
-   [如何针对 ENTSSO MA 配置 MIIS](../core/how-to-configure-miis-for-entsso-ma.md)  
  
-   [如何配置 ENTSSO 以实现 MIIS 密码同步](../core/how-to-configure-entsso-for-miis-password-sync.md)