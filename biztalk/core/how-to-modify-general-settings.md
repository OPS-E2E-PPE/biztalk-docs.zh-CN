---
title: 如何修改常规设置 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- Bts10.settings.HostGeneral
ms.assetid: f0c90b44-e713-4d27-b125-833a747ab758
caps.latest.revision: 16
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c32787a46299938b5f84801e9a74b11f20433574
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65336100"
---
# <a name="how-to-modify-general-settings"></a>如何修改常规设置
使用设置仪表板，可以修改整个 BizTalk 组的给定主机的常规配置设置。 本主题提供了执行此操作的分步过程。  

## <a name="prerequisites"></a>先决条件  
 若要执行此操作，必须以 BizTalk Server Administrators 组的成员的身份登录。  

### <a name="to-modify-the-general-settings-of-a-host"></a>若要修改主机的常规设置  

1. 在中**BizTalk Server 管理控制台**，展开[!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)]，右键单击**BizTalk 组**，然后单击**设置**。  

2. 在中**BizTalk 设置仪表板**对话框中，在**主机**页上，单击**常规**选项卡。  

3. 执行以下操作，然后依次**应用**以应用修改并转到另一个选项卡。或单击**确定**应用所做的修改并退出设置仪表板。  


   |                  使用此选项                   |                                                                                                                                                                                                                                                                                                                                                       执行的操作                                                                                                                                                                                                                                                                                                                                                        |          边界值          | 默认值 |                                                                                       升级逻辑                                                                                       |
   |---------------------------------------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|-----------------------------------|---------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
   |                    主机                     |                                                                                                                                                                                                                                                                             从下拉列表中，选择表示主机[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]运行时实例。                                                                                                                                                                                                                                                                             |                 -                 |       -       |                                                                                                                                                                                           |
   |      **将跟踪数据移动到 DTA 数据库**       |                                                                  指示主机是否加载 BizTalk 跟踪组件，以处理运行状况监视和业务数据。<br /><br /> 如果选中此复选框，当前主机将具有读/写访问 MessageBox 数据库中的跟踪表以及跟踪数据库。 因此，在此主机中运行的所有对象也都具有对这些数据库的读/写访问权限。<br /><br /> 如果不选择此复选框，主机将 MessageBox 数据库中具有只写访问权限的跟踪表，并且不会对跟踪数据库的访问。                                                                  |              On、 Off              |      On       |                                                                                                                                                                                           |
   |         **受信任的身份验证**          |                                                                                                                                                                                                                             指示 BizTalk 主机是否可信任，以收集身份验证信息。<br /><br /> 通过指定哪些主机可信，哪些不能，可以定义用户对象和代码可信或不受信任的安全边界。                                                                                                                                                                                                                             |              On、 Off              |      Off      |                                                                                                                                                                                           |
   |               **仅限 32 位**               |                                                                                                                                                                                                                                                                                                        指示是否应创建主机实例进程为 32 位 32 位和 64 位服务器上。                                                                                                                                                                                                                                                                                                        |              On、 Off              |      On       |                                                                                                                                                                                           |
   | **独立适配器的默认应用程序域** | 指示独立的适配器是否在默认应用域或调用方的域中运行。<br /><br /> 默认情况下调用方的域中创建所有消息引擎对象。 如果 Web 服务的时间出于任何原因长时间处于非活动状态，IIS 将卸载调用方域。 在此情况下，宿主进程中的所有服务都变为不可用。<br /><br /> 当选择默认 AppDomain 时，默认值而不是在自己的 Appdomain 的 AppDomain 中创建 BizTalk 消息引擎对象。 和都不会卸载默认 AppDomain。<br /><br /> 仅当在默认 AppDomain 中创建的任何主机实例时，此选项才可用。 |              On、 Off              |      Off      |                                                     如果设置为此，任何主机的主机实例，则为 TRUE。 FALSE 否则为。                                                      |
   |       **旧的空白行为**        |                                                                                                                                                                                                                                                                                                                          指定你想要创建映射时保留空白区域。                                                                                                                                                                                                                                                                                                                          |              On、 Off              |      Off      | 每个主机实例计算机上，值为 TRUE，如果计算机上存在注册表值 > 0。 对于每个主机，值为 TRUE，如果任何一个主机实例将该值设置为 TRUE。 |
   |        **允许多个响应**         |                                                                                                                                                                                                                                                                                                           指示是否允许将多个响应发送回双向接收位置。                                                                                                                                                                                                                                                                                                           |              On、 Off              |      Off      |                                                 如果为 TRUE 的主机的任何主机实例，使主机设置 = TRUE。 否则为 FALSE。                                                  |
   |            **响应超时**             |                                                                                                                                                                                                                                                                                                                               指定请求响应消息的默认的超时。                                                                                                                                                                                                                                                                                                                                | 1 – 最大值类型为 Integer |      20       |                                         进程内主机-主机实例的最大值<br /><br /> 独立主机-计算机上的最大值                                         |
   |         **最大引擎线程**          |                                                                                          指示最大消息引擎线程，每个 CPU 的数目。<br /><br /> 此选项指定的最大可用的终结点管理器 (EPM) 线程数。 EPM 开始等效于此值的 10%的线程数，随着负载的增加添加线程，直到指定的值。 随着负载降低或根据需要限制减少分配的线程数。<br /><br /> **请注意**修改此值，如果需要更改才能生效，必须重新启动主机。                                                                                           |              [1,50]               |      20       |                                                                                             -                                                                                             |
   |      **显示性能计数器**      |                                      选择你想要显示的性能计数器的服务。<br /><br /> 如果设置为消息传送，性能监视器显示消息传送消息代理的计数器。 如果主机包含业务流程，将不显示业务流程 (XLANG) 实例的任何消息代理输出。<br /><br /> 如果主机仅包含业务流程，更改**显示性能计数器**设置为业务流程以显示业务流程实例的消息代理计数器。 如果主机仅包含接收端口/发送端口，保留消息传送选项可显示的消息传送实例消息代理计数器。                                       |     消息传送，业务流程     |   消息传送   |                     如果主机的所有主机实例都具有相同的值，则为主机选择该值。 如果没有冲突或没有设置值，请选择默认值。                      |

    **轮询间隔**  


   |      使用此选项      |                                                                                                执行的操作                                                                                                 |          边界值          | 默认值 | 升级逻辑  |
   |--------------------|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|-----------------------------------|---------------|----------------|
   |   **消息传送**    |   设置[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]轮询间隔 （毫秒） 时 BizTalk 主机实例查找新消息在 MessageBox 中。   | 1 – 最大值类型为 Integer |      500      | 现有的值 |
   | **业务流程** | 设置[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]轮询间隔 （毫秒） 时 BizTalk 主机实例查找数据库中的新业务流程。 | 1 – 最大值类型为 Integer |      500      | 现有的值 |

   > [!NOTE]
   >  若要还原默认设置，请单击**还原为默认值**。  

## <a name="see-also"></a>请参阅  
 [如何修改主机设置](../core/how-to-modify-host-settings.md)