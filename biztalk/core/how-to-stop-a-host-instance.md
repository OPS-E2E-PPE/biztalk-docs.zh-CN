---
title: 停止主机实例 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: c1f2e0c1-a387-4182-82ef-e25f49ac509b
caps.latest.revision: 20
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ac42fce4aa18be316d5090aa95240437d6deed47
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65333976"
---
# <a name="stop-a-host-instance"></a>停止主机实例

## <a name="overview"></a>概述
可以使用[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理控制台或 Windows Management Instrumentation (WMI) 来停止主机实例。 必须先停止主机实例，然后才能将其删除，或从计算机中删除 BizTalk Server。 你可以停止已安装并启动的主机实例。 有关主机实例的详细信息，请参阅[主机实例](../core/host-instances.md)。  
  
 有关使用 WMI 停止主机实例的信息，请参阅**MSBTS_HostInstance (WMI)** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]。
  
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
  
3. 在详细信息窗格中，右键单击你想要停止，然后单击该主机实例**停止**。  
  
    主机实例的状态将变为**已停止**。  
  
   停止主机实例后，可以启动它，将其删除，或从计算机中删除 BizTalk Server。 有关启动主机实例的信息，请参阅[如何启动主机实例](../core/how-to-start-a-host-instance.md)。 有关删除主机实例的信息，请参阅[如何删除主机实例](../core/how-to-delete-a-host-instance.md)。  
  
## <a name="see-also"></a>请参阅  
 [管理 BizTalk 主机和主机实例](../core/managing-biztalk-hosts-and-host-instances.md)   
 [如何添加主机实例](../core/how-to-add-a-host-instance.md)   
 [如何启动主机实例](../core/how-to-start-a-host-instance.md)   
 [如何删除主机实例](../core/how-to-delete-a-host-instance.md)   
 [如何修改主机实例属性](../core/how-to-modify-host-instance-properties.md)