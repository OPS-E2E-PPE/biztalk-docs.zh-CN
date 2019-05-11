---
title: 启动主机实例 |Microsoft Docs
description: 使用 BizTalk 管理 BizTalk Server 中启动主机实例
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: a96a4362-2147-4b8e-a270-bf9a17477ba3
caps.latest.revision: 18
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 0dc17eec6a1782a1b607be812003978793d49c6f
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65383838"
---
# <a name="start-a-host-instance"></a>启动主机实例
可以使用[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理控制台或 Windows Management Instrumentation (WMI) 来启动主机实例。 添加或停止主机实例后，您必须启动它，以便它正在运行，并且将消息路由到 MessageBox 数据库。  
  
> [!IMPORTANT]
>  为主机实例指定的服务帐户应是关联的主机的 Windows 组的成员。 否则，主机实例可能没有适当的权限或在运行时的身份验证。 此外，出于安全原因，该帐户应具有最小特权因为业务流程主机实例所承载的可能执行潜在的恶意的自定义代码。  
  
 有关主机实例的详细信息，请参阅[主机实例](../core/host-instances.md)。 有关使用 WMI 启动主机实例的信息，请参阅**MSBTS_HostInstance (WMI)** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]。
  
## <a name="prerequisites"></a>先决条件  
 若要执行此过程，必须以 Administrators 组和 BizTalk Server Administrators 组的成员的身份登录。  
  
 此外，您还必须是 db_securityadmin SQL Server 数据库角色和以下数据库所在的服务器上的 securityadmin SQL Server 角色的成员：  
  
-   BAM 主导入 (BAMPrimaryImport)  
  
-   BizTalk 管理 (BizTalkMgmtDb)  
  
-   BizTalk MessageBox (BizTalkMsgBoxDb) （全部）  
  
-   BizTalk 跟踪 (BizTalk DTADb)  
  
-   规则引擎 (BizTalkRuleEngineDb)  
  
> [!CAUTION]
>  我们建议使用 BizTalk Server 管理控制台或 Windows Management Instrumentation (WMI) 脚本更新主机实例的帐户信息。 这可确保 BizTalk Server 可以更新 BizTalk Server 数据库中的帐户信息并保持数据库和同步的主机实例之间的安全配置。  
  
## <a name="steps"></a>步骤
  
1. 单击**启动**，单击**所有程序**，单击[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]，然后单击**BizTalk Server 管理**。  
  
2. 在控制台树中，展开**BizTalk Server 管理**，展开 BizTalk 组，单击**平台设置**，然后单击**主机实例**。  
  
3. 在详细信息窗格中，右键单击你想要开始，然后单击该主机实例**启动**。  
  
    主机实例的状态将变为**启动挂起**。 主机实例启动后，状态将更改为**运行**。  
  
   启动主机实例后，可以停止它以防止它将消息路由到 MessageBox 数据库。 可以从给定计算机上删除 BizTalk Server 之前，必须停止主机实例。 有关停止主机实例的信息，请参阅[如何停止主机实例](../core/how-to-stop-a-host-instance.md)。  
  
## <a name="see-also"></a>请参阅  
 [管理 BizTalk 主机和主机实例](../core/managing-biztalk-hosts-and-host-instances.md)   
 [添加主机实例](../core/how-to-add-a-host-instance.md)   
 [停止主机实例](../core/how-to-stop-a-host-instance.md)   
 [删除主机实例](../core/how-to-delete-a-host-instance.md)   
 [修改主机实例属性](../core/how-to-modify-host-instance-properties.md)