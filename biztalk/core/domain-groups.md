---
title: 域组 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 9adc090e-e18c-46b6-b985-49b200d42966
caps.latest.revision: 11
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: afa529aa98f0eee379f4e2000970549ab9305a20
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65389318"
---
# <a name="domain-groups-in-biztalk"></a>在 BizTalk 中的域组
BizTalk Server 支持单个和多计算机配置中的域组和用户帐户。 对于多计算机配置，必须遵守的要求和安装指南中的多服务器环境注意事项本部分中提供。 有关详细信息，请参阅[安装概述](../install-and-config-guides/biztalk-server-what-s-new-installation-configuration-and-upgrade.md)。  
  
## <a name="before-you-begin"></a>开始之前
-   如果你的 BizTalk Server 配置为使用域组，必须手动创建组，然后再配置 BizTalk Server。 配置管理器无法创建域组。  
  
-   创建域组和/或用户帐户之后, 将用户帐户添加到根据在组隶属关系的适当组[Windows 组和 BizTalk Server 中的用户帐户](../core/windows-groups-and-user-accounts-in-biztalk-server.md)。  
  
-   使用 **\<DomainName\>\\< 用户名\>** 指定 Configuration Manager 中的域帐户信息时。  
  
-   BizTalk Server 的所有聚类分析方案要求使用域帐户。 使用 SQL Server 群集或群集的 SSO 服务器 （主密钥服务器），不能使用本地帐户。  
  
-   安装和配置 BizTalk Server 的管理员必须是以下组的成员：SSO Administrators （仅当配置主密钥服务器）;本地管理员;sysadmin SQL Server 角色;OLAP 管理员。  
  
> [!NOTE]
>  如果在 SSO Administrators 和 SSO Affiliate Administrators，配置过程中指定域组，并且有足够的特权，可以自动创建的域组。 如果你没有足够的权限，请确保这些组已存在。  
  
## <a name="see-also"></a>请参阅  
 [本地组](../core/local-groups.md)   
 [安装概述](../install-and-config-guides/biztalk-server-what-s-new-installation-configuration-and-upgrade.md)   
 [Windows 组和 BizTalk Server 中的用户帐户](../core/windows-groups-and-user-accounts-in-biztalk-server.md)
