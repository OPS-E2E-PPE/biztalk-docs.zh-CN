---
redirect_url: /biztalk/core/deploying-biztalk-adapter-for-tibco-enterprise-message-service/
redirect_document_id: true
ROBOTS: NOINDEX
ms.openlocfilehash: 936f25f9dda62cf881b4539a0eee475118294f95
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65342382"
---
# <a name="how-to-clean-the-target-computer"></a>如何清理目标计算机
部署会覆盖接收位置配置。 当将绑定文件 （和程序集） 部署的目标计算机上，发送端口和接收位置将替换 XML 绑定文件中所导入。  
  
### <a name="to-clean-the-target-computer"></a>若要清理目标计算机  
  
-   删除任何发送端口和接收位置绑定到业务流程。  
  
     如果没有在目标计算机上安装 Microsoft Visual Studio，则可以通过运行这些脚本删除端口：  
  
     \<Microsoft BizTalk Server\>\SDK\Samples\Admin\WMI\Remove Send Port\VBScript\RemoveSendPort.vbs  
  
     \<Microsoft BizTalk Server\>\SDK\Samples\Admin\WMI\Remove Receive Port\VBScript\RemoveReceivePort.vbs  
  
     例如，在命令提示符下运行：  
  
     **cscript RemoveSendPort.vbs\<发送端口名称\>**  
  
