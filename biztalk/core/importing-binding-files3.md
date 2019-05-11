---
redirect_url: /biztalk/core/deploying-biztalk-adapter-for-jd-edwards-oneworld/
redirect_document_id: true
ROBOTS: NOINDEX
ms.openlocfilehash: 920693d0e3ff02b00d8675261db3050f8866b234
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65332171"
---
# <a name="importing-binding-files"></a>导入绑定文件

## <a name="overview"></a>概述
使用 BizTalk Server 导入绑定文件之前，请验证以下：  
  
-   CLASSPATH 指向 JD Edwards 特定文件的特定位置。 验证这些文件的位置是相同的新计算机上，或编辑绑定文件。  
  
-   用于响应文件夹存在并在新计算机上完全相同或编辑绑定文件。  
  
-   JD Edwards 系统密码，如果存在在配置中，将保存为 * * * 绑定文件中。 
  
> [!NOTE]
>  部署会覆盖接收位置配置。 在目标计算机上部署绑定文件 （和程序集），发送端口和接收位置将替换 XML 绑定文件中导入它们。  
  
## <a name="import-the-binding-files"></a>导入绑定文件  
  
1.  上**启动**菜单，依次指向**Program Files**，指向**Microsoft BizTalk Server**，然后单击**BizTalk Server 管理**若要启动 BizTalk Server 管理控制台。  
  
2.  展开 BizTalk Server 管理，展开**BizTalk 组**，然后展开**应用程序**。  
  
3.  右键单击所需应用程序，指向**导入**，然后单击**绑定**。  
  
4.  在中**导入绑定**对话框中，浏览并选择绑定文件，然后单击**打开**。  
  
## <a name="cleaning-the-target-computer"></a>清理目标计算机  
删除发送端口和绑定到业务流程的接收位置。  
  
## <a name="see-also"></a>请参阅  
 [将项目添加到 BizTalk 管理](../core/adding-biztalk-adapter-for-jd-edwards-oneworld.md)   
 [导入 JD Edwards OneWorld 应用程序](deploying-biztalk-adapter-for-jd-edwards-oneworld.md)