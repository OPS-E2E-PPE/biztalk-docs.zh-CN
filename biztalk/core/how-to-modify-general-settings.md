---
title: "如何修改常规设置 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: Bts10.settings.HostGeneral
ms.assetid: f0c90b44-e713-4d27-b125-833a747ab758
caps.latest.revision: "16"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 2a07a49d4905b13c33f87dcc694ca69c1a044fd2
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-modify-general-settings"></a>如何修改常规设置
使用设置仪表板，你可以在 BizTalk 组中修改给定主机的常规配置设置。 本主题提供执行该操作的分步过程。  
  
## <a name="prerequisites"></a>先决条件  
 若要执行此操作，则必须以 BizTalk Server Administrators 组成员的身份登录。  
  
### <a name="to-modify-the-general-settings-of-a-host"></a>修改主机的常规设置  
  
1.  在**BizTalk Server 管理控制台**，展开[!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)]，右键单击**BizTalk 组**，然后单击**设置**。  
  
2.  在**BizTalk 设置仪表板**对话框中，在**主机**页上，单击**常规**选项卡。  
  
3.  执行以下操作，并依次**应用**应用修改再转到另一个选项卡。或单击**确定**应用进行修改并退出设置仪表板。  
  
    |使用此选项|执行的操作|边界值|默认值|升级逻辑|  
    |--------------|----------------|---------------------|-------------------|-------------------|  
    |主机|从下拉列表中，选择代表 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 运行时实例的主机。|-|-||  
    |**将跟踪数据移到 DTA DB**|指示主机是否加载 BizTalk 跟踪组件，以处理运行状况监视和业务数据。<br /><br /> 如果选中此复选框，当前主机需要跟踪数据库中的表的 MessageBox，以及到跟踪数据库的读/写访问。 因此，运行在此主机中的任何对象也具有对这些数据库的读/写权限。<br /><br /> 如果不选中此复选框，该主机将仅对 MessageBox 数据库中的跟踪表具有写入权限，并且无权访问跟踪数据库。|打开、 关闭|On||  
    |**受信任的身份验证**|指示 BizTalk 主机是否可信任，以收集身份验证信息。<br /><br /> 通过指定哪些主机可信，哪些主机不可信，可以定义衡量用户对象和代码可信或不可信的安全边界。|打开、 关闭|Off||  
    |**仅限 32 位**|指示该主机实例进程在 32 位和 64 位服务器上是否均创建为 32 位。|打开、 关闭|On||  
    |**独立的适配器的的默认应用程序域**|指示独立适配器是在默认应用程序域中运行，还是在调用方的域中运行。<br /><br /> 默认情况下，在调用方的域中创建所有的消息引擎对象。 如果 Web 服务出于任何原因在很长一段时间内处于不活动状态，IIS 将卸载调用方域。 出现这样的情况时，承载进程中的所有服务都不能使用。<br /><br /> 如果选择默认 AppDomain，则 BizTalk 消息引擎对象将在默认 AppDomain 中创建，而非在其自己的 AppDomains 中创建。 并且，永远不会卸载默认 AppDomain。<br /><br /> 只有当你在默认 AppDomain 中创建任何主机实例时，此选项才可用。|打开、 关闭|Off|如果主机的任何主机实例设置为此，则为 TRUE。 FALSE 否则为。|  
    |**旧的空格行为**|指定是否要在创建映射时保留空白区域。|打开、 关闭|Off|对于在计算机上每个主机实例，值为 TRUE，如果计算机上存在注册表值 > 0。 对于每个主机，值为 TRUE，如果主机实例之一将该选项设置为 TRUE。|  
    |**允许多个响应**|指示是否允许将多个响应发送回双向接收位置。|打开、 关闭|Off|如果主机的任何主机实例为 TRUE，则将主机设置设为 TRUE。 否则为 FALSE。|  
    |**响应超时**|指定请求响应消息的默认超时。|1 – Integer 类型的最大值|20|进程内主机 - 主机实例的最大值<br /><br /> 独立主机 - 计算机上的最大值|  
    |**最大引擎线程**|指示每个 CPU 的最大消息引擎线程数。<br /><br /> 此选项指定端点管理器 (EPM) 可以使用的最大线程数。 EPM 开始时使用等于此值的 10% 的线程数，然后随着负载增加，线程数也随之增加，但最多可使用指定值的线程数。 随着负载降低或根据阻止的需要，所分配的线程数将随之减少。<br /><br /> **请注意**如果修改此值时，主机需要重新启动以使更改生效。|[1,50]|20|-|  
    |**显示性能计数器**|选择要显示性能计数器的服务。<br /><br /> 设置为“消息传送”时，性能监视器将显示用于消息传送的消息代理计数器。 如果主机包含业务流程，则不会显示业务流程 (XLANG) 实例的任何消息代理输出。<br /><br /> 如果主机仅包含业务流程，更改**显示性能计数器**设置为业务流程为显示业务流程实例的消息代理计数器。 如果主机仅包含接收端口/发送端口，则保留“消息传送”选项以显示消息传送实例的消息代理计数器。|消息传送、业务流程|消息传送|如果主机的所有主机实例都具有相同的值，请为该主机选择该值。 如果存在冲突或没有设置值，请选择默认值。|  
  
     **轮询间隔**  
  
    |使用此选项|执行的操作|边界值|默认值|升级逻辑|  
    |--------------|----------------|---------------------|-------------------|-------------------|  
    |**消息传送**|当 BizTalk 主机实例正在 MessageBox 中查找新消息时，请设置 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 轮询间隔（以毫秒为单位）。|1 – Integer 类型的最大值|500|现有的值|  
    |**业务流程**|当 BizTalk 主机实例正在数据库中查找新业务流程时，请设置 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 轮询间隔（以毫秒为单位）。|1 – Integer 类型的最大值|500|现有的值|  
  
    > [!NOTE]
    >  若要还原默认设置，请单击**还原为默认值**。  
  
## <a name="see-also"></a>另请参阅  
 [如何修改主机设置](../core/how-to-modify-host-settings.md)