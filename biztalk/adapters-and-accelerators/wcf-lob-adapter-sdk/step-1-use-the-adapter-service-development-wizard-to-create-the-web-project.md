---
title: 步骤 1： 使用适配器服务开发向导来创建 Web 项目 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 7ea0e33c-0d8d-4656-a6f0-3008b90f93f8
caps.latest.revision: 21
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 1144b7e6827882b37f6f9991a7315cdc3cdbb88d
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/28/2017
ms.locfileid: "25966963"
---
# <a name="step-1-use-the-adapter-service-development-wizard-to-create-the-web-project"></a>步骤 1： 使用适配器服务开发向导来创建 Web 项目
![步骤 1 4](../../adapters-and-accelerators/adapter-oracle-ebs/media/step-1of4.gif "Step_1of4")  
  
 **完成时间：** 10 分钟  
  
 在此步骤中，你创建使用 Visual Studio 项目和[!INCLUDE[afsvcdevwizshort](../../includes/afsvcdevwizshort-md.md)]。 [!INCLUDE[afsvcdevwizshort](../../includes/afsvcdevwizshort-md.md)]收集有关适配器、 操作和终结点配置的信息并生成然后部署到 IIS 的 Web 项目。  
  
## <a name="prerequisites"></a>先决条件  
 必须生成和部署 Echo 示例中所述[教程 1： 开发 Echo 适配器](../../adapters-and-accelerators/wcf-lob-adapter-sdk/tutorial-1-develop-the-echo-adapter.md)在开始本教程之前。  
  
### <a name="to-start-the-adapter-service-development-wizard"></a>若要启动适配器服务开发向导  
  
1.  启动 Visual Studio，然后在**文件**菜单上，指向**新建**，然后单击**网站**。  
  
2.  在**新网站**对话框框中，执行以下操作：  
  
    |使用此选项|执行的操作|  
    |--------------|----------------|  
    |**语言**|单击**Visual C#**。|  
    |**模板**|单击**WCF 适配器服务**。|  
    |**位置**|选择**文件系统**，然后键入**C:\Tutorials\EchoWeb**作为路径。|  
  
3.  单击 **“确定”**。  
  
4.  上**欢迎页**，单击**下一步**。  
  
### <a name="to-select-the-adapter-and-uri"></a>若要选择的适配器和 URI  
  
1.  上**选择要生成服务协定的操作**页上，选择**echoAdapterBindingV2**从**选择的绑定**下拉列表，，然后单击**配置**。  
  
2.  上**安全**选项卡**配置适配器**对话框中，设置**客户端凭据类型**到**用户名**，然后设置**用户名凭据**，如下所示：  
  
    |属性|值|  
    |--------------|-----------|  
    |**用户名**|username|  
    |**密码**|password|  
  
    > [!NOTE]
    >  用户名和密码在此处输入仅用于在向导中，执行步骤时连接到适配器和向导完成后，将不会保留。  
  
3.  单击**URI 属性**选项卡上，并将属性，如下所示：  
  
    |属性|值|  
    |--------------|-----------|  
    |**应用程序**|LobApplication|  
    |**EnableAuthentication**|True|  
    |**主机名**|lobhostname|  
    |**EchoInUpperCase**|False|  
  
    > [!NOTE]
    >  在此处选择的 URI 属性将用于创建\<**客户端**\>\<**终结点**\> web.config 文件中的元素。  
  
4.  单击**绑定属性**选项卡。请注意默认值，并依次**确定**。  
  
    > [!NOTE]
    >  绑定值将用于生成\<**绑定**\>\<**echoAdapterBindingV2** \> web.config 文件中的元素。  
  
### <a name="to-select-the-contract-and-operations"></a>若要选择的协定和操作  
  
1.  上**选择要生成服务协定的操作**页上，单击**连接**。  
  
2.  在**选择类别**树中，选择**Main 类别**。 这将填充**可用类别和操作**列表。  
  
    > [!NOTE]
    >  你也可以输入中的搜索词**类别中的搜索**字段以确定包含搜索词的任何操作。  
  
3.  在**可用类别和操作**列表中，选择**EchoGreetings**单击**添加**。 这样会将移动到的 EchoGreetings 操作**添加类别和操作**列表。 在此处选择的操作会公开给客户端应用程序可以通过由向导生成的客户端代理代码。  
  
     ![选择协定和操作](../../adapters-and-accelerators/wcf-lob-adapter-sdk/media/de497b32-c820-480f-84f3-a9d0d2ded86b.gif "de497b32-c820-480f-84f3-a9d0d2ded86b")  
  
4.  单击 **“下一步”**。  
  
### <a name="to-configure-service-and-endpoint-behavior"></a>若要配置服务和终结点行为  
  
1.  上**配置服务和终结点行为**页上，输入以下值**服务行为配置**:  
  
    |属性|值|  
    |--------------|-----------|  
    |**EnableMetadataExchange**|True|  
    |**IncludeExceptionDetailsinFault**|True|  
    |**名称**|customServiceBehavior|  
    |**UseServiceCertificate**|False|  
  
     使用这些值来填充\< **serviceBehaviors**\>。  
  
2.  输入以下值**终结点行为配置**:  
  
    |属性|值|  
    |--------------|-----------|  
    |**名称**|customEndpointBehavior|  
    |**AuthenticationType**|**HTTPUsernamePassword**|  
    |**UsernameHeader**|MyUserHeader|  
    |**PasswordHeader**|MyPassHeader|  
  
     将使用这些值来指定**adapterSecurityBridgeType**中 <**endpointBehaviors** web.confg 中的元素。  
  
     ![终结点配置](../../adapters-and-accelerators/wcf-lob-adapter-sdk/media/3fd5784c-64e5-47c1-9a6f-10f12f77f726.gif "3fd5784c-64e5-47c1-9a6f-10f12f77f726")  
  
3.  单击 **“下一步”**  
  
### <a name="to-configure-the-binding"></a>若要配置绑定  
  
1.  上**配置的服务终结点绑定和地址**页上，选择**BindingConfiguration**中的条目**配置的地址和协定绑定**，和然后单击省略号 (**...**) 按钮。  
  
2.  在**自定义绑定**对话框中，设置**模式**到**TransportWithMessageCredential**，然后单击**确定**。  
  
3.  单击**应用**，然后单击**下一步**。  
  
4.  上**摘要**页上，查看协定和操作为此项目中，选择，然后单击**完成**。 你将看到 EchoWeb 解决方案，其中包含创建的项目文件[!INCLUDE[afsvcdevwizshort](../../includes/afsvcdevwizshort-md.md)]  
  
## <a name="what-did-i-just-do"></a>内容回顾  
 在此步骤中，你使用了[!INCLUDE[afsvcdevwizshort](../../includes/afsvcdevwizshort-md.md)]生成 Web 项目，在发布到 IIS 中，将回显适配器开发中的主机[教程 1： 开发 Echo 适配器](../../adapters-and-accelerators/wcf-lob-adapter-sdk/tutorial-1-develop-the-echo-adapter.md)在 IIS 中处理。 生成的 Web 项目允许 Web 服务和 WCF 客户端访问所选的操作。  
  
## <a name="next-steps"></a>后续步骤  
 若要生成和部署 Web 项目时，继续执行到[步骤 2： 部署 Web 项目](../../adapters-and-accelerators/wcf-lob-adapter-sdk/step-2-deploy-the-web-project.md)  
  
## <a name="see-also"></a>另请参阅  
 [教程 1：开发 Echo 适配器](../../adapters-and-accelerators/wcf-lob-adapter-sdk/tutorial-1-develop-the-echo-adapter.md)