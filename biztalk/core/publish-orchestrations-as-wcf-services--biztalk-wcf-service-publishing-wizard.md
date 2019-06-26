---
title: 如何使用 BizTalk WCF 服务发布向导将业务流程发布为 WCF 服务 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- tools, WCF Service Publishing Wizard
- WCF services, WCF Service Publishing Wizard
- WCF services, orchestrations
- publishing, orchestrations [WCF services]
- orchestrations, WCF services
- WCF Service Publishing Wizard
ms.assetid: db352132-2fe8-4d53-b239-45e5c3525b6c
caps.latest.revision: 21
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c2e3edfb54f9864b0c5d17ed455d96df7e15b9ce
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65398408"
---
# <a name="how-to-use-the-biztalk-wcf-service-publishing-wizard-to-publish-orchestrations-as-wcf-services"></a>如何使用 BizTalk WCF 服务发布向导将业务流程发布为 WCF 服务
使用 BizTalk WCF 服务发布向导将业务流程作为 WCF 服务发布。  
  
> [!NOTE]
>  在运行 BizTalk WCF 服务发布向导前必须生成 BizTalk 项目。 BizTalk 项目必须包括至少具有一个接收的端口的类型修饰符是公共的业务流程。 创建端口时，此类型修饰符存在业务流程的属性中。  
  
### <a name="to-publish-an-orchestration-as-a-wcf-service"></a>若要将业务流程作为 WCF 服务发布  
  
1. 单击**启动**，依次指向**所有程序**，指向[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]，然后单击**BizTalk WCF 服务发布向导**。  
  
   > [!NOTE]
   >  若要创建并将 BizTalk 业务流程和架构发布为 WCF 适配器的 WCF 服务，你可以使用 BizTalk WCF 服务发布向导。 若要将业务流程和架构发布为 Web 服务使用 SOAP 适配器，您可以使用 BizTalk Web Services 发布向导。  
  
2. 上**欢迎使用 BizTalk WCF 服务发布向导**页上，单击**下一步**。  
  
3. 上**WCF 服务类型**页上，选择**服务终结点**上发布的 WCF 服务中选择选项，BizTalk 业务流程的 BizTalk 程序集。  
  
    ![WCF 服务类型页](../core/media/959900fd-44c9-4f3a-8836-9786a2f5e707.gif "959900fd-44c9-4f3a-8836-9786a2f5e707")  
  
4. 上**WCF 服务类型**页上，选择**启用元数据终结点**复选框，指示是否独立的 WCF 接收位置由 Internet 信息服务 (IIS) 承载发布服务元数据使用 HTTP/GET 请求检索。 通过启用此复选框，向导生成的 Web.config 其中**httpGetEnabled**的属性 **\<serviceMetadata\>** 元素设置为 **，则返回 true**. 您可以使用元数据导入工具（如 SvcUtil.exe）生成在开发环境中调用此服务所需的客户端代码。 发布元数据的地址为终结点地址加上 **？ wsdl**查询字符串。  
  
   > [!NOTE]
   >  为了避免无意中泄漏可能的敏感服务元数据，建议在生产环境中禁用此行为。 这可以通过将 httpgetenabled 设置为 false，或删除 MEX 虚拟目录。  
  
5. 上**WCF 服务类型**页上，在**适配器名称 （传输类型）** 下拉列表中，选择的 WCF 服务发布使用独立的 WCF 适配器。 您可以选择任何以下适配器：  
  
   -   **WCF-BasicHttp.** Wcf-basichttp 适配器能够与 WS-基本配置文件 1.1 的 web 服务与基于 ASMX 的服务一样。  
  
   -   **WCF-WSHttp.** Wcf-wshttp 适配器能够与服务的 WS-* 标准通过 HTTP 和 HTTPS。  
  
   -   **WCF CustomIsolated。** Wcf-customisolated 适配器支持通过 HTTP 传输使用 Windows Communication Foundation (WCF) 扩展性功能。  
  
6. 上**WCF 服务类型**页上，选择**以下应用程序中的创建 BizTalk 接收位置**复选框以创建接收端口和对应于每个生成的.svc 文件的位置在中选择的 WCF 适配器**适配器名称**下拉列表。 如果接收位置已存在，则不会替换它。 选择此选项后，选择应用程序中生成接收端口和位置**BizTalk 应用程序名称**下拉列表，再单击**下一步**。  
  
7. 上**创建 WCF 服务**页上，选择**BizTalk 业务流程发布为 WCF 服务**，然后单击**下一步**。  
  
    ![创建 WCF 服务页](../core/media/86cb66b5-6842-4330-8942-20afa68ec5fa.gif "86cb66b5-6842-4330-8942-20afa68ec5fa")  
  
8. 上**BizTalk 程序集**页上，在**BizTalk 程序集文件 (\*.dll)** 文本框中，键入 BizTalk 程序集文件的名称，或单击**浏览**以浏览到包含业务流程的程序集以发布，然后单击**下一步**。  
  
   > [!NOTE]
   >  之前选择 BizTalk 程序集文件，将所有依赖程序集复制到同一文件夹中，与 BizTalk 程序集或依赖程序集安装到全局程序集缓存 (GAC)。  
  
   > [!NOTE]
   >  如果 BizTalk 程序集文件安装到 GAC 中时，请确保已经使用将在中选择的程序集更新了 GAC 中的程序集**BizTalk 程序集**对话框。 如果 GAC 中的程序集具有相同的完全限定的名称，BizTalk WCF 服务发布向导将使用 GAC 中的程序集文件而不是所选。  
  
   > [!NOTE]
   >  路径长度超过 260 个字符可能会导致错误消息的路径太长。  
  
    ![BizTalk 程序集页面](../core/media/d34a027e-ea82-4048-8b15-d97df795b0d4.gif "d34a027e-ea82-4048-8b15-d97df795b0d4")  
  
9. 上**业务流程和端口**页上，单击加号 （+） 展开每个程序集和业务流程的树节点。 选择业务流程和端口发布通过选中相应树节点复选框。 如果你想要创建一个 WCF 服务 （.svc 文件） 的所有选定的接收端口，而不是一个 WCF 服务，每个接收端口，请选择**所有选定的端口合并为单个 WCF 服务**选项，并单击**下一步**。  
  
    > [!NOTE]
    >  您将所有选定的端口合并为单个 WCF 服务时，所有选定端口都具有相同的端口类型，并且端口中的操作名称都是唯一。  
  
     ![操作和端口页](../core/media/97112744-ddd4-4512-ac56-41317ba9412b.gif "97112744-ddd4-4512-ac56-41317ba9412b")  
  
10. 上**WCF 服务属性**页上，在**的 WCF 服务 Targetnamespace**文本框中，键入 WCF 服务的目标命名空间，然后单击**下一步**。  
  
     ![WCF 服务属性页](../core/media/07518c78-bcae-4274-bb14-aeef107ee4c6.gif "07518c78-bcae-4274-bb14-aeef107ee4c6")  
  
11. 上**WCF 服务位置**页上，在**位置**文字框中，键入在其中生成 WCF 服务的 Web 目录名称。 您可以接受默认位置 (`http://localhost/<BizTalk Assembly Name>`)，键入用于中的 WCF 服务位置**位置**文本框中或单击**浏览**并选择 Web 目录。 选择以下选项之一：  
  
    - **覆盖现有项目。** 此选项才可用的 Web 目录已存在。 你将能够发布到相同位置，才选择此选项。 否则，必须输入不同的项目位置。  
  
    - **允许匿名访问 WCF 服务。** 此选项将添加到创建的虚拟目录的匿名访问。 默认情况下，虚拟目录的访问权限从继承其父虚拟目录或 Web 站点 （如果它是顶级虚拟目录）。  
  
      在完成此页上，单击**下一步**。  
  
      ![WCF 服务位置页](../core/media/76285470-1520-4d77-a5b6-c58cbe8fc575.gif "76285470-1520-4d77-a5b6-c58cbe8fc575")  
  
    > [!NOTE]
    >  项目位置可位于其他服务器上。 若要将 WCF 服务发布到另一台服务器，键入项目名称设置为`http://<servername>/<WCF service location>`。  
  
    > [!NOTE]
    >  项目位置可位于非默认网站上。 发布到非默认网站时，请在该 URL 中包括网站的端口号。 例如，`http://<servername>:8080/<WCF service location>`。  
  
    > [!NOTE]
    >  在使用向导创建接收位置时，向导会使用默认值创建接收位置。 接收管道的默认值是**Microsoft.BizTalk.DefaultPipelines.PassThruReceive**管道。 如果通过已发布的 WCF 服务接收的消息需要任何特殊的管道处理 （例如，验证、 关联/属性升级或入站/出站映射），则应将接收管道设置为**Microsoft.BizTalk.DefaultPipelines.XMLReceive**，或到自定义管道，使用 BizTalk Server 管理控制台。  
  
    > [!NOTE]
    >  如果你决定不使用**业务流程发布为 WCF 服务**选项在上访问此页上之后,**创建 WCF 服务**页上，你可能会看到， **Web 服务说明**服务和方法名称从之前你所选择的 BizTalk 程序集的显示更改发布选项。 这是因为更改发布方法时不会清除内存中 Web 服务说明。  
  
12. 上**WCF 服务摘要**页上，查看您的 WCF 服务的设置。  
  
13. 单击**创建**创建 WCF 服务。  
  
14. 单击**完成**完成 BizTalk WCF 服务发布向导。  
  
15. 发布 WCF 服务使用 BizTalk WCF 服务发布向导之后, 必须正确配置它们。 有关如何配置独立的 WCF 接收适配器，请参阅[如何使用 BizTalk WCF 服务发布向导配置 WCF 服务发布](../core/configure-wcf-services-published-with-the-biztalk-wcf-service-publishing-wizard.md)。  
  
## <a name="see-also"></a>请参阅  
 [如何配置使用 BizTalk WCF 服务发布向导发布 WCF 服务](../core/configure-wcf-services-published-with-the-biztalk-wcf-service-publishing-wizard.md)   
 [演练：使用 Wcf-basichttp 适配器发布 WCF 服务](../core/walkthrough-publishing-wcf-services-with-the-wcf-basichttp-adapter.md)   
 [如何使用 BizTalk WCF 服务发布向导将架构发布为 WCF 服务](../core/publish-schemas-as-wcf-services--use-the-biztalk-wcf-service-publishing-wizard.md)