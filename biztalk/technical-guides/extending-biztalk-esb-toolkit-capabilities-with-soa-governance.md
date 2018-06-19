---
title: 扩展 SOA 治理 BizTalk ESB 工具包功能 |Microsoft 文档
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
ms.openlocfilehash: f872d24c7c792d01f80463da0e3c27f31d76d8ee
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22299789"
---
# <a name="extending-biztalk-esb-toolkit-capabilities-with-soa-governance"></a>扩展 SOA 治理 BizTalk ESB 工具包功能
[!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]随[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]是一套工具和扩展的库和[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]支持松散耦合和动态的消息传递体系结构的功能。 它充当提供工具来快速中介服务与其使用者之间的中间件。 在运行时，启用最大的灵活性[!INCLUDE[esbToolkit_short](../includes/esbtoolkit-short-md.md)]简化了的服务终结点的松散耦合的组合和管理服务之间的交互。  
  
 Sentinet BizTalk 服务器扩展增强的功能[!INCLUDE[esbToolkit_short](../includes/esbtoolkit-short-md.md)]通过将它与 Sentinet，SOA 监管和适用于 Microsoft 平台的 API 管理软件解决方案集成。 第一版 Sentinet[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]扩展提供[!INCLUDE[esbToolkit_short](../includes/esbtoolkit-short-md.md)]SOA 存储库冲突解决程序，与 BizTalk Server 2013 集成[!INCLUDE[esbToolkit_short](../includes/esbtoolkit-short-md.md)]，和 Visual Studio 2012。  
  
 有关如何此白皮书谈话 Sentinet SOA 冲突解决程序扩展[!INCLUDE[esbToolkit_short](../includes/esbtoolkit-short-md.md)]功能，如何配置 Sentinet SOA 冲突解决程序，和最后一个示例演示如何使用 Sentinet SOA 冲突解决程序。  
  
## <a name="esb-toolkit-and-sentinet-soa-resolver"></a>ESB 工具包和 Sentinet SOA 冲突解决程序  
 除了别的之外 ESB 工具包解析程序必须提供以下功能：  
  
-   运行时解析服务终结点以及它们的配置  
  
-   BizTalk ESB 松散耦合的消息传送解决方案。  
  
 Sentinet 提供一个强健和全面[SOA 存储库](http://www.nevatech.com/sentinet/soa-repository)SOA 集成解决方案，以及高级 SOA 监管和运行时提供管理功能。 结合 Sentinet SOA 存储库，Sentinet SOA 冲突解决程序提供[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]ESB 体系结构使用高级且易于使用 ESB 配置、 动态的邮件路由，和消息安全实现功能。  
  
 下面一个高级图示显示如何 Sentinet SOA 冲突解决程序配合[!INCLUDE[esbToolkit_short](../includes/esbtoolkit-short-md.md)]体系结构。  
  
 ![使用 BizTalk ESB 工具包 Sentinet](../technical-guides/media/sentinetwp-arch.png "SentinetWP_Arch")  
  
 在运行时，**终结点解析和路由**组件图 （这是 ESB 工具包冲突解决程序框架的一部分） 中使用 （在 Visual Studio 路线设计器中创建） 的路线文档来实例化特定冲突解决程序，并请求冲突解决程序提供服务终结点和其配置。 路线本身必须具有到服务终结点，引用进行配置以便解析程序可使用此引用中的注册表或存储库中找到请求的终结点。 在设计时 （路线创建） 时，不已知的服务终结点的实际物理地址，且既不是服务要求的安全策略。 在稍后阶段，运行时使用的 ESB 工具包解析服务终结点配置关闭负载增加动态发送端口将消息发送到与所需的服务的安全设置的实际物理服务地址。 如果服务终结点地址、 通信协议、 或安全要求更改仅注册表/存储库配置已更新。 ESB 或 BizTalk 服务器项目的运行时配置不需要进行更新。  
  
## <a name="how-does-the-sentinet-resolver-add-value-to-an-esb-toolkit-application"></a>如何 Sentinet 冲突解决程序未向 ESB 工具包应用程序添加值？  
 SOA 存储库以及使用 Sentinet 解析程序的两个主要优点有：  
  
-   将客户端标识分配给已解析的外部服务终结点 – 大多数情况下，解决的 ESB 终结点需要特定的客户端标识来调用外部服务 （如用户名/密码、 特定 Windows 帐户凭据或特定 X.509证书）。 这是很常见的安全要求，这不由其他 ESB 冲突解决程序/注册表适当地处理。  
  
-   将访问限制为安全信息 – 若要解决以前的限制，其他冲突解决程序可以使用手动配置 Tmodel 包括具有所需的安全标识的复杂 XML。 但是，注册表/存储库的一部分保存的安全信息不是正确的做法。 这提供了服务使用者轻松访问的安全详细信息，例如用户名、 密码等来访问服务。  
  
 Sentinet 解析程序和 Sentinet SOA 存储库提供了灵活地对功能并安全地将任何特定的客户端标识分配给通过标准或自定义 WCF 终结点行为的解析 ESB 终结点。 Sentinet 从而实现此目的使用的安全信息配置 Sentinet 冲突解决程序，并不 Sentinet SOA 存储库。 使用此 Sentinet 冲突解决程序配置的所有客户端凭据以加密形式存储。  
  
 除此之外，以下是一些使用 Sentinet 解析器和 Sentinet SOA 存储库的其他好处。  
  
-   可提供全面的 SOA 存储库。 存储库提供了服务元数据内容、 服务标识和访问策略，支持服务版本，等等。  
  
-   易于通过上载服务 WSDL Sentinet 注册表中注册物理服务。  
  
-   全面且易于使用 Sentinet 管理控制台。 控制台提供对所有服务元数据的管理访问权限和项目，与简单用户界面到访问服务操作其数据架构、 服务终结点、 安全策略，等等。  
  
-   管理和配置为解析终结点的自定义行为。 Sentinet 冲突解决程序提供的解析终结点的完全可自定义且易于配置的终结点行为。  
  
-   若要使用不同的搜索条件配置 Sentinet 解析程序的选项。 路线可以定义分配给服务终结点，任何关键字，或使用指向存储库服务层次结构中的服务的服务路径。  
  
-   测试功能的高级解析程序。 Sentinet 解析程序配置可以直接从 Visual Studio 路线设计器进行测试。 虽然其他冲突解决程序只能提供有关终结点的基本属性的信息，Sentinet 冲突解决程序提供了有关解析终结点的扩展的信息。 终结点的基本属性，除了 Sentinet 解析程序将显示标识的属性解析 Sentinet 储存库中的服务和终结点的位置。 路线设计器可以测试如何 Sentinet 冲突解决程序和其不同的搜索条件影响解析结果之前在运行时使用自身的路线。  
  
## <a name="installing-the-sentinet-biztalk-server-extensions"></a>安装 Sentinet BizTalk 服务器扩展  
 你可以下载并安装与中的 Sentinet BizTalk 扩展[此处](http://www.nevatech.com/download)。 安装扩展安装 ESB 工具包、 文档和有关如何使用扩展的示例适用于 Sentinet 解析程序。  
  
 详细介绍如何安装和配置 Sentinet BizTalk Server 扩展的文档可作为产品下载的一部分。  
  
## <a name="using-the-sentinet-biztalk-server-extensions"></a>使用 Sentinet BizTalk 服务器扩展  
 在本部分中，我们了解如何使用 Sentinet BizTalk Server 扩展和展示上面提到的功能。  
  
### <a name="prerequisites"></a>先决条件  
 在本白皮书中的说明假定你具备以下条件安装和配置：  
  
-   Visual Studio 2012。  
  
-   BizTalk Server 2013。 有关说明，请参阅[安装 BizTalk Server 2013](http://msdn.microsoft.com/library/jj248688\(v=bts.80\).aspx)。  
  
-   BizTalk Server ESB 工具包。 有关说明，请参阅[安装和配置 Microsoft BizTalk ESB 工具包](http://msdn.microsoft.com/library/jj684558\(v=bts.80\).aspx)。  
  
-   Sentinet BizTalk 服务器扩展。 有关说明，请参阅提供的文档提供产品下载的一部分[此处](http://www.nevatech.com/download)。  
  
### <a name="register-a-web-service"></a>注册 web 服务  
 由 Sentinet 基础结构管理的 web 服务必须在存储库中注册。 本白皮书 Sentinet 安装包中使用提供的是一个 WCF 客户搜索示例服务。  
  
1.  启动**客户搜索**示例安装 Sentinet 安装包的服务。 启动以管理员身份的客户搜索示例中，选择策略绑定 (例如**wsHttpBinding**)，然后单击**启动**。  
  
2.  服务运行后，单击**视图 Wsdl**链接以打开浏览器使用服务元数据 URL 和服务的 WSDL。 从浏览器地址栏复制元数据 URL。  
  
3.  打开浏览器并输入 URL (`https://[computer-name]/sentinet`) 以启动 Sentinet 管理控制台。 登录名和选择**存储库**中的根元素**存储库**视图面板。 右键单击**存储库**根元素，并单击**添加 > 服务 > SOAP**菜单选项。  
  
4.  在**添加服务**对话框中，为**从 URL 的 WSDL**选项，粘贴你在更早版本，复制的服务元数据 URL，然后单击**下一步**。  
  
     ![添加服务 URL](../technical-guides/media/sentinetwp-addserviceurl.png "SentinetWP_AddServiceURL")  
  
5.  向导将启动下载服务元数据。 下载完成后，向导将显示 Web 服务树状结构。 提供服务的名称，然后单击**完成**服务元数据上载到 Sentinet 存储库。  
  
     ![Web 服务结构](../technical-guides/media/sentinetwp-servicestructure.png "SentinetWP_ServiceStructure")  
  
6.  服务是作为导入到存储库版本 1。 选择的版本，然后选择终结点。 在**终结点详细信息**窗格的底部，单击**附件**选项卡上，并依次**修改**。  
  
     ![修改服务终结点](../technical-guides/media/sentinetwp-serviceendpoint.png "SentinetWP_ServiceEndpoint")  
  
7.  在终结点详细信息选项卡，单击 (**+**) 针对登录**关键字**，输入与该终结点相关联的关键字 (例如， **TestKeyword**)，和然后单击**保存**。 关键字用作终结点标记 （或标识符） 的 SOA 存储库中。  
  
     ![指定的关键字](../technical-guides/media/sentinetwp-enterkeyword.png "SentinetWP_EnterKeyword")  
  
 重复上述步骤以添加新版本的**CustomerSearch**服务，但具有不同的绑定，例如**basicHttpBinding**。 稍后在本白皮书中，我们将演示如何 Sentinet 冲突解决程序可以解析为不同的服务 （或相同服务的不同版本） 只需通过将关联到服务终结点的搜索关键字。  
  
### <a name="configure-sentinet-resolver"></a>配置 Sentinet 冲突解决程序  
 本部分说明如何在简单 BizTalk ESB 路线设计器项目中，配置 Sentinet 冲突解决程序以及特别是如何使用关键字来唯一地解析的服务终结点。 本部分还演示如何测试从 Visual Studio 本身，而不包含所有 ESB 消息的都发送的解析程序。  
  
1.  启动 Visual Studio 并创建**BizTalk ESB 路线设计器**项目。  
  
2.  在解决方案资源管理器中，双击路线在路线设计器中打开它。  
  
3.  从工具箱拖放**路线服务**设计器图面上的形状。  
  
4.  选择**路线服务**调整和更改**路线服务扩展程序**属性**消息传送扩展程序**从下拉列表。  
  
     ![设置消息扩展程序属性](../technical-guides/media/sentinetwp-setmessageextender.png "SentinetWP_SetMessageExtender")  
  
5.  右键单击**冲突解决程序**中的元素**路线服务**的形状，然后单击**添加新解析程序**。  
  
     ![添加新的解析程序](../technical-guides/media/sentinetwp-addnewresolver.png "SentinetWP_AddNewResolver")  
  
6.  选择新的冲突解决程序元素，将其重命名 (例如， **MyResolver**)，和有关**解析程序实现**属性中，选择**Sentinet 冲突解决程序扩展**。  
  
     ![设置解析程序实现](../technical-guides/media/sentinetwp-addresolverimplementation.png "SentinetWP_AddResolverImplementation")  
  
7.  指定**操作**和**关键字**Sentinet 冲突解决程序扩展的属性。 我们将使用这些属性将唯一地解析为我们前面添加到 Sentinet 存储库的服务。 有其他属性也可以指定为 Sentinet 冲突解决程序扩展。 若要了解有关这些属性的详细信息，请参阅 Sentinet BizTalk 扩展用户指南。  
  
    |属性|Description|  
    |--------------|-----------------|  
    |操作|消息唯一地标识而调用的服务操作的操作标头。 此操作标头是服务 WSDL 的一部分，可以找到在服务的 WSDL，或从 Sentinet 管理控制台用户界面 （在下操作的请求消息属性。|  
    |关键字|提供关键字 (例如**TestKeyword**) 分配给 Sentinet 管理控制台中的服务。|  
  
     以下屏幕截图显示为指定的操作和关键字属性**MyResolver**配置。  
  
     ![Sentinet Resolvery 配置](../technical-guides/media/sentinetwp-resolverconfig.png "SentinetWP_ResolverConfig")  
  
8.  将更改保存到配置。  
  
#### <a name="advanced-resolver-configuration"></a>高级解析程序配置  
 Sentinet BizTalk 扩展配置应用程序修改**Sentinet.BizTalk.config**位于包安装文件夹的根目录中的文件 (默认位置是`<installation drive>:\Program Files\Nevatech\Sentinet BizTalk Extensions\Sentinet.BizTalk.config`)。 可以修改该文件以外部**Sentinet BizTalk 扩展配置**应用程序以提供高级的配置选项。 例如，在许多实际 ESB 方案解析终结点必须使用服务终结点地址和绑定，不仅能还与特定客户端标识 （用户名/密码、 特定 Windows 帐户凭据或 X.509 客户端提供证书）。 如果正确的客户端标识，没有 ESB 关闭负载增加发送端口无法调用外部服务。 Sentinet 冲突解决程序允许路线开发人员分配提供合适的客户端终结点标识的特定终结点行为。 多个终结点行为可以是预配置为标准中的 WCF 终结点行为**Sentinet.BizTalk.config**文件，然后特定终结点行为可以在从 Sentinet 冲突解决程序路线的情况下引用通过指定名称的行为的配置**解析终结点行为**属性。  
  
### <a name="test-the-resolver-configuration"></a>测试解析程序配置  
 Sentinet 解析程序配置由指定的相关属性值后，你可以测试从 Visual Studio 本身的冲突解决程序。  
  
1.  在设计图面上，右键单击你添加到此 Sentinet 冲突解决程序**路线服务**形状，并依次**测试解析程序配置**。  
  
     输出窗格中显示测试结果，其中摘要是类似于下面所示：  
  
    ```  
    ***** Resolved Service Endpoint *****  
  
    Service Path and Name          : /CustomerSearch  
    Service Id                     : 2b6d686a-cae1-4b7b-93da-99affef98478  
    Service Version                : 1  
    Endpoint Name                  : WSHttpBinding_ICustomerSearch  
    Endpoint Address               : http://btscloudcar/CustomerSearch/1  
    ```  
  
     请注意，冲突解决程序返回的终结点**CustomerSearch**服务**版本 1**到搜索条件 (**TestKeyword**) 连接。  
  
2.  删除**TestKeyword**与关联**版本 1**的**CustomerSearch**服务并将其与服务的第二个版本的终结点相关联。  
  
    1.  打开 Sentinet 管理控制台，单击**版本 1**下**CustomerSearch**服务，单击 wsHttpBinding 的终结点，，然后单击**附件**选项卡上，并依次**修改**。  
  
         ![从 CustomerSearch 服务中删除关键字](../technical-guides/media/sentinetwp-removekeyword.png "SentinetWP_RemoveKeyword")  
  
    2.  单击针对你输入之前删除关键字，请单击关键字按钮**是**在消息框中，然后单击**保存**。  
  
         ![从 CustomerSearch 服务中删除关键字](../technical-guides/media/sentinetwp-removekeyword-2.png "SentinetWP_RemoveKeyword_2")  
  
    3.  现在，将分配同一关键字 (**TestKeyword**) 到**basicHttpBinding**终结点下的**版本 2**同一服务。  
  
3.  返回到 Visual Studio 和测试的解析程序配置。 右键单击你添加到此 Sentinet 冲突解决程序**路线服务**形状，并依次**测试解析程序配置**。  
  
     输出窗格中显示测试结果，其中摘要是类似于下面所示：  
  
    ```  
    ***** Resolved Service Endpoint *****  
  
    Service Path and Name          : /CustomerSearch  
    Service Id                     : 5b9e5878-7016-44ab-9f0e-5282a8c3e508  
    Service Version                : 2  
    Endpoint Name                  : BasicHttpBinding_ICustomerSearch  
    Endpoint Address               : http://btscloudcar/CustomerSearch/2  
    ```  
  
4.  请注意如何解析程序现在返回的详细信息**版本 2**的服务即使你未更改任何内容 ESB 路线应用程序中。  
  
 分配关键字 (**TestKeyword**) 返回到服务的版本 1 (与**WSHttpBinding**终结点)。  
  
## <a name="using-the-sentinet-biztalk-server-extensions"></a>使用 Sentinet BizTalk 服务器扩展  
 在本部分中，我们将介绍了如何使用 Sentinet BizTalk 扩展，以及 ESB 冲突解决程序，来唯一标识服务，并且将发送到该服务，只需极少的消息或不需要更改路由到服务或客户端发送消息。 我们将测试两个方案：  
  
-   向服务注册 Sentinet 存储库中 （使用附加关键字） 发送的示例消息。 然后，更改使用 Sentinet 管理控制台的服务的策略绑定并发送另一个示例消息。 此方案演示如何更改服务的安全策略都不会影响客户端应用程序也不 ESB 路线。  
  
-   在 Sentinet 存储库中注册 （使用附加的关键字） 的服务终结点发送的示例消息。 然后，将使用同一关键字附加到另一个版本的相同的服务，并再次发送消息。 此方案演示如何自动附加到不同的服务版本的关键字将消息路由到新的服务版本。  
  
 若要测试这些方案，我们将使用下面的示例：  
  
-   **客户搜索服务**提供与 Sentinet 安装程序。 可以从开始菜单启动此服务。  
  
-   **Nevatech.Vsb.BizTalk.Samples**与 Sentinet 安装程序提供解决方案。 此示例位于`<installation drive>:\Program Files\Nevatech\Sentinet BizTalk Extensions\Samples`。  
  
-   ESB。Itinerary.Test 示例附带[!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]。 这是在`<install drive>:\Program Files (x86)\Microsoft BizTalk ESB Toolkit\ESBSource.zip\Source\Samples\Itinerary\Source\ESB.Itinerary.Test`和用于测试对客户搜索服务的示例消息。  
  
#### <a name="to-test-the-sentinet-resolver-by-changing-the-service-policy-binding"></a>若要通过更改服务策略绑定测试 Sentinet 冲突解决程序  
  
1.  请确保**CustomerSearch**与 wsHttpBinding 一起部署的服务正在运行。  
  
2.  从**Nevatech.Vsb.BizTalk.Samples**示例中，打开**CustomerSearch.Search.itinerary**，选择**解决服务终结点**下**消息扩展程序**内**将邮件路由**形状，并为**关键字**属性，指定一个关键字，如**TestKeyword**。  
  
     ![分配关键字](../technical-guides/media/sentinetwp-assignkeyword.png "SentinetWP_AssignKeyword")  
  
3.  将所做的更改保存到路线，并导出模型。 右键单击任意位置路线设计器图面，然后单击**导出模型**。  
  
4.  在 BizTalk Server 管理控制台中，右键单击**Microsoft.Practices.ESB**应用程序中，单击导入，，然后单击绑定。 导航到 ESB 冲突解决程序示例位置`<installation drive>:\Program Files\Nevatech\Sentinet BizTalk Extensions\Samples\ESB Resolver`，并打开**BizTalk.Bindings.xml**文件。 这将创建**Sentinet 请求-响应**和**Sentinet 单向**发送示例路线所需的端口。  
  
     此外，请确保所有发送端口和接收位置**Microsoft.Practices.ESB** BizTalk 应用程序是登记和启动。  
  
5.  打开**ESB。Itinerary.Test**应用程序中，生成它，并运行它。 在启动路线测试客户端，请执行以下步骤：  
  
    1.  在路线测试客户端下, **Web 服务选项**，清除**使用 WCF 服务**，然后选择**两个方式服务**。  
  
    2.  从**服务类型**下拉列表中，选择**消息**。  
  
    3.  单击**负载路线**并导航到**CustomerSearch.Search.Itinerary.xml**示例项目中位于文件**ExportedItineraries** 文件夹`<installation drive>:\Program Files\Nevatech\Sentinet BizTalk Extensions\Samples\ESB Resolver\ExportedItineraries`.  
  
    4.  单击省略号按钮 (**...**) 下**负载消息**组并导航到**CustomerSearch.Search.Request.xml**位于项目的**SampleMessages** 文件夹`<installation drive>:\Program Files\Nevatech\Sentinet BizTalk Extensions\Samples\ESB Resolver\SampleMessages`.  
  
    5.  单击**提交请求**和验证收到的响应。  
  
6.  上**CustomerSearch**对话框中，请注意，该计数器加一。  
  
7.  在 Sentinet 管理控制台中，更新来代替 wsHttpBinding basicHttpBinding 的终结点详细信息。  
  
    1.  选择服务终结点，单击**详细信息**选项卡上，并依次**修改**。  
  
    2.  在**详细信息**选项卡上，单击省略号 (**...**) 中**策略**部分，若要启动**修改策略**向导。  
  
         ![启动修改策略向导](../technical-guides/media/sentinetwp-modifypolicy-1.png "SentinetWP_ModifyPolicy_1")  
  
    3.  在第一页上，保留策略类型作为**私有**，然后单击**下一步**。  
  
    4.  在第二个页面上，更改**wsHttpBinding** XML 元素**basicHttpBinding** （区分大小写），然后单击**完成**。  
  
         ![正在更新策略绑定](../technical-guides/media/sentinetwp-modifypolicy-2.png "SentinetWP_ModifyPolicy_2")  
  
    5.  单击**保存**将更改保存到的终结点详细信息。  
  
8.  停止**CustomerSearch**服务，将更改从绑定**wsHttpBinding**到**basicHttpBinding**，然后再次启动该服务。  
  
     ![使用不同的绑定重新启动服务](../technical-guides/media/sentinetwp-restartcustservice.png "SentinetWP_RestartCustService")  
  
9. 从**测试路线客户端**，再次将一条测试消息发送到客户搜索服务。 请注意客户搜索服务对话框中的计数器就会再次递增 1。  
  
     一旦成功收到消息，则从 Sentinet 管理控制台中，更改的策略详细信息回**wsHttpBinding**。 同样，停止**客户搜索**服务，将策略更改回 wsHttpBinding 并启动服务。  
  
 此示例演示如何 Sentinet 存储库中的服务详细信息可以更新为目标的更新的服务终结点而无需更改路线或客户端。  
  
#### <a name="to-test-the-sentinet-resolver-by-changing-keyword-assignments"></a>若要通过更改关键字分配测试 Sentinet 冲突解决程序  
  
1.  请确保两个实例**CustomerSearch**使用 wsHttpBinding 和 basicHttpBinding 部署的服务是否正在运行。  
  
2.  从**Nevatech.Vsb.BizTalk.Samples**示例中，打开**CustomerSearch.Search.itinerary**，选择**解决服务终结点**下**消息扩展程序**内**将邮件路由**形状，并为**关键字**属性，指定一个关键字，如**TestKeyword**。  
  
     ![分配关键字](../technical-guides/media/sentinetwp-assignkeyword.png "SentinetWP_AssignKeyword")  
  
3.  将所做的更改保存到路线，并导出模型。 右键单击任意位置路线设计器图面，然后单击**导出模型**。  
  
4.  在 BizTalk Server 管理控制台中，右键单击**Microsoft.Practices.ESB**应用程序中，单击导入，，然后单击绑定。 导航到 ESB 冲突解决程序示例位置`<installation drive>:\Program Files\Nevatech\Sentinet BizTalk Extensions\Samples\ESB Resolver`，并打开**BizTalk.Bindings.xml**文件。 这将创建**Sentinet 请求-响应**和**Sentinet 单向**发送示例路线所需的端口。  
  
     此外，请确保所有发送端口和接收位置**Microsoft.Practices.ESB** BizTalk 应用程序是登记和启动。  
  
5.  打开**ESB。Itinerary.Test**应用程序中，生成它，并运行它。 在启动路线测试客户端，请执行以下步骤：  
  
    1.  在路线测试客户端下, **Web 服务选项**，清除**使用 WCF 服务**，然后选择**两个方式服务**。  
  
    2.  从**服务类型**下拉列表中，选择**消息**。  
  
    3.  单击**负载路线**并导航到**CustomerSearch.Search.Itinerary.xml**示例项目中位于文件**ExportedItineraries** 文件夹`<installation drive>:\Program Files\Nevatech\Sentinet BizTalk Extensions\Samples\ESB Resolver\ExportedItineraries`.  
  
    4.  单击省略号按钮 (**...**) 下**负载消息**组并导航到**CustomerSearch.Search.Request.xml**位于项目的**SampleMessages** 文件夹`<installation drive>:\Program Files\Nevatech\Sentinet BizTalk Extensions\Samples\ESB Resolver\SampleMessages`.  
  
    5.  单击**提交请求**和验证收到的响应。  
  
6.  上**CustomerSearch**对话框中，请注意，该计数器加一。  
  
7.  从 Sentinet 管理控制台中，删除**TestKeyword**与关联**版本 1**的**CustomerSearch**服务并将其与**版本 2**的服务。  
  
    1.  打开 Sentinet 管理控制台，单击**版本 1**下**CustomerSearch**服务，单击 wsHttpBinding 的终结点，，然后单击**附件**选项卡上，并依次**修改**。  
  
         ![从 CustomerSearch 服务中删除关键字](../technical-guides/media/sentinetwp-removekeyword.png "SentinetWP_RemoveKeyword")  
  
    2.  单击针对你输入之前删除关键字，请单击关键字按钮**是**在消息框中，然后单击**保存**。  
  
         ![从 CustomerSearch 服务中删除关键字](../technical-guides/media/sentinetwp-removekeyword-2.png "SentinetWP_RemoveKeyword_2")  
  
    3.  现在，将分配同一关键字 (**TestKeyword**) 到**basicHttpBinding**终结点下的**版本 2**同一服务。  
  
8.  发送测试消息再次从**测试路线客户端**，请注意，此时，计数器将递增表示使用 basicHttpBinding 部署的服务的版本 2 的对话框中。