---
title: 如何使用 BizTalk WCF 服务发布向导发布服务元数据的 WCF 接收位置的基于内容的路由 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- WCF Service Publishing Wizard, publishing metadata
- WCF services, metadata
ms.assetid: e900b0a0-db17-4db9-a639-54891e02d6d7
caps.latest.revision: 16
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 9e3aaab98733058877bcbed5022c85aef8fb2159
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "37017081"
---
# <a name="how-to-use-the-biztalk-wcf-service-publishing-wizard-to-publish-service-metadata-for-a-wcf-receive-location-for-content-based-routing"></a>如何使用 BizTalk WCF 服务发布向导为基于内容的路由的 WCF 接收位置发布服务元数据
你可以使用 BizTalk WCF 服务发布向导创建 WCF 服务，以便为基于内容的路由的现有 WCF 接收位置发布服务元数据。  

> [!NOTE]
>  在运行 BizTalk WCF 服务发布向导之前，必须生成 BizTalk 项目。 BizTalk 项目必须包括要发布为 WCF 服务的架构。 为 WCF 适配器发布服务元数据之前，还必须使用 BizTalk 服务器管理控制台或 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 附带的 BTSTask 命令行工具创建 WCF 接收位置。 详细了解如何创建 WCF 接收位置，请参阅中每个 WCF 适配器的相应主题[WCF 适配器](../core/wcf-adapters.md)。  

### <a name="to-publish-service-metadata-for-an-existing-wcf-receive-location-for-content-based-routing"></a>为基于内容的路由的现有 WCF 接收位置发布服务元数据  

1. 单击**启动**，依次指向**所有程序**，指向**[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]**，然后单击**BizTalk WCF 服务发布向导**。  

   > [!NOTE]
   >  若要创建和发布 WCF 服务元数据的 BizTalk 业务流程和架构，您可以使用 BizTalk WCF 服务发布向导。 若要使用 SOAP 适配器将业务流程和架构发布为 Web Services，可以使用 BizTalk Web Services 发布向导。  

2. 上**欢迎使用 BizTalk WCF 服务发布向导**页上，单击**下一步**。  

3. 上**WCF 服务类型**页上，选择**元数据仅终结点 (MEX)** 选项来发布 WCF 服务以提供服务元数据为 WCF 接收位置将在下一步中选择。  

    ![WCF 服务类型页](../core/media/794a85b5-6454-4cce-8c15-382b5583b0f2.gif "794a85b5-6454-4cce-8c15-382b5583b0f2")  

4. 上**WCF 服务类型**页上，在**接收位置发布元数据用于**下拉列表中，选择 WCF 接收位置发布服务元数据，然后单击**下一步**.  

5. 上**创建 WCF 服务**页上，选择**将架构发布为 WCF 服务**，然后单击**下一步**。  

    ![创建 WCF 服务页](../core/media/717db27a-2843-4950-899d-0946460f5c1f.gif "717db27a-2843-4950-899d-0946460f5c1f")  

6. 上**WCF 服务**页上，选择要发布服务元数据的 WCF 服务约定。 使用中的树**Web 服务说明**对话框可以添加、 删除、 重命名和编辑要发布的 WCF 服务的 Web 服务说明节点。 **信息**对话框提供了有关所选节点的信息，并显示当前节点或任何子节点中的任何错误：  

   -   树的根节点（Web Services 说明）描述了要发布的 WCF 服务协定。 虚拟目录名称使用该根节点作为默认名称。 您可以修改要通过选择发布的 WCF 服务的 Web 服务说明名称**重命名 web 服务说明**。  

        ![WCF 服务页](../core/media/35131a58-dae7-45fe-ac6a-928c8570f27d.gif "35131a58-dae7-45fe-ac6a-928c8570f27d")  

   -   Web 方法节点， **Operation1**，默认服务节点， **Service1**，默认情况下所示**Web 服务说明**对话框可用于请求-响应接收位置。 如果选择了一个单向 WCF 接收位置，用于此服务约定中，右键单击默认的 Web 方法节点，单击**删除 web 方法**，然后按如下所示创建一个单向 Web 方法： 右键单击默认服务节点，点向**添加 web 方法**，然后单击**单向**。  

   -   若要添加新的 WCF 服务，右键单击 Web 服务说明的名称，然后依次**添加 web 服务**。 这会创建一个不带有任何 WCF 操作的新 WCF 服务。 若要修改 WCF 服务的名称，请右键单击 WCF 服务节点，单击**重命名 web 服务**，然后按 ENTER 以接受新名称。  

   -   若要添加新的 WCF 操作，请右键单击 WCF 服务节点，指向**添加 Web 方法**，然后单击**单向**（对于请求 WCF 操作） 或**请求-响应**(为请求-响应 WCF 操作）。  

   -   若要设置的请求和响应架构类型，请右键单击**请求**或**响应**节点，，然后单击**选择架构类型**。 在中**请求消息类型**框中，键入包含文档架构中的程序集名称**BizTalk 程序集文件**文本框中或单击**浏览**搜索程序集。 **可用架构类型**列表视图中显示的架构的每个根元素。 选择要作为请求或响应架构类型添加的根节点。  

       > [!NOTE]
       >  如果在全局程序集缓存 (GAC) 中安装 BizTalk 程序集文件，请确保已经使用将在中选择的程序集更新了 GAC 中的程序集**请求消息类型**对话框。 如果 GAC 中的程序集具有相同的完全限定名，则 BizTalk WCF 服务发布向导将使用 GAC 中的程序集文件而不是您选择的程序集文件。  

        ![请求消息类型页](../core/media/6bb4cc17-b108-4692-a5ca-548c7ef46045.gif "6bb4cc17-b108-4692-a5ca-548c7ef46045")  

   -   您可以重命名**请求**并**响应**节点而不会影响生成的代码。 在定义了架构之后，可以重命名部分元素，这会修改 WCF 操作的参数名称。 通过查看要发布的 WCF 服务的服务元数据，可以看到发生的更改。  

   > [!NOTE]
   >  在重命名任何 Web Services 说明节点时，不能使用空格。  

7. 单击**下一步**继续执行向导。  

8. 上**WCF 服务属性**页上，在**的 WCF 服务 Targetnamespace**文本框中，键入 WCF 服务的目标命名空间，然后单击**下一步**。  

    ![WCF 服务属性页](../core/media/07518c78-bcae-4274-bb14-aeef107ee4c6.gif "07518c78-bcae-4274-bb14-aeef107ee4c6")  

9. 上**WCF 服务位置**页上，在**位置**文字框中，键入在其中生成 WCF 服务的 Web 目录名称。 您可以接受默认位置 (http://localhost/<*Web 服务说明名称*>)，键入用于中的 WCF 服务位置**位置**文本框中或单击**浏览**并选择 Web 目录。 选择以下任何选项：  

   - **覆盖现有项目。** 此选项才可用，仅当 Web 目录已存在。 仅当选择了此选项时，您才能够发布到同一位置。 否则，必须输入不同的项目位置。  

   - **允许匿名访问 WCF 服务。** 此选项会为已创建的虚拟目录添加匿名访问权限。 默认情况下，虚拟目录继承其父虚拟目录或网站（如果该目录是顶级虚拟目录）的访问权限。  

     在完成此页上，单击**下一步**。  

     ![WCF 服务位置页](../core/media/76285470-1520-4d77-a5b6-c58cbe8fc575.gif "76285470-1520-4d77-a5b6-c58cbe8fc575")  

     > [!NOTE]
     >  项目位置可位于其他服务器上。 若要将 WCF 服务发布到另一台服务器，键入项目名称作为 http://<*servername*>/<*WCF 服务位置*>。  

     > [!NOTE]
     >  项目位置可位于非默认网站上。 发布到非默认网站时，请在该 URL 中包括网站的端口号。 例如， http://&lt*servername*>: 8080 / <*WCF 服务位置*>。  

     > [!NOTE]
     >  向导在 Web 应用程序的 \App_Data\Temp 文件夹中创建的 BindingInfo.xml 文件使用管道的默认值。 接收管道的默认值是**Microsoft.BizTalk.DefaultPipelines.XMLReceive**管道和默认值为发送管道**Microsoft.BizTalk.DefaultPipelines.PassThruTransmit**管道。  

10. 上**WCF 服务摘要**页上，查看您的 WCF 服务的设置。  

11. 单击**创建**创建 WCF 服务。  

12. 单击**完成**完成 BizTalk WCF 服务发布向导。  

### <a name="to-configure-the-web-application-for-publishing-service-metadata"></a>为发布服务元数据配置 Web 应用程序  

1. 为 BizTalk WCF 服务发布向导创建的 Web 应用程序启用 ASP.NET。 有关详细信息，请参阅[启用 Web 服务](../core/enabling-web-services.md)。  

   > [!NOTE]
   >  如果您使用的是其他版本的 Windows 操作系统，则必须将应用程序池的标识帐户添加到 BizTalk Server Administrators 组。 将相应的帐户添加到 BizTalk Server Administrators 组后，需要重新启动 IIS 服务，设置才能生效。  

2. 打开命令提示符，请转到 BizTalk WCF 服务发布向导创建 WCF 服务中 %SystemDrive%\InetPub 所在的文件夹\\，然后打开 Web.config 文件使用记事本。  

3. 在记事本中，添加以下行**\<system.web\>** 元素：  

   ```  
   <trust level="Full" originUrl="" />  
   ```  

   > [!NOTE]
   >  此设置是可选的，用于向已发布的 WCF 服务的宿主 ASP.NET 应用程序授予对受操作系统安全机制保护的任何资源的访问权限。 如果在已发布的 WCF 服务所在的计算机上安装并运行了 Windows SharePoint Services，则这是 WCF 所必需的信任级别。  

4. 在 Internet Explorer 中，在**地址**框中，键入格式为 http:// 的 WCF 服务 URL<em>主机 [: 端口]</em>/*apppath* /*wcfservicename.svc*以测试已发布的 WCF 服务。 介绍了下表的参数。  


   |      参数       |                                                            ReplTest1                                                            |
   |----------------------|-----------------------------------------------------------------------------------------------------------------------------|
   |    *主机 [: 端口]*     | 在其中部署了你的 WCF 服务的计算机的名称。 此服务器名称后面可跟冒号和端口号。 |
   |      *apppath*       |                              虚拟目录和 Web 应用程序路径的名称。                               |
   | *wcfservicename.svc* |                                           WCF 服务 .svc 文件的名称。                                            |


5. 为了避免无意中泄漏可能敏感的服务元数据，我们建议执行下列任务以在生产环境中禁止此行为：  

   1.  在记事本中，打开 BizTalk WCF 服务发布向导创建 WCF 服务中 %SystemDrive%\InetPub 所在的文件夹中的 Web.config\\。  

   2.  在记事本中，设置**httpGetEnabled**属性中**\<serviceMetadata\>** 元素为 false，如以下行：  

       ```  
       <serviceMetadata httpGetEnabled="false" httpsGetEnabled="false" />  
       ```  

## <a name="see-also"></a>请参阅  
 [如何使用 BizTalk WCF 服务发布向导将架构发布为 WCF 服务](../core/publish-schemas-as-wcf-services--use-the-biztalk-wcf-service-publishing-wizard.md)   
 [演练：通过 WCF-NetMsmq 适配器发布 WCF 服务](../core/walkthrough-publishing-wcf-services-with-the-wcf-netmsmq-adapter.md)