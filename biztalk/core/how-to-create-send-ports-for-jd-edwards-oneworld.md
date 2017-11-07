---
redirect_url: /biztalk/core/adding-biztalk-adapter-for-jd-edwards-oneworld/
redirect_document_id: True
ROBOTS: NOINDEX
ms.openlocfilehash: d65b87fbcbdaf89289406ae6850b70c605123451
ms.sourcegitcommit: dd7c54feab783ae2f8fe75873363fe9ffc77cd66
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/07/2017
---
# <a name="how-to-create-send-ports-for-jd-edwards-oneworld"></a>如何创建 JD Edwards OneWorld 的发送端口
使用以下过程创建发送端口。  
  
### <a name="to-create-a-send-port"></a>创建发送端口的步骤  
  
1.  在 BizTalk Server 管理控制台中，展开**BizTalk Server 管理**，展开**BizTalk 组**，展开**应用程序**，然后导航到所需的应用程序。  
  
2.  右键单击**发送端口**，指向**新建**，然后单击**静态请求-响应发送端口**。  
  
    > [!NOTE]
    >  你还可以使用**静态单向端口**。  
  
3.  在**发送端口属性**对话框中，在**名称**字段中，键入发送端口名称 (例如，键入**SendToJDE**。)  
  
4.  在**类型**下拉列表中，选择**JDEOneWorld**。  
  
5.  在**URI**下拉列表中，选择发送处理程序。  
  
6.  单击 **“确定”**。  
  
