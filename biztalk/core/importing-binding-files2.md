---
redirect_url: /biztalk/core/deploying-biztalk-adapter-for-jd-edwards-enterpriseone/
redirect_document_id: True
ROBOTS: NOINDEX
ms.openlocfilehash: 0bc5b29ff129b145d6b55cbe44ea3aa6a97def76
ms.sourcegitcommit: dd7c54feab783ae2f8fe75873363fe9ffc77cd66
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/07/2017
---
# <a name="importing-binding-files"></a>导入绑定文件
本主题提供有关导入过程，为博士 Edwards EnterpriseOne 部署的 BizTalk Adapter 时的一些信息。 当你重新绑定文件 （和程序集） 部署的目标计算机上，发送端口和接收位置已替换为 XML 绑定文件中时它们重新导入。  
  
### <a name="to-clean-the-target-computer"></a>若要清除目标计算机中的  
  
-   删除发送端口和接收位置绑定到业务流程。  
  
     如果未安装目标计算机上安装的 Visual Studio，你可以通过运行脚本中删除的端口：  
  
     [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]SDK\Samples\Admin\WMI\  
  
     删除发送 Port\VBScript\RemoveSendPort.vbs  
  
     [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]SDK\Samples\Admin\WMI\  
  
     删除接收 Port\VBScript\RemoveReceivePort.vbs  
  
     例如，从命令提示符下运行：  
  
     **cscript RemoveSendPort.vbs\<发送端口名称 >**  
  
## <a name="see-also"></a>另请参阅  
 [导入博士 Edwards EnterpriseOne 应用](../core/deploying-biztalk-adapter-for-jd-edwards-enterpriseone.md)