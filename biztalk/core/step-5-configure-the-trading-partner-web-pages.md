---
title: "步骤 5： 配置贸易合作伙伴网页 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 38c3054d-932a-42b6-a821-8b30604d8426
caps.latest.revision: "38"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 25be80ea28231ebf5e7b79ca9c087461dc8efb4c
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="step-5-configure-the-trading-partner-web-pages"></a>步骤 5： 配置贸易合作伙伴网页
![步骤 5 11](../core/media/tut-step5-of-11.gif "Tut_Step5_of_11")  
  
 在此步骤中，您将执行以下任务设置贸易伙伴网页：  
  
-   启用 HTTP 传输所需的 BTS HTTP Receive ISAPI 筛选器。  
  
-   设置一个文件夹和一个 aspx 页以使用 HTTP 传输将 997 确认路由至合作伙伴组织 Fabrikam。 Fabrikam 虚拟目录将删除为该 997 确认\\997 发送端口的 Destination_URL 设置调出的 _997ToFabrikam 文件夹。  
  
-   将 ASPX 页设置为将原始消息路由至本组织 Contoso。 Contoso 虚拟目录使用 BTSHttpReceive.dll 接收 AS2 消息并将其提交至接收位置。  
  
> [!NOTE]
>  本主题中提供的过程适用于 IIS 7.0。  
  
## <a name="prerequisites"></a>先决条件  
 你必须以 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理员组成员的身份登录。  
  
### <a name="to-enable-the-bts-isapi-filter"></a>启用 BTS ISAPI 筛选器  
  
1.  单击**启动**，指向**所有程序**，指向**管理工具**，然后单击**Internet Information Services (IIS) Manager**.  
  
2.  选择的根 Web 服务器条目并在**功能视图**，双击**处理程序映射**然后在**操作**窗格中，单击**添加脚本映射**.  
  
    > [!NOTE]
    >  在 Web 服务器级别配置脚本映射会导致此映射应用于所有子网站。 如果你想要限制映射到特定的网站或虚拟文件夹，选择目标站点或而不是 Web 服务器的文件夹。  
  
3.  在**添加脚本映射**对话框框中，输入`BtsHttpReceive.dll`中**请求路径**字段。  
  
4.  在**可执行文件**字段中，单击**省略号 （...）**按钮，然后浏览到[!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]HttpReceive。 选择**BtsHttpReceive.dll**，然后单击**确定**。  
  
5.  输入`BizTalk HTTP Receive`中`Name`字段，然后再单击**请求限制**。  
  
6.  在**请求限制**对话框中，选择**谓词**选项卡上，然后选择**的以下谓词之一**。 输入`POST`作为谓词。  
  
7.  上**访问**选项卡上，选择**脚本**，然后单击**确定**。  
  
8.  单击**确定**出现提示时允许 ISAPI 扩展插件，则单击**是**。  
  
9. 右键单击该 BTSHttpReceive.dll 条目，，然后选择**编辑功能权限**。  
  
10. 确保**读取**，**脚本**和**执行**未选中，然后单击**确定**。  
  
11. 单击**功能视图**，然后双击**ISAPI 和 CGI 限制**。  
  
12. 确保 BTSHTTPReceive.dll 的条目存在，并且**限制**设置为**允许**。  
  
    > [!NOTE]
    >  创建脚本映射时，将自动创建 BTSHTTPReceive.dll 的“ISAPI 和 CGI 限制”条目。  
  
### <a name="to-configure-the-fabrikam-web-page"></a>配置 Fabrikam 网页  
  
1.  在 IIS 管理器中，右键单击**应用程序池**和选择**添加应用程序池**。  
  
2.  在**添加应用程序池**对话框框中，输入**BizTalkAppPool**中**名称**，然后选择**.NET Framework V4.0.30210**中**.NET framework 版本**下拉列表。 单击 **“确定”**。  
  
    > [!NOTE]
    >  根据计算机上安装的 [!INCLUDE[netfx40_short](../includes/netfx40-short-md.md)] 版本，.NET Framework 的版本可能会有所不同。  
  
3.  选择**应用程序池**中**功能视图**选择**BizTalkAppPool**，然后单击**高级设置**中**操作**窗格。  
  
4.  在**高级设置**对话框中，设置**启用 32 位应用程序**到**True**。  
  
    > [!NOTE]
    >  仅当希望让 IIS 在 64 位计算机上以 32 位模式运行时，才需要执行此步骤。  
  
5.  选择**标识**，然后单击**省略号 （...）**按钮。  
  
6.  在**应用程序池标识**对话框中，选择**自定义帐户**，然后单击**设置**。  
  
7.  输入**用户名**和**密码**是 administrators 组的成员的用户帐户，输入中的密码**确认密码**，然后单击**确定**三次以返回到 IIS 管理器。  
  
8.  在 IIS 管理器中，打开**站点**文件夹。 右键单击**Default Web Site**，然后选择**添加应用程序**。  
  
9. 在**添加应用程序**对话框框中，输入**Fabrikam**中**别名**，然后单击**选择**。  
  
10. 在**选择应用程序池**对话框中，选择**BizTalkAppPool**单击**确定**。  
  
11. 单击**省略号 （...）**按钮，然后浏览到[!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]为 SDK\AS2 Tutorial\Fabrikam**物理路径**。  
  
12. 单击**测试设置**并验证没有显示在错误**测试连接**对话框。 单击 **“关闭”**，然后单击 **“确定”**。  
  
13. 在 IIS 管理器中，选择 Fabrikam 虚拟目录和在**功能视图**，双击**身份验证**。  
  
14. 在**身份验证**，选择**匿名身份验证**并确认**状态**是**已启用**。 如果**状态**是**禁用**，单击**启用**中**操作**窗格。  
  
### <a name="to-configure-the-contoso-web-page"></a>配置 Contoso 网页  
  
1.  在 IIS 管理器中，打开**站点**文件夹。 右键单击**Default Web Site** ，然后选择**添加应用程序**。  
  
2.  在**添加应用程序**对话框框中，输入**Contoso**中**别名**，然后单击**选择**。  
  
3.  在**选择应用程序池**对话框中，选择**BizTalkAppPool**单击**确定**。  
  
    > [!NOTE]
    >  BizTalkAppPool 是以前在配置 Fabrikam 网页时创建的，并且应设置成管理员组成员的用户标识。  
  
4.  单击**省略号 （...）**按钮，然后浏览到[!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]为 HttpReceive**物理路径**。  
  
5.  单击**测试设置**并验证没有显示在错误**测试连接**对话框。 单击 **“关闭”**，然后单击 **“确定”**。  
  
6.  在 IIS 管理器中，选择 Contoso 虚拟目录和在**功能视图**，双击**身份验证**。  
  
7.  在**身份验证**，选择**匿名身份验证**并确认**状态**是**已启用**。 如果**状态**是**禁用**，单击**启用**中**操作**窗格。  
  
## <a name="next-steps"></a>后续步骤  
 配置接收位置 (**Receive_AS2**) 中所述从 Fabrikam，接收 AS2 消息[步骤 6： 配置 EDI AS2 接收位置](../core/step-6-configure-the-edi-as2-receive-location.md)。  
  
## <a name="see-also"></a>另请参阅  
 [教程 3: AS2 教程](../core/tutorial-3-as2-tutorial.md)