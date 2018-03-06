---
title: "主机组 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 0d92478b-b3a2-4c5a-925e-5495ee481e82
caps.latest.revision: 
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 4b3132b4084ed0d153895e252c5c64419ce0ac72
ms.sourcegitcommit: 32f380810b90b70e5df7be72a6a14988a747868e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/28/2018
---
# <a name="host-groups"></a>主机组

## <a name="overview"></a>概述
主机组是用于对进程内 BizTalk 主机（BizTalk Server 中的主机进程）具有访问权限的帐户的 Windows 组（默认情况下名为 BizTalk Application Users 组）。 建议对环境中的每个进程内主机分别使用一个主机组。  
  
 你只能将一个 Windows 组与关联的主机 (称为 *主机组*)。 主机组必须在所有相关 BizTalk Server 数据库中具有 SQL Server 登录名和权限。 在将主机与主机组相关联时，会将主机组的权限授予该主机。  
  
 如果使用配置向导创建主机，并指定将为主机使用本地 Windows 组，则配置向导将自动创建两个 Windows 组。 这两个组的默认名称为 BizTalk Application Users 组和 BizTalk Isolated Host Users 组。  
  
 在创建与主机组关联的主机的实例时，该实例将继承主机组的数据库权限。  
  
 主机组是主机 Windows 管理规范 (WMI) 对象的属性。 如果主机没有实例，则可以更改该主机所属的 Windows 组。  
  
 在创建主机时指定主机所属的主机组。 BizTalk WMI 提供程序会将主机组拥有的权限（例如，运行时功能所需的 BizTalk Server 权限，包括 SQL Server 登录和数据库用户访问）授予该主机。 在创建主机实例时，必须指定正确的服务帐户（主机），以便 BizTalk Server WMI 提供程序将主机组的权限授予该主机实例。  
  
> [!NOTE]
>  若要创建本地主机组，可以创建一个本地 Windows 组，然后分配一个域用户作为该组的成员。 如果为主机指定本地 Windows 组，则该 Windows 组成员（无论是域用户还是本地用户）可以用作主机实例登录用户。  

## <a name="required-permissions"></a>所需的权限  
 主机组需要以下权限：  
  
-   它必须是以下数据库中的 BTS_HOST_USERS SQL Server 角色的成员：  
  
    -   BizTalk 管理 
  
    -   MessageBox  
  
    -   规则引擎  
  
    -   跟踪  
  
    -   BAM 主导入  
  
-   它必须属于 BTS_\<进程内主机名\>（_u） SQL Server 数据库角色的 MessageBox  
  
-   它必须是 BAM 主导入数据库中的 BAM_EVENT_WRITER SQL Server 角色的成员。  
  
> [!NOTE]
>  如果将某个主机指定为跟踪主机，对于跟踪数据库，BizTalk Server 管理将自动从 SQL Server 角色中删除 BizTalk 主机组。 对于 BizTalk 管理数据库和 MessageBox 数据库，必须手动从 SQL Server 角色中删除 BizTalk 主机组。 有关作为跟踪主机指定主机的信息，请参阅[修改主机属性](../core/how-to-modify-host-properties.md)。  
  
## <a name="see-also"></a>另请参阅  
 [实体](../core/entities.md)