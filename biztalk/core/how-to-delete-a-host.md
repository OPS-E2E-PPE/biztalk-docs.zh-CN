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
ms.openlocfilehash: 351311d526500529c293fffbd400a5c1d317ed16
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65385389"
---
# <a name="delete-a-host"></a>删除主机
可以删除仅在下列情况中的主机：  

- 它不是默认主机。  

- 它不进行主机跟踪的唯一主机。  

- 它不承载任何适配器处理程序。  

- 它有没有已登记的业务流程。  

- 没有已启动的主机的实例。  

- 如果主机未群集化。  

  有关主机的详细信息，请参阅[主机](../core/hosts.md)。  

## <a name="prerequisites"></a>先决条件  
 必须具有以下的用户权限，才能创建主机、 修改主机属性和删除主机：  

-   必须是 BizTalk Server Administrators 组的成员。  

-   SQL Server 中，必须具有以下权限：  

    -   您必须是 SQL Server 管理员或在 BizTalk 跟踪数据库 (BizTalk DTADb)、 MessageBox (BizTalkMsgBoxDb) 数据库和 BAM 主导入数据库 （中的 db_owner 或 db_securityadmin 的 SQL Server 数据库角色的成员BAMPrimaryImport)。  

    -   其中有 MessageBox 数据库或所有 MessageBox 数据库的 db_owner 或 db_ddladmin SQL Server 角色的成员，您必须是所有计算机上的 sysadmin SQL Server 角色的成员。  

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
