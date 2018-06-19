---
redirect_url: /biztalk/core/deploying-biztalk-adapter-for-peoplesoft-enterprise/
redirect_document_id: true
ROBOTS: NOINDEX
ms.openlocfilehash: 907c21377a6affd5a99576137a5babaa1626c135
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/28/2017
ms.locfileid: "25971299"
---
# <a name="import-binding-files"></a>导入绑定文件

## <a name="overview"></a>概述
在使用 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 导入绑定文件之前，请验证以下各项：  
  
-   CLASSPATH 指向 PeopleSoft 特定文件的特定位置。 验证这些文件的位置是否在新计算机上相同，或编辑绑定文件。  
  
-   响应的文件夹必须存在并且可在新计算机上完全相同，或编辑绑定文件。  
  
-   如果在配置中存在 PeopleSoft Enterprise 系统密码，则在绑定文件中另存为 *****。 
  
> [!NOTE]
>  部署会覆盖接收位置配置。 如果在目标计算机上部署绑定文件和程序集，则发送端口和接收位置将替换为所导入的 XML 绑定文件中的发送端口和接收位置。  
  
 有关导入绑定文件的分步指导信息，请参阅 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 文档中的主题“如何将绑定导入到 BizTalk 组”。  
  
## <a name="clean-the-target-computer"></a>清除目标计算机中的  
若要清除目标计算机上部署新的应用程序、 删除发送端口和接收位置绑定到业务流程。  
  
如果没有在目标计算机上安装 Microsoft [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]，则可通过运行下面的脚本删除端口：  
  
**\<Microsoft BizTalk Server\>\SDK\Samples\Admin\WMI\Remove 发送 Port\VBScript\RemoveSendPort.vbs**  
  
**\<Microsoft BizTalk Server\>\SDK\Samples\Admin\WMI\Remove 接收 Port\VBScript\RemoveReceivePort.vbs**  
  
例如，在命令提示符下运行：  
  
**cscript RemoveSendPort.vbs\<发送端口名称\>**  
  
