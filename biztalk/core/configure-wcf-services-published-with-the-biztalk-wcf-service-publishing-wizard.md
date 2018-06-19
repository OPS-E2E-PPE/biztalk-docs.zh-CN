---
title: 如何配置 WCF 服务与 BizTalk WCF 服务发布向导发布 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- WCF services, WCF Service Publishing Wizard
- WCF services, configuring
- configuring, WCF services
- WCF Service Publishing Wizard
ms.assetid: f51b86c0-8c19-453d-a66d-3f373e9f096e
caps.latest.revision: 26
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 19383ca97f979d6932698d06eabd507b4a00954f
ms.sourcegitcommit: 36350889f318e1f7e0ac9506dc8df794d475bda6
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/18/2018
ms.locfileid: "25969627"
---
# <a name="how-to-configure-wcf-services-published-with-the-biztalk-wcf-service-publishing-wizard"></a>如何配置使用 BizTalk WCF 服务发布向导发布的 WCF 服务
使用 BizTalk WCF 服务发布向导发布 WCF 服务之后，必须对其进行正确配置。 本主题介绍如何配置发布的 WCF 服务。  
  
> [!NOTE]
>  你必须生成 BizTalk 项目，然后通过运行 BizTalk WCF 服务发布向导将其发布。 有关如何使用 BizTalk WCF 服务发布向导的详细信息，请参阅[如何使用 BizTalk WCF 服务发布向导发布业务流程作为 WCF 服务](../core/publish-orchestrations-as-wcf-services--biztalk-wcf-service-publishing-wizard.md)和[如何使用 BizTalk WCF 服务发布向导发布作为 WCF 服务的架构](../core/publish-schemas-as-wcf-services--use-the-biztalk-wcf-service-publishing-wizard.md)。  
  
### <a name="to-configure-the-receive-locations-for-a-published-wcf-service"></a>配置已发布 WCF 服务的接收位置  
  
1.  通过运行 BizTalk WCF 服务发布向导来发布 BizTalk 项目。  
  
2.  如果你未选择 **创建 BizTalk 接收位置** 选项如下图中，在创建 WCF 服务时，创建新的接收端口和接收的已发布的 WCF 服务的位置，然后选择接收位置将使用的传输类型的 WCF 适配器。 你必须选择相同的 WCF 适配器上选择了 **WCF 服务类型** 下图中显示网页。 有关创建接收位置的详细信息，请参阅[如何创建接收位置](../core/how-to-create-a-receive-location.md)。  
  
    > [!NOTE]
    >  BizTalk WCF 服务发布向导会在已发布 WCF 服务（.svc 文件）的 Web 目录中的 \App_Data\Temp 文件夹中创建一个绑定文件 BindingInfo.xml。 如果你选择 **创建 BizTalk 接收位置** 选项，向导使用的绑定文件来创建接收位置。 在 BizTalk Server 管理控制台中，可以通过导入该绑定文件来手动创建接收位置。 有关导入绑定文件的详细信息，请参阅[导入绑定](../core/importing-bindings2.md)。  
  
     ![WCF 服务类型页](../core/media/959900fd-44c9-4f3a-8836-9786a2f5e707.gif "959900fd-44c9-4f3a-8836-9786a2f5e707")  
  
3.  如果有必要，请打开 BizTalk Server 管理控制台，如下所示︰ 单击 **启动**, ，指向 **程序**, ，指向 **Microsoft BizTalk Server**, ，然后单击 **BizTalk Server 管理**。  
  
4.  在控制台树中，展开 **BizTalk Server 管理**, ，展开 **BizTalk 组**, ，展开 **应用程序**, ，展开应用程序生成的 WCF 服务应将放置到的位置展开 **接收位置**, ，然后双击接收位置的 WCF 服务。  
  
5.  在 **接收位置属性** 对话框中，单击 **配置**。  
  
6.  如果接收位置中托管的 WCF BasicHttp 或 WCF WSHttp 适配器， **传输属性** 对话框中，单击 **安全** 选项卡上，，然后配置选项卡上的安全属性。如果接收位置中承载的 WCF CustomIsolated 适配器，**传输属性**对话框中，单击**绑定**选项卡上，然后配置选项卡上的绑定信息。  
  
     ![WCF 的安全选项卡&#45;BasicHttp 适配器](../core/media/585ecdad-bdee-40c0-b2f1-7ace74d503e5.gif "585ecdad-bdee-40c0-b2f1-7ace74d503e5")  
  
    > [!NOTE]
    >  独立 WCF 适配器的传输客户端凭据类型属性必须与承载此接收位置的 Internet 信息服务 (IIS) 虚拟目录的验证方案相匹配。 例如，如果该属性设置为 **Windows**, ，还需要启用 **集成 Windows 身份验证** 承载此虚拟目录接收位置。 相似地，如果将该属性设置为“无” ，则你必须允许匿名访问此接收位置所在的虚拟目录。 有关如何配置 WCF BasicHttp 和 WCF WSHttp 适配器的安全属性的详细信息，请参阅[如何配置 WCF BasicHttp 接收位置](http://msdn.microsoft.com/library/43f18e5d-ba28-453c-b8ce-5bcdc6f27fdd)，和[如何配置 WCF WSHttp 接收位置](../core/how-to-configure-a-wcf-wshttp-receive-location.md)。 有关如何配置的绑定信息的详细信息，请参阅[如何配置 WCF CustomIsolated 接收位置](../core/how-to-configure-a-wcf-customisolated-receive-location.md)。  
  
7.  如果你未选择 **创建 BizTalk 接收位置** 选项时创建 WCF 服务，在 **传输属性** 对话框中，单击 **常规** 选项卡。上**常规**选项卡上，键入此接收中的位置的 URI**地址**文本框。 指定虚拟目录以及上一步骤中 BizTalk WCF 服务发布向导生成的 .svc 文件名，例如 /path/service.svc。  
  
    > [!NOTE]
    >  **地址** 属性应以正斜杠 （"/"） 开头，以".svc"结尾。 **地址**属性必须包含协议方案、 计算机名或端口号如http://host:port。 只能将虚拟目录路径用于该属性。 WCF 服务标记文件的扩展名必须为 .svc。  
  
     ![WCF 的一般选项卡&#45;BasicHttp 适配器](../core/media/1126fa6a-e3e9-44ad-aeb0-90c78226aeeb.gif "1126fa6a-e3e9-44ad-aeb0-90c78226aeeb")  
  
8.  如果你选择 **传输** 或 **TransportWithMessageCredential** 中 **安全模式** 上的下拉列表 **安全** 选项卡用于 WCF BasicHttp 和 WCF WSHttp 适配器，必须设置了安全套接字层 (SSL) 在 IIS 中。 如果你设置 **传输** 或 **TransportWithMessageCredential** WCF CustomIsolated 适配器的绑定信息中的安全模式，你还必须设置在 IIS 中的 SSL。  
  
9. 如果接收位置中托管的 WCF BasicHttp 或 WCF WSHttp 适配器， **传输属性** 对话框框中，配置 **常规**, ，**绑定**, ，和 **消息** 如有必要使用 tab 键。 如果接收位置托管的 WCF CustomIsolated 适配器，配置 **常规**, ，**行为**, ，**其他**, ，和 **消息** 选项卡为你的目的。 对于 WCF CustomIsolated 适配器中，你可以导入 **地址 (URI)** 和 **终结点标识** 属性 **常规** 选项卡上，在上绑定信息 **绑定** 选项卡上，和上的行为 **行为** 此选项卡接收从配置文件的位置。  
  
10. 使用 BizTalk Server 管理控制台为已发布的 WCF 服务启用接收位置。 有关如何启用接收位置的详细信息，请参阅[如何启用接收位置](../core/how-to-enable-a-receive-location.md)。  
  
    > [!NOTE]
    >  接收位置在创建时处于禁用状态。 使用 BizTalk Server WCF 服务向导创建接收位置后，必须启用接收位置。  
  
11. 使用 IIS 管理控制台配置 IIS 应用程序池以承载已发布的 WCF 服务的接收位置。 有关如何配置独立的 WCF 适配器的应用程序池的详细信息，请参阅[将 IIS 配置为独立的 WCF 接收适配器](../core/configuring-iis-for-the-isolated-wcf-receive-adapters.md)。  
  
12. 打开命令提示符，请转到 BizTalk Server WCF 服务发布向导中为 %SystemDrive%\InetPub 而创建的 WCF 服务的文件夹\\, ，然后打开 Web.config 文件使用记事本。  
  
13. 在记事本中，添加以下代码行内的**\<system.web\>** 元素：  
  
    ```  
    <trust level="Full" originUrl="" />  
    ```  
  
    > [!NOTE]
    >  此设置是可选的，用于向已发布的 WCF 服务的宿主 ASP.NET 应用程序授予对受操作系统安全机制保护的任何资源的访问权限。 如果在已发布的 WCF 服务所在的计算机上安装并运行了 Windows SharePoint Services，则这是 WCF 所必需的信任级别。  
  
14. 在 Internet Explorer 中，在 **地址** 框中，键入使用格式 http:// 的 WCF 服务的 URL*主机 [: 端口]*/*apppath*/*wcfservicename.svc* 若要测试已发布的 WCF 服务。 以下表所述的参数。  
  
    |参数|“值”|  
    |---------------|-----------|  
    |*主机 [: 端口]*|在其中部署了你的 WCF 服务的计算机的名称。 此服务器名称后面可跟冒号和端口号。|  
    |*apppath*|虚拟目录和 Web 应用程序路径的名称。|  
    |*wcfservicename.svc*|WCF 服务 .svc 文件的名称。|  
  
15. 为了避免无意中泄漏可能为敏感信息的服务元数据，我们建议执行下列任务以在生产环境中禁止此行为：  
  
    1.  在记事本中，打开 BizTalk Server WCF 服务发布向导中为 %SystemDrive%\InetPub 而创建的 WCF 服务的文件夹中的 Web.config\\。  
  
    2.  在记事本中，设置**httpGetEnabled**属性中**\<serviceMetadata\>** 元素为 false 为以下行：  
  
        ```  
        <serviceMetadata httpGetEnabled="false" httpsGetEnabled="false" />  
        ```  
  
## <a name="see-also"></a>另请参阅  
 [配置 WCF BasicHttp 适配器](http://msdn.microsoft.com/library/5929a338-46e0-4fc4-8837-792d7f7ae0fe)   
 [配置 WCF WSHttp 适配器](../core/configuring-the-wcf-wshttp-adapter.md)   
 [配置 WCF CustomIsolated 适配器](../core/configuring-the-wcf-customisolated-adapter.md)   
 [如何在 Windows Server 2003 中配置 IIS 网站身份验证](http://go.microsoft.com/fwlink/?LinkID=75699)