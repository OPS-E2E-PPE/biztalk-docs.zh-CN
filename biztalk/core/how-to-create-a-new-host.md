---
title: 创建新的主机 |Microsoft Docs
descriptions: Use BizTalk Administration to create a new host in BizTalk Server
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 811e6e57-5c37-471a-aff4-5b2b68c367b1
caps.latest.revision: 27
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: d16d1f8c3e38d085f14a45101e1a81e7377b0d6a
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65339995"
---
# <a name="create-a-new-host"></a>创建新的主机
BizTalk 主机是诸如适配器处理程序的逻辑容器，接收位置 （包括管道） 和业务流程。 我们建议对于处理、 接收和发送消息，使用单独的主机以及使用受信任和不可信任项不同的主机，以便实施安全措施和改进可管理性的主机。 可以安装每个 BizTalk server 的主机只有一个的实例。 有关主机的详细信息，请参阅[主机](../core/hosts.md)。  

 有关使用 Windows Management Instrumentation (WMI) 来创建新的主机的信息，请参阅**MSBTS_Host (WMI)** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]。

## <a name="prerequisites"></a>先决条件  
 必须具有以下的用户权限，才能创建主机、 修改主机属性和删除主机：  

-   必须是 BizTalk Server Administrators 组的成员。  

-   SQL Server 中，必须具有以下权限：  

    -   您必须是 SQL Server 管理员或在 BizTalk 跟踪 (BizTalk DTADb) 数据库、 MessageBox (BizTalkMsgBoxDb) 数据库和 BAM 主导入 (BAMPrimaryImport) 中的 db_owner 或 db_securityadmin 的 SQL Server 数据库角色的成员数据库。  

    -   其中有 MessageBox 数据库或所有 MessageBox 数据库的 db_owner 或 db_ddladmin SQL Server 角色的成员，您必须是所有计算机上的 sysadmin SQL Server 角色的成员。  

## <a name="steps"></a>步骤

1. 单击**启动**，单击**所有程序**，单击[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]，然后单击**BizTalk Server 管理**。  

2. 在控制台树中，展开[!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)]，展开 BizTalk 组，单击**平台设置**，然后单击**主机**。  

3. 在细节窗格中，右键单击**主机**，单击**新建**，然后单击**主机**。  

4. 在中**主机属性**对话框中，在**常规**选项卡上，执行以下操作：  

   |使用此选项|执行的操作|  
   |--------------|----------------|  
   |**名称**|显示主机的名称。 在创建时命名主机。 主机名不能超过 80 个字符的长度。|  
   |**类型**|显示主机类型。 进程内主机可以作为业务流程、 某些发送处理程序和接收处理程序。 独立主机是 BizTalk Server 之外的处理边界和所需的某些发送和接收处理程序。 您可以登记到进程内主机上，业务流程和进程内主机可以承载发送或接收处理程序。|  

    **选项**  


   |                  使用此选项                   |                                                                                                                                                                                                                                                                            执行的操作                                                                                                                                                                                                                                                                             |
   |---------------------------------------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
   |           **允许主机跟踪**           | 选中此复选框以指示主机将处理运行状况监视和业务数据。 如果选中此复选框，当前主机将具有 MessageBox 数据库中的跟踪表以及 BizTalk 跟踪数据库的读/写权限。 因此，在此主机中运行的所有对象也都具有对这些数据库的读/写访问权限。 如果清除该复选框，主机将 MessageBox 数据库中具有只写访问权限的跟踪表，并不会访问 BizTalk 跟踪数据库的权限。 |
   |         **受信任的身份验证**          |                                                                                                                                                                                                                                           选中此复选框可指定 BizTalk Server 应信任此主机。                                                                                                                                                                                                                                            |
   |               **仅限 32 位**               |                                                                                                                                               如果你想要允许主机实例进程在创建为 32 位 32 位和 64 位服务器上，请选中此复选框。 如果清除此复选框，则将为 32 位 32 位服务器上并为 64 位 64 位服务器上创建主机实例进程。                                                                                                                                                |
   | **将此组中的默认主机** |                                                                                                                                      选择此复选框可在此主机标识为默认主机。 创建的端口和业务流程会自动使用默认主机来承载业务流程中，除非你明确选择其他主机。 如果此复选框将被选中并且不可用，则此主机是默认值。                                                                                                                                      |
   |              **Windows 组**              |                                                                                                                                                                                                                  键入主机的本地或域组。 Windows 组的成员将有权运行此主机的实例。                                                                                                                                                                                                                   |


5. 上**证书**选项卡上，执行以下操作，并单击**确定**:  

   |使用此选项|执行的操作|  
   |--------------|----------------|  
   |**公用名**|显示所显示的解密证书的说明。|  
   |**Thumbprint**|显示使用此主机对入站的消息进行解密的私钥证书的指纹。 证书指纹的格式 HHHH HHHH HHHH HHHH HHHH HHHH HHHH HHHH HHHH HHHH，其中 H 为十六进制数字 （从 0 到 9 的数字） 或为从 A 到 F 的字母。|  
   |**删除证书**|单击此项可从主机删除所显示的解密证书。|  
   |**“浏览”**|单击此项可显示**Windows 安全**对话框中，其中从当前用户或你想要使用与主机的个人存储区中选择的解密证书。|  

## <a name="see-also"></a>请参阅  
 [管理 BizTalk 主机和主机实例](../core/managing-biztalk-hosts-and-host-instances.md)   
 [修改主机属性](../core/how-to-modify-host-properties.md)   
 [删除主机](../core/how-to-delete-a-host.md)