---
title: 如何修改主机属性 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: e5df9d7f-b6c2-4bb7-a845-284e6323e3d6
caps.latest.revision: 28
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 1d6946405b2e0c00bd79de26b3174004e0b8a9c4
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65384587"
---
# <a name="update-host-properties"></a>更新主机属性

## <a name="overview"></a>概述
可以使用[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理控制台来修改以下主机属性：  

-   **Windows 组：** Windows 组的成员有权运行主机默认情况下此主机的实例。 当 BizTalk 主机选择 Windows 用户组时，我们建议创建专用于该主机的新组。 如果您使用现有组，请确保组不具有超出所需的权限。 有关详细信息，请参阅[访问控制和数据安全性](../core/access-control-and-data-security.md)。  

    > [!NOTE]
    >  如果更改组成员身份的当前登录的用户，并且组也是域的成员，您应该注销并登录，需要完成的更改。 如果不这样做将导致被拒绝访问，因为新的组成员身份将不会反映由当前登录名。  

-   **主机跟踪：** 必须在组中的至少一个主机来跟踪运行状况和业务数据。 此选项指示主机加载 BizTalk 跟踪组件，以处理运行状况监视和业务数据。  

    > [!NOTE]
    >  我们建议创建至少一个主机实例的跟踪主机。 如果没有任何正在运行的跟踪主机的主机实例，MessageBox 数据库将继续累计数据与导致性能下降。  

     执行主机跟踪的主机具有到 MessageBox 数据库中的跟踪表的读/写访问，以及对 BizTalk 跟踪数据库的访问。 因此，为执行主机跟踪还在主机中运行的所有对象都具有读/写访问这些数据库表。 不执行主机跟踪的主机只具有写权限的跟踪表在 MessageBox 数据库中，并不具有访问 BizTalk 跟踪数据库的权限。  

    > [!NOTE]
    >  指定某个特定主机执行主机跟踪将在同一主机上运行的应用程序的性能产生影响。 因此，您可能需要考虑创建专用的主机，只需为"允许主机跟踪"，出于此原因。  

-   **受信任的身份验证：** 您可以指定 BizTalk Server 信任某个主机。 BizTalk Server 信任**身份验证受信任的主机**要放置于受信任的主机正在排队映射到主机以外的其他用户的消息的发件人安全 ID (SSID)。 有关受信任验证主机的详细信息，请参阅[进行身份验证消息的发件人](../core/authenticating-the-sender-of-a-message.md)。  

     受信任的主机的主机实例和不受信任主机的实例不能使用相同的服务帐户。 如果你想要更改信任设置为主机实例和主机实例使用其他主机实例使用的服务帐户，可以执行下列任一操作：  

    -   可以更改你想要将信任设置更改为新的服务帐户的主机实例的服务帐户。  

    -   到其他主机实例具有相同信任设置使用现有的服务帐户，可以更改主机实例的服务帐户。  

    -   可以删除该主机实例，并使用不同的信任设置和服务帐户重新创建它。  

-   **在组中的默认主机：** 必须有默认主机组中所有时间。 业务流程登记过程会自动使用默认主机来承载业务流程中，除非用户明确选择其他主机。 创建的第一个主机标记为默认主机。 有关默认主机的信息，请参阅[主机](../core/hosts.md)。  

## <a name="prerequisites"></a>先决条件  
 必须具有以下的用户权限，才能创建主机、 修改主机属性和删除主机：  

-   必须是 BizTalk Server Administrators 组的成员。 有关将用户添加到 BizTalk Server Administrators 组的信息，请参阅[如何管理 BizTalk Server Administrators 组](../core/how-to-manage-the-biztalk-server-administrators-group.md)。  

-   SQL Server 中，必须具有以下权限：  

    -   您必须是 SQL Server 管理员或在 BizTalk 跟踪数据库 (BizTalk DTADb)、 MessageBox (BizTalkMsgBoxDb) 数据库和 BAM 主导入数据库 （中的 db_owner 或 db_securityadmin 的 SQL Server 数据库角色的成员BAMPrimaryImport)。  

    -   其中有 MessageBox 数据库或所有 MessageBox 数据库的 db_owner 或 db_ddladmin SQL Server 角色的成员，您必须是所有计算机上的 sysadmin SQL Server 角色的成员。  

## <a name="steps"></a>步骤  

1. 单击**启动**，单击**所有程序**，单击[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]，然后单击**BizTalk Server 管理**。  

2. 在控制台树中，展开**BizTalk Server 管理**，展开 BizTalk 组，单击**平台设置**，然后单击**主机**。  

3. 在细节窗格中，右键单击你想要修改，然后单击的主机**属性**。  

4. 在中**主机属性**对话框中，在**常规**选项卡上，执行以下操作：  

   |使用此选项|执行的操作|  
   |--------------|----------------|  
   |**名称**|显示主机的名称。 在创建时命名主机。|  
   |**类型**|显示主机类型。 您可以登记到进程内主机上，业务流程和进程内主机可以承载发送处理程序。 独立主机在 BizTalk Server 安装之外操作。|  

    **选项**  


   |                  使用此选项                   |                                                                                                                                                                                                                                                                                    执行的操作                                                                                                                                                                                                                                                                                    |
   |---------------------------------------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
   |           **允许主机跟踪**           | 选中此复选框以指示主机加载 BizTalk 跟踪组件，以处理运行状况监视和业务数据。 如果选中此复选框，当前主机将具有读/写访问 MessageBox 数据库中的跟踪表以及跟踪数据库。 因此，在此主机中运行的所有对象也都具有对这些数据库的读/写访问权限。 如果清除该复选框，主机将 MessageBox 数据库中具有只写访问权限的跟踪表，并且不会对跟踪数据库的访问。 |
   |         **受信任的身份验证**          |                                                                                                                                                                                                                                                   选中此复选框可指定 BizTalk Server 应信任此主机。                                                                                                                                                                                                                                                   |
   |               **仅限 32 位**               |                     如果你想要创建为 32 位 32 位和 64 位服务器上该主机实例进程，请选中此复选框。 如果清除此复选框，则将为 32 位 32 位服务器上并为 64 位 64 位服务器上创建主机实例进程。<br /><br /> **请注意**为将 32 位主机实例进程更改为 64 位主机实例进程，删除所有主机实例，然后清除**仅限 32 位**复选框。 当在 64 位服务器上创建主机的实例时，它们将创建为 64 位。                     |
   | **将此组中的默认主机** |                                                                                                                                           选择此复选框可在此主机标识为默认主机。 业务流程登记过程会自动使用默认主机来承载业务流程中，除非你明确选择其他主机。 如果此复选框将被选中并且不可用，则此主机是默认值。                                                                                                                                           |
   |              **Windows 组**              |                                                                                                                                                                                                                          键入主机的本地或域组。 Windows 组的成员将有权运行此主机的实例。                                                                                                                                                                                                                          |


5. 上**证书**选项卡上，执行以下操作，并单击**确定**:  

   |使用此选项|执行的操作|  
   |--------------|----------------|  
   |**说明**|显示所显示的解密证书的说明。|  
   |**Thumbprint**|显示使用此主机对入站的消息进行解密的私钥证书的指纹。 证书指纹的格式 HHHH HHHH HHHH HHHH HHHH HHHH HHHH HHHH HHHH HHHH，其中 H 为十六进制数字 （从 0 到 9 的数字） 或为从 A 到 F 的字母。|  
   |**删除证书**|单击此项可从主机删除所显示的解密证书。|  
   |**“浏览”**|单击此项可显示**选择证书**对话框中，您选择想要使用与主机的本地计算机或其他人证书存储的解密证书。|  

## <a name="see-also"></a>请参阅  
- [通过主机阻止优化资源使用情况](../core/optimizing-resource-usage-through-host-throttling.md)   
- [限制设计建议](../core/throttling-design-recommendations.md)   
- [管理 BizTalk 主机和主机实例](../core/managing-biztalk-hosts-and-host-instances.md)   
- [如何创建新的主机](../core/how-to-create-a-new-host.md)   
- [如何删除主机](../core/how-to-delete-a-host.md)   
- **MSBTS_Host (WMI)** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]
