---
redirect_url: /biztalk/core/deploying-biztalk-adapter-for-tibco-rendezvous/
redirect_document_id: true
ROBOTS: NOINDEX
ms.openlocfilehash: 12e8a37da357693b97659c1717ead750e558e62b
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "37018440"
---
# <a name="how-to-clean-the-target-computer"></a>如何清理目标计算机
部署会覆盖接收位置配置。 当将绑定文件 （和程序集） 部署的目标计算机上，发送端口和接收位置将替换 XML 绑定文件中所导入。  
  
### <a name="to-clean-the-target-computer"></a>若要清理目标计算机  
  
- 删除发送端口和接收位置绑定到业务流程。  
  
   如果没有在目标计算机上安装 Microsoft Visual Studio，则可以通过运行这些脚本删除端口：  
  
  - [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]SDK\Samples\Admin\WMI\Remove Send Port\VBScript\RemoveSendPort.vbs  
  
  - [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]SDK\Samples\Admin\WMI\Remove Receive Port\VBScript\RemoveReceivePort.vbs  
  
     例如，在命令提示符下运行：  
  
     **cscript RemoveSendPort.vbs\<发送端口名称\>**  
  
