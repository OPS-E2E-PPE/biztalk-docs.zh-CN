---
title: 如何使用 BizTalk WCF 服务发布向导将架构发布为 WCF 服务 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- schemas, WCF services
- tools, WCF Service Publishing Wizard
- publishing, schemas [WCF services]
- WCF services, schemas
- WCF Service Publishing Wizard
ms.assetid: 3b770fd5-5b7b-493f-9016-d7d58854c5ff
caps.latest.revision: 15
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ed13b7f94cf7dea10837295e81063a3f42499c40
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65398400"
---
# <a name="how-to-use-the-biztalk-wcf-service-publishing-wizard-to-publish-schemas-as-wcf-services"></a>如何使用 BizTalk WCF 服务发布向导将架构发布为 WCF 服务
使用 BizTalk WCF 服务发布向导将架构发布为 WCF 服务。  
  
> [!NOTE]
>  在运行 BizTalk WCF 服务发布向导前必须生成 BizTalk 项目。 BizTalk 项目必须包括要发布为 WCF 服务的架构。  
  
### <a name="to-publish-schemas-as-wcf-servicees"></a>若要将架构发布为 WCF 服务  
  
1. 单击**启动**，依次指向**所有程序**，指向[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]，然后单击**BizTalk WCF 服务发布向导**。  
  
   > [!NOTE]
   >  若要创建并将 BizTalk 业务流程和架构发布为 WCF 适配器的 WCF 服务，你可以使用 BizTalk WCF 服务发布向导。 若要将业务流程和架构发布为 Web 服务使用 SOAP 适配器，您可以使用 BizTalk Web Services 发布向导。  
  
2. 上**欢迎使用 BizTalk WCF 服务发布向导**页上，单击**下一步**。  
  
3. 上**WCF 服务类型**页上，选择**服务终结点**上发布的 WCF 服务中选择选项，BizTalk 业务流程的 BizTalk 程序集。  
  
    ![WCF 服务类型页](../core/media/959900fd-44c9-4f3a-8836-9786a2f5e707.gif "959900fd-44c9-4f3a-8836-9786a2f5e707")  
  
4. 上**WCF 服务类型**页上，选中或清除**启用元数据终结点**复选框以指示独立的 WCF 接收位置由 Internet 信息服务 (IIS) 承载是否将发布使用 HTTP/GET 请求进行检索服务元数据。  
  
    选中此复选框后，向导生成的 Web.config 文件中的**httpGetEnabled**的属性 **\<serviceMetadata\>** 元素设置为 **，则返回 true**。 您可以使用元数据导入工具（如 SvcUtil.exe）生成在开发环境中调用此服务所需的客户端代码。 发布元数据的地址为终结点地址加上 **？ wsdl**查询字符串。  
  
   > [!NOTE]
   >  若要防止无意中泄漏可能敏感的服务元数据，我们建议禁用此行为在生产环境中。 这可以通过将 httpgetenabled 设置为 false，或删除 MEX 虚拟目录。  
  
5. 上**WCF 服务类型**页上，在**适配器名称 （传输类型）** 下拉列表中，选择的 WCF 服务发布使用独立的 WCF 适配器。 您可以选择任何以下适配器：  
  
   -   **WCF-BasicHttp.** Wcf-basichttp 适配器能够与 WS-基本配置文件 1.1 的 web 服务与基于 ASMX 的服务一样。  
  
   -   **WCF-WSHttp.** Wcf-wshttp 适配器能够与服务的 WS-* 标准通过 HTTP 和 HTTPS。  
  
   -   **WCF CustomIsolated。** Wcf-customisolated 适配器支持通过 HTTP 传输使用 Windows Communication Foundation (WCF) 扩展性功能。  
  
6. 上**WCF 服务类型**页上，选择**以下应用程序中的创建 BizTalk 接收位置**复选框以创建接收端口和对应于每个生成的.svc 文件的位置在中选择的 WCF 适配器**适配器名称**下拉列表。 如果接收位置已存在，则不会替换它。 选择此选项后，选择应用程序中生成接收端口和位置**BizTalk 应用程序名称**下拉列表，再单击**下一步**。  
  
7. 上**创建 WCF 服务**页上，选择**将架构发布为 WCF 服务**，然后单击**下一步**。  
  
    ![创建 WCF 服务页](../core/media/717db27a-2843-4950-899d-0946460f5c1f.gif "717db27a-2843-4950-899d-0946460f5c1f")  
  
8. 上**WCF 服务**页上，选择要发布的 WCF 服务。 使用中的树**Web 服务说明**对话框可以添加、 删除、 重命名和编辑要发布的 WCF 服务的 Web 服务说明节点。 **信息**对话框提供了有关所选节点的信息，并显示当前节点或子节点中的任何错误：  
  
   -   （Web 服务说明） 的树的根节点描述了要发布的 WCF 服务。 虚拟目录名称使用的根节点作为默认名称。 您可以修改要通过选择发布的 WCF 服务的 Web 服务说明名称**重命名 web 服务说明**。  
  
        ![WCF 服务页](../core/media/35131a58-dae7-45fe-ac6a-928c8570f27d.gif "35131a58-dae7-45fe-ac6a-928c8570f27d")  
  
   -   Web 方法节点， **Operation1**，默认服务节点， **Service1**，默认情况下所示**Web 服务说明**对话框可用于请求-响应接收位置。 如果你打算发布一个单向 WCF 接收位置，用于此服务说明，右键单击默认的 Web 方法节点，单击**删除 web 方法**，然后创建一个单向 Web 方法，如下所示：右键单击默认服务节点，指向**添加 web 方法**，然后单击**单向**。  
  
   -   若要添加新的 WCF 服务，右键单击 Web 服务说明的名称，然后依次**添加 web 服务**。 这将创建一个新的 WCF 服务，而无需任何 WCF 操作。 若要修改 WCF 服务的名称，请右键单击 WCF 服务节点，单击**重命名 web 服务**，然后按 ENTER 以接受新名称。  
  
   -   若要添加新的 WCF 操作，请右键单击 WCF 服务节点，指向**添加 Web 方法**，然后单击**单向**（对于请求 WCF 操作） 或**请求-响应**(为请求-响应 WCF 操作）。  
  
   -   若要设置的请求和响应架构类型，请右键单击**请求**或**响应**节点，，然后单击**选择架构类型**。 在中**请求消息类型**框中，键入包含文档架构中的程序集名称**BizTalk 程序集文件**文本框中或单击**浏览**搜索程序集。 **可用架构类型**列表视图中显示的架构的每个根元素。 选择要添加为请求或响应架构类型的根节点。  
  
       > [!NOTE]
       >  如果在全局程序集缓存 (GAC) 中安装 BizTalk 程序集文件，请确保已经使用将在中选择的程序集更新了 GAC 中的程序集**请求消息类型**对话框。 如果 GAC 具有相同的完全限定的名称，BizTalk WCF 服务发布向导将使用 GAC 中的程序集文件而不是所选的一个。  
  
        ![请求消息类型页](../core/media/6bb4cc17-b108-4692-a5ca-548c7ef46045.gif "6bb4cc17-b108-4692-a5ca-548c7ef46045")  
  
   -   您可以重命名**请求**并**响应**节点而不会影响生成的代码。 在之后定义了架构，您可以重命名部分元素中，这会修改 WCF 操作参数名称。 通过查看要发布的 WCF 服务的服务元数据，可以看到所做的更改。  
  
       > [!NOTE]
       >  重命名任何 Web 服务说明节点时，不能使用空格。  
  
9. 单击**下一步**继续执行向导。  
  
10. 上**WCF 服务属性**页上，在**的 WCF 服务 Targetnamespace**文本框中，键入 WCF 服务的目标命名空间，然后单击**下一步**。  
  
     ![WCF 服务属性页](../core/media/07518c78-bcae-4274-bb14-aeef107ee4c6.gif "07518c78-bcae-4274-bb14-aeef107ee4c6")  
  
11. 上**WCF 服务位置**页上，在**位置**文字框中，键入在其中生成 WCF 服务的 Web 目录名称。 您可以接受默认位置 (`http://localhost/<Web service description name>`)，键入用于中的 WCF 服务位置**位置**文本框中或单击**浏览**并选择 Web 目录。 选择以下选项之一：  
  
    - **覆盖现有项目。** 此选项才可用，仅当 Web 目录已存在。 你将能够发布到相同位置，才选择此选项。 否则，必须输入不同的项目位置。  
  
    - **允许匿名访问 WCF 服务。** 此选项将添加到创建的虚拟目录的匿名访问。 默认情况下，虚拟目录的访问权限从继承其父虚拟目录或 Web 站点 （如果它是顶级虚拟目录）。  
  
      在完成此页上，单击**下一步**。  
  
      ![WCF 服务位置页](../core/media/76285470-1520-4d77-a5b6-c58cbe8fc575.gif "76285470-1520-4d77-a5b6-c58cbe8fc575")  
  
    > [!NOTE]
    >  项目位置可位于其他服务器上。 若要将 WCF 服务发布到另一台服务器，键入项目名称设置为`http://<servername>/<WCF service location>`。  
  
    > [!NOTE]
    >  项目位置可位于非默认网站上。 发布到非默认网站时，请在该 URL 中包括网站的端口号。 例如，`http://<servername>:8080/<WCF service location>`。  
  
    > [!NOTE]
    >  在使用向导创建接收位置时，向导会使用默认值创建接收位置。 接收管道的默认值是**Microsoft.BizTalk.DefaultPipelines.PassThruReceive**管道。 如果通过已发布的 WCF 服务接收的消息需要任何特殊的管道处理 （例如，验证、 关联/属性升级或入站/出站映射），则应将接收管道设置为**Microsoft.BizTalk.DefaultPipelines.XMLReceive**，或通过使用 BizTalk 管理控制台中自定义管道。  
  
12. 上**WCF 服务摘要**页上，查看您的 WCF 服务的设置。  
  
13. 单击**创建**创建 WCF 服务。  
  
14. 单击**完成**完成 BizTalk WCF 服务发布向导。  
  
15. 发布 WCF 服务使用 BizTalk WCF 服务发布向导之后, 必须正确配置它们。 有关如何配置独立的 WCF 接收适配器，请参阅[如何使用 BizTalk WCF 服务发布向导配置 WCF 服务发布](../core/configure-wcf-services-published-with-the-biztalk-wcf-service-publishing-wizard.md)。  
  
## <a name="see-also"></a>请参阅  
 [如何配置使用 BizTalk WCF 服务发布向导发布 WCF 服务](../core/configure-wcf-services-published-with-the-biztalk-wcf-service-publishing-wizard.md)   
 [演练：使用 Wcf-basichttp 适配器发布 WCF 服务](../core/walkthrough-publishing-wcf-services-with-the-wcf-basichttp-adapter.md)   
 [如何使用 BizTalk WCF 服务发布向导将业务流程发布为 WCF 服务](../core/publish-orchestrations-as-wcf-services--biztalk-wcf-service-publishing-wizard.md)