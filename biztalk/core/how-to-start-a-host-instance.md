---
title: "启动主机实例 |Microsoft 文档"
description: "使用 BizTalk 管理在 BizTalk Server 中启动的主机实例"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: a96a4362-2147-4b8e-a270-bf9a17477ba3
caps.latest.revision: "18"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: dd5cccc48b33dda4b6458f8dfa8f56a84ad3cd62
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="start-a-host-instance"></a>启动主机实例
可以使用 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理控制台或 Windows 管理规范 (WMI) 来启动主机实例。 在添加或停止主机实例之后，必须启动该实例以便其运行并将消息路由至 MessageBox 数据库。  
  
> [!IMPORTANT]
>  为主机实例指定的服务帐户应该是所关联主机的 Windows 组的成员。 否则，主机实例在运行时可能不具有相应的权限或验证。 此外，为安全起见，该帐户应具有最低特权，因为以主机实例为宿主的业务流程可能会执行有恶意的自定义代码。  
  
 有关主机实例的详细信息，请参阅[主机实例](../core/host-instances.md)。 有关使用 WMI 来启动主机实例的信息，请参阅**MSBTS_HostInstance (WMI)** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]。
  
## <a name="prerequisites"></a>先决条件  
 若要执行此过程，则必须以 Administrators 组和 BizTalk Server Administrators 组成员的身份登录。  
  
 此外，您还必需是以下数据库所在服务器上的 db_securityadmin SQL Server 数据库角色和 securityadmin SQL Server 角色的成员：  
  
-   BAM 主导入 (BAMPrimaryImport)  
  
-   BizTalk 管理 (BizTalkMgmtDb)  
  
-   BizTalk MessageBox (BizTalkMsgBoxDb)（全部）  
  
-   BizTalk 跟踪 (BizTalk DTADb)  
  
-   规则引擎 (BizTalkRuleEngineDb)  
  
> [!CAUTION]
>  建议使用 BizTalk Server 管理控制台或 Windows 管理规范 (WMI) 脚本来更新主机实例的帐户信息。 这样可以确保 BizTalk Server 能够更新 BizTalk Server 数据库中的帐户信息，并在数据库与主机实例之间保持安全配置同步。  
  
## <a name="steps"></a>步骤
  
1.  单击**启动**，单击**所有程序**，单击[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]，然后单击**BizTalk Server 管理**。  
  
2.  在控制台树中，展开**BizTalk Server 管理**，展开 BizTalk 组，单击**平台设置**，然后单击**主机实例**。  
  
3.  在详细信息窗格中，右键单击你想要启动，，然后单击该主机实例**启动**。  
  
     主机实例的状态更改为**启动挂起**。 主机实例启动后，状态将更改为**运行**。  
  
 启动主机实例之后，可以停止它，以防止其将消息路由至 MessageBox 数据库。 必须先停止主机实例才能从给定计算机上删除 BizTalk Server。 要停止的主机实例的信息，请参阅[如何停止主机实例](../core/how-to-stop-a-host-instance.md)。  
  
## <a name="see-also"></a>另请参阅  
 [管理 BizTalk 主机和主机实例](../core/managing-biztalk-hosts-and-host-instances.md)   
 [添加一个主机实例](../core/how-to-add-a-host-instance.md)   
 [停止主机实例](../core/how-to-stop-a-host-instance.md)   
 [删除的主机实例](../core/how-to-delete-a-host-instance.md)   
 [修改主机实例属性](../core/how-to-modify-host-instance-properties.md)