---
redirect_url: /biztalk/core/mqseries-adapter-deployment-options
redirect_document_id: true
ROBOTS: NOINDEX
ms.openlocfilehash: 38711ace8fd2c1ea328edc2ba8d4ecf83a320070
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65396796"
---
# <a name="using-mqseries-adapter-with-an-earlier-version-of-the-adapter"></a>通过早期版本的适配器使用 MQSeries 适配器
不同的 BizTalk Server 版本的 MQSeries 适配器的所有可使用同一远程 WebSphere MQ Server 在 Windows。 这可能是因为与 MQSeries 适配器一起使用的 COM + 应用程序的以下版本可以共存于同一 WebSphere MQSeries 计算机上：  
  
-   **MQSAgent (MQSAgent2) COM + 应用程序**与 MQSeries 适配器 (BizTalk Server 2006) 一起使用 
  
-   **MQSAgent COM + 应用程序**与 MQSeries 适配器 (BizTalk Server 2004) 一起使用  
  
-   **MQHelper COM + 应用程序**与 MQSeries 适配器 (BizTalk Server 2002) 一起使用 
  
> [!NOTE]
>  在配置这些 COM + 应用程序的并行安装，请确保这些 COM + 应用程序配置为使用相同的 MQSeries 队列。  
  
> [!IMPORTANT]
>  如果在 WebSphere 上未安装早期版本的 BizTalk Server 仅支持通过并行安装 BizTalk Server 2006 版本的 MQSeries 适配器 COM + 应用程序与早期版本的 MQSeries 适配器 COM + 应用程序的MQSeries 计算机。  
  
### <a name="to-install-the-biztalk-server-2006-version-of-the-mqseries-adapter-com-application-on-a-websphere-mqseries-computer-that-is-running-an-earlier-version-of-the-mqseries-adapter-com-application"></a>若要运行的是早期版本的 MQSeries 适配器 COM + 应用程序的 WebSphere MQSeries 计算机上安装 BizTalk Server 2006 版本的 MQSeries 适配器 COM + 应用程序  
  
1.  从 BizTalk Server 2006 CD 将依赖文件 MSVCR80.dll 和 msvcp80.dll 复制复制到 WebSphere MQSeries 计算机的 \Platform\BootStrap\ 目录运行 Bootstrap.msi。  
  
2.  将从 BizTalk Server 2006 cd 的 \msi\program files\ 目录的文件 MQSAgent.dll 复制到 WebSphere MQSeries 计算机中。  
  
    > [!NOTE]
    >  此外将文件 MQSTrace.cmd 目录中复制此到 WebSphere MQSeries 计算机如果计划使用 MQSAgent 跟踪实用工具。 有关 MQSAgent 跟踪实用工具，请参阅[使用跟踪工具分析 MQSeries 适配器错误](../core/analyzing-mqseries-adapter-errors-with-the-trace-tools.md)。  
  
3.  手动注册组件 MQSAgent.dll 中通过 WebSphere MQSeries 计算机上运行 regsvr32 mqsagent.dll 以：  
  
    ```  
    regsvr32 MQSAgent.dll  
    ```  
  
    > [!NOTE]
    >  从复制到 MQSAgent.dll 的相同目录中运行此命令。  
  
4.  创建一个新 COM + 应用程序为 MQSAgent 组件：  
  
    -   右键单击 COM + 应用程序中，单击**新建**，**应用程序**以显示**COM + 应用程序安装向导**然后单击**下一步**。  
  
    -   单击**创建一个空应用程序**。  
  
    -   输入的名称**MQSAgent2**，请保留为默认选项**服务器应用程序**启用，然后单击**下一步**。  
  
    -   选择的选项**此用户**，输入相应的帐户信息，然后单击**下一步**。  
  
        > [!NOTE]
        >  此帐户应具有连接和 put 和/或获取相应的 IBM WebSphere MQ 队列的权限。  
  
    -   单击**下一步**在添加**应用程序角色**对话框。  
  
    -   单击**下一步**上**向角色添加用户**对话框。  
  
    -   单击 **“完成”**。  
  
5.  将 MQSAgent.dll 组件添加到 MQSAgent2 COM + 应用程序：  
  
    -   单击此项可展开**MQSAgent2** COM + 应用程序。  
  
    -   右键单击**组件**然后单击**新建**，**组件**以启动 COM + 组件安装向导，然后单击**下一步**。  
  
    -   单击**安装新组件**，浏览至文件 MQSAgent.dll，然后单击**打开**。  
  
    -   单击“下一步” ，然后单击“完成” 。  
  
## <a name="see-also"></a>请参阅  
 [使用 MQSeries 适配器](../core/using-the-mqseries-adapter.md)