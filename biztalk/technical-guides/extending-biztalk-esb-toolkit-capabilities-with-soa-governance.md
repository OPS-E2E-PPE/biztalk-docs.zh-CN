---
title: 扩展 BizTalk ESB 工具包功能使用 SOA Governance |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: b66a121b-d86f-4f97-a05f-5141ffe719e8
caps.latest.revision: 14
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a770599e082d2f25062588247acfeb6a0449b974
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36977502"
---
# <a name="extending-biztalk-esb-toolkit-capabilities-with-soa-governance"></a>使用 SOA Governance 扩展 BizTalk ESB 工具包功能
[!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]随[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]是一系列工具和扩展的库和[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]支持松散耦合和动态的消息传递体系结构的功能。 它充当快速中介服务及其使用者之间提供了工具的中间件。 在运行时，启用最大的灵活性[!INCLUDE[esbToolkit_short](../includes/esbtoolkit-short-md.md)]简化了松散耦合的服务终结点组合和管理服务的交互。  
  
 Sentinet BizTalk Server 扩展增强的功能[!INCLUDE[esbToolkit_short](../includes/esbtoolkit-short-md.md)]通过将其与 Sentinet，SOA 监管和适用于 Microsoft 平台的 API 管理软件解决方案。 首次发布 Sentinet[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]扩展产品/服务[!INCLUDE[esbToolkit_short](../includes/esbtoolkit-short-md.md)]SOA 存储库解析程序，它与 BizTalk Server 2013 集成[!INCLUDE[esbToolkit_short](../includes/esbtoolkit-short-md.md)]，和 Visual Studio 2012。  
  
 此白皮书讨论的是如何 Sentinet SOA 冲突解决程序扩展了[!INCLUDE[esbToolkit_short](../includes/esbtoolkit-short-md.md)]功能，如何配置 Sentinet SOA 的冲突解决程序，并最后演示如何使用 Sentinet SOA 冲突解决程序的示例。  
  
## <a name="esb-toolkit-and-sentinet-soa-resolver"></a>ESB 工具包和 Sentinet SOA 冲突解决程序  
 除此之外，ESB 工具包解析程序必须提供以下信息：  
  
- 运行时解析服务终结点和它们的配置  
  
- BizTalk ESB 松散耦合的消息传送解决方案。  
  
  Sentinet 提供一个可靠的、 全面[SOA 存储库](http://www.nevatech.com/sentinet/soa-repository)SOA 的集成解决方案，以及高级 SOA 管理和运行时提供管理功能。 结合 Sentinet SOA 存储库，Sentinet SOA 冲突解决程序提供了[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]ESB 体系结构和高级且易于使用 ESB 配置、 动态消息路由和消息安全实现功能。  
  
  下面概要关系图显示了如何 Sentinet SOA 冲突解决程序适应[!INCLUDE[esbToolkit_short](../includes/esbtoolkit-short-md.md)]体系结构。  
  
  ![含 BizTalk ESB 工具包的 Sentinet](../technical-guides/media/sentinetwp-arch.png "SentinetWP_Arch")  
  
  在运行时，**终结点解析和路由**组件图 （这是 ESB 工具包冲突解决程序框架的一部分） 中使用 （在 Visual Studio 路线设计器中创建） 的路线文档来实例化特定冲突解决程序，并请求冲突解决程序提供服务终结点和其配置。 路线本身必须使用服务终结点，对引用进行配置，以便解析程序可以使用此引用要在注册表或存储库中查找请求的终结点。 在设计时 （在创建路线） 时，不知道服务终结点的实际物理地址，并且不会需要执行此服务的安全策略。 在后续阶段中，运行时使用的 ESB 工具包解析服务终结点配置关闭负载增加动态发送端口以将消息发送到使用所需的服务的安全设置的实际物理服务地址。 如果服务终结点地址、 通信协议或安全要求更改专用注册表/存储库配置必须进行更新。 ESB 或 BizTalk Server 项目的运行时配置不需要进行更新。  
  
## <a name="how-does-the-sentinet-resolver-add-value-to-an-esb-toolkit-application"></a>如何 Sentinet 冲突解决程序 does 到 ESB 工具包应用程序添加值？  
 SOA 存储库以及使用 Sentinet 冲突解决程序的两个主要优点是：  
  
- 将客户端标识分配给已解析的外部服务终结点 – 大多数情况下，解析的 ESB 终结点需要特定的客户端标识来调用外部服务 （例如用户名/密码、 特定的 Windows 帐户凭据或特定的 X.509证书）。 这是很常见的安全要求，这不由其他 ESB 解析程序/注册表适当地处理。  
  
- 对安全信息 – 若要解决以前的限制，限制访问其他冲突解决程序可能使用 Tmodel 的手动的配置包含与所需的安全标识的复杂 XML。 但是，注册表/存储库的一部分保存的安全信息不是正确的方法。 这提供了服务使用者轻松访问用户名、 密码等访问该服务的安全详细信息。  
  
  Sentinet 冲突解决程序和 Sentinet SOA 存储库功能，灵活地提供了对功能和安全地将任何特定的客户端标识分配给通过标准或自定义 WCF 终结点行为的解析 ESB 终结点。 Sentinet 来实现此安全信息通过使用配置 Sentinet 冲突解决程序，并不 Sentinet SOA 存储库。 使用 Sentinet 解析程序配置的所有客户端凭据以加密形式存储。  
  
  除此之外，以下是一些使用 Sentinet 冲突解决程序和 Sentinet SOA 存储库的其他好处。  
  
- 提供了全面的 SOA 存储库。 存储库提供访问服务元数据内容、 服务标识和策略，对服务版本等的支持。  
  
- 易于通过上传服务 WSDL Sentinet 注册表中注册物理服务。  
  
- 全面且易于使用 Sentinet 管理控制台。 在控制台提供管理访问权限的所有服务元数据和项目，与访问服务操作及其数据架构、 服务终结点、 安全策略和等等的简单用户界面。  
  
- 管理和配置为解析终结点的自定义行为。 Sentinet 冲突解决程序解决终结点提供完全可自定义且易于配置的终结点行为。  
  
- 若要配置不同的搜索条件 Sentinet 冲突解决程序的选项。 路线可以定义分配给服务终结点，任何关键字，或使用指向存储库服务层次结构中的服务的服务路径。  
  
- 测试功能的高级解析程序。 Sentinet 解析程序配置可以直接从 Visual Studio 路线设计器进行测试。 其他冲突解决程序可以仅提供有关终结点的基本属性的信息，Sentinet 冲突解决程序提供了有关解决终结点的扩展的信息。 终结点的基本属性，除了 Sentinet 冲突解决程序显示的属性标识的已解析的 Sentinet 存储库中的服务和终结点位置。 路线设计器可以测试如何 Sentinet 冲突解决程序和不同的搜索条件对其影响解析结果之前在运行时使用自身的路线。  
  
## <a name="installing-the-sentinet-biztalk-server-extensions"></a>安装 Sentinet BizTalk Server 扩展  
 可以下载并安装中的 Sentinet BizTalk 扩展[此处](http://www.nevatech.com/download)。 安装扩展的 ESB 工具包、 文档和有关如何使用扩展的示例安装 Sentinet 冲突解决程序。  
  
 详细说明了如何安装和配置 Sentinet BizTalk Server 扩展的文档是可用的产品下载的一部分。  
  
## <a name="using-the-sentinet-biztalk-server-extensions"></a>使用 Sentinet BizTalk Server 扩展  
 在本部分中，我们介绍了如何使用 Sentinet BizTalk Server 扩展并展示上面提到的功能。  
  
### <a name="prerequisites"></a>必要條件  
 在本白皮书中的说明假定有以下安装和配置：  
  
-   Visual Studio 2012。  
  
-   BizTalk Server 2013。 有关说明，请参阅[安装 BizTalk Server 2013](http://msdn.microsoft.com/library/jj248688\(v=bts.80\).aspx)。  
  
-   BizTalk Server ESB 工具包。 有关说明，请参阅[安装和配置 Microsoft BizTalk ESB 工具包](http://msdn.microsoft.com/library/jj684558\(v=bts.80\).aspx)。  
  
-   Sentinet BizTalk Server 扩展。 有关说明，请参阅提供的文档作为产品下载可用的一部分[此处](http://www.nevatech.com/download)。  
  
### <a name="register-a-web-service"></a>注册 web 服务  
 必须在存储库中注册由 Sentinet 基础结构管理的 web 服务。 本白皮书将附带的 WCF 客户搜索示例服务使用 Sentinet 安装包。  
  
1. 启动**客户搜索**示例安装由 Sentinet 安装包的服务。 启动以管理员身份客户搜索示例中，选择策略绑定 (例如**wsHttpBinding**)，然后单击**启动**。  
  
2. 服务开始运行后，单击**视图 Wsdl**链接以打开浏览器使用服务元数据 URL 和 WSDL 的服务。 从浏览器地址栏复制元数据 URL。  
  
3. 打开浏览器并输入 URL (`https://[computer-name]/sentinet`) 以启动 Sentinet 管理控制台。 登录名，然后选择**存储库**中的根元素**存储库**视图面板。 右键单击**存储库**根元素，并单击**添加 > 服务 > SOAP**菜单选项。  
  
4. 在**添加的服务**对话框中，对于**URL 从 WSDL**选项，粘贴前面复制的服务元数据 URL，然后单击**下一步**。  
  
    ![添加服务 URL](../technical-guides/media/sentinetwp-addserviceurl.png "SentinetWP_AddServiceURL")  
  
5. 向导将启动下载服务元数据。 下载完成后，向导将显示 Web 服务树状结构。 提供服务的名称，然后单击**完成**服务元数据上载到 Sentinet 存储库。  
  
    ![Web 服务结构](../technical-guides/media/sentinetwp-servicestructure.png "SentinetWP_ServiceStructure")  
  
6. 该服务将作为导入到存储库版本 1。 选择的版本，然后选择该终结点。 在中**终结点详细信息**窗格的底部，单击**附件**选项卡，然后依次**修改**。  
  
    ![修改服务终结点](../technical-guides/media/sentinetwp-serviceendpoint.png "SentinetWP_ServiceEndpoint")  
  
7. 在终结点详细信息选项卡中单击 (**+**) 对登录**关键字**，输入与该终结点相关联的关键字 (例如， **TestKeyword**)，和然后单击**保存**。 SOA 存储库中作为终结点标记 （或标识符） 使用了关键字。  
  
    ![指定一个关键字](../technical-guides/media/sentinetwp-enterkeyword.png "SentinetWP_EnterKeyword")  
  
   重复上述步骤来添加的新版本**CustomerSearch**服务，但具有不同的绑定，例如**basicHttpBinding**。 稍后在本白皮书中，我们将演示如何 Sentinet 冲突解决程序可以解析为不同的服务 （或相同服务的不同版本） 只需通过将关联到服务终结点搜索关键字。  
  
### <a name="configure-sentinet-resolver"></a>配置 Sentinet 冲突解决程序  
 本部分介绍如何在简单 BizTalk ESB 路线设计器项目中，配置 Sentinet 冲突解决程序，特别是如何使用关键字来唯一地解析为服务终结点。 本部分还演示了如何测试而不发送任何 ESB 消息本身，Visual Studio 中的冲突解决程序。  
  
1.  启动 Visual Studio 并创建**BizTalk ESB 路线设计器**项目。  
  
2.  在解决方案资源管理器，双击路线以便在路线设计器中打开它。  
  
3.  从工具箱拖放**路线服务**设计器图面上的形状。  
  
4.  选择**路线服务**形状，然后更改**路线服务扩展器**属性设置为**消息扩展器**从下拉列表。  
  
     ![设置消息扩展程序属性](../technical-guides/media/sentinetwp-setmessageextender.png "SentinetWP_SetMessageExtender")  
  
5.  右键单击**冲突解决程序**中的元素**路线服务**形状，然后单击**添加新解析程序**。  
  
     ![添加新的冲突解决程序](../technical-guides/media/sentinetwp-addnewresolver.png "SentinetWP_AddNewResolver")  
  
6.  选择新的冲突解决程序元素，将其重命名 (例如， **MyResolver**)，并为**解析程序实现**属性中，选择**Sentinet 冲突解决程序扩展**。  
  
     ![设置解析程序实现](../technical-guides/media/sentinetwp-addresolverimplementation.png "SentinetWP_AddResolverImplementation")  
  
7.  指定**操作**并**关键字**Sentinet 冲突解决程序扩展的属性。 我们将使用这些属性来唯一地解析为我们之前添加到 Sentinet 存储库的服务。 有也可以指定 Sentinet 冲突解决程序扩展的其他属性。 若要了解有关这些属性的详细信息，请参阅 Sentinet BizTalk 扩展用户指南。  
  
    |“属性”|Description|  
    |--------------|-----------------|  
    |操作|消息操作标头，用于唯一地标识而调用的服务操作。 此操作标头是服务 WSDL 的一部分，可在服务 WSDL、 中或从 Sentinet 管理控制台用户界面 （在下操作的请求消息属性。|  
    |关键字|提供关键字 (例如**TestKeyword**) 分配给 Sentinet 管理控制台中的服务。|  
  
     下面的屏幕截图显示了为指定的操作和关键字属性**MyResolver**配置。  
  
     ![Sentinet Resolver 配置](../technical-guides/media/sentinetwp-resolverconfig.png "SentinetWP_ResolverConfig")  
  
8.  将更改保存到配置。  
  
#### <a name="advanced-resolver-configuration"></a>高级的解析程序配置  
 Sentinet BizTalk 扩展配置应用程序修改**Sentinet.BizTalk.config**位于包安装文件夹的根目录中的文件 (默认位置是`<installation drive>:\Program Files\Nevatech\Sentinet BizTalk Extensions\Sentinet.BizTalk.config`)。 可以修改的文件之外**Sentinet BizTalk 扩展配置**应用程序以提供高级的配置选项。 例如，在很多实用的 ESB 方案解决终结点必须不仅与服务终结点地址和绑定，而且还具有特定的客户端标识 （用户名/密码、 特定 Windows 帐户凭据或 X.509 客户端提供证书）。 如果没有正确的客户端标识，ESB 接入点关闭发送端口无法调用外部服务。 Sentinet 冲突解决程序，将分配提供相应的客户端终结点标识的特定终结点行为的路线开发人员。 多个终结点行为可以是预配置为在标准 WCF 终结点行为**Sentinet.BizTalk.config**文件，然后特定终结点行为可以在从 Sentinet 冲突解决程序路线的情况下引用配置中，通过指定名称的行为**解析终结点行为**属性。  
  
### <a name="test-the-resolver-configuration"></a>测试冲突解决程序配置  
 通过指定相关的属性值来配置 Sentinet 冲突解决程序后，可以测试从 Visual Studio 本身的冲突解决程序。  
  
1. 在设计图面上，右键单击 Sentinet 冲突解决程序添加到**路线服务**形状，然后依次**测试解析程序配置**。  
  
    输出窗格中显示测试结果，其中的一段摘录是类似于如下所示：  
  
   ```  
   ***** Resolved Service Endpoint *****  
  
   Service Path and Name          : /CustomerSearch  
   Service Id                     : 2b6d686a-cae1-4b7b-93da-99affef98478  
   Service Version                : 1  
   Endpoint Name                  : WSHttpBinding_ICustomerSearch  
   Endpoint Address               : http://btscloudcar/CustomerSearch/1  
   ```  
  
    请注意，冲突解决程序返回的终结点**CustomerSearch**服务**版本 1**到搜索条件 (**TestKeyword**) 连接。  
  
2. 删除**TestKeyword**与关联**版本 1**的**CustomerSearch**服务并将其与服务的第二个版本的终结点相关联。  
  
   1.  打开 Sentinet 管理控制台中，单击**第 1 版**下**CustomerSearch**服务，单击 wsHttpBinding 终结点，然后单击**附件**选项卡，然后依次**修改**。  
  
        ![从 CustomerSearch 服务删除关键字](../technical-guides/media/sentinetwp-removekeyword.png "SentinetWP_RemoveKeyword")  
  
   2.  单击以删除关键字时，单击以前输入的关键字对按钮**是**在消息框，然后单击**保存**。  
  
        ![从 CustomerSearch 服务删除关键字](../technical-guides/media/sentinetwp-removekeyword-2.png "SentinetWP_RemoveKeyword_2")  
  
   3.  现在，将分配相同的关键字 (**TestKeyword**) 到**basicHttpBinding**下的终结点**版本 2**的同一个服务。  
  
3. 返回到 Visual Studio 和测试的冲突解决程序配置。 右键单击 Sentinet 冲突解决程序添加到**路线服务**形状，然后依次**测试解析程序配置**。  
  
    输出窗格中显示测试结果，其中的一段摘录是类似于如下所示：  
  
   ```  
   ***** Resolved Service Endpoint *****  
  
   Service Path and Name          : /CustomerSearch  
   Service Id                     : 5b9e5878-7016-44ab-9f0e-5282a8c3e508  
   Service Version                : 2  
   Endpoint Name                  : BasicHttpBinding_ICustomerSearch  
   Endpoint Address               : http://btscloudcar/CustomerSearch/2  
   ```  
  
4. 请注意，冲突解决程序现在在返回方式的详细信息**版本 2**服务的即使未更改 ESB 路线应用程序中的任何内容。  
  
   分配关键字 (**TestKeyword**) 返回到该服务的版本 1 (与**WSHttpBinding**终结点)。  
  
## <a name="using-the-sentinet-biztalk-server-extensions"></a>使用 Sentinet BizTalk Server 扩展  
 在本部分中，我们将介绍如何使用 Sentinet BizTalk 扩展，与 ESB 冲突解决程序，一起唯一地标识服务并将消息与该服务，只需极少或无需更改路由到服务或客户端发送消息。 我们将测试两个方案：  
  
- 将示例消息发送到 （使用附加的关键字） Sentinet 存储库中注册的服务。 然后，使用 Sentinet 管理控制台的服务的策略绑定更改并发送另一个示例消息。 此方案演示如何更改服务的安全策略都不会影响客户端应用程序，也不 ESB 路线。  
  
- 将示例消息发送到服务终结点在 Sentinet 存储库中注册 （使用附加的关键字）。 然后，将该关键字附加到同一服务的另一个版本并重新发送该消息。 此方案演示如何将关键字自动附加到不同的服务版本将消息路由到新的服务版本。  
  
  若要测试这些方案，我们将使用下面的示例：  
  
- **客户搜索服务**随附 Sentinet 安装程序。 可以从开始菜单启动此服务。  
  
- **Nevatech.Vsb.BizTalk.Samples**将 Sentinet 安装程序随附的解决方案。 此示例位于`<installation drive>:\Program Files\Nevatech\Sentinet BizTalk Extensions\Samples`。  
  
- ESB。Itinerary.Test 示例附带[!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]。 这是在`<install drive>:\Program Files (x86)\Microsoft BizTalk ESB Toolkit\ESBSource.zip\Source\Samples\Itinerary\Source\ESB.Itinerary.Test`和用于测试与客户搜索服务的示例消息。  
  
#### <a name="to-test-the-sentinet-resolver-by-changing-the-service-policy-binding"></a>若要测试通过更改服务策略绑定的 Sentinet 冲突解决程序  
  
1. 请确保**CustomerSearch**使用 wsHttpBinding 部署的服务是否正在运行。  
  
2. 从**Nevatech.Vsb.BizTalk.Samples**示例中，打开**CustomerSearch.Search.itinerary**，选择**解析服务终结点**下**消息扩展程序**内**将邮件路由**形状，以及**关键字**属性，指定一个关键字，如**TestKeyword**。  
  
    ![分配关键字](../technical-guides/media/sentinetwp-assignkeyword.png "SentinetWP_AssignKeyword")  
  
3. 将所做的更改保存到路线，并导出该模型。 右键单击任意路线设计器图面，然后单击**导出模型**。  
  
4. 在 BizTalk Server 管理控制台中，右键单击**Microsoft.Practices.ESB**应用程序中，单击导入、，然后单击绑定。 导航到的 ESB 解析程序示例位置`<installation drive>:\Program Files\Nevatech\Sentinet BizTalk Extensions\Samples\ESB Resolver`，并打开**BizTalk.Bindings.xml**文件。 这将创建**Sentinet 要求-响应**并**Sentinet 单向**发送端口所需的示例路线。  
  
    此外，请确保所有发送端口和接收位置的**Microsoft.Practices.ESB**登记和启动 BizTalk 应用程序。  
  
5. 打开**ESB。Itinerary.Test**应用程序中，生成它，并运行它。 在启动路线测试客户端，请执行以下步骤：  
  
   1.  在路线测试客户端下, **Web 服务选项**，清除**使用 WCF 服务**，然后选择**两种方式服务**。  
  
   2.  从**服务类型**下拉列表中，选择**消息传送**。  
  
   3.  单击**负载路线**并导航到**CustomerSearch.Search.Itinerary.xml**文件中的示例项目位于**ExportedItineraries**文件夹`<installation drive>:\Program Files\Nevatech\Sentinet BizTalk Extensions\Samples\ESB Resolver\ExportedItineraries`.  
  
   4.  单击省略号按钮 (**...**) 下**负载消息**组，并导航到**CustomerSearch.Search.Request.xml**位于项目的**SampleMessages** 文件夹`<installation drive>:\Program Files\Nevatech\Sentinet BizTalk Extensions\Samples\ESB Resolver\SampleMessages`.  
  
   5.  单击**提交请求**和确认收到的响应。  
  
6. 上**CustomerSearch**对话框中，请注意，该计数器增加 1。  
  
7. 在 Sentinet 管理控制台中，更新终结点详细信息，若要使用 basicHttpBinding 替代 wsHttpBinding。  
  
   1.  选择服务终结点，请单击**详细信息**选项卡，然后依次**修改**。  
  
   2.  在中**详细信息**选项卡上，单击省略号 (**...**) 中**策略**部分中，以启动**修改策略**向导。  
  
        ![启动修改策略向导](../technical-guides/media/sentinetwp-modifypolicy-1.png "SentinetWP_ModifyPolicy_1")  
  
   3.  在第一页上，保留策略类型作为**私有**，然后单击**下一步**。  
  
   4.  在第二页上，更改**wsHttpBinding** XML 元素**basicHttpBinding** （区分大小写），然后单击**完成**。  
  
        ![更新策略绑定](../technical-guides/media/sentinetwp-modifypolicy-2.png "SentinetWP_ModifyPolicy_2")  
  
   5.  单击**保存**将更改保存到的终结点详细信息。  
  
8. 停止**CustomerSearch**服务，请从绑定更改**wsHttpBinding**到**basicHttpBinding**，然后再次启动该服务。  
  
    ![使用其他绑定重新启动服务](../technical-guides/media/sentinetwp-restartcustservice.png "SentinetWP_RestartCustService")  
  
9. 从**测试客户端路线**，再次将测试消息发送到客户搜索服务。 请注意，客户搜索服务对话框中的计数器再次增加 1。  
  
     已成功收到消息，Sentinet 管理控制台中，从后更改的详细信息返回到的策略**wsHttpBinding**。 同样，停止**客户搜索**服务、 将策略更改回为 wsHttpBinding 和启动服务。  
  
   此示例演示如何 Sentinet 存储库中的服务详细信息可以更新为目标的已更新的服务终结点而无需更改路线或客户端。  
  
#### <a name="to-test-the-sentinet-resolver-by-changing-keyword-assignments"></a>若要通过更改关键字分配测试 Sentinet 冲突解决程序  
  
1.  请确保的两个实例**CustomerSearch**使用 basicHttpBinding 和 wsHttpBinding 部署的服务是否正在运行。  
  
2.  从**Nevatech.Vsb.BizTalk.Samples**示例中，打开**CustomerSearch.Search.itinerary**，选择**解析服务终结点**下**消息扩展程序**内**将邮件路由**形状，以及**关键字**属性，指定一个关键字，如**TestKeyword**。  
  
     ![分配关键字](../technical-guides/media/sentinetwp-assignkeyword.png "SentinetWP_AssignKeyword")  
  
3.  将所做的更改保存到路线，并导出该模型。 右键单击任意路线设计器图面，然后单击**导出模型**。  
  
4.  在 BizTalk Server 管理控制台中，右键单击**Microsoft.Practices.ESB**应用程序中，单击导入、，然后单击绑定。 导航到的 ESB 解析程序示例位置`<installation drive>:\Program Files\Nevatech\Sentinet BizTalk Extensions\Samples\ESB Resolver`，并打开**BizTalk.Bindings.xml**文件。 这将创建**Sentinet 要求-响应**并**Sentinet 单向**发送端口所需的示例路线。  
  
     此外，请确保所有发送端口和接收位置的**Microsoft.Practices.ESB**登记和启动 BizTalk 应用程序。  
  
5.  打开**ESB。Itinerary.Test**应用程序中，生成它，并运行它。 在启动路线测试客户端，请执行以下步骤：  
  
    1.  在路线测试客户端下, **Web 服务选项**，清除**使用 WCF 服务**，然后选择**两种方式服务**。  
  
    2.  从**服务类型**下拉列表中，选择**消息传送**。  
  
    3.  单击**负载路线**并导航到**CustomerSearch.Search.Itinerary.xml**文件中的示例项目位于**ExportedItineraries**文件夹`<installation drive>:\Program Files\Nevatech\Sentinet BizTalk Extensions\Samples\ESB Resolver\ExportedItineraries`.  
  
    4.  单击省略号按钮 (**...**) 下**负载消息**组，并导航到**CustomerSearch.Search.Request.xml**位于项目的**SampleMessages** 文件夹`<installation drive>:\Program Files\Nevatech\Sentinet BizTalk Extensions\Samples\ESB Resolver\SampleMessages`.  
  
    5.  单击**提交请求**和确认收到的响应。  
  
6.  上**CustomerSearch**对话框中，请注意，该计数器增加 1。  
  
7.  从 Sentinet 管理控制台中，删除**TestKeyword**与关联**版本 1**的**CustomerSearch**服务并将其与**版本 2**的服务。  
  
    1.  打开 Sentinet 管理控制台中，单击**第 1 版**下**CustomerSearch**服务，单击 wsHttpBinding 终结点，然后单击**附件**选项卡，然后依次**修改**。  
  
         ![从 CustomerSearch 服务删除关键字](../technical-guides/media/sentinetwp-removekeyword.png "SentinetWP_RemoveKeyword")  
  
    2.  单击以删除关键字时，单击以前输入的关键字对按钮**是**在消息框，然后单击**保存**。  
  
         ![从 CustomerSearch 服务删除关键字](../technical-guides/media/sentinetwp-removekeyword-2.png "SentinetWP_RemoveKeyword_2")  
  
    3.  现在，将分配相同的关键字 (**TestKeyword**) 到**basicHttpBinding**下的终结点**版本 2**的同一个服务。  
  
8.  发送测试消息从重新**测试客户端路线**并请注意，这一次，此计数器递增在对话框中，表示与的 basicHttpBinding 一起部署的服务的版本 2。