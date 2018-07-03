---
redirect_url: /biztalk/core/deploying-biztalk-adapter-for-jd-edwards-enterpriseone/
redirect_document_id: true
ROBOTS: NOINDEX
ms.openlocfilehash: db28e1db8a0f2d4149e0539e2bce195cd91b1279
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36973982"
---
# <a name="importing-binding-files"></a>导入绑定文件
本主题提供有关导入过程，在部署用于 JD Edwards EnterpriseOne 的 BizTalk 适配器时的一些信息。 当重新绑定文件 （和程序集） 部署的目标计算机上，发送端口和接收位置将替换中的 XML 绑定文件时它们重新导入。  
  
### <a name="to-clean-the-target-computer"></a>若要清理目标计算机  
  
- 删除发送端口和接收位置绑定到业务流程。  
  
   如果未安装目标计算机上安装的 Visual Studio，则可以通过运行脚本删除端口：  
  
   [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]SDK\Samples\Admin\WMI\  
  
   删除发送 Port\VBScript\RemoveSendPort.vbs  
  
   [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]SDK\Samples\Admin\WMI\  
  
   删除接收 Port\VBScript\RemoveReceivePort.vbs  
  
   例如，从命令提示符下运行：  
  
   **cscript RemoveSendPort.vbs\<发送端口名称\>**  
  
## <a name="see-also"></a>请参阅  
 [导入 JD Edwards EnterpriseOne 应用程序](../core/deploying-biztalk-adapter-for-jd-edwards-enterpriseone.md)