---
title: "如何使用发布向导的 BizTalk WCF 服务的 WCF 接收位置发布服务元数据绑定到业务流程端口 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- WCF Service Publishing Wizard, publishing metadata
- WCF services, orchestration ports
- WCF services, metadata
- orchestrations, WCF services
ms.assetid: 04ccce9f-8d18-433a-8299-d06fa155db06
caps.latest.revision: "17"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a2dce9a66465285dc16f8de804c7a6e99fa7e62a
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/28/2017
---
# <a name="how-to-use-the-biztalk-wcf-service-publishing-wizard-to-publish-service-metadata-for-a-wcf-receive-location-bound-to-an-orchestration-port"></a>如何使用 BizTalk WCF 服务发布向导为已绑定到业务流程端口的 WCF 接收位置发布服务元数据
您可以使用 BizTalk WCF 服务发布向导创建 WCF 服务，以便为已绑定到业务流程端口的现有 WCF 接收位置发布服务元数据。  
  
> [!NOTE]
>  在运行 BizTalk WCF 服务发布向导之前，必须生成 BizTalk 项目。 这些 BizTalk 项目必须包括至少具有一个公用类型修饰符的接收端口的业务流程。 在发布服务元数据的 WCF 适配器之前，你还必须创建 WCF 使用 BizTalk 管理控制台或包含的 BTSTask 命令行工具接收位置[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]。 有关如何创建 WCF 的详细信息接收位置，请参阅中的每个 WCF 适配器的相应主题[WCF 适配器](../core/wcf-adapters.md)。  
  
### <a name="to-publish-service-metadata-for-an-existing-wcf-receive-location-bound-to-an-orchestration-port"></a>为已绑定到业务流程端口的现有 WCF 接收位置发布服务元数据  
  
1.  单击**启动**，指向**所有程序**，指向[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]，然后单击**BizTalk WCF 服务发布向导**。  
  
    > [!NOTE]
    >  若要为 BizTalk 业务流程和架构创建并发布 WCF 服务元数据，可以使用 BizTalk WCF 服务发布向导。 若要使用 SOAP 适配器将业务流程和架构发布为 Web Services，可以使用 BizTalk Web Services 发布向导。  
  
2.  上**BizTalk WCF 服务发布向导欢迎**页上，单击**下一步**。  
  
3.  上**WCF 服务类型**页上，选择**元数据仅终结点 (MEX)**选项可将发布为提供 WCF 服务元数据的 WCF 服务接收将在下一步中选择的位置。  
  
     ![WCF 服务类型页](../core/media/794a85b5-6454-4cce-8c15-382b5583b0f2.gif "794a85b5-6454-4cce-8c15-382b5583b0f2")  
  
4.  上**WCF 服务类型**页上，在**发布元数据接收位置**下拉列表中，选择 WCF 接收位置以发布服务元数据，然后单击**下一步**.  
  
5.  上**创建 WCF 服务**页上，选择**作为 WCF 服务发布 BizTalk 业务流程**，然后单击**下一步**。  
  
     ![创建 WCF 服务页](../core/media/86cb66b5-6842-4330-8942-20afa68ec5fa.gif "86cb66b5-6842-4330-8942-20afa68ec5fa")  
  
6.  上**BizTalk 程序集**页上，在**BizTalk 程序集文件 (\*.dll)**文本框中，键入 BizTalk 程序集文件的名称，或单击**浏览**以浏览到包含业务流程的程序集以发布服务元数据，然后单击**下一步**。  
  
    > [!NOTE]
    >  在选择 BizTalk 程序集文件之前, 将所有依赖程序集复制到同一文件夹中，与 BizTalk 程序集或安装到全局程序集缓存 (GAC 中) 的依赖程序集。  
  
    > [!NOTE]
    >  如果 BizTalk 程序集文件安装到 GAC 中，请确保在 GAC 的程序集，已更新与程序集将在中选择**BizTalk 程序集**对话框。 如果位于 GAC 中的程序集具有相同的完全限定的名，BizTalk WCF 服务发布向导将使用而不是所选的 GAC 中的程序集文件。  
  
    > [!NOTE]
    >  路径长度超过 260 个字符时，可能会出现错误消息，指示路径太长。  
  
     ![BizTalk 程序集页](../core/media/d34a027e-ea82-4048-8b15-d97df795b0d4.gif "d34a027e-ea82-4048-8b15-d97df795b0d4")  
  
7.  上**业务流程和端口**页上，单击加号 （+） 展开每个程序集和业务流程的树节点。 选中相应树节点的复选框以选择要为其发布元数据的业务流程和端口。 如果你想要创建一个 WCF 服务 （.svc 文件） 的所有而不是一个 WCF 服务，每个所选的接收端口接收端口，请选择**合并到单个 WCF 服务的所有所选的端口**选项，并依次**下一步**。  
  
    > [!NOTE]
    >  将所有选定端口合并到单个 WCF 服务后，所有选定端口都具有相同的端口类型，并且端口中的操作名称都是唯一的。  
  
     ![操作和端口页面](../core/media/97112744-ddd4-4512-ac56-41317ba9412b.gif "97112744-ddd4-4512-ac56-41317ba9412b")  
  
8.  上**WCF 服务属性**页上，在**的 WCF 服务的 Targetnamespace**文本框中，键入 WCF 服务的目标命名空间，然后单击**下一步**。  
  
     ![WCF 服务属性页](../core/media/07518c78-bcae-4274-bb14-aeef107ee4c6.gif "07518c78-bcae-4274-bb14-aeef107ee4c6")  
  
9. 上**WCF 服务位置**页上，在**位置**文本框中，键入中生成的 WCF 服务的 Web 目录名称。 你可以接受默认位置 (http://localhost/ <*BizTalk 程序集名称*>)，键入用于中的 WCF 服务的位置**位置**文本框中或单击**浏览**并选择 Web 目录。 选择以下任何选项：  
  
    -   **覆盖现有项目。** 此选项是 Web 目录已存在时才可用。 仅当选择了此选项时，您才能够发布到同一位置。 否则，必须输入不同的项目位置。  
  
    -   **允许匿名访问 WCF 服务。** 此选项会为已创建的虚拟目录添加匿名访问权限。 默认情况下，虚拟目录继承其父虚拟目录或网站（如果该目录是顶级虚拟目录）的访问权限。  
  
     在完成此页，单击**下一步**。  
  
     ![WCF 服务位置页](../core/media/76285470-1520-4d77-a5b6-c58cbe8fc575.gif "76285470-1520-4d77-a5b6-c58cbe8fc575")  
  
    > [!NOTE]
    >  项目位置可位于其他服务器上。 若要将 WCF 服务发布到不同的服务器，键入项目名称，作为 http://&lt*servername*>/<*WCF 服务位置*>。  
  
    > [!NOTE]
    >  项目位置可位于非默认网站上。 发布到非默认网站时，请在该 URL 中包括网站的端口号。 例如，http://&lt*servername*>: 8080 / <*WCF 服务位置*>。  
  
    > [!NOTE]
    >  向导将创建 Web 应用程序的 App_DataTemp 文件夹中的 BindingInfo.xml 文件管道中使用的默认值。 接收管道的默认值是**Microsoft.BizTalk.DefaultPipelines.XMLReceive**管道，而默认值为发送管道**Microsoft.BizTalk.DefaultPipelines.PassThruTransmit**管道。  
  
10. 上**WCF 服务摘要**页上，查看您的 WCF 服务的设置。  
  
11. 单击**创建**创建 WCF 服务。  
  
12. 单击**完成**完成 BizTalk WCF 服务发布向导。  
  
### <a name="to-configure-the-web-application-for-publishing-service-metadata"></a>为发布服务元数据配置 Web 应用程序  
  
1.  为 BizTalk WCF 服务发布向导创建的 Web 应用程序启用 ASP.NET。 有关详细信息，请参阅[启用 Web 服务](../core/enabling-web-services.md)。  
  
    > [!NOTE]
    >  如果使用的是 Windows Server 2008 或 Windows Vista，则必须将应用程序池的标识帐户添加到 BizTalk Server Administrators 组。 将相应帐户添加到 BizTalk Server Administrators 组之后，需要重新启动 IIS 服务以使设置生效。  
  
2.  打开命令提示符，请转到 BizTalk WCF 服务发布向导中为 %SystemDrive%\InetPub 而创建的 WCF 服务的文件夹\\，然后打开 Web.config 文件使用记事本。  
  
3.  在记事本中，添加以下代码行内的 **\<system.web\>** 元素：  
  
    ```  
    <trust level="Full" originUrl="" />  
    ```  
  
    > [!NOTE]
    >  此设置是可选的，用于向已发布的 WCF 服务的宿主 ASP.NET 应用程序授予对受操作系统安全机制保护的任何资源的访问权限。 如果在已发布的 WCF 服务所在的计算机上安装并运行了 Windows SharePoint Services，则这是 WCF 所必需的信任级别。  
  
4.  在 Internet Explorer 中，在**地址**框中，键入使用格式 http:// 的 WCF 服务的 URL*主机 [: 端口]*/*apppath* /*wcfservicename.svc*若要测试已发布的 WCF 服务。 以下表所述的参数。  
  
    |参数|值|  
    |---------------|-----------|  
    |*主机 [: 端口]*|在其中部署了你的 WCF 服务的计算机的名称。 此服务器名称后面可跟冒号和端口号。|  
    |*apppath*|虚拟目录和 Web 应用程序路径的名称。|  
    |*wcfservicename.svc*|WCF 服务 .svc 文件的名称。|  
  
5.  为了避免无意中泄漏可能敏感的服务元数据，我们建议执行下列任务以在生产环境中禁止此行为：  
  
    1.  在记事本中，打开 BizTalk WCF 服务发布向导中为 %SystemDrive%\InetPub 而创建的 WCF 服务的文件夹中的 Web.config\\。  
  
    2.  在记事本中，设置**httpGetEnabled**属性中 **\<serviceMetadata\>** 元素为 false，如下所示的以下行：  
  
        ```  
        <serviceMetadata httpGetEnabled="false" httpsGetEnabled="false" />  
        ```  
  
## <a name="see-also"></a>另请参阅  
 [如何使用发布向导的 BizTalk WCF 服务的 WCF 接收位置用于基于内容的路由发布服务元数据](../core/publish-service-metadata-for-a-wcf-receive-location-for-content-based-routing.md)   
 [演练：通过 WCF-NetMsmq 适配器发布 WCF 服务](../core/walkthrough-publishing-wcf-services-with-the-wcf-netmsmq-adapter.md)