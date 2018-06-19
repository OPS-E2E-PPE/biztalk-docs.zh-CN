---
title: 如何创建服务帐户的新主机和主机实例 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- Configuration Manager, service accounts
- Windows groups, service accounts
- Configuration Manager
- service accounts, Windows groups
- hosts, service accounts
- service accounts, hosts
- service accounts, Configuration Manager
- service accounts, creating
- creating, service accounts
ms.assetid: cef97f4a-8db1-41b6-9614-608c2fbf59a9
caps.latest.revision: 15
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 5d4887d78466340b12b95ed43d27523955ab0689
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/28/2017
ms.locfileid: "25969372"
---
# <a name="how-to-create-service-accounts-for-new-hosts-and-host-instances"></a>如何为新主机和主机实例创建服务帐户
在单台计算机上安装和配置 BizTalk Server 时，配置管理器将配置必需的 Windows 组和用户帐户。  
  
 必须手动创建 Windows 组和用户帐户，并将用户帐户添加到域环境中的 Windows 组，然后才能运行配置管理器。 有关详细信息，请参阅[域组](../core/domain-groups.md)。  
  
 在创建新主机或主机实例前，必须先执行以下步骤。  
  
## <a name="prerequisites"></a>先决条件  
 必须以 Administrators 组或域 Admins 组成员的身份登录，才能执行此过程。  
  
### <a name="to-create-service-accounts-for-new-hosts-or-host-instances"></a>为新主机或主机实例创建服务帐户  
  
1.  为您将要创建的新主机创建主机 Windows 组。 有关创建新的主机的详细信息，请参阅[如何创建新的主机](../core/how-to-create-a-new-host.md)。  
  
2.  为将要添加到新主机中的每个主机实例创建服务帐户。 有关创建新的主机实例的详细信息，请参阅[如何添加一个主机实例](../core/how-to-add-a-host-instance.md)。  
  
3.  可根据需要向该主机的 Windows 组中添加服务帐户。 您必须将服务帐户添加到其中的 Windows 组有关的信息，请参阅[Windows 组和 BizTalk Server 中的用户帐户](../core/windows-groups-and-user-accounts-in-biztalk-server.md)。  
  
4.  在创建主机和主机实例时，可使用 Windows 组和服务帐户。  
  
    > [!NOTE]
    >  未指定\<*计算机名称*\>\ 作为单个计算机的设置与本地组中的前缀。  
  
    > [!NOTE]
    >  如果你正在使用域组，你必须指定\<*域 NetBIOS 名称*\>\ 作为主机 Windows 组名的前缀。 例如 CONTOSO\btssvc。  
  
## <a name="see-also"></a>另请参阅  
 [管理主机和服务帐户](../core/managing-hosts-and-service-accounts.md)   
 [管理 BizTalk Server 安全性](../core/managing-biztalk-server-security.md)   
 [如何管理 BizTalk Server Administrators 组](../core/how-to-manage-the-biztalk-server-administrators-group.md)   
 [管理 Windows 组和用户帐户的最佳做法](../core/best-practices-for-managing-windows-groups-and-user-accounts.md)