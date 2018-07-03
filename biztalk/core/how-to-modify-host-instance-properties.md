---
title: 更改主机实例属性 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: a35ca0c8-89b3-483a-b2fc-c8f43a8864d1
caps.latest.revision: 22
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 53a64257f752e161963539256dcaca3f7f8f1077
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "37003342"
---
# <a name="update-host-instance-properties"></a>更新主机实例属性

## <a name="overview"></a>概述
可以使用 BizTalk Server 管理控制台或 Windows 管理规范 (WMI) 来修改主机实例。 可以修改运行主机实例的服务帐户。 还可以禁用主机实例。 例如，如果要保留主机实例的设置并且不想启动它，则可以将其禁用。 有关主机实例的详细信息，请参阅[主机实例](../core/host-instances.md)。  
  
 受信任主机和非信任主机的实例不能使用相同的服务帐户。 如果希望更改某个主机实例的信任设置，并且该主机实例与其他主机实例使用了相同的服务帐户，请执行以下操作之一：  
  
-   对于要更改信任设置的主机实例，可以将其服务帐户更改为新的服务帐户。  
  
-   可以将主机实例的服务帐户更改为具有相同信任设置的其他主机实例所用的现有服务帐户。  
  
-   可以删除主机实例，然后使用不同的信任设置和服务帐户重新进行创建。  
  
> [!CAUTION]
>  必须通过更新主机实例的属性来更改主机实例的凭据。 如果更改相应服务的凭据，则为主机实例指定的服务帐户必须是主机上的组的成员。 不要使用服务管理单元或计算机管理控制台来更改主机实例的凭据，否则，主机实例可能无法正常运行。  
  
> [!CAUTION]
>  如果更改主机实例的凭据，则还必须更改相应的 SQL Server 凭据。 如果不更新 SQL Server 凭据，则主机实例将无法正常工作。  
  
 有关使用 WMI 修改主机实例的信息，请参阅**MSBTS_HostInstance (WMI)** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]。
  
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
  
2. 在控制台树中，展开[!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)]，展开 BizTalk 组，单击**平台设置**，然后单击**主机实例**。  
  
3. 在详细信息窗格中，右键单击你想要修改，然后单击该主机实例**属性**。  
  
4. 在中**主机实例属性**对话框中，单击**配置**若要修改的服务帐户信息。  
  
5. 在中**登录凭据**对话框框中，输入帐户名和密码的帐户的主机实例将在其下运行，然后依次**确定**。  
  
6. 在中**主机实例属性**对话框中，执行以下操作，然后依次**确定**:  
  
   |使用此选项|执行的操作|  
   |--------------|----------------|  
   |**主机名**|显示与所选服务器关联的主机名称。|  
   |**Server**|显示与所选主机关联的服务器。|  
   |**登录**|显示用于运行主机实例的新服务帐户的帐户名。|  
   |**配置**|单击此项可显示**登录凭据**对话框框中，您可以在其中输入帐户名称和主机实例将运行的帐户的密码。|  
   |**禁止主机实例启动**|选中此复选框可将所选主机的状态从“已启用”改为“已禁用”。 如果不希望启动主机实例，但还要保留其设置，禁用主机实例就十分有用。|  
  
## <a name="see-also"></a>请参阅  
 [管理 BizTalk 主机和主机实例](../core/managing-biztalk-hosts-and-host-instances.md)   
 [添加主机实例](../core/how-to-add-a-host-instance.md)   
 [启动主机实例](../core/how-to-start-a-host-instance.md)   
 [停止主机实例](../core/how-to-stop-a-host-instance.md)   
 [删除主机实例](../core/how-to-delete-a-host-instance.md)