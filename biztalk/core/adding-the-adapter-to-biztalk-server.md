---
redirect_url: /biztalk/core/adding-biztalk-adapter-for-jd-edwards-oneworld/
redirect_document_id: true
ROBOTS: NOINDEX
ms.openlocfilehash: e464a792ab13d1b05b9c4d2ee9cc46ed15b1a55b
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65360831"
---
# <a name="adding-the-adapter-to-biztalk-server"></a>将适配器添加到 BizTalk Server
用于 JD Edwards OneWorld 的 Microsoft BizTalk 适配器包含接收处理程序和发送处理程序文件夹。 发送处理程序文件夹包含 BizTalkServerApplication。 用于 JD Edwards OneWorld 的 BizTalk 适配器是可创建对象;在进程中运行它与 BizTalk Server 运行，而不在独立的主机进程中。  
  
 使用以下过程将适配器添加到 BizTalk Server。  
  
### <a name="to-add-biztalk-adapter-for-jd-edwards-oneworld"></a>若要添加用于 JD Edwards OneWorld 的 BizTalk 适配器  
  
1. 上**启动**菜单，依次指向**Program Files**，指向[!INCLUDE[btsBizTalkServer2006r3ui](../includes/btsbiztalkserver2006r3ui-md.md)]，然后单击**BizTalk Server 管理**启动[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理控制台。  
  
2. 展开**BizTalk Server 管理**，展开**BizTalk 组**，然后展开**平台设置**。  
  
3. 右键单击**适配器**，依次指向**新建**，然后单击**适配器**。  
  
4. 在中**适配器属性**对话框中，键入适配器的名称。 例如，JDEdwards。  
  
5. 选择**JDEOneWorld**从**适配器**列表，，然后单击**确定**。  
  
## <a name="verifying-the-adapter"></a>验证适配器  
 在中[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理控制台中，你可以验证适配器工作正常，通过查看**逻辑系统**窗口。 在初始安装时，此窗口为空，因为尚未建立与服务器系统的连接也没有建立任何逻辑系统。  
  
#### <a name="to-verify-that-the-adapter-is-running-correctly"></a>若要验证适配器正常运行  
  
1. 在中[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理控制台中，展开**BizTalk 组**，展开**平台设置**，展开**适配器**，然后选择**JDEOneWorld**。  
  
2. 在细节窗格中，右键单击**BizTalkServerApplication**，然后选择**属性**。  
  
3. 单击 **“属性”** 选项卡。  
  
4. 设置 SQL 连接参数。  
  
   -   **定义 SQL 数据库参数-** SQL Server 名称和数据库都是在安装时设置。 这是您可以重新定义的服务器和数据库的此适配器的文本区域。  
  
5. 单击**关闭**退出**逻辑系统**窗口。  
  
    下一步是添加逻辑系统使用[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]。  
  
## <a name="see-also"></a>请参阅  
 [规划和体系结构](../core/planning-and-architecture17.md)   
 [用于 JD Edwards OneWorld 的 BizTalk 适配器中的安全性](../core/security-in-biztalk-adapter-for-jd-edwards-oneworld.md)   
 [添加用于 JD Edwards OneWorld 的 BizTalk 适配器](../core/adding-biztalk-adapter-for-jd-edwards-oneworld.md)