---
title: 如何配置 HTTP 接收处理程序 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- permissions, receive handlers
- configuring [HTTP adapters], permissions
- HTTP adapters, receive handlers
- receive handlers, permissions
- configuring [HTTP adapters], receive handlers
- permissions, HTTP adapters
- receive handlers, HTTP adapters
- HTTP adapters, permissions
ms.assetid: c295489e-dbbb-44f7-bddb-d3cdfe302cf5
caps.latest.revision: 27
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c0aec49f0334a62e559c0812a7b44029c25b4c95
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65386443"
---
# <a name="how-to-configure-an-http-receive-handler"></a>如何配置 HTTP 接收处理程序
使用以下过程可配置的属性的 HTTP 接收处理程序。  
  
> [!NOTE]
>  每个主机只能有一个接收处理程序与之关联。  
> 
> [!NOTE]
>  HTTP 接收适配器运行在 BizTalk 独立主机实例的上下文中。  
> 
> [!CAUTION]
>  在使用 HTTP 或 SOAP 适配器处理程序，建议在 Microsoft 上安装这些处理程序的主机实例[!INCLUDE[btsWinSvr2k8](../includes/btswinsvr2k8-md.md)]或[!INCLUDE[btsWinSvr2k8R2](../includes/btswinsvr2k8r2-md.md)]计算机。  
  
### <a name="to-configure-the-general-properties-for-an-http-receive-handler"></a>若要配置的常规属性用于 HTTP 接收处理程序  
  
1. 在中[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理控制台中，展开[!INCLUDE[btsBizTalkServer2006r3ui](../includes/btsbiztalkserver2006r3ui-md.md)]**管理**，展开**BizTalk 组**，展开**平台设置**，然后展开**适配器**。  
  
2. 在展开的适配器列表中，单击**HTTP**在右窗格中，右键单击你想要配置，然后单击的接收处理程序**属性**。  
  
3. 在中**适配器处理程序属性**对话框中，在**常规**选项卡上，在**主机名**列表中，选择接收处理程序将关联的主机。  
  
4. 单击**属性**访问**批大小**属性的 HTTP 接收处理程序。  
  
5. 从 1 到 256 的数字输入一个值，然后单击**确定**。  
  
6. 单击“确定” 。  
  
   BizTalk Server 旨在有效地处理消息批并不非常快速地处理一条消息。 如果此接收处理程序将使用两个方法/请求-响应接收位置，则可以尽量减少延迟，通过执行以下步骤：  
  
- 设置**批大小**属性的值为 1。  
  
- 减少**MaxReceiveInterval**值小于 100 的值从默认值 500**独立消息传送、 XLANG/s，** 并**进程内消息**服务类。  更改**adm_ServiceClass** BizTalk 管理数据库，其中包含每个服务类型的一条记录的表。  更改此设置，因为这是服务类型范围更改时要格外小心。 此设置指定的最大轮询间隔 （以毫秒为单位） 从该处[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]消息传递代理轮询[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]消息的 Messagebox 数据库。  它还用于阻止控制器决定是否在特定负载条件下需要消息阻止功能。 如果需要阻止控制器将以递增方式延迟消息调度时间间隔在系统上的繁忙情况。 在高吞吐量系统中，将不使用此设置。  使用此值，但是，时间间隔将动态更改 maxreceiveinteral/10 和 MaxReceiveInterval 之间。  
  
  > [!NOTE]
  >  更改此设置会影响使用创建的所有主机**主机类型**的**独立**。  
  
- 重新启动 IIS 应用程序池相关联的任何 HTTP 接收已配置的函数。  
  
  登录帐户**BizTalkServerIsolatedHost**主机实例必须具有读取和写入到临时目录或目录的权限以动态编译 HTTP 使用的代码隐藏文件接收函数。 使用以下过程授予的权限。  
  
### <a name="to-grant-the-account-for-the-biztalkserverisolatedhost-host-instance-read-and-write-permissions-to-the-temp-directory-of-your-biztalk-server"></a>以向帐户授予 biztalkserverisolatedhost 主机实例将读取和写入到 BizTalk server 的临时目录的权限  
  
1. 单击**启动**，单击**运行**，类型**CMD**，然后按 ENTER。  
  
2. 在命令提示符处，键入**设置 TEMP**然后按 enter 键以显示与关联的目录**TEMP**环境变量。  
  
3. 在命令提示符处，键入**设置 TMP**然后按 enter 键以显示与关联的目录**TMP**环境变量。  
  
   指定为的登录帐户的帐户授予**BizTalkServerIsolatedHost**托管实例读取和写入权限的目录或目录与相关联**TEMP**并**TMP**环境变量。 若要确定的登录帐户**BizTalkServerIsolatedHost**实例，在[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理控制台中，展开[!INCLUDE[btsBizTalkServer2006r3ui](../includes/btsbiztalkserver2006r3ui-md.md)]**管理**，展开**BizTalk 组**，展开**平台设置**，展开**主机实例**，右键单击**BizTalkServerIsolatedHost**主机在右窗格中，实例，然后单击**属性**。 用于主机实例的登录帐户列出旁边**登录**标签。  
  
## <a name="see-also"></a>请参阅  
 [配置 HTTP 适配器](../core/configuring-the-http-adapter.md)