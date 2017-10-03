---
title: "创建新的主机 |Microsoft 文档"
descriptions: Use BizTalk Administration to create a new host in BizTalk Server
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 811e6e57-5c37-471a-aff4-5b2b68c367b1
caps.latest.revision: "27"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 700f0bb43a4f31b76819e7aca6fe5895cc2b6ab6
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="create-a-new-host"></a>创建新的主机
BizTalk 主机是诸如适配器处理程序、接收位置（包括管道）和业务流程等项的逻辑容器。 建议使用单独的主机来处理、接收和发送消息，并且对可信任项和非可信任项使用不同的主机，以便实施安全措施并改进主机的可管理性。 对于每个 BizTalk Server，只能安装一个主机实例。 有关主机的详细信息，请参阅[主机](../core/hosts.md)。  
  
 有关使用 Windows Management Instrumentation (WMI) 来创建新的主机的信息，请参阅**MSBTS_Host (WMI)** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]。
  
## <a name="prerequisites"></a>先决条件  
 必须具有以下用户权限才能创建主机、修改主机属性和删除主机：  
  
-   必须是 BizTalk Server Administrators 组的成员。  
  
-   必须在 SQL Server 中具有以下权限：  
  
    -   必须是 SQL Server 管理员，或者是 BizTalk 跟踪 (BizTalk DTADb) 数据库、MessageBox (BizTalkMsgBoxDb) 数据库和 BAM 主导入 (BAMPrimaryImport) 数据库中的 db_owner 或 db_securityadmin SQL Server 数据库角色的成员。  
  
    -   必须是 MessageBox 数据库所在的所有计算机上的 sysadmin SQL Server 角色的成员，或者是所有 MessageBox 数据库的 db_owner 或 db_ddladmin SQL Server 角色的成员。  
  
## <a name="steps"></a>步骤
  
1.  单击**启动**，单击**所有程序**，单击[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]，然后单击**BizTalk Server 管理**。  
  
2.  在控制台树中，展开[!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)]，展开 BizTalk 组，单击**平台设置**，然后单击**主机**。  
  
3.  在细节窗格中，右键单击**主机**，单击**新建**，然后单击**主机**。  
  
4.  在**主机属性**对话框中，在**常规**选项卡上，执行以下操作：  
  
    |使用此选项|执行的操作|  
    |--------------|----------------|  
    |**名称**|显示主机的名称。 创建主机时命名该主机。 主机名称的长度不得超过 80 个字符。|  
    |**类型**|显示主机类型。 进程内主机可以作为业务流程、某些发送处理程序和接收处理程序的宿主。 独立主机是 BizTalk Server 之外的处理边界，并且是某些发送和接收处理程序必需的。 可以向进程内主机登记业务流程，并且进程内主机可以作为发送或接收处理程序的宿主。|  
  
     **选项**  
  
    |使用此选项|执行的操作|  
    |--------------|----------------|  
    |**允许主机跟踪**|选定此复选框，以指示主机将处理运行状况监视和业务数据。 如果选中此复选框，则当前主机将对 MessageBox 数据库中的跟踪表以及 BizTalk 跟踪数据库具有读/写权限。 因此，运行在此主机中的任何对象也具有对这些数据库的读/写权限。 如果清除该复选框，则主机将只对 MessageBox 数据库中的跟踪表具有写权限，并且无权访问 BizTalk 跟踪数据库。|  
    |**受信任的身份验证**|选中此复选框可指定 BizTalk Server 应信任此主机。|  
    |**仅限 32 位**|如果希望使主机实例进程在 32 位和 64 位服务器上均创建为 32 位，请选中此复选框。 如果清除此复选框，主机实例进程将在 32 位服务器上创建为 32 位，在 64 位服务器上创建为 64 位。|  
    |**将此组中的默认主机**|选中此复选框可将此主机标识为默认主机。 除非明确选择其他主机，否则创建的端口和业务流程将自动使用默认主机作为业务流程的宿主。 如果此复选框被选中并且不可用，则此主机是默认主机。|  
    |**Windows 组**|键入主机的本地组或域组。 Windows 组的成员将具有运行此主机实例的权限。|  
  
5.  上**证书**选项卡上，执行以下操作，，然后单击**确定**:  
  
    |使用此选项|执行的操作|  
    |--------------|----------------|  
    |**公用名**|显示所显示解密证书的说明。|  
    |**指纹**|显示用于对此主机的入站消息进行解密的私钥证书的指纹。 证书指纹的格式 HHHH HHHH HHHH HHHH HHHH HHHH HHHH HHHH HHHH HHHH，其中 H 是十六进制数字 （介于 0 到 9） 或从 A 到 F 字母。|  
    |**删除证书**|单击此项可从主机删除所显示解密证书。|  
    |**浏览**|单击此项可显示**Windows 安全性**对话框中，其中从当前用户或你想要使用与主机的个人存储区中选择解密证书。|  
  
## <a name="see-also"></a>另请参阅  
 [管理 BizTalk 主机和主机实例](../core/managing-biztalk-hosts-and-host-instances.md)   
 [修改主机属性](../core/how-to-modify-host-properties.md)   
 [删除主机](../core/how-to-delete-a-host.md)