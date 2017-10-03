---
title: "使用早期版本的适配器 MQSeries 适配器 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: MQSeries adapters, compatibility
ms.assetid: 278a13ff-8e46-4af4-a76e-b6d4aad5b768
caps.latest.revision: "22"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ba635b9bc4569f17418fc925c54c64d0fdc67461
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="using-mqseries-adapter-with-an-earlier-version-of-the-adapter"></a>MQSeries 适配器使用早期版本的适配器
[!INCLUDE[btsBizTalkServer2006](../includes/btsbiztalkserver2006-md.md)]， [!INCLUDE[btsBizTalkServer2004](../includes/btsbiztalkserver2004-md.md)]，和[!INCLUDE[btsBizTalkServer2002](../includes/btsbiztalkserver2002-md.md)]MQSeries 适配器版本可以与相同的远程 WebSphere MQ 服务器在 Windows 上的所有工作。 这是由于与 MQSeries 适配器一起使用的以下版本的 COM+ 应用程序可以同时存在于同一 WebSphere MQSeries 计算机上：  
  
-   **MQSAgent (MQSAgent2) COM + 应用程序**与 MQSeries 适配器[!INCLUDE[btsBizTalkServer2006](../includes/btsbiztalkserver2006-md.md)]。  
  
-   **MQSAgent COM + 应用程序**与 MQSeries 适配器[!INCLUDE[btsBizTalkServer2004](../includes/btsbiztalkserver2004-md.md)]。  
  
-   **MQHelper COM + 应用程序**与 MQSeries 适配器[!INCLUDE[btsBizTalkServer2002](../includes/btsbiztalkserver2002-md.md)]。  
  
> [!NOTE]
>  在配置这些 COM+ 应用程序的并行安装时，请确保这些 COM+ 应用程序均未配置为使用相同的 MQSeries 队列。  
  
> [!IMPORTANT]
>  通过并行安装[!INCLUDE[btsBizTalkServer2006](../includes/btsbiztalkserver2006-md.md)]支持仅使用 MQSeries 适配器 COM + 应用程序的较早版本 MQSeries 适配器 COM + 应用程序的版本，如果 WebSphere MQSeries 上未安装 BizTalk Server 的早期版本计算机。  
  
### <a name="to-install-the-biztalk-server-2006-version-of-the-mqseries-adapter-com-application-on-a-websphere-mqseries-computer-that-is-running-an-earlier-version-of-the-mqseries-adapter-com-application"></a>将 BizTalk Server 2006 版本的 MQSeries 适配器 COM+ 应用程序安装在运行早期版本的 MQSeries 适配器 COM+ 应用程序的 WebSphere MQSeries 计算机上  
  
1.  从的 \Platform\BootStrap\ 目录中运行 Bootstrap.msi [!INCLUDE[btsBizTalkServer2006](../includes/btsbiztalkserver2006-md.md)] CD 来复制依赖项文件到 WebSphere MQSeries 计算机 MSVCR80.dll 和 MSVCP80.dll。  
  
2.  在将文件复制 MQSAgent.dll 从 \Msi\Program Files\ 目录[!INCLUDE[btsBizTalkServer2006](../includes/btsbiztalkserver2006-md.md)]键入 cd 转到 WebSphere MQSeries 计算机。  
  
    > [!NOTE]
    >  如果您计划使用 MQSAgent 跟踪实用工具，请从此目录将文件 MQSTrace.cmd 也复制到 WebSphere MQSeries 计算机中。 跟踪实用工具 MQSAgent 有关详细信息请参阅[分析 MQSeries 适配器跟踪工具错误](../core/analyzing-mqseries-adapter-errors-with-the-trace-tools.md)。  
  
3.  请通过在 WebSphere MQSeries 计算机上运行 regsvr32 mqsagent.dll 以手动方式注册 MQSAgent.dll 中的组件。  
  
    ```  
    regsvr32 MQSAgent.dll  
    ```  
  
    > [!NOTE]
    >  从 MQSAgent.dll 所复制到的目标目录运行此命令。  
  
4.  为 MQSAgent 组件创建新的 COM+ 应用程序：  
  
    -   右键单击 COM + 应用程序，单击**新建**，**应用程序**以显示**COM + 应用程序安装向导**单击**下一步**。  
  
    -   单击**创建空的应用程序**。  
  
    -   输入的名称**MQSAgent2**，保留默认选项为**服务器应用程序**启用和单击**下一步**。  
  
    -   选择的选项**此用户**，输入合适的帐户信息，请单击**下一步**。  
  
        > [!NOTE]
        >  该帐户应该在相应的 IBM WebSphere MQ 队列中拥有 connect 及 put 和/或 get 权限。  
  
    -   单击**下一步**在添加**应用程序角色**对话框。  
  
    -   单击**下一步**上**向角色添加用户**对话框。  
  
    -   单击 **“完成”**。  
  
5.  将 MQSAgent.dll 组件添加到 MQSAgent2 COM+ 应用程序：  
  
    -   单击以展开**MQSAgent2** COM + 应用程序。  
  
    -   右键单击**组件**单击**新建**，**组件**启动 COM + 组件安装向导，然后单击**下一步**。  
  
    -   单击**安装新组件**，浏览到文件 MQSAgent.dll，然后单击**打开**。  
  
    -   单击“下一步” ，然后单击“完成” 。  
  
## <a name="see-also"></a>另请参阅  
 [使用 MQSeries 适配器](../core/using-the-mqseries-adapter.md)