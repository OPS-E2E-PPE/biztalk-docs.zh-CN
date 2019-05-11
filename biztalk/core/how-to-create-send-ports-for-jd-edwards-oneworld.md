---
redirect_url: /biztalk/core/adding-biztalk-adapter-for-jd-edwards-oneworld/
redirect_document_id: true
ROBOTS: NOINDEX
ms.openlocfilehash: e2101cee6e82283984bd0e830a583a96613d21b6
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65385424"
---
# <a name="how-to-create-send-ports-for-jd-edwards-oneworld"></a>如何创建 JD Edwards OneWorld 的发送端口
使用以下过程创建发送端口。  
  
### <a name="to-create-a-send-port"></a>若要创建的发送端口  
  
1.  在 BizTalk Server 管理控制台中，展开**BizTalk Server 管理**，展开**BizTalk 组**，展开**应用程序**，然后导航到所需的应用程序。  
  
2.  右键单击**发送端口**，依次指向**新建**，然后单击**静态要求响应发送端口**。  
  
    > [!NOTE]
    >  此外可以使用**静态单向端口**。  
  
3.  在中**发送端口属性**对话框中**名称**字段中，键入发送端口名称 (例如，键入**SendToJDE**。)  
  
4.  在中**类型**下拉列表中，选择**JDEOneWorld**。  
  
5.  在中**URI**下拉列表中，选择发送处理程序。  
  
6.  单击“确定” 。  
  
