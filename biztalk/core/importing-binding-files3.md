---
redirect_url: /biztalk/core/deploying-biztalk-adapter-for-jd-edwards-oneworld/
redirect_document_id: True
ROBOTS: NOINDEX
ms.openlocfilehash: 5c5cce40f3fbeb580ec7ba854d02cb243e1742b4
ms.sourcegitcommit: dd7c54feab783ae2f8fe75873363fe9ffc77cd66
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/07/2017
---
# <a name="importing-binding-files"></a>导入绑定文件

## <a name="overview"></a>概述
BizTalk Server 用于导入绑定文件之前，请验证以下各项：  
  
-   CLASSPATH 指向 JD Edwards 特定文件的特定位置。 验证在新计算机上这些文件的位置是否相同，否则编辑绑定文件。  
  
-   用于响应的文件夹存在，并且在新计算机上相同，否则编辑绑定文件。  
  
-   如果在配置中存在 JD Edwards 系统密码，则在绑定文件中另存为 *****。 
  
> [!NOTE]
>  部署将覆盖接收位置配置。 如果在目标计算机上部署绑定文件（和程序集），则发送端口和接收位置将替换为所导入的 XML 绑定文件中的发送端口和接收位置。  
  
## <a name="import-the-binding-files"></a>导入的绑定文件  
  
1.  上**启动**菜单上，指向**Program Files**，指向**Microsoft BizTalk Server**，然后单击**BizTalk Server 管理**若要启动 BizTalk Server 管理控制台。  
  
2.  展开 BizTalk Server 管理中，展开**BizTalk 组**，然后展开**应用程序**。  
  
3.  右键单击所需应用程序，指向**导入**，然后单击**绑定**。  
  
4.  在**导入绑定**对话框中，浏览并选择绑定文件，然后单击**打开**。  
  
## <a name="cleaning-the-target-computer"></a>清理目标计算机  
删除发送端口和绑定到业务流程的接收位置。  
  
## <a name="see-also"></a>另请参阅  
 [将项目添加到 BizTalk 管理](../core/adding-biztalk-adapter-for-jd-edwards-oneworld.md)   
 [导入博士 Edwards OneWorld 应用](deploying-biztalk-adapter-for-jd-edwards-oneworld.md)