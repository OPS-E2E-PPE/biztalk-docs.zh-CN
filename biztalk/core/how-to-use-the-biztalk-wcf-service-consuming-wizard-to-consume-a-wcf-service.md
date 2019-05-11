---
title: 如何使用 BizTalk WCF 服务使用向导来使用 WCF 服务 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- WCF services, WCF Service Consuming Wizard
- WCF Service Consuming Wizard
- tools, WCF Service Consuming Wizard
- consuming, WCF Service Consuming Wizard
ms.assetid: d5fad2ac-4d98-4720-8026-88ebab78b120
caps.latest.revision: 23
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e694e094f3d67215227cd574ba1ff8fc81c39c10
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65383292"
---
# <a name="how-to-use-the-biztalk-wcf-service-consuming-wizard-to-consume-a-wcf-service"></a>如何使用 BizTalk WCF 服务使用向导来使用 WCF 服务
BizTalk 适配器框架提供了一种方法将适配器架构和 BizTalk 类型添加到 BizTalk 项目。 BizTalk WCF 服务使用向导，可将 WCF 发送适配器添加到 BizTalk 项目。 对于 WCF 发送适配器，您必须选择发送端口的现有元数据交换 (MEX) 终结点。 然后，您需要输入用于生成架构和类型的信息。 向导完成后，向 BizTalk 项目添加架构和使用 WCF 服务所需的类型。  
  
### <a name="to-add-the-schemas-and-types-for-wcf-send-adapters-to-your-project"></a>若要添加的架构和类型为 WCF 发送适配器到你的项目  
  
1. 在 Microsoft [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] BizTalk 项目，请在解决方案资源管理器，右键单击你的项目，单击**添加**，然后单击**添加生成的项**。  
  
2. 在中**添加生成的项- \<** <em>项目名称</em>**\>** 对话框中，在**模板**部分中，选择**使用 WCF 服务**，然后单击**添加**。  
  
3. 上**欢迎使用 BizTalk WCF 服务使用向导**页上，单击**下一步**。  
  
4. 上**元数据来源**页上，选择要导入，然后依次的元数据的源**下一步**。  
  
    ![元数据源页](../core/media/2478a788-23ff-4ba9-a183-82e533b57f46.gif "2478a788-23ff-4ba9-a183-82e533b57f46")  
  
    若要从正在运行的服务的元数据交换终结点中下载元数据文档，请选择**元数据交换 (MEX) 终结点**选项。 这使我们能够创建发送端口来充当 WCF 服务的客户端。 若要使用此选项，服务终结点必须发布服务元数据以便使用 HTTP/GET 或 HTTPS/GET 请求进行检索。 服务终结点还必须允许匿名用户凭据或用户凭据的用户名和密码的基本身份验证方案使用窗体中的元数据访问。  
  
   > [!NOTE]
   >  使用基本身份验证方案，凭据以明文形式发送，并且很容易被截获。 方案还提供了对传递从服务返回的信息的任何保护。 必须使用安全套接字层 (SSL) 对数据进行加密。  
  
    对于任何其他元数据文档导入，请选择**元数据文件 （WSDL 和 XSD）** 选项以从文件系统导入元数据。  
  
   > [!NOTE]
   >  并非所有服务都必须都发布元数据。 禁用元数据发布可以减少您的服务的攻击面并降低意外泄漏信息的风险。  
  
5. 如果所选**元数据交换 (MEX) 终结点**选项卡上**元数据源**页上，**元数据终结点**页将出现。 上**元数据终结点**页上，指定正在运行的服务，提供通过 WS-元数据交换或 Http-get 下载的元数据的 URL。 若要从该 URL 获取元数据文档，请单击**获取**。 如果正在运行的服务需要使用基本身份验证方案的用户凭据，请单击**编辑**以打开**BizTalk WCF 服务使用向导**对话框可以在其中提供用户名和若要访问运行服务时使用的密码。  
  
    ![元数据终结点页面](../core/media/2b17f85a-64d0-4719-99c4-ce61c706f10c.gif "2b17f85a-64d0-4719-99c4-ce61c706f10c")  
  
   > [!NOTE]
   >  若要下载通过 HTTP 或 HTTPS 发布的 WCF 服务的元数据，不能使用 MEX 终结点，例如 http://localhost:8087/CalculatorService/mex 有关 **元数据地址** 文本框。 对于 WCF 服务中，您必须使用 WSDL 元数据下载元数据，如下所示： http://localhost:8087/CalculatorService 或 http://localhost:8087/CalculatorService?wsdl  
  
6. 如果所选**元数据文件 （WSDL 和 XSD）** 选项卡上**元数据源**页上，**元数据终结点**页将出现。 上**元数据终结点**页上，指定要导入的元数据文件。 单击**外**以添加要导入到的元数据文件**元数据文件**视图。 这将打开**添加元数据文件**对话框可以在其中搜索元数据文件的磁盘位置。  
  
    在中**添加元数据文件**对话框中，选择要用于元数据的一组完整的 WSDL 和 XSD 文件。 可以通过在命令提示符下键入以下命令来生成这些元数据文件：  
  
    **svcutil.exe /t:metadata http://localhost/service.svc/mex**  
  
    单击**删除**若要删除的元数据文件中所选**元数据文件**视图。  
  
    ![元数据文件页](../core/media/445bccd1-88b0-41ad-b91d-e899e7d5902d.gif "445bccd1-88b0-41ad-b91d-e899e7d5902d")  
  
   > [!NOTE]
   >  SvcUtil.exe 包含在 Microsoft Windows 软件开发工具包 (SDK) 的 Windows Vista 和.NET Framework 运行时组件。  
  
   > [!NOTE]
   >  服务元数据可以篡改或伪造时检索到不安全的方式。 篡改的元数据无法将客户端重定向到恶意服务、 包含泄漏的安全设置，或包含恶意 XML 结构。 元数据文档可能会非常大并经常保存到文件系统。 必须确保元数据文件未被篡改。  
  
7. 上**导入 WCF 服务元数据摘要**页上，查看你的设置。 可以单击**回**需进行任何更改。 然后单击**导入**创建 BizTalk 项目和类型用于使用 WCF 服务。  
  
8. 上**完成 BizTalk WCF 服务使用向导**页上，单击**完成**。 如果你想要再次运行此向导，选择**再次运行此向导**选项，并单击**完成**。  
  
    BizTalk WCF 服务使用向导创建 BizTalk 项目中的 BizTalk 架构和类型需使用 WCF 服务。 BizTalk 类型，如端口类型和业务流程中创建多部分消息类型。 我们建议您不要修改向导创建的业务流程。 相反，可以供您使用 BizTalk 项目中添加新的业务流程。 BizTalk WCF 服务使用向导还会创建两个绑定文件， **BizTalkServiceInstance.BindingInfo.xml**并**BizTalkServiceInstance_Custom.BindingInfo.xml**。 **BizTalkServiceInstance.BindingInfo.xml**是一个 BizTalk 绑定文件，可以通过开发命令行工具或向导以使用标准绑定 WCF 适配器配置发送端口导入 — 例如，Wcf-netmsmq 和 Wcf-wshttp适配器。 **BizTalkServiceInstance.BindingInfo.xml**是可以通过开发命令行工具或向导以使用 WCF 自定义适配器配置发送端口导入一个 BizTalk 绑定文件。  
  
    导入生成的绑定文件时，它将填充**WCF。操作**采用操作映射格式的属性。 若要查看如何配置此属性，请查看**操作**上的文本框中**常规**WCF 发送端口传输属性对话框中的 BizTalk 管理控制台中的选项卡。  
  
    您可以指定**WCF。操作**两种不同方式的属性： 单一操作格式和操作映射格式。 例如，将此属性设置中的单一操作格式-如果 http://contoso.com/Svc/Op1 - **SOAPAction**标头传出消息将始终设置为此属性中指定的值。 如果将此属性设置采用操作映射格式，传出**SOAPAction**标头由**BTS。操作**上下文属性。 例如，如果此属性设置为下面的 XML 格式和**BTS。操作**属性设置为**Op1**，WCF 发送适配器将使用 http://contoso.com/Svc/Op1 传出**SOAPAction**标头。  
  
    `<BtsActionMapping>`  
  
    `<Operation Name="Op1" Action="http://contoso.com/Svc/Op1" />`  
  
    `<Operation Name="Op2" Action="http://contoso.com/Svc/Op2" />`  
  
    `</BtsActionMapping>`  
  
    如果传出消息来自某个业务流程端口，业务流程实例动态设置**BTS。操作**使用的端口的操作名称的属性。 如果使用基于内容的路由来路由传出消息，则可以设置**BTS。操作**管道组件中的属性。 由 BizTalk WCF 使用向导生成的端口具有名称与匹配的操作**名称**中的属性**<BtsActionMapping>** 元素。 不需要显式设置**BTS。操作**时由向导生成的端口发送消息的业务流程中的属性。  
  
## <a name="see-also"></a>请参阅  
 [如何使用 BizTalk WCF 服务发布向导将业务流程发布为 WCF 服务](../core/publish-orchestrations-as-wcf-services--biztalk-wcf-service-publishing-wizard.md)   
 [如何使用 BizTalk WCF 服务发布向导将架构发布为 WCF 服务](../core/publish-schemas-as-wcf-services--use-the-biztalk-wcf-service-publishing-wizard.md)