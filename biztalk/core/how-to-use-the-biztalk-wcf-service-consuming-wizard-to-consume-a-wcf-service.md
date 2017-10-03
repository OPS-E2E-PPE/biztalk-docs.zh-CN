---
title: "如何通过 BizTalk WCF 服务使用向导来使用 WCF 服务 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- WCF services, WCF Service Consuming Wizard
- WCF Service Consuming Wizard
- tools, WCF Service Consuming Wizard
- consuming, WCF Service Consuming Wizard
ms.assetid: d5fad2ac-4d98-4720-8026-88ebab78b120
caps.latest.revision: "23"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b218fa44b93211fdb51080d68b429744b5aabf72
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-use-the-biztalk-wcf-service-consuming-wizard-to-consume-a-wcf-service"></a>如何利用 BizTalk WCF 服务使用向导来使用 WCF 服务
BizTalk 适配器框架提供了一条将适配器架构和 BizTalk 类型添加到 BizTalk 项目的途径。 通过 BizTalk WCF 服务使用向导，可以将 WCF 发送适配器添加到 BizTalk 项目。 对于 WCF 发送适配器，必须为发送端口选择现有的元数据交换 (MEX) 终结点。 然后，您需要输入用于生成架构和类型的信息。 在向导完成后，使用 WCF 服务所需的架构和类型便会添加到 BizTalk 项目中。  
  
### <a name="to-add-the-schemas-and-types-for-wcf-send-adapters-to-your-project"></a>将 WCF 发送适配器的架构和类型添加到您的项目  
  
1.  在你的 Microsoft [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] BizTalk 项目，请在解决方案资源管理器，右键单击你的项目，单击**添加**，然后单击**添加生成的项**。  
  
2.  在**添加生成的项的\<** *项目名称* **>** 对话框中，在**模板**部分中，选择**使用 WCF 服务**，然后单击**添加**。  
  
3.  上**欢迎 BizTalk WCF 服务使用向导**页上，单击**下一步**。  
  
4.  上**元数据源**页上，选择要导入，并依次的元数据的源**下一步**。  
  
     ![元数据源页面](../core/media/2478a788-23ff-4ba9-a183-82e533b57f46.gif "2478a788-23ff-4ba9-a183-82e533b57f46")  
  
     若要从正在运行的服务元数据交换终结点中下载元数据文档，请选择**元数据交换 (MEX) 终结点**选项。 这样可以创建一个发送端口来充当 WCF 服务的客户端。 若要使用此选项，服务终结点必须使用 HTTP/GET 或 HTTPS/GET 请求发布服务元数据以供检索。 服务终结点还必须允许使用匿名用户凭据或用户凭据（对于基本身份验证方案，其形式为用户名和密码）访问元数据。  
  
    > [!NOTE]
    >  对于基本身份验证方案，凭据以明文方式发送，因此很容易被截获。 而且，该方案也没有为从服务传回的信息提供任何保护。 您必须使用安全套接字层 (SSL) 加密您的数据。  
  
     对于任何其他元数据文档导入，请选择**元数据文件 （WSDL 和 XSD）**选项以从文件系统导入元数据。  
  
    > [!NOTE]
    >  并不是所有的服务都必须发布元数据。 使元数据发布功能保留为禁用状态可减少服务遭受攻击的可能性，同时降低无意中泄露信息的危险。  
  
5.  如果你选择**元数据交换 (MEX) 终结点**选项**元数据源**页上，**元数据终结点**页将出现。 上**元数据终结点**页上，指定正在运行的服务，通过 WS 元数据交换或 Http Get 的下载可提供元数据的 URL。 若要从 URL 中获取的元数据文档，请单击**获取**。 如果正在运行的服务要求具有基本身份验证方案的用户凭据，请单击**编辑**以打开**BizTalk WCF 服务使用向导**对话框中，你可以在其中提供用户名和访问运行服务时要使用的密码。  
  
     ![元数据终结点页面](../core/media/2b17f85a-64d0-4719-99c4-ce61c706f10c.gif "2b17f85a-64d0-4719-99c4-ce61c706f10c")  
  
    > [!NOTE]
    >  若要下载的元数据的 WCF 服务通过 HTTP 或 HTTPS 发布，不能使用 MEX 终结点，如 http://localhost:8087/CalculatorService/mex 为**元数据地址**文本框。 对于 WCF 服务中，你必须使用 WSDL 元数据下载元数据，如下所示： http://localhost:8087/CalculatorService 或 http://localhost:8087/CalculatorService？ wsdl  
  
6.  如果你选择**元数据文件 （WSDL 和 XSD）**选项**元数据源**页上，**元数据终结点**页将出现。 上**元数据终结点**页上，指定要导入的元数据文件。 单击**添加**添加要导入到的元数据文件**元数据文件**视图。 这将打开**添加元数据文件**对话框中，可以在其中搜索元数据文件的磁盘位置。  
  
     在**添加元数据文件**对话框中，选择一组完整的 WSDL 和 XSD 文件用于元数据。 可以通过在命令提示符下键入以下命令来生成这些元数据文件：  
  
     **svcutil.exe /t:metadata http://localhost/service.svc/mex**  
  
     单击**删除**来删除元数据文件中所选**元数据文件**视图。  
  
     ![元数据文件页](../core/media/445bccd1-88b0-41ad-b91d-e899e7d5902d.gif "445bccd1-88b0-41ad-b91d-e899e7d5902d")  
  
    > [!NOTE]
    >  SvcUtil.exe 包含在 Windows Vista 和 .NET Framework 运行时组件的 Microsoft Windows 软件开发工具包 (SDK) 中。  
  
    > [!NOTE]
    >  如果以不安全的方式检索，服务元数据可能被篡改或伪造。 篡改的元数据可能会将您的客户端重定向至包含泄漏的安全设置或包含恶意 XML 结构的恶意服务。 元数据文档可能非常大并经常保存到文件系统。 您必须确保元数据文件未被篡改。  
  
7.  上**导入 WCF 服务元数据摘要**页上，查看你的设置。 你可以单击**回**需进行任何更改。 然后单击**导入**创建 BizTalk 项目和要用于使用 WCF 服务的类型。  
  
8.  上**完成 BizTalk WCF 服务使用向导**页上，单击**完成**。 如果你想要再次运行此向导，选择**再次运行此向导**选项，并依次**完成**。  
  
     BizTalk WCF 服务使用向导在您的 BizTalk 项目中创建使用 WCF 服务所需的 BizTalk 架构和类型。 在业务流程中创建诸如端口类型和多部分消息类型这样的 BizTalk 类型。 我们建议您不要修改向导创建的业务流程。 但是，您可以根据自己的需要在 BizTalk 项目中添加新的业务流程。 BizTalk WCF 服务使用向导还会创建两个绑定文件， **BizTalkServiceInstance.BindingInfo.xml**和**BizTalkServiceInstance_Custom.BindingInfo.xml**。 **BizTalkServiceInstance.BindingInfo.xml**是可以由开发命令行工具或向导以使用标准绑定 WCF 适配器配置发送端口导入的 BizTalk 绑定文件-例如，WCF NetMsmq 和 WCF WSHttp适配器。 **BizTalkServiceInstance.BindingInfo.xml**是可以由开发命令行工具或向导来配置与 WCF 自定义适配器发送端口导入的 BizTalk 绑定文件。  
  
     当你导入生成的绑定文件时，它将填充**WCF。操作**操作映射格式中的属性。 若要查看此属性的配置时，查看**操作**上的文本框**常规**WCF 发送端口传输属性对话框中的选项卡在 BizTalk 管理控制台中。  
  
     你可以指定**WCF。操作**两个不同的方式的属性： 单个操作格式和操作映射格式。 如果将此属性设置中的单个操作格式-例如，http://contoso.com/Svc/Op1- **SOAPAction**标头为传出消息始终设置为此属性中指定的值。 如果在操作映射格式，传出中设置此属性**SOAPAction**标头由**BTS。操作**上下文属性。 例如，如果此属性设置为以下 XML 格式和**BTS。操作**属性设置为**Op1**，WCF 发送适配器可用于 http://contoso.com/Svc/Op1 传出**SOAPAction**标头。  
  
     `<BtsActionMapping>`  
  
     `<Operation Name="Op1" Action="http://contoso.com/Svc/Op1" />`  
  
     `<Operation Name="Op2" Action="http://contoso.com/Svc/Op2" />`  
  
     `</BtsActionMapping>`  
  
     如果传出消息来自于业务流程端口，动态设置业务流程实例**BTS。操作**与操作名称的端口的属性。 如果使用基于内容的路由路由传出消息，则可以设置**BTS。操作**管道组件中的属性。 通过 BizTalk WCF 使用向导生成的端口具有名称与相匹配的操作**名称**中的属性 **<BtsActionMapping>** 元素。 不需要显式设置**BTS。操作**在通过由向导生成的端口发送消息时的业务流程中的属性。  
  
## <a name="see-also"></a>另请参阅  
 [如何使用发布向导的 BizTalk WCF 服务发布作为 WCF 服务的业务流程](../core/publish-orchestrations-as-wcf-services--biztalk-wcf-service-publishing-wizard.md)   
 [如何使用发布向导的 BizTalk WCF 服务发布作为 WCF 服务的架构](../core/publish-schemas-as-wcf-services--use-the-biztalk-wcf-service-publishing-wizard.md)