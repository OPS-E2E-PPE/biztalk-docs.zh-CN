---
title: 调试自定义管道 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 27e5445a-6415-4c52-a450-b74a71fc4aa2
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 3841b300647a7a0b5859fca828f8aa5a840e9755
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65352570"
---
# <a name="debugging-custom-pipelines"></a>调试自定义管道
当消息处理失败时在自定义管道中时，可以使用源级别调试来确定和解决问题。 完成源级别调试使用[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]调试器附加到 BTSNTSVC.exe （如果部署自定义管道） 或 Pipeline.exe （如果使用独立的管道工具）。  
  
## <a name="procedures"></a>过程  
 使用以下过程调试自定义管道。  
  
### <a name="how-to-debug-a-deployed-pipeline"></a>如何调试已部署的管道  
 组中心页和事件查看器中的跟踪查询，提供有关已部署组件中消息处理失败的有用信息。 此信息通常用于缩小问题的来源。 一旦已其中涉及自定义管道，源级别调试可用来确定任何有问题的代码。  
  
##### <a name="to-debug-a-deployed-custom-pipeline-using-visual-studio"></a>若要调试已部署的自定义管道使用 Visual Studio  
  
1. 加载到自定义管道项目解决方案[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]。  
  
2. 更改您的解决方案的输出路径*\<安装文件夹\>* \Pipeline Components。 在解决方案资源管理器中右键单击你的项目，单击生成选项卡，然后通过单击更改输出路径**浏览**按钮，然后选择*\<安装文件夹\>* \Pipeline components 目录。  
  
3. 从内部[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]，通过单击部署解决方案**构建** &#124; **部署**。  
  
4. 重新启动运行管道的主机实例。 使用 BizTalk Server 管理控制台，导航到运行管道的主机实例，右键单击主机实例，然后单击**重新启动**。  
  
5. 附加[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]BTSNTSVC.exe 的调试器。 这可以通过单击**调试** &#124; **附加到进程**，在所有会话中，单击显示的进程，然后双击 BTSNTSVC.exe。  
  
6. 设置断点。  
  
7. 将消息放入适当的位置，可以启动自定义管道组件。 处理应在你设置的断点处停止。  
  
> [!NOTE]
>  如果你的代码引发异常，BizTalk Server 将其捕获并最终挂起消息。 若要避免此行为，应在第一机会异常上中断。  
  
### <a name="how-to-debug-using-pipelineexe"></a>如何调试使用 Pipeline.exe  
 此外可以测试自定义管道使用 Pipeline.exe。 这一优点是您无需部署代价是类似于生产的条件下无法运行管道。  
  
> [!NOTE]
>  如果在自定义管道使用平面文件组装器 / 拆装器，Pipeline.exe 将不会正确执行。 这是因为 Pipeline.exe 不访问 BizTalk 数据库。 一种解决方案是删除这些组装器 / 拆装器组件并分别使用 FFDasm.exe 和 FFAsm.exe 测试它们。 请参阅[管道工具](../core/pipeline-tools.md)有关详细信息。  
  
##### <a name="to-debug-a-custom-pipeline-using-pipelineexe-and-visual-studio"></a>若要调试自定义管道使用 Pipeline.exe 和 Visual Studio  
  
1. 加载到自定义管道项目解决方案[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]。  
  
2. 更改您的解决方案的输出路径*\<安装文件夹\>* \Pipeline Components。 在解决方案资源管理器中右键单击你的项目，单击生成选项卡，然后通过单击更改输出路径**浏览**按钮，然后选择*\<安装文件夹\>* \Pipeline components 目录。  
  
3. 更改你的解决方案的启动操作。 在解决方案资源管理器中右键单击你的项目，单击调试选项卡，单击启动外部程序，然后单击 **...** 然后导航到*\<安装文件夹\>* \SDK\Utilities\PipelineTools，然后选择 Pipeline.exe。 在启动选项下输入适合您的组件的命令行参数。 有关 Pipeline.exe 的详细信息，请参阅[管道工具](../core/pipeline-tools.md)。 典型配置指定管道和示例文件：  
  
   ```  
   <Path>\YourPipeline.btp -d <Path>\YourTestFile.txt -c  
   ```  
  
4. 设置您的断点。  
  
5. 按 F5 开始调试。  
  
## <a name="see-also"></a>请参阅  
 [管道工具](../core/pipeline-tools.md)