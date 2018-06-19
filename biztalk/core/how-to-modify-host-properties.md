---
title: 如何修改主机属性 |Microsoft 文档
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
ms.openlocfilehash: 46a5dac64bb50cf84c0d14277687d1641b6fa536
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22255653"
---
# <a name="update-host-properties"></a>更新主机属性

## <a name="overview"></a>概述
您可以使用 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理控制台来修改以下主机属性：  
  
-   **Windows 组：** Windows 组的成员有权运行主机的默认情况下此主机的实例。 为 BizTalk 主机选择 Windows 用户组时，建议您创建一个专用于该主机的新组。 如果确实要使用现有组，应确保该组的权限不会超出所需的权限。 有关详细信息，请参阅[访问控制和数据安全](../core/access-control-and-data-security.md)。  
  
    > [!NOTE]
    >  如果更改当前已登录用户的组成员身份，并且组也是域成员，您应该注销并在完成更改后再登录。 不这样做将导致拒绝访问，因为当前登录名不会反映出新的组成员身份。  
  
-   **跟踪主机：** 组中的至少一个主机必须跟踪运行状况和业务数据。 此选项指示主机加载 BizTalk 跟踪组件来处理运行状况监视和业务数据。  
  
    > [!NOTE]
    >  建议您至少创建一个跟踪主机实例。 如果跟踪主机没有任何运行的实例，MessageBox 数据库将继续累计数据，而这会导致性能下降。  
  
     执行主机跟踪的主机对 MessageBox 数据库中的跟踪表具有读/写权限，并且可以访问 BizTalk 跟踪数据库。 因此，在执行主机跟踪的主机中运行的所有对象对这些数据库表也都具有读/写权限。 不执行主机跟踪的主机只对 MessageBox 数据库中的跟踪表具有写权限，而无权访问 BizTalk 跟踪数据库。  
  
    > [!NOTE]
    >  指定某个特定主机执行主机跟踪将会影响在同一主机上运行的应用程序的性能。 因此，您最好考虑创建一个仅“允许主机跟踪”的专用主机。  
  
-   **受信任的身份验证：** 可以指定 BizTalk Server 信任主机。 BizTalk Server 信任**身份验证受信任主机**要放置于受信任的主机正在排队映射到主机以外的其他用户的消息的发件人安全标识符 (SSID)。 有关受信任的身份验证主机的详细信息，请参阅[进行身份验证消息的发件人](../core/authenticating-the-sender-of-a-message.md)。  
  
     受信任主机和非信任主机的实例不能使用相同的服务帐户。 如果希望更改某个主机实例的信任设置，并且该主机实例与其他主机实例使用了相同的服务帐户，请执行以下操作之一：  
  
    -   对于要更改信任设置的主机实例，可以将其服务帐户更改为新的服务帐户。  
  
    -   可以将主机实例的服务帐户更改为具有相同信任设置的其他主机实例所用的现有服务帐户。  
  
    -   可以删除主机实例，然后使用不同的信任设置和服务帐户重新进行创建。  
  
-   **默认主机组中：** 必须具有默认主机组中的所有时间。 除非用户明确选择其他主机，否则业务流程登记进程将自动使用默认主机作为业务流程的宿主。 创建的第一个主机将标记为默认主机。 有关默认主机的信息，请参阅[主机](../core/hosts.md)。  
  
## <a name="prerequisites"></a>先决条件  
 必须具有以下用户权限才能创建主机、修改主机属性和删除主机：  
  
-   必须是 BizTalk Server Administrators 组的成员。 有关将用户添加到 BizTalk Server Administrators 组的信息，请参阅[如何管理 BizTalk Server Administrators 组](../core/how-to-manage-the-biztalk-server-administrators-group.md)。  
  
-   必须在 SQL Server 中具有以下权限：  
  
    -   必须是 SQL Server 管理员，或者是 BizTalk 跟踪数据库 (BizTalk DTADb)、MessageBox 数据库 (BizTalkMsgBoxDb) 和 BAM 主导入数据库 (BAMPrimaryImport) 中的 db_owner 或 db_securityadmin SQL Server 数据库角色的成员。  
  
    -   必须是 MessageBox 数据库所在的所有计算机上的 sysadmin SQL Server 角色的成员，或者是所有 MessageBox 数据库的 db_owner 或 db_ddladmin SQL Server 角色的成员。  
  
## <a name="steps"></a>步骤  
  
1.  单击**启动**，单击**所有程序**，单击[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]，然后单击**BizTalk Server 管理**。  
  
2.  在控制台树中，展开**BizTalk Server 管理**，展开 BizTalk 组，单击**平台设置**，然后单击**主机**。  
  
3.  在详细信息窗格中，右键单击你想要修改，然后单击的主机**属性**。  
  
4.  在**主机属性**对话框中，在**常规**选项卡上，执行以下操作：  
  
    |使用此选项|执行的操作|  
    |--------------|----------------|  
    |**名称**|显示主机的名称。 创建主机时命名该主机。|  
    |**类型**|显示主机类型。 可以向进程内主机登记业务流程，并且进程内主机可以作为发送处理程序的宿主。 独立主机在 BizTalk Server 安装之外操作。|  
  
     **选项**  
  
    |使用此选项|执行的操作|  
    |--------------|----------------|  
    |**允许主机跟踪**|选中此复选框可指示主机加载 BizTalk 跟踪组件以处理运行状况监视数据和业务数据。 如果选中此复选框，当前主机需要跟踪数据库中的表的 MessageBox，以及到跟踪数据库的读/写访问。 因此，运行在此主机中的任何对象也具有对这些数据库的读/写权限。 如果清除此复选框，该主机将仅对 MessageBox 数据库中的跟踪表具有写权限并且无权访问跟踪数据库。|  
    |**受信任的身份验证**|选中此复选框可指定 BizTalk Server 应信任此主机。|  
    |**仅限 32 位**|如果希望主机实例进程在 32 位和 64 位服务器上均创建为 32 位，请选中此复选框。 如果清除此复选框，主机实例进程将在 32 位服务器上创建为 32 位，在 64 位服务器上创建为 64 位。<br /><br /> **请注意**为将 32 位主机实例进程更改为 64 位主机实例进程，删除的主机，所有实例，然后清除**仅限 32 位**复选框。 在 64 位服务器上创建主机实例时，将以 64 位的形式创建这些实例。|  
    |**将此组中的默认主机**|选中此复选框可将此主机标识为默认主机。 除非明确选择其他主机，否则业务流程登记进程将自动使用默认主机作为业务流程的宿主。 如果此复选框被选中并且不可用，则此主机是默认主机。|  
    |**Windows 组**|键入主机的本地组或域组。 Windows 组的成员将具有运行此主机实例的权限。|  
  
5.  上**证书**选项卡上，执行以下操作，，然后单击**确定**:  
  
    |使用此选项|执行的操作|  
    |--------------|----------------|  
    |**Description**|显示所显示解密证书的说明。|  
    |**指纹**|显示用于对此主机的入站消息进行解密的私钥证书的指纹。 证书指纹的格式 HHHH HHHH HHHH HHHH HHHH HHHH HHHH HHHH HHHH HHHH，其中 H 是十六进制数字 （介于 0 到 9） 或从 A 到 F 字母。|  
    |**删除证书**|单击此项可从主机删除所显示解密证书。|  
    |**浏览**|单击此项可显示**选择证书**对话框中，你选择你想要使用与主机的本地计算机或其他人证书存储解密证书。|  
  
## <a name="see-also"></a>另请参阅  
-  [通过主机限制的优化资源使用情况](../core/optimizing-resource-usage-through-host-throttling.md)   
-  [限制的设计建议](../core/throttling-design-recommendations.md)   
-  [管理 BizTalk 主机和主机实例](../core/managing-biztalk-hosts-and-host-instances.md)   
-  [如何创建新的主机](../core/how-to-create-a-new-host.md)   
-  [如何删除主机](../core/how-to-delete-a-host.md)   
-  **MSBTS_Host (WMI)**[!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]