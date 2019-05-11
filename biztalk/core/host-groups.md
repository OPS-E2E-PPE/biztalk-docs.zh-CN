---
title: 主机组 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 0d92478b-b3a2-4c5a-925e-5495ee481e82
caps.latest.revision: 15
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 93e56411a55fefd4c54c1a0583b619e68b868e2c
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65344270"
---
# <a name="host-groups"></a>主机组

## <a name="overview"></a>概述
主机组是 （默认情况下，名为 BizTalk Application Users 组） 的 Windows 组用于对进程内 BizTalk 主机 （BizTalk Server 中的主机进程） 具有访问权限的帐户。 建议使用一个主机组的每个进程内主机在环境中。  
  
 只能将一个主机关联与一个 Windows 组 (称为*主机组*)。 主机组必须在所有相关的 BizTalk Server 数据库中具有 SQL Server 登录名和特权。 时将主机与主机组相关联，可以授予主机的主机组的权限。  
  
 如果你使用配置向导创建主机，并指定要使用的主机的本地 Windows 组，配置向导将自动创建两个 Windows 组。 这些组的默认名称是 BizTalk Application Users 组和 BizTalk Isolated Host Users 组。  
  
 当您创建与主机组相关联的主机的主机实例时，该实例将继承主机组的数据库权限。  
  
 主机组是主机 Windows Management Instrumentation (WMI) 对象的属性。 可以更改主机是否存在任何主机的实例所属的 Windows 组。  
  
 指定当您创建一个主机时，主机所属的主机组。 BizTalk WMI 提供程序授予权限的主机组对主机拥有 （例如，运行时功能，包括 SQL Server 登录名和数据库用户访问权限所需的 BizTalk Server 权限）。 您必须指定正确的服务帐户 （主机） 时创建的主机实例，以便 BizTalk Server WMI 提供程序的主机组的权限授予主机实例。  
  
> [!NOTE]
>  如果你想要创建本地主机组，可以创建一个本地 Windows 组并将域用户分配为组的成员。 如果为主机指定本地 Windows 组，Windows 组成员，无论是域或本地用户，可以使用作为主机实例登录用户。  

## <a name="required-permissions"></a>所需的权限  
 主机组需要以下权限：  
  
-   它必须是以下数据库中的 BTS_HOST_USERS SQL Server 角色的成员：  
  
    -   BizTalk 管理 
  
    -   MessageBox  
  
    -   规则引擎  
  
    -   跟踪  
  
    -   BAM 主导入  
  
-   它必须属于 BTS_\<进程内主机名称\>（_u） MessageBox 数据库的 SQL Server 角色  
  
-   它必须是 BAM 主导入数据库中的 BAM_EVENT_WRITER SQL Server 角色的成员。  
  
> [!NOTE]
>  如果为跟踪主机指定一个主机，BizTalk Server 管理自动从跟踪数据库的 SQL Server 角色中删除 BizTalk 主机组。 从 BizTalk 管理数据库和 MessageBox 数据库的 SQL Server 角色，必须手动删除 BizTalk 主机组。 有关将主机指定为跟踪主机的信息，请参阅[修改主机属性](../core/how-to-modify-host-properties.md)。  
  
## <a name="see-also"></a>请参阅  
 [实体](../core/entities.md)