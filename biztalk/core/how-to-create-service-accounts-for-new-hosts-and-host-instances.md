---
title: 如何创建服务帐户为新主机和主机实例 |Microsoft Docs
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
ms.openlocfilehash: 983cbb2b21b2a9027830f9bad326798b84c0f2bc
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65385405"
---
# <a name="how-to-create-service-accounts-for-new-hosts-and-host-instances"></a>如何创建服务帐户为新主机和主机实例
安装和配置 BizTalk Server 的单台计算机上时，Configuration Manager 会配置必要的 Windows 组和用户帐户。  
  
 必须手动创建 Windows 组和用户帐户，并在运行 Configuration Manager 之前的用户帐户添加到域环境中的 Windows 组。 有关详细信息，请参阅[域组](../core/domain-groups.md)。  
  
 创建新的主机或主机实例前，必须执行以下过程。  
  
## <a name="prerequisites"></a>先决条件  
 您必须为要执行此过程的 Administrators 或 Domain Admins 组的成员身份登录。  
  
### <a name="to-create-service-accounts-for-new-hosts-or-host-instances"></a>若要创建新主机或主机实例服务帐户  
  
1.  您将创建的新主机创建主机 Windows 组。 有关创建新的主机的详细信息，请参阅[如何创建新的主机](../core/how-to-create-a-new-host.md)。  
  
2.  创建将添加到新主机的每个主机实例的服务帐户。 有关创建新的主机实例的详细信息，请参阅[如何将主机实例添加](../core/how-to-add-a-host-instance.md)。  
  
3.  将服务帐户添加到主机 Windows 组中，根据需要。 有关必须向其添加服务帐户的 Windows 组的信息，请参阅[Windows 组和 BizTalk Server 中的用户帐户](../core/windows-groups-and-user-accounts-in-biztalk-server.md)。  
  
4.  使用 Windows 组和服务帐户时创建的主机和主机实例。  
  
    > [!NOTE]
    >  未指定\<*计算机名*\>\ 作为具有本地组的单个计算机设置中的前缀。  
  
    > [!NOTE]
    >  如果使用域组，必须指定\<*域 NetBIOS 名称*\>\ 作为主机 Windows 组名的前缀。 例如 CONTOSO\btssvc。  
  
## <a name="see-also"></a>请参阅  
 [管理主机和服务帐户](../core/managing-hosts-and-service-accounts.md)   
 [管理 BizTalk Server 安全性](../core/managing-biztalk-server-security.md)   
 [如何管理 BizTalk Server Administrators 组](../core/how-to-manage-the-biztalk-server-administrators-group.md)   
 [管理 Windows 组和用户帐户的最佳做法](../core/best-practices-for-managing-windows-groups-and-user-accounts.md)