---
title: 删除主机实例 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 35a06480-0962-4bdc-add2-56f979a2f1c9
caps.latest.revision: 23
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 6ecc7999e807b4036f80e8fdd1941d447f7af163
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "37023579"
---
# <a name="delete-a-host-instance"></a>删除主机实例

## <a name="overview"></a>概述
可以使用 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理控制台或 Windows 管理规范 (WMI) 来删除主机实例。 有关主机实例的详细信息，请参阅[主机实例](../core/host-instances.md)。 有关使用 WMI 删除主机实例的信息，请参阅**MSBTS_HostInstance (WMI)** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]。
  
 在删除主机实例时，将会从关联的服务器中删除 izTalk Server 运行时的实例，并更新 BizTalk 管理数据库以从该主机中删除该实例。  
  
 为了避免在删除主机实例时丢失消息，BizTalk Server 会在实际删除该实例之前完成所有的处理任务。  
  
## <a name="prerequisites"></a>必要條件  
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
  
1. 单击**启动**，单击**所有程序**，单击[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]，然后单击**BizTalk Server 管理**。  
  
2. 在控制台树中，展开**BizTalk Server 管理**，展开 BizTalk 组，单击**平台设置**，然后单击**主机实例**。  
  
3. 在详细信息窗格中，右键单击你想要删除，然后单击该主机实例**删除**。  
  
4. 在中**确认删除主机实例**对话框中，单击**是**。  
  
   > [!NOTE]
   >  如果 BizTalk Server 无法删除该主机实例，则将会显示一个对话框，您可以在此对话框中强制删除该主机实例。 阅读完后提供的信息，请单击**是**以删除该主机实例。  
  
## <a name="see-also"></a>请参阅  
 [管理 BizTalk 主机和主机实例](../core/managing-biztalk-hosts-and-host-instances.md)   
 [如何添加主机实例](../core/how-to-add-a-host-instance.md)   
 [如何启动主机实例](../core/how-to-start-a-host-instance.md)   
 [如何停止主机实例](../core/how-to-stop-a-host-instance.md)   
 [如何修改主机实例属性](../core/how-to-modify-host-instance-properties.md)