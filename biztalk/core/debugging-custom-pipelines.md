---
title: 调试自定义管道 |Microsoft 文档
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
ms.openlocfilehash: be0c8714f0349ad415beca010795d2cb0b57aabb
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/28/2017
ms.locfileid: "25970347"
---
# <a name="debugging-custom-pipelines"></a>调试自定义管道
当消息处理在您的自定义管道中失败时，可以使用源级别的调试来确定和解决问题。 源级别调试都完成使用[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]调试器将附加到 BTSNTSVC.exe （如果部署自定义管道） 或 Pipeline.exe （如果使用独立的管道工具）。  
  
## <a name="procedures"></a>过程  
 使用以下过程调试自定义管道  
  
### <a name="how-to-debug-a-deployed-pipeline"></a>如何调试已部署的管道  
 “组中心”页中的跟踪查询和事件查看器提供有关已部署组件中消息处理失败的有用信息。 此信息通常可用于缩小问题来源的范围。 一旦发觉问题可能涉及某一自定义管道后，就可以使用源级别调试来确定任何有问题的代码。  
  
##### <a name="to-debug-a-deployed-custom-pipeline-using-visual-studio"></a>使用 Visual Studio 调试已部署的自定义管道  
  
1.  加载自定义管道项目解决方案到[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]。  
  
2.  更改您的解决方案的输出路径*\<安装文件夹\>* \Pipeline 组件。 在解决方案资源管理器，右键单击你的项目，单击生成选项卡，然后通过单击更改输出路径**浏览**按钮，然后选择*\<安装文件夹\>* \Pipeline 组件的目录。  
  
3.  在[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]，通过单击部署解决方案**生成**&#124;**部署**。  
  
4.  重新启动运行管道的主机实例。 使用 BizTalk Server 管理控制台，导航到运行管道的主机实例，右键单击主机实例，然后单击**重新启动**。  
  
5.  附加[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]BTSNTSVC.exe 的调试器。 这可以通过单击**调试**&#124;**附加到进程**，在所有会话中，单击显示进程，然后双击 BTSNTSVC.exe。  
  
6.  设置断点。  
  
7.  将某一消息放入适当位置可以启动自定义管道组件。 处理应在您设置的断点处停止。  
  
> [!NOTE]
>  如果您的代码引发异常，BizTalk Server 将会捕获该异常并最终挂起消息。 若要避免此行为，您应该在第一次偶然出现异常时中止。  
  
### <a name="how-to-debug-using-pipelineexe"></a>如何使用 Pipeline.exe 进行调试  
 你还可以测试使用 Pipeline.exe 的自定义管道。 这样做不要求你能够部署代价不在与生产类似的条件下运行管道的优势。  
  
> [!NOTE]
>  如果您的自定义管道使用平面文件组装器/拆装器，则 Pipeline.exe 将不会正确执行。 其原因在于，Pipeline.exe 并不访问 BizTalk 数据库。 一种解决方案是删除汇编 / 反汇编程序组件并单独 FFAsm.exe FFDasm.exe 与对其进行测试。 请参阅[管道工具](../core/pipeline-tools.md)有关详细信息。  
  
##### <a name="to-debug-a-custom-pipeline-using-pipelineexe-and-visual-studio"></a>使用 Pipeline.exe 和 Visual Studio 调试自定义管道  
  
1.  加载自定义管道项目解决方案到[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]。  
  
2.  更改您的解决方案的输出路径*\<安装文件夹\>* \Pipeline 组件。 在解决方案资源管理器，右键单击你的项目，单击生成选项卡，然后通过单击更改输出路径**浏览**按钮，然后选择*\<安装文件夹\>* \Pipeline 组件的目录。  
  
3.  更改解决方案的启动操作。 在解决方案资源管理器，右键单击你的项目，单击调试选项卡，单击启动外部程序，然后单击 **...** 并导航到*\<安装文件夹\>* \SDK\Utilities\PipelineTools 选择 Pipeline.exe。 在启动选项，输入适合你的组件的命令行自变量。 Pipeline.exe 的详细信息，请参阅[管道工具](../core/pipeline-tools.md)。 典型配置指定管道和示例文件：  
  
    ```  
    <Path>\YourPipeline.btp -d <Path>\YourTestFile.txt -c  
    ```  
  
4.  设置您的断点。  
  
5.  按下 F5 以便开始调试。  
  
## <a name="see-also"></a>另请参阅  
 [管道工具](../core/pipeline-tools.md)