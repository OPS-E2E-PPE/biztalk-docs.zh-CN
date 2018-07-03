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
ms.openlocfilehash: 68c354f2250e9abc6a02ea52f4b7c106f57144e6
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "37018473"
---
# <a name="how-to-use-the-entsso-management-agent"></a>如何使用 ENTSSO 管理代理
企业单一登录 (SSO) 的此版本包含 Microsoft Identity Integration Server (MIIS) 的管理代理 (MA)，后者将企业 SSO 与 MIIS 的帐户同步功能集成在一起。 这样，MIIS 管理员便可管理 SSO 数据库中的 SSO 映射。  
  
 在企业 SSO 之间创建映射的 Windows 域帐户 (*域名 \ 用户名*) 和外部凭据。 如果为外部数据源具有 Active Directory 管理代理和管理代理 (示例： RACF MA)，可以使用企业 SSO MA (ENTSSO MA) 来管理 SSO 数据库中的映射。 ENTSSO MA 是*基于呼叫的导出*仅管理代理。  
  
 您需在三个不同的部分配置该管理代理：  
  
- 配置文件 (ENTSSO.xml)  
  
- MIIS 用户界面  
  
- ENTSSO 用户界面  
  
  本部分中的主题将介绍这一配置过程。  
  
## <a name="in-this-section"></a>本节内容  
  
-   [配置 XML 文件](../core/configuring-the-xml-file.md)  
  
-   [如何针对 ENTSSO MA 配置 MIIS](../core/how-to-configure-miis-for-entsso-ma.md)  
  
-   [如何配置 ENTSSO 以实现 MIIS 密码同步](../core/how-to-configure-entsso-for-miis-password-sync.md)