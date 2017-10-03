---
title: "如何使用 ENTSSO 管理代理 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 9c89b494-db12-4d2a-a030-6acd34489cab
caps.latest.revision: "7"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 03c0f7d2c04a2707cf965f64ff7a559d8642a12c
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-use-the-entsso-management-agent"></a>如何使用 ENTSSO 管理代理
企业单一登录 (SSO) 的此版本包含 Microsoft Identity Integration Server (MIIS) 的管理代理 (MA)，后者将企业 SSO 与 MIIS 的帐户同步功能集成在一起。 这样，MIIS 管理员便可管理 SSO 数据库中的 SSO 映射。  
  
 在企业 SSO 映射创建 Windows 域帐户之间 (*域名 \ 用户名*) 和外部凭据。 如果你有 Active Directory 管理代理，并管理代理为外部数据源 (示例： RACF MA)，你可以使用企业 SSO MA (ENTSSO MA) 来管理 SSO 数据库中的映射。 ENTSSO MA 是*基于调用的导出*仅管理代理。  
  
 您需在三个不同的部分配置该管理代理：  
  
-   配置文件 (ENTSSO.xml)  
  
-   MIIS 用户界面  
  
-   ENTSSO 用户界面  
  
 本部分中的主题将介绍这一配置过程。  
  
## <a name="in-this-section"></a>本节内容  
  
-   [配置 XML 文件](../core/configuring-the-xml-file.md)  
  
-   [如何为 ENTSSO MA 配置 MIIS](../core/how-to-configure-miis-for-entsso-ma.md)  
  
-   [如何配置 ENTSSO miis 进行密码同步](../core/how-to-configure-entsso-for-miis-password-sync.md)