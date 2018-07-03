---
title: 删除主机 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: e3df8719-27cb-4010-82e3-68226ab74b17
caps.latest.revision: 20
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e65c2997fa19ed961515285ce04f51acc4c196e5
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36995278"
---
# <a name="delete-a-host"></a>删除主机
只有在下列情况下才能删除主机：  

- 该主机不是默认主机。  

- 该主机不是进行主机跟踪的唯一主机。  

- 该主机未用作任何适配器处理程序的宿主。  

- 该主机没有已登记的业务流程。  

- 该主机没有已启动的实例。  

- 未对该主机进行群集。  

  有关主机的详细信息，请参阅[主机](../core/hosts.md)。  

## <a name="prerequisites"></a>必要條件  
 必须具有以下用户权限才能创建主机、修改主机属性和删除主机：  

-   必须是 BizTalk Server Administrators 组的成员。  

-   必须在 SQL Server 中具有以下权限：  

    -   必须是 SQL Server 管理员，或者是 BizTalk 跟踪数据库 (BizTalk DTADb)、MessageBox 数据库 (BizTalkMsgBoxDb) 和 BAM 主导入数据库 (BAMPrimaryImport) 中的 db_owner 或 db_securityadmin SQL Server 数据库角色的成员。  

    -   必须是 MessageBox 数据库所在的所有计算机上的 sysadmin SQL Server 角色的成员，或者是所有 MessageBox 数据库的 db_owner 或 db_ddladmin SQL Server 角色的成员。  

## <a name="steps"></a>步骤 

1. 单击**启动**，单击**所有程序**，单击[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]，然后单击**BizTalk Server 管理**。  

2. 在控制台树中，展开[!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)]，展开 BizTalk 组，单击**平台设置**，然后单击**主机**。  

3. 在细节窗格中，右键单击你想要删除，然后单击的主机**删除**。  

4. 在中**确认主机删除**对话框中，单击**是**。  

## <a name="see-also"></a>请参阅  
- [管理 BizTalk 主机和主机实例](../core/managing-biztalk-hosts-and-host-instances.md)   
- [如何创建新的主机](../core/how-to-create-a-new-host.md)   
- [如何修改主机属性](../core/how-to-modify-host-properties.md)   
- **MSBTS_Host (WMI)** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]
