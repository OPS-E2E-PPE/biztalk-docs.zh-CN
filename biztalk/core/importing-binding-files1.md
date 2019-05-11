---
redirect_url: /biztalk/core/deploying-biztalk-adapter-for-peoplesoft-enterprise/
redirect_document_id: true
ROBOTS: NOINDEX
ms.openlocfilehash: 7f8c87e4d29b06b46b559dccf18c3e1038a34fae
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65332125"
---
# <a name="import-binding-files"></a>导入绑定文件

## <a name="overview"></a>概述
在使用之前[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]要导入绑定文件，请确认以下：  
  
-   CLASSPATH 指向 PeopleSoft 特定文件的特定位置。 验证这些文件的位置，并在新计算机上相同，或编辑绑定文件。  
  
-   用于响应文件夹必须存在并且可在新计算机上完全相同，或编辑绑定文件。  
  
-   PeopleSoft Enterprise 系统密码，如果存在在配置中，将保存为 * * * 绑定文件中。 
  
> [!NOTE]
>  部署会覆盖接收位置配置。 当部署绑定文件和程序集的目标计算机上，发送端口和接收位置将替换 XML 绑定文件中所导入。  
  
 有关导入绑定文件的分步说明请参阅中的主题"如何为导入绑定到 BizTalk 组"[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]文档。  
  
## <a name="clean-the-target-computer"></a>清理目标计算机  
若要清理目标计算机部署新应用程序、 删除发送端口和接收位置绑定到业务流程。  
  
如果你没有 Microsoft[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]安装在目标计算机上，您可通过运行这些脚本删除端口：  
  
**\<Microsoft BizTalk Server\>\SDK\Samples\Admin\WMI\Remove Send Port\VBScript\RemoveSendPort.vbs**  
  
**\<Microsoft BizTalk Server\>\SDK\Samples\Admin\WMI\Remove Receive Port\VBScript\RemoveReceivePort.vbs**  
  
例如，在命令提示符下运行：  
  
**cscript RemoveSendPort.vbs\<发送端口名称\>**  
  
