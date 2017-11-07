---
redirect_url: /biztalk/core/deploying-biztalk-adapter-for-tibco-enterprise-message-service/
redirect_document_id: True
ROBOTS: NOINDEX
ms.openlocfilehash: 93cb3a1420b60183ff42108c32224cf4707b9cd7
ms.sourcegitcommit: dd7c54feab783ae2f8fe75873363fe9ffc77cd66
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/07/2017
---
# <a name="how-to-clean-the-target-computer"></a>如何清洗目标计算机
部署将覆盖接收位置配置。 当你部署的目标计算机上，发送端口的绑定文件 （和程序集） 和接收位置已替换为 XML 绑定文件中导入时。  
  
### <a name="to-clean-the-target-computer"></a>若要清除目标计算机中的  
  
-   删除与业务流程绑定的所有发送端口和接收位置。  
  
     如果你没有在目标计算机上安装的 Microsoft Visual Studio，你可以通过运行这些脚本中删除的端口：  
  
     \<Microsoft BizTalk Server > \SDK\Samples\Admin\WMI\Remove 发送 Port\VBScript\RemoveSendPort.vbs  
  
     \<Microsoft BizTalk Server > \SDK\Samples\Admin\WMI\Remove 接收 Port\VBScript\RemoveReceivePort.vbs  
  
     例如，在命令提示符下运行：  
  
     **cscript RemoveSendPort.vbs\<发送端口名称 >**  
  
