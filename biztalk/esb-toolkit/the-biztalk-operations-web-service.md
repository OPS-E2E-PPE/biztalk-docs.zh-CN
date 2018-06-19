---
title: BizTalk 操作 Web 服务 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: af38815f-f643-4598-9148-6499071d12e4
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 5d09fb2cdcca83e8a9f2e4e7704178d40a915065
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22296909"
---
# <a name="the-biztalk-operations-web-service"></a>BizTalk 操作 Web 服务
Microsoft BizTalk 操作 Web 服务公开的对象和 BizTalk Server 中的消息有关的信息。 服务名称是**ESB.BizTalkOperationsService**，并且服务将公开各种返回如列表项的主机、 业务流程、 应用程序和 BizTalk 应用程序状态的方法。  
  
 提供了以下方法：  
  
-   **应用程序**。 此方法没有采用任何参数并返回的名称和描述的所有已安装的 BizTalk 应用程序的集合作为**BTApplication**对象。  
  
-   **ApplicationStatus**。 此方法将作为参数的应用程序名称，并返回有关指定 BizTalk 应用程序作为信息**BTSysStatus**实例。 此信息包括业务流程、 发送端口、 接收位置和主机的详细信息。  
  
-   **GetLiveMessageBody**。 消息 ID 和实例 ID，此方法使用作为参数并返回该消息的正文从作为实时环境**BTMsgBody**实例。  
  
-   **GetMessageInstances**。 此方法将作为参数的消息类型，并返回匹配的所有消息的集合作为**BTMsgInstance**对象。  
  
-   **GetOrchestrationInstances**。 此方法使用作为参数的业务流程的名称和它将返回的集合**BTOrchestrationInstance**包含匹配的业务流程的详细信息的对象。  
  
-   **GetTrackedMessageBody**。 此方法将作为参数消息 GUID，并返回作为该消息的正文**BTMsgBody**实例后在 BizTalk 中处理。  
  
-   **主机**。 此方法将作为参数而主机的名称和它返回有关指定的主机实例的集合的信息**BTHost**实例。 使用主机名称参数为空字符串返回有关所有主机实例的信息。  
  
-   **MessageFlowTree**。 此方法将作为参数的实例 ID，并返回作为该消息的消息流的详细信息**RouteTreeNode**实例。  
  
-   **业务流程**。 此方法将作为参数的名称的业务流程，并返回适用于为该业务流程的所有信息**BTSysStatus**实例。 业务流程名称参数为空字符串用于返回有关所有业务流程的信息。  
  
-   **接收位置**。 此方法将作为参数接收位置的名称并返回匹配与位置的所有信息**BTSysStatus**实例。 接收位置名称参数为空字符串用于返回有关所有位置的信息。  
  
-   **ReceiveLocationsByDescription**。 此方法将作为参数接收位置的说明，并返回匹配与位置的所有信息**BTSysStatus**实例。 Description 参数为空字符串用于返回有关所有位置的信息。  
  
-   **发送端口**。 此方法将作为参数的名称发送端口，并返回匹配的端口的所有信息**BTSysStatus**实例。 发送端口名称参数为空字符串用于返回有关所有端口的信息。  
  
-   **SendPortsByDescription**。 此方法将作为参数发送端口的说明，并返回匹配的端口的所有信息**BTSysStatus**实例。 使用 description 参数为空字符串返回有关所有端口的信息。  
  
-   **StatusChanged**。 此方法将作为参数一个时间戳，并返回自指定时间戳作为以来修改的 BizTalk 对象 （如端口、 主机和业务流程） 的详细信息**BTSysStatus**实例。  
  
-   **SystemStatus**。 此方法没有采用任何参数，它返回的形式的 BizTalk 系统状态的完整详细信息**BTSysStatus**实例。  
  
-   **UpdateReceiveLocationDescription**。 此方法将更新指定的接收位置使用包含应用程序名称、 接收端口名称、 接收位置名称，和接收位置描述的参数值的说明。 它将返回一个字符串，指示该操作的结果。 请注意测试客户端应用程序从其 App.config 文件中读取此信息。  
  
-   **UpdateSendPortDescription**。 使用包含发送端口名称和发送端口描述的参数值指定的发送端口的说明更新为此方法。 它将返回一个字符串，指示该操作的结果。 请注意测试客户端应用程序从其 App.config 文件中读取此信息。  
  
## <a name="configuring-the-biztalk-operations-web-service"></a>配置 BizTalk 操作 Web 服务  
 BizTalk 操作 Web 服务可以直接与 BizTalk Server 管理数据库使用 Windows Management Instrumentation (WMI) 通信或它使用 BizTalk 操作和资源管理器 API 来获取所需的信息。 因此，你必须确保你的系统满足以下条件和配置下列安全权限设置：  
  
-   设置**allowOverride**到计算机级别的 Web.config 文件中的属性**false**若要确保开发人员不能更改其应用程序的信任级别。  
  
-   默认情况下，BizTalk 操作 Web 服务未配置为需要安全套接字层 (SSL) 时的客户端访问。 你应配置服务，因此它需要 SSL 客户端访问和保护 Internet Information Services (IIS) Web 服务主机计算机和运行承载 BizTalkMgmtDb 数据库使用的 SQL Server 的计算机之间的连接网络级别 IPSec 和相应的文件级访问控制列表 (ACL) 权限。  
  
-   访问 BizTalk Operations Web 服务的用户必须对某些方法默认 BizTalk Server Administrators 组的成员和成员的默认 BizTalk 应用程序用户组的其他方法。  
  
-   你必须确保 BizTalk 操作 Web 服务驻留在名为已禁用的匿名访问的 ESB.BizTalkOperationsService 的 IIS 虚拟目录。  
  
-   用户必须具有**选择**位于 BizTalkMgmtDb 数据库和 BizTalkMsgBoxDb 数据库的 SQL Server 中为多个表的权限。 使用 SQL Server Management Studio 设置以下权限：  
  
    -   在 BizTalkMgmtDb 数据库中，配置具有 BTS_ADMIN_USERS 数据库角色**选择**以下表的权限：  
  
        -   adm_Server2HostMapping  
  
        -   adm_Server  
  
        -   adm_hostInstance  
  
    -   在 BizTalkMsgBoxDb 数据库中，配置具有 BTS_ADMIN_USER 数据库角色**选择**ProcessHeartbeats 表的权限。  
  
 在 SQL Server Management Studio，你可以配置所需的权限。 若要执行此操作，展开**安全**在左窗格中对象资源管理器树视图中，展开**角色**，展开**DatabaseRoles**、 选择 BTS_ADMIN_USERS 角色，然后编辑此角色，如图 1 中所示的的属性。  
  
 ![SQL Server 管理 Studio](../esb-toolkit/media/ch4-sqlservermgmtstudio.gif "第四章第 4 SQLServerMgmtStudio")  
  
 **图 1**  
  
 **编辑在 Microsoft SQL Server Management Studio 中的 BTS_ADMIN_USERS 数据库角色的权限**  
  
> [!NOTE]
>  你必须配置为使用 Windows 集成安全性并在内置网络服务帐户下运行此服务。 你还必须启用 Kerberos 身份验证 IIS Web 服务器上，以便它将此标头发**协商、 NTLM**到客户端。 有关详细信息，请参阅[如何配置 IIS 以支持用于网络身份验证的 Kerberos 协议和 NTLM 协议](http://go.microsoft.com/fwlink/?LinkId=186430)([http://go.microsoft.com/fwlink/?LinkId=186430](http://go.microsoft.com/fwlink/?LinkId=186430))。  
>   
>  默认情况下，BizTalk 操作 Web 服务未配置为需要 SSL 时的客户端访问。 你应配置服务，因此需要 SSL 的客户端访问和保护 IIS Web 服务主机计算机和承载使用网络级别 IPSec 和相应的文件级 ACL 权限 UDDI 服务的服务器之间的连接。