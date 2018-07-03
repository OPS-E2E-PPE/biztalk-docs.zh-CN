---
title: 管理主机和服务帐户 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- security, managing
- managing [user accounts]
- service accounts, security
- managing [hosts], security
- security, hosts
- managing [Windows groups]
- hosts, security
- security, service accounts
- Windows groups, managing
- user accounts, managing
ms.assetid: 25797571-f1f9-42a4-8fff-5b03076bbe36
caps.latest.revision: 16
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f0f33a484d67981bb72908243b82e7835e0390e3
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "37016111"
---
# <a name="managing-hosts-and-service-accounts"></a>管理主机和服务帐户
配置 BizTalk Server 后，必须对 Windows 组和用户帐户进行管理。 本部分提供有关如何管理 BizTalk Server 中的这些帐户的信息。  
  
> [!NOTE]
>  在多服务器 BizTalk Server 安装中，必须使用全局域组。 而在单服务器 BizTalk Server 安装中，既可以使用全局域组，也可以使用本地组。  
  
 要执行以下任务，您必须是 Windows 管理员：  
  
- 创建主机 Windows 组  
  
- 为每个主机实例创建服务帐户  
  
- 向该主机的 Windows 组中添加服务帐户  
  
- 修改与该主机相关联的 Windows 组  
  
  有关完整列表和组和 BizTalk Server 中其关联的用户帐户的说明，请参阅[Windows 组和 BizTalk Server 中的用户帐户](../core/windows-groups-and-user-accounts-in-biztalk-server.md)。  
  
  最低安全用户权限来执行管理任务的详细信息，请参阅[最低安全用户权限](../core/minimum-security-user-rights.md)。  
  
## <a name="in-this-section"></a>本节内容  
  
-   [如何创建服务帐户为新主机和主机实例](../core/how-to-create-service-accounts-for-new-hosts-and-host-instances.md)  
  
-   [如何更改服务帐户和密码](../core/how-to-change-service-accounts-and-passwords.md)