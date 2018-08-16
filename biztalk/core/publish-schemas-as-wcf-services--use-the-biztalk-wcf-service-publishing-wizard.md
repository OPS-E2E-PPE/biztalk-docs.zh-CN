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
ms.openlocfilehash: cf10236b5db5b1af1a0a115e57a71ad2ae415eda
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "37022163"
---
# <a name="how-to-use-the-biztalk-wcf-service-publishing-wizard-to-publish-schemas-as-wcf-services"></a>如何使用 BizTalk WCF 服务发布向导将架构发布为 WCF 服务
可使用 BizTalk WCF 服务发布向导将架构发布为 WCF 服务。  
  
> [!NOTE]
>  在运行 BizTalk WCF 服务发布向导之前，必须生成 BizTalk 项目。 BizTalk 项目必须包括要发布为 WCF 服务的架构。  
  
### <a name="to-publish-schemas-as-wcf-servicees"></a>将架构发布为 WCF 服务  
  
1. 单击**启动**，依次指向**所有程序**，指向[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]，然后单击**BizTalk WCF 服务发布向导**。  
  
   > [!NOTE]
   >  若要创建 BizTalk 业务流程和架构并使用 WCF 适配器将其发布为 WCF 服务，可以使用 BizTalk WCF 服务发布向导。 若要使用 SOAP 适配器将业务流程和架构发布为 Web Services，可以使用 BizTalk Web Services 发布向导。  
  
2. 上**欢迎使用 BizTalk WCF 服务发布向导**页上，单击**下一步**。  
  
3. 上**WCF 服务类型**页上，选择**服务终结点**上发布的 WCF 服务中选择选项，BizTalk 业务流程的 BizTalk 程序集。  
  
    ![WCF 服务类型页](../core/media/959900fd-44c9-4f3a-8836-9786a2f5e707.gif "959900fd-44c9-4f3a-8836-9786a2f5e707")  
  
4. 上**WCF 服务类型**页上，选中或清除**启用元数据终结点**复选框以指示独立的 WCF 接收位置由 Internet 信息服务 (IIS) 承载是否将发布使用 HTTP/GET 请求进行检索服务元数据。  
  
    选中此复选框后，向导生成的 Web.config 文件中的**httpGetEnabled**的属性**\<serviceMetadata\>** 元素设置为 **，则返回 true**。 您可以使用元数据导入工具（如 SvcUtil.exe）生成在开发环境中调用此服务所需的客户端代码。 发布元数据的地址为终结点地址加上 **？ wsdl**查询字符串。  
  
   > [!NOTE]
   >  为了避免无意中泄漏可能敏感的服务元数据，建议在生产环境中禁用此行为。 这可通过将 httpgetenabled 设置为 false 完成，或删除 MEX 虚拟目录。  
  
5. 上**WCF 服务类型**页上，在**适配器名称 （传输类型）** 下拉列表中，选择的 WCF 服务发布使用独立的 WCF 适配器。 可以选择以下任意适配器：  
  
   -   **Wcf-basichttp。** WCF-BasicHttp 适配器可与符合 WS-I Basic Profile 1.1 的 Web Services（如基于 ASMX 的服务）进行通信。  
  
   -   **WCF-WSHttp。** WCF-WSHttp 适配器可通过 HTTP 和 HTTPS 上的 WS-* 标准与服务通信。  
  
   -   **WCF CustomIsolated。** WCF-CustomIsolated 适配器支持通过 HTTP 传输使用 Windows Communication Foundation (WCF) 扩展性功能。  
  
6. 上**WCF 服务类型**页上，选择**以下应用程序中的创建 BizTalk 接收位置**复选框以创建接收端口和对应于每个生成的.svc 文件的位置在中选择的 WCF 适配器**适配器名称**下拉列表。 如果接收位置已经存在，则不会替换它。 选择此选项后，选择应用程序中生成接收端口和位置**BizTalk 应用程序名称**下拉列表，再单击**下一步**。  
  
7. 上**创建 WCF 服务**页上，选择**将架构发布为 WCF 服务**，然后单击**下一步**。  
  
    ![创建 WCF 服务页](../core/media/717db27a-2843-4950-899d-0946460f5c1f.gif "717db27a-2843-4950-899d-0946460f5c1f")  
  
8. 上**WCF 服务**页上，选择要发布的 WCF 服务。 使用中的树**Web 服务说明**对话框可以添加、 删除、 重命名和编辑要发布的 WCF 服务的 Web 服务说明节点。 **信息**对话框提供了有关所选节点的信息，并显示当前节点或子节点中的任何错误：  
  
   -   树的根节点（Web Services 说明）描述了要发布的 WCF 服务。 虚拟目录名称使用该根节点作为默认名称。 您可以修改要通过选择发布的 WCF 服务的 Web 服务说明名称**重命名 web 服务说明**。  
  
        ![WCF 服务页](../core/media/35131a58-dae7-45fe-ac6a-928c8570f27d.gif "35131a58-dae7-45fe-ac6a-928c8570f27d")  
  
   -   Web 方法节点， **Operation1**，默认服务节点， **Service1**，默认情况下所示**Web 服务说明**对话框可用于请求-响应接收位置。 如果你打算发布一个单向 WCF 接收位置，用于此服务说明，右键单击默认的 Web 方法节点，单击**删除 web 方法**，然后按如下所示创建一个单向 Web 方法： 右键单击默认服务节点，指向**添加 web 方法**，然后单击**单向**。  
  
   -   若要添加新的 WCF 服务，右键单击 Web 服务说明的名称，然后依次**添加 web 服务**。 这会创建一个不带有任何 WCF 操作的新 WCF 服务。 若要修改 WCF 服务的名称，请右键单击 WCF 服务节点，单击**重命名 web 服务**，然后按 ENTER 以接受新名称。  
  
   -   若要添加新的 WCF 操作，请右键单击 WCF 服务节点，指向**添加 Web 方法**，然后单击**单向**（对于请求 WCF 操作） 或**请求-响应**(为请求-响应 WCF 操作）。  
  
   -   若要设置的请求和响应架构类型，请右键单击**请求**或**响应**节点，，然后单击**选择架构类型**。 在中**请求消息类型**框中，键入包含文档架构中的程序集名称**BizTalk 程序集文件**文本框中或单击**浏览**搜索程序集。 **可用架构类型**列表视图中显示的架构的每个根元素。 选择要作为请求或响应架构类型添加的根节点。  
  
       > [!NOTE]
       >  如果在全局程序集缓存 (GAC) 中安装 BizTalk 程序集文件，请确保已经使用将在中选择的程序集更新了 GAC 中的程序集**请求消息类型**对话框。 如果 GAC 中的程序集具有相同的完全限定名，则 BizTalk WCF 服务发布向导将使用 GAC 中的程序集文件而不是您选择的程序集文件。  
  
        ![请求消息类型页](../core/media/6bb4cc17-b108-4692-a5ca-548c7ef46045.gif "6bb4cc17-b108-4692-a5ca-548c7ef46045")  
  
   -   您可以重命名**请求**并**响应**节点而不会影响生成的代码。 在定义了架构之后，可以重命名部分元素，这会修改 WCF 操作的参数名称。 通过查看要发布的 WCF 服务的服务元数据，可以看到发生的更改。  
  
       > [!NOTE]
       >  在重命名任何 Web Services 说明节点时，不能使用空格。  
  
9. 单击**下一步**继续执行向导。  
  
10. 上**WCF 服务属性**页上，在**的 WCF 服务 Targetnamespace**文本框中，键入 WCF 服务的目标命名空间，然后单击**下一步**。  
  
     ![WCF 服务属性页](../core/media/07518c78-bcae-4274-bb14-aeef107ee4c6.gif "07518c78-bcae-4274-bb14-aeef107ee4c6")  
  
11. 上**WCF 服务位置**页上，在**位置**文字框中，键入在其中生成 WCF 服务的 Web 目录名称。 您可以接受默认位置 (http://localhost/<*Web 服务说明名称*>)，键入用于中的 WCF 服务位置**位置**文本框中或单击**浏览**并选择 Web 目录。 选择以下任何选项：  
  
    - **覆盖现有项目。** 此选项才可用，仅当 Web 目录已存在。 仅当选择了此选项时，您才能够发布到同一位置。 否则，必须输入不同的项目位置。  
  
    - **允许匿名访问 WCF 服务。** 此选项会为已创建的虚拟目录添加匿名访问权限。 默认情况下，虚拟目录继承其父虚拟目录或网站（如果该目录是顶级虚拟目录）的访问权限。  
  
      在完成此页上，单击**下一步**。  
  
      ![WCF 服务位置页](../core/media/76285470-1520-4d77-a5b6-c58cbe8fc575.gif "76285470-1520-4d77-a5b6-c58cbe8fc575")  
  
    > [!NOTE]
    >  项目位置可位于其他服务器上。 若要将 WCF 服务发布到另一台服务器，键入项目名称作为 http://&lt*servername*>/<*WCF 服务位置*>。  
  
    > [!NOTE]
    >  项目位置可位于非默认网站上。 发布到非默认网站时，请在该 URL 中包括网站的端口号。 例如，http://&lt*servername*>: 8080 / <*WCF 服务位置*>。  
  
    > [!NOTE]
    >  在使用向导创建接收位置时，向导会使用默认值创建接收位置。 接收管道的默认值是**Microsoft.BizTalk.DefaultPipelines.PassThruReceive**管道。 如果通过已发布的 WCF 服务接收的消息需要任何特殊的管道处理 （例如，验证、 关联/属性升级或入站/出站映射），则应将接收管道设置为**Microsoft.BizTalk.DefaultPipelines.XMLReceive**，或通过使用 BizTalk 管理控制台中自定义管道。  
  
12. 上**WCF 服务摘要**页上，查看您的 WCF 服务的设置。  
  
13. 单击**创建**创建 WCF 服务。  
  
14. 单击**完成**完成 BizTalk WCF 服务发布向导。  
  
15. 使用 BizTalk WCF 服务发布向导发布 WCF 服务之后，必须对其进行正确配置。 有关如何配置独立的 WCF 接收适配器，请参阅[如何使用 BizTalk WCF 服务发布向导配置 WCF 服务发布](../core/configure-wcf-services-published-with-the-biztalk-wcf-service-publishing-wizard.md)。  
  
## <a name="see-also"></a>请参阅  
 [如何配置使用 BizTalk WCF 服务发布向导发布 WCF 服务](../core/configure-wcf-services-published-with-the-biztalk-wcf-service-publishing-wizard.md)   
 [演练： 发布具有 Wcf-basichttp 适配器的 WCF 服务](../core/walkthrough-publishing-wcf-services-with-the-wcf-basichttp-adapter.md)   
 [如何使用 BizTalk WCF 服务发布向导将业务流程发布为 WCF 服务](../core/publish-orchestrations-as-wcf-services--biztalk-wcf-service-publishing-wizard.md)