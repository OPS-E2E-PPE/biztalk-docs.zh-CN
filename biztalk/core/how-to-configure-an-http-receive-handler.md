---
title: 如何配置 HTTP 接收处理程序 |Microsoft 文档
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
ms.openlocfilehash: 0b199ac25fea412e9912e7989ff1f16e6e0e8d9d
ms.sourcegitcommit: 3fc338e52d5dbca2c3ea1685a2faafc7582fe23a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/01/2017
ms.locfileid: "26007606"
---
# <a name="how-to-configure-an-http-receive-handler"></a>如何配置 HTTP 接收处理程序
使用以下过程来为 HTTP 配置属性接收处理程序。  
  
> [!NOTE]
>  每个主机只能有一个接收与之关联的处理程序。  
  
> [!NOTE]
>  HTTP 接收适配器运行独立 BizTalk 主机实例的上下文中。  
  
> [!CAUTION]
>  使用 HTTP 或 SOAP 适配器处理程序时，建议在 Microsoft [!INCLUDE[btsWinSvr2k8](../includes/btswinsvr2k8-md.md)] 或 [!INCLUDE[btsWinSvr2k8R2](../includes/btswinsvr2k8r2-md.md)] 计算机上安装这些处理程序的主机实例。  
  
### <a name="to-configure-the-general-properties-for-an-http-receive-handler"></a>若要配置 HTTP 的常规属性接收处理程序  
  
1.  在[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理控制台中，展开[!INCLUDE[btsBizTalkServer2006r3ui](../includes/btsbiztalkserver2006r3ui-md.md)]**管理**，展开**BizTalk 组**，展开**平台设置**，然后展开**适配器**。  
  
2.  在展开的适配器列表中，单击**HTTP，** 在右窗格中，右键单击你想要配置，，然后单击接收处理程序**属性**。  
  
3.  在**适配器处理程序属性**对话框中，在**常规**选项卡上，在**主机名**列表中，选择接收处理程序将与之关联的主机。  
  
4.  单击**属性**访问**批大小**属性 HTTP 接收处理程序。  
  
5.  输入一个介于 1 到 256 和单击**确定**。  
  
6.  单击 **“确定”**。  
  
 BizTalk Server 旨在以有效处理的消息的批次，而不是非常快速地处理一条消息。 因此如果此接收处理程序准备用于双向/请求响应接收位置，则可以通过以下这些步骤将延迟时间缩为最短：  
  
-   设置**批大小**属性的值为 1。  
  
-   减少**MaxReceiveInterval**从 500 的默认值为小于 100 的值的值**独立消息传送、 XLANG/s，** 和**消息传送过程中**服务类。  进行更改**adm_ServiceClass** BizTalk 管理数据库，其中包含上述每种服务类型的一条记录的表。  更改此设置，因为这是服务类型范围的更改时要格外小心。 此设置指定最大的轮询间隔时间（以毫秒为单位），[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 消息传送代理会为消息轮询 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Messagebox 数据库。  阻止控制器还会将其用来决定消息阻止是否在某些加载条件下需要。 如果需要，根据系统的繁忙情况，阻止控制器会以递增方式延迟消息调度时间间隔。 在较高吞吐量系统中，将不会使用此设置。  但是，如果使用此值，时间间隔将在 MaxReceiveInteral/10 和 MaxReceiveInterval 间发生动态更改。  
  
    > [!NOTE]
    >  更改此设置会影响使用创建的所有主机**主机类型**的**Isolated**。  
  
-   重新启动 IIS 应用程序池关联的任何 HTTP 接收已配置的函数。  
  
 登录帐户**BizTalkServerIsolatedHost**主机实例必须具有读取和写入到临时目录或目录的权限来动态编译使用 HTTP 的代码隐藏文件接收函数。 使用以下过程向其授予权限。  
  
### <a name="to-grant-the-account-for-the-biztalkserverisolatedhost-host-instance-read-and-write-permissions-to-the-temp-directory-of-your-biztalk-server"></a>向帐户授予的 BizTalkServerIsolatedHost 主机实例将读取和写入到 BizTalk server 的临时目录的权限  
  
1.  单击**启动**，单击**运行**，类型**CMD**，然后按 ENTER。  
  
2.  在命令提示符处，键入**设置 TEMP** ，然后按 enter 键以显示与关联的目录**TEMP**环境变量。  
  
3.  在命令提示符处，键入**设置 TMP** ，然后按 enter 键以显示与关联的目录**TMP**环境变量。  
  
 指定为的登录帐户的帐户授予**BizTalkServerIsolatedHost**托管实例读取和写入权限或多个目录与关联**TEMP**和**TMP**环境变量。 若要确定的登录帐户**BizTalkServerIsolatedHost**实例，在[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理控制台中，展开[!INCLUDE[btsBizTalkServer2006r3ui](../includes/btsbiztalkserver2006r3ui-md.md)]**管理**，展开**BizTalk 组**，展开**平台设置**，展开**主机实例**，右键单击**BizTalkServerIsolatedHost**主机在右窗格中，实例，然后单击**属性**。 用于的主机实例的登录帐户列出旁边**登录**标签。  
  
## <a name="see-also"></a>另请参阅  
 [配置 HTTP 适配器](../core/configuring-the-http-adapter.md)