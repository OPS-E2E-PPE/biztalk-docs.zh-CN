---
title: 步骤 5：配置贸易合作伙伴网页 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 38c3054d-932a-42b6-a821-8b30604d8426
caps.latest.revision: 38
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 149e4a2ad60cc082890b0beb8a5517142e4a27c8
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65244392"
---
# <a name="step-5-configure-the-trading-partner-web-pages"></a>步骤 5：配置贸易合作伙伴网页
![步骤 5 11](../core/media/tut-step5-of-11.gif "Tut_Step5_of_11")  
  
 在此步骤中，您可以执行以下任务设置贸易伙伴网页：  
  
-   启用 HTTP 传输所需的 BTS HTTP Receive ISAPI 筛选器。  
  
-   设置文件夹和一个 aspx 页以将 997 确认路由到合作伙伴组织 Fabrikam 使用 HTTP 传输。 Fabrikam 虚拟目录将 997 确认到\\_997ToFabrikam 文件夹，997 发送端口的 Destination_URL 设置中调出。  
  
-   设置 ASPX 页以原始消息路由至本组织 Contoso。 Contoso 虚拟目录使用 BTSHttpReceive.dll 接收 AS2 消息并将其提交到接收位置。  
  
> [!NOTE]
>  本主题中提供的过程适用于 IIS 7.0。  
  
## <a name="prerequisites"></a>先决条件  
 必须以成员的身份登录[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]Administrators 组。  
  
### <a name="to-enable-the-bts-isapi-filter"></a>若要启用 BTS ISAPI 筛选器  
  
1. 单击**启动**，依次指向**所有程序**，指向**管理工具**，然后单击**Internet Information Services (IIS) Manager**.  
  
2. 选择根 Web 服务器条目并在**功能视图**，双击**处理程序映射**，然后在**操作**窗格中，单击**添加脚本映射**.  
  
   > [!NOTE]
   >  在 Web 服务器级别配置的脚本映射将导致此映射应用于所有子网站。 如果你想要将映射限制到特定网站或虚拟文件夹，选择文件夹而不是 Web 服务器的目标站点。  
  
3. 在中**添加脚本映射**对话框框中，输入`BtsHttpReceive.dll`中**请求路径**字段。  
  
4. 在中**可执行文件**字段中，单击**省略号 （...）** 按钮并浏览到[!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]\HttpReceive。 选择**BtsHttpReceive.dll**，然后单击**确定**。  
  
5. 输入`BizTalk HTTP Receive`中`Name`字段中，然后依次**请求限制**。  
  
6. 在中**请求限制**对话框中，选择**谓词**选项卡，然后选择**以下谓词之一**。 输入`POST`作为谓词。  
  
7. 上**访问**选项卡上，选择**脚本**，然后单击**确定**。  
  
8. 单击**确定**并在提示是否允许 ISAPI 扩展，请单击**是**。  
  
9. 右键单击 BTSHttpReceive.dll 条目，然后选择**编辑功能权限**。  
  
10. 絋粄**读**，**脚本**并**Execute**未选中，然后单击**确定**。  
  
11. 单击**功能视图**，然后双击**ISAPI 和 CGI 限制**。  
  
12. 确保 BTSHTTPReceive.dll 条目存在，并且**限制**设置为**允许**。  
  
    > [!NOTE]
    >  创建脚本映射时，将自动创建 btshttpreceive.dll 的 ISAPI 和 CGI 限制条目。  
  
### <a name="to-configure-the-fabrikam-web-page"></a>若要配置 Fabrikam 网页  
  
1. 在 IIS 管理器中，右键单击**应用程序池**，然后选择**添加应用程序池**。  
  
2. 在中**添加应用程序池**对话框框中，输入**BizTalkAppPool**中**名称**，然后选择 **.NET Framework V4.0.30210**中 **.NET framework 版本**下拉列表。 单击“确定” 。  
  
   > [!NOTE]
   >  版本号可能会有所不同，具体取决于版本的[!INCLUDE[netfx40_short](../includes/netfx40-short-md.md)]在计算机上安装。  
  
3. 选择**应用程序池**，在**功能视图**选择**BizTalkAppPool**，然后单击**高级设置**中**操作**窗格。  
  
4. 在中**高级设置**对话框中，将**启用 32 位应用程序**到**True**。  
  
   > [!NOTE]
   >  如果你希望 IIS 在 32 位模式下运行，仅在 64 位计算机上需要此步骤。  
  
5. 选择**标识**，然后单击**省略号 （...）** 按钮。  
  
6. 在中**应用程序池标识**对话框中，选择**自定义帐户**，然后单击**设置**。  
  
7. 输入**用户名**并**密码**是 administrators 组的成员的用户帐户，请输入中的密码**确认密码**，然后单击**确定**三次以返回到 IIS 管理器。  
  
8. 在 IIS 管理器中，打开**站点**文件夹。 右键单击**Default Web Site**，然后选择**添加应用程序**。  
  
9. 在中**添加应用程序**对话框框中，输入**Fabrikam**中**别名**，然后单击**选择**。  
  
10. 在中**选择应用程序池**对话框中，选择**BizTalkAppPool**然后单击**确定**。  
  
11. 单击**省略号 （...）** 按钮并浏览到[!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]SDK\AS2 tutorial\fabrikam 作为**物理路径**。  
  
12. 单击**测试设置**并验证是否没有显示在错误**测试连接**对话框。 单击 **“关闭”**，然后单击 **“确定”**。  
  
13. 在 IIS 管理器中，选择 Fabrikam 虚拟目录并在**功能视图**，双击**身份验证**。  
  
14. 在中**身份验证**，选择**匿名身份验证**，并验证**状态**是**已启用**。 如果**状态**是**禁用**，单击**启用**中**操作**窗格。  
  
### <a name="to-configure-the-contoso-web-page"></a>若要配置 Contoso 网页  
  
1. 在 IIS 管理器中，打开**站点**文件夹。 右键单击**Default Web Site** ，然后选择**添加应用程序**。  
  
2. 在中**添加应用程序**对话框框中，输入**Contoso**中**别名**，然后单击**选择**。  
  
3. 在中**选择应用程序池**对话框中，选择**BizTalkAppPool**然后单击**确定**。  
  
   > [!NOTE]
   >  BizTalkAppPool 以前创建的配置 Fabrikam 网页时，应设置为是 administrators 组的成员的用户的标识。  
  
4. 单击**省略号 （...）** 按钮并浏览到[!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]httpreceive 作为**物理路径**。  
  
5. 单击**测试设置**并验证是否没有显示在错误**测试连接**对话框。 单击 **“关闭”**，然后单击 **“确定”**。  
  
6. 在 IIS 管理器中，选择 Contoso 虚拟目录并在**功能视图**，双击**身份验证**。  
  
7. 在中**身份验证**，选择**匿名身份验证**，并验证**状态**是**已启用**。 如果**状态**是**禁用**，单击**启用**中**操作**窗格。  
  
## <a name="next-steps"></a>后续步骤  
 配置接收位置 (**Receive_AS2**) 以从 Fabrikam 接收 AS2 消息中所述[步骤 6:配置 EDI-AS2 接收位置](../core/step-6-configure-the-edi-as2-receive-location.md)。  
  
## <a name="see-also"></a>请参阅  
 [教程 3：AS2 教程](../core/tutorial-3-as2-tutorial.md)
