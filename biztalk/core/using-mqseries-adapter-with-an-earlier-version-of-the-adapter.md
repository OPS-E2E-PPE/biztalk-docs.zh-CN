---
redirect_url: /biztalk/core/mqseries-adapter-deployment-options
redirect_document_id: true
ROBOTS: NOINDEX
ms.openlocfilehash: 2aa74be2d86bcb8f32661fdcf06727eb6391861d
ms.sourcegitcommit: 32f380810b90b70e5df7be72a6a14988a747868e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/28/2018
ms.locfileid: "29710704"
---
# <a name="using-mqseries-adapter-with-an-earlier-version-of-the-adapter"></a>MQSeries 适配器使用早期版本的适配器
MQSeries 适配器的不同 BizTalk Server 版本可以所有使用同一个远程 WebSphere MQ 服务器上 Windows。 这是由于与 MQSeries 适配器一起使用的以下版本的 COM+ 应用程序可以同时存在于同一 WebSphere MQSeries 计算机上：  
  
-   **MQSAgent (MQSAgent2) COM + 应用程序**用于 MQSeries 适配器 (BizTalk Server 2006) 
  
-   **MQSAgent COM + 应用程序**用于 MQSeries 适配器 （BizTalk Server 2004 年）  
  
-   **MQHelper COM + 应用程序**用于 MQSeries 适配器 (BizTalk Server 2002) 
  
> [!NOTE]
>  在配置这些 COM+ 应用程序的并行安装时，请确保这些 COM+ 应用程序均未配置为使用相同的 MQSeries 队列。  
  
> [!IMPORTANT]
>  如果上 WebSphere 未安装 BizTalk Server 的早期版本，则仅支持通过并行安装的 MQSeries 适配器 COM + 应用程序使用 MQSeries 适配器 COM + 应用程序的较早版本的 BizTalk Server 2006 版本MQSeries 计算机。  
  
### <a name="to-install-the-biztalk-server-2006-version-of-the-mqseries-adapter-com-application-on-a-websphere-mqseries-computer-that-is-running-an-earlier-version-of-the-mqseries-adapter-com-application"></a>将 BizTalk Server 2006 版本的 MQSeries 适配器 COM+ 应用程序安装在运行早期版本的 MQSeries 适配器 COM+ 应用程序的 WebSphere MQSeries 计算机上  
  
1.  从 BizTalk Server 2006 CD 来将 MSVCR80.dll 和 MSVCP80.dll 的依赖文件复制到 WebSphere MQSeries 计算机的 \Platform\BootStrap\ 目录中运行 Bootstrap.msi。  
  
2.  将文件 MQSAgent.dll 从 BizTalk Server 2006 CD 上的 \Msi\Program Files\ 目录复制到 WebSphere MQSeries 计算机。  
  
    > [!NOTE]
    >  如果您计划使用 MQSAgent 跟踪实用工具，请从此目录将文件 MQSTrace.cmd 也复制到 WebSphere MQSeries 计算机中。 跟踪实用工具 MQSAgent 有关详细信息请参阅[分析 MQSeries 适配器跟踪工具错误](../core/analyzing-mqseries-adapter-errors-with-the-trace-tools.md)。  
  
3.  请通过在 WebSphere MQSeries 计算机上运行 regsvr32 mqsagent.dll 以手动方式注册 MQSAgent.dll 中的组件。  
  
    ```  
    regsvr32 MQSAgent.dll  
    ```  
  
    > [!NOTE]
    >  从 MQSAgent.dll 所复制到的目标目录运行此命令。  
  
4.  为 MQSAgent 组件创建新的 COM+ 应用程序：  
  
    -   右键单击 COM + 应用程序，单击 **新建**, ，**应用程序** 以显示 **COM + 应用程序安装向导** 单击 **下一步**。  
  
    -   单击 **创建空的应用程序**。  
  
    -   输入的名称 **MQSAgent2**, ，保留默认选项为 **服务器应用程序** 启用和单击 **下一步**。  
  
    -   选择的选项 **此用户**, ，输入合适的帐户信息，请单击 **下一步**。  
  
        > [!NOTE]
        >  该帐户应该在相应的 IBM WebSphere MQ 队列中拥有 connect 及 put 和/或 get 权限。  
  
    -   单击 **下一步** 在添加 **应用程序角色** 对话框。  
  
    -   单击 **下一步** 上 **向角色添加用户** 对话框。  
  
    -   单击 **“完成”**。  
  
5.  将 MQSAgent.dll 组件添加到 MQSAgent2 COM+ 应用程序：  
  
    -   单击以展开 **MQSAgent2** COM + 应用程序。  
  
    -   右键单击 **组件** 单击 **新建**, ，**组件** 启动 COM + 组件安装向导，然后单击 **下一步**。  
  
    -   单击 **安装新组件**, ，浏览到文件 MQSAgent.dll，然后单击 **打开**。  
  
    -   单击“下一步” ，然后单击“完成” 。  
  
## <a name="see-also"></a>另请参阅  
 [使用 MQSeries 适配器](../core/using-the-mqseries-adapter.md)