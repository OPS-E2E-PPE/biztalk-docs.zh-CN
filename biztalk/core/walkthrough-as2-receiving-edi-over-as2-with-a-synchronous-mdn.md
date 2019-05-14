---
title: 演练 (AS2):使用同步 MDN 通过 AS2 接收 EDI |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 0b63395f-03f4-45e8-a68a-9bbbd8dfa344
caps.latest.revision: 53
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 4486a45acb9d5a6fd9ed67ca23fa503e41b1d27c
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65320753"
---
# <a name="walkthrough-as2-receiving-edi-over-as2-with-a-synchronous-mdn"></a>演练 (AS2):使用同步 MDN 通过 AS2 接收 EDI
本演练介绍创建通过 AS2 传输，返回异步 Mdn 接收 EDI 消息的解决方案的一组的分步过程。  

## <a name="prerequisites"></a>先决条件  
 以下是执行本主题中的过程的先决条件：  

- 必须以成员的身份登录[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理员或[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]B2B Operators 组。  

- 运行此演练的计算机必须具有 Internet 信息服务 (IIS) 7 安装。  

- 如果使用 64 位版本的 Windows 安装运行此演练的计算机，则必须确保 BizTalk 主机仅标记为 32 位。 此外必须确保 IIS 已启用 32 位应用程序设置，应用程序池设置为 **，则返回 True**。 有关详细信息，请参阅[教程 3:AS2 教程](../core/tutorial-3-as2-tutorial.md)。  

## <a name="how-the-solution-receives-an-edias2-message-and-returns-a-synchronous-mdn"></a>该解决方案如何接收 EDI/AS2 消息并返回同步 MDN  
 该解决方案将执行以下操作：  

1. 接收一个 AS2 消息，其中包含 EDI 从贸易合作伙伴 Fabrikam 通过 HTTP 交换并对来自 ediint/as2 的交换进行解码。  

   > [!NOTE]
   >  显示的顺序可能不是此列表中的事件。  

2. 返回同步 MDN 给贸易合作伙伴使用请求-响应接收端口。  

3. 将 EDI 格式的交换转换为内部 XML 格式，并将其放入 MessageBox。  

4. 具有 PassThruTransmit 管道的 FILE 发送端口提取消息 XML 文件。  

5. 发送端口将 EDI 交换 XML 文件发送到 Contoso 参与方的文件夹。  

   下图显示了此解决方案的体系结构。  

   ![使用同步 MDN 的 AS2 接收](../core/media/4ff20070-1c36-42e5-af14-832771d63b88.gif "4ff20070-1c36-42e5-af14-832771d63b88")  

## <a name="the-functionality-in-this-solution"></a>此解决方案中的功能  
 以下内容适用于本演练的功能：  

-   不会生成 EDI 确认。 生成 EDI 确认进行了演示[演练 (X12):接收 EDI 交换并发送回确认](../core/walkthrough-x12--receive-edi-interchanges-and-send-back-an-acknowledgement.md)。 中介绍了通过 AS2 传输发送 EDI 确认[演练 (AS2):使用同步 MDN 通过 AS2 发送 EDI](../core/walkthrough-as2-sending-edi-over-as2-with-a-synchronous-mdn.md)。  

-   该解决方案专用于使用 X12 编码而不是 EDIFACT 交换编码。  

    > [!NOTE]
    >  用于 EDIFACT 编码的配置是近与用于 X12 编码。  

-   将传入交换上执行 EDI 类型和扩展的验证。  

-   将启用 AS2 和 EDI 报告，并保存事务集以从交换状态报告进行查看。  

-   此解决方案不会在不可否认数据库中配置签名、 压缩、 加密或消息存储。 有关配置这些属性的过程，请参阅[配置 AS2 属性](../core/configuring-as2-properties.md)。  

## <a name="configuring-and-testing-the-walkthrough"></a>配置和测试演练  
 此解决方案所需的过程包括：  

- 生成和部署具有必需的消息架构，使架构可供使用的 BizTalk 项目[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]中处理收到的交换。  

- 启用接收 AS2 消息中使用的 BTS ISAPI 筛选器。  

- 创建一个用于从 Fabrikam 接收 AS2 消息的 Contoso 虚拟目录，如接收位置中的配置。  

- 指定 Contoso 虚拟目录不由 Windows SharePoint Services 托管。  

- 创建一个静态双向 HTTP 接收端口[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]以接收包含 EDI 交换的贸易合作伙伴的 AS2 消息并发送 MDN 响应。 接收管道配置为 AS2EDIReceive 管道和发送管道为 AS2Send 管道。  

- 创建静态单向 FILE 发送端口以将 （采用 XML 格式） 的 EDI 负载路由到本地文件夹。 创建本地文件夹。  

- 为 Fabrikam 和 Contoso 创建参与方 （贸易合作伙伴）。  

- 为这两个贸易参与方创建业务配置文件每个。  

- 创建 AS2 协议的业务配置文件，Fabrikam 和 Contoso 之间。 包含属性，以发送 AS2 消息，且接收返回同步 MDN 的 AS2 协议。  

- 创建 X12 协议的业务配置文件，Fabrikam 和 Contoso 之间接收 X12 消息。  

- AS2 教程文件中通过附带的 HTTP 发送方实用工具中测试解决方案。 此实用程序将发送一个测试通过 AS2 传输 (X12_00401_864-Sync.edi，还随附在 AS2 教程) 包含有 EDI 交换的 AS2 消息。 您必须修改 HTTP 发件人和测试消息从本教程中的版本。 这些更改相关的以下各节所述。  

### <a name="configuring-the-walkthrough"></a>配置演练  
 本部分介绍配置本演练的步骤。  

##### <a name="to-deploy-the-message-schema"></a>若要部署的消息架构  

1. 在中[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]，打开项目[!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]SDK\AS2 Tutorial\Schemas\Schemas.btproj。  

   > [!NOTE]
   >  此 AS2 教程附带的项目包括一个 864 架构以与测试消息一起使用。  

   > [!NOTE]
   >  本主题假定你已从对 BizTalk EDI 应用程序，其中包含 EDI 架构、 管道和业务流程应用程序中添加了一个引用。 如果没有，请参阅[如何添加对 BizTalk Server EDI 应用程序的引用](http://msdn.microsoft.com/library/7af066fb-372f-4709-b566-c8d6b4a9d782)。  

2. 右键单击**架构**项目在解决方案资源管理器，并单击**属性**。 单击**签名**选项卡在项目设计器中，检查**程序集签名**复选框，并从下拉列表中选择**新建**并提供所需的值来创建强名称密钥文件。 保存所做的更改并关闭项目属性窗口。  

3. 生成并部署 Schemas.btproj。  

##### <a name="to-enable-the-bts-isapi-filter"></a>若要启用 BTS ISAPI 筛选器  

1. 单击**启动**，依次指向**所有程序**，指向**管理工具**，然后单击**Internet Information Services (IIS) Manager**.  

   > [!TIP]
   >  根据操作系统，管理工具启动菜单选项可能不可用。 在这种情况下，单击**启动**，单击**运行**，然后输入`inetmgr`打开 Internet 信息服务 (IIS) 管理器。  

2. 选择根 Web 服务器条目并在**功能视图**，双击**处理程序映射**，然后在**操作**窗格中，单击**添加脚本映射**.  

   > [!NOTE]
   >  在 Web 服务器级别配置的脚本映射将导致此映射应用于所有子网站。 如果你想要将映射限制到特定的网站或虚拟文件夹，选择文件夹而不是 Web 服务器的目标站点。  

3. 在中**添加脚本映射**对话框框中，输入`BtsHttpReceive.dll`中**请求路径**字段。  

4. 在中**可执行文件**字段中，单击**省略号 （...）** 按钮并浏览到[!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]HttpReceive。 选择 BtsHttpReceive.dll，然后单击**确定**。  

5. 输入`BizTalk HTTP Receive`中**名称**字段，，然后单击**请求限制**。  

6. 在中**请求限制**对话框中，选择**谓词**选项卡，然后选择**以下谓词之一**。 输入`POST`作为谓词。  

7. 上**访问**选项卡上，选择**脚本**，然后单击**确定**。  

8. 单击**确定**并在提示是否允许 ISAPI 扩展，请单击**是**。  

##### <a name="to-configure-the-contoso-web-page"></a>若要配置 Contoso 网页  

1. 在 IIS 管理器中，右键单击**应用程序池**，然后选择**添加应用程序池**。  

2. 在中**添加应用程序池**对话框框中，输入**BizTalkAppPool**中**名称**，然后选择 **.NET Framework V4.0.30210**中 **.NET framework 版本**下拉列表中。 单击“确定” 。  

   > [!NOTE]
   >  版本号可能会有所不同，具体取决于版本的[!INCLUDE[netfx40_short](../includes/netfx40-short-md.md)]在计算机上安装。  

3. 选择**应用程序池**，在功能视图中，选择**BizTalkAppPool**，然后单击**高级设置**中**操作**窗格。  

4. 在中**高级设置**对话框中，选择**标识**，然后单击**省略号 （...）** 按钮。  

5. 在中**应用程序池标识**对话框中，选择**自定义帐户**，然后单击**设置**。  

6. 输入**用户名**并**密码**是 administrators 组的成员的用户帐户，请输入中的密码**确认密码**，然后单击**确定**三次以返回到 IIS 管理器。  

7. 在 IIS 管理器中，打开**站点**文件夹。 右键单击**Default Web Site**节点，并选择**添加应用程序**。  

8. 在中**添加应用程序**对话框框中，输入**Contoso**中**别名**文本框中，，然后单击**选择**。  

9. 在中**选择应用程序池**对话框中，选择**BizTalkAppPool**然后单击**确定**。  

10. 有关**物理路径**，单击**省略号 （...）** 按钮并浏览到[!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]HttpReceive。  

11. 单击**测试设置**并验证是否没有显示在错误**测试连接**对话框。 单击 **“关闭”**，然后单击 **“确定”**。  

12. 在 IIS 管理器中，选择 Contoso 虚拟目录并在**功能视图**，双击**身份验证**。  

13. 在中**身份验证**页上，选择**匿名身份验证**，并验证**状态**是**已启用**。 如果**状态**是**禁用**，单击**启用**中**操作**窗格。  

##### <a name="to-specify-that-your-virtual-directory-is-not-managed-by-windows-sharepoint-services"></a>若要指定虚拟目录不由 Windows SharePoint Services 托管  

1.  如果您的计算机上安装 Windows SharePoint Services，请单击**启动**，依次指向**所有程序**，指向**管理工具**，然后单击**SharePoint 3.0 管理中心**。  

    > [!NOTE]
    >  如果您设置演练了在同一台计算机上安装 Windows SharePoint 服务器，则需要此过程。 在这种情况下，必须指定 IIS 虚拟目录未正在由 Windows SharePoint Server 托管。  

2.  上**Central Administration**页面上，在**管理中心**，单击**应用程序管理**。  

3.  上**应用程序管理**页上，单击**定义管理路径**。  

4.  中**定义管理路径**页面上，在**添加新路径**，然后在**路径**文字框中，输入**Contoso**。 下**类型**，单击**排除的路径**，然后单击**确定**。  

##### <a name="to-create-a-receive-port-to-receive-the-edi-over-as2-message-and-return-an-mdn"></a>若要创建用于通过 AS2 消息接收 EDI 并返回 MDN 的接收端口  

1. 在中[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理控制台中，右键单击**接收端口**节点下的**BizTalk Application 1**节点，指向**新建**，然后单击**请求-响应接收端口**。  

2. 接收端口的名称，然后单击**接收位置**在控制台树中。  

3. 单击 **“新建”**。  

4. 名称的接收位置，选择**HTTP**有关**类型**，然后单击**配置**。  

5. 有关**虚拟目录和 ISAPI 扩展**，输入`/Contoso/BTSHTTPReceive.dll`。  

6. 选择**挂起失败的请求**复选框，然后单击**确定**。  

7. 有关**接收管道**，选择**AS2EDIReceive**。  

8. 有关**发送管道**，选择**AS2Send**。  

9. 单击**确定**，然后单击**确定**试。  

10. 在中**接收位置**窗格中的 BizTalk Server 管理控制台中，右键单击该接收位置，并单击**启用**。  

##### <a name="to-create-a-send-port-to-send-the-edi-payload-to-a-local-folder"></a>若要创建发送端口以将 EDI 负载发送到本地文件夹  

1. 在 Windows 资源管理器，创建名为的本地文件夹**EDI_to_Contoso**用于接收 EDI 负载。  

2. 在中[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理控制台中，右键单击**发送端口**，依次指向**新建**，然后单击**静态单向发送端口**。  

3. 在中**发送端口属性**对话框框中，将发送端口，例如， **Send_Payload**。 选择**文件**有关**类型**，然后单击**配置**。  

4. 在中**FILE 传输属性**对话框中，对于**目标文件夹**，浏览到并选择**EDI_to_Contoso**步骤 1 中创建的文件夹。 将保留**文件名**作为 **%MessageID%.xml**。 单击“确定” 。  

5. 有关**发送管道**下拉列表中，接受默认**PassThruTransmit**。  

6. 单击**筛选器**在控制台树中。 有关**属性**，输入**BTS。MessageType**。 有关**运算符**，输入**==**。 有关**值**，输入您的消息，消息类型`http://schemas.microsoft.com/BizTalk/Edi/X12/2006#X12_00401_864`。  

7. 单击“确定” 。  

8. 在中**发送端口**窗格[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理控制台中，右键单击该发送端口，然后依次**启动**。  

##### <a name="to-create-a-party-and-a-business-profile-for-fabrikam"></a>创建 Fabrikam 参与方和业务配置文件  

1. 右键单击**参与方**中的节点[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理控制台中，依次指向**新建**，然后单击**方**。  

2. 输入中的参与方的名称**名称**文本框中，，然后单击**确定**。  

   > [!NOTE]
   >  通过选择**本地 BizTalk 处理接收的来自此参与方发送消息的参与方或支持消息**复选框，可以指定要创建的参与方是为同一组织与托管[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]. 此基础，某些属性将启用，或禁用在创建协议时。 但是，对于此演练中，可以选中此复选框。  

3. 右键单击参与方名称，指向**新建**，然后单击**业务配置文件**。  

4. 在中**配置文件属性**对话框中，在**常规**页上，输入**Fabrikam_Profile**中**名称**文本框。  

   > [!NOTE]
   >  创建一个参与方时，还创建配置文件。 可以重命名，并使用该配置文件而不是创建一个新。 若要重命名配置文件，请右键单击该配置文件，然后选择**属性**。 在中**常规**页上，指定配置文件的名称。  

##### <a name="to-create-a-party-and-a-business-profile-for-contoso"></a>为 Contoso 创建参与方和业务配置文件  

1. 右键单击**参与方**中的节点[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理控制台中，依次指向**新建**，然后单击**方**。  

2. 输入中的参与方的名称**名称**文本框中，，然后单击**确定**。  

   > [!NOTE]
   >  通过选择**本地 BizTalk 处理接收的来自此参与方发送消息的参与方或支持消息**复选框，可以指定要创建的参与方是为同一组织与托管[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]. 此基础，某些属性将启用，或禁用在创建协议时。 但是，对于此演练中，可以选中此复选框。  

3. 右键单击参与方名称，指向**新建**，然后单击**业务配置文件**。  

4. 在中**配置文件属性**对话框中，在**常规**页上，输入**Contoso_Profile**中**名称**文本框。  

   > [!NOTE]
   >  创建一个参与方时，还创建配置文件。 可以重命名，并使用该配置文件而不是创建一个新。 若要重命名配置文件，请右键单击该配置文件，然后选择**属性**。 在中**常规**页上，指定配置文件的名称。  

##### <a name="to-create-an-as2-agreement-between-the-two-business-profiles"></a>若要创建两个业务配置文件之间的 AS2 协议  

1.  右键单击**Fabrikam_Profile**，依次指向**新建**，然后单击**协议**。  

2.  在**常规属性**页上，对于**名称**文字框中，输入协议的名称。  

3.  从**协议**下拉列表中，选择**AS2**。  

4.  在中**第二个合作伙伴**部分中，从**名称**下拉列表中，选择**Contoso**。  

5.  在中**第二个合作伙伴**部分中，从**配置文件**下拉列表中，选择**Contoso_Profile**。  

     你将注意到两个新选项卡获取旁边添加**常规**选项卡。每个选项卡是用于配置一个单向 AS2 协议。  

6.  在中**常规**选项卡中，**常规属性**页上，在**公用主机设置**部分中，选择**打开报告**。  

7.  在执行以下任务**Fabrikam-> Contoso**选项卡。  

    1.  上**标识符**页上，输入值**AS2-从**并**AS2-到**。 有关**AS2-从**，输入`Fabrikam`。 有关**AS2-To**，输入`Contoso`。  

8.  在执行以下任务**Contoso-> Fabrikam**选项卡。  

    > [!NOTE]
    >  在本演练中，我们指定的选项卡中所需的值，以便可以成功创建协议。 若要成功创建协议，两个单向协议选项卡必须具有定义为值**AS2_From**并**AS2-到**。  

    1.  上**标识符**页上，输入值**AS2-从**并**AS2-到**。 有关**AS2-从**，输入`Contoso`。 有关**AS2-To**，输入`Fabrikam`。  

9. 单击 **“应用”**。  

10. 单击“确定” 。 中列出新添加的协议**协议**一部分**参与方和业务配置文件**窗格。 默认情况下启用新添加的协议。  

##### <a name="to-create-an-x12-agreement-between-the-two-business-profiles"></a>若要创建 X12 协议之间的两个业务配置文件  

1. 右键单击**Fabrikam_Profile**，依次指向**新建**，然后单击**协议**。  

2. 在**常规属性**页上，对于**名称**文字框中，输入协议的名称。  

3. 从**协议**下拉列表中，选择**X12**。  

4. 在中**第二个合作伙伴**部分中，从**名称**下拉列表中，选择**Contoso**。  

5. 在中**第二个合作伙伴**部分中，从**配置文件**下拉列表中，选择**Contoso_Profile**。  

    你将注意到两个新选项卡获取旁边添加**常规**选项卡。每个选项卡可用于配置一个单向 X12 协议。  

6. 在中**常规**选项卡中，**常规属性**页上，在**公用主机设置**部分中，选择**打开报告**，，然后选择**存储消息负载以用于报告**。  

7. 在执行以下任务**Fabrikam-> Contoso**选项卡。  

   1. 上**标识符**页**交换设置**部分中，输入限定符和标识符字段的值 (**ISA5**， **ISA6**， **ISA7**，并**ISA8**) 的测试消息中这些标头字段的值相对应。  

      > [!NOTE]
      >  [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 需要发送方和接收方限定符和标识符字段才能执行协议解析。 它将匹配的值**ISA5**， **ISA6**， **ISA7**，以及**ISA8**与协议属性中的交换标头中。 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 此外将通过匹配发送方限定符和标识符 （不接收方限定符和标识符） 来解析协议。 如果[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]不能解析协议，它将使用后备协议属性。  
      > 
      > [!NOTE]
      >  对于本演练中，设置**ISA5**到**ZZ**， **ISA6**到**7654321**， **ISA7**到**ZZ**，并**ISA8**到**1234567**。  

   2. 上**验证**页**交换设置**部分中，请确保**检查重复的 isa13**选项处于未选中状态。  

      > [!NOTE]
      >  清除**检查重复的 isa13**属性使您能够接收同一消息的多个实例。  

   3. 如果你使用附带的标准架构之一[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]，然后在**本地主机设置**页下**事务集设置**部分中，选择要使用的架构的命名空间处理传入的交换。  


      |       使用此选项       |                           执行的操作                            |
      |----------------------|-----------------------------------------------------------------|
      |     **默认**      |                列中选中的复选框                |
      | **目标 Namespace** | 选择 <http://schemas.microsoft.com/BizTalk/EDI/X12/2006>。 |

      > [!NOTE]
      >  设置属性后，[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]来确定要处理传入 850 交换时使用的架构。 如果交换具有网格的行输入的 GS02 和 ST01 值，然后将使用在同一行的目标命名空间来确定要使用的架构。  

8. 在执行以下任务**Contoso-> Fabrikam**选项卡。  

   > [!NOTE]
   >  在本演练中，我们指定的选项卡中所需的值，以便可以成功创建协议。 若要成功创建协议，两个单向协议选项卡必须具有定义为值**ISA5**， **ISA6**， **ISA7**，以及**ISA8**。  

   1.  上**标识符**页**交换设置**部分中，输入限定符和标识符字段的值 (**ISA5**， **ISA6**， **ISA7**，并**ISA8**) 的测试消息中这些标头字段的值相对应。  

       > [!NOTE]
       >  对于本演练中，设置**ISA5**到**ZZ**， **ISA6**到**1234567**， **ISA7**到**ZZ**，并**ISA8**到**7654321**。  

9. 单击 **“应用”**。  

10. 单击“确定” 。 中列出新添加的协议**协议**一部分**参与方和业务配置文件**窗格。 默认情况下启用新添加的协议。  

### <a name="testing-the-walkthrough"></a>测试演练  
 本部分提供有关如何测试演练的信息。  

##### <a name="to-test-the-solution"></a>若要测试解决方案  

1. 在中[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]，打开中的 Sender.csproj 项目[!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]SDK\AS2 Tutorial\Sender 文件夹。  

2. 在 HttpSender.cs 中，注释掉以下行 （紧接在 //Request Asynchronous MDN 注释行) 下面：  

   ```  
   Stream sr = new FileStream(getBizTalkInstallPath() + @"SDK\AS2 Tutorial\X12_00401_864.edi", FileMode.Open, FileAccess.Read);  
   ```  

3. 取消注释掉以下行 （紧接在 //Request Synchronous MDN 注释行) 下面：  

   ```  
   Stream sr = new FileStream(getBizTalkInstallPath() + @"SDK\AS2 Tutorial\X12_00401_864-Sync.edi", FileMode.Open, FileAccess.Read);  
   ```  

4. 生成此项目。  

5. 在 Windows 资源管理器，转到[!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]SDK\AS2 Tutorial。 在记事本中打开 X12_00401_864-Sync.edi。 删除定义的处理设置通知选项标头的行，然后保存文件。  

6. 打开命令窗口。 将移动到[!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]SDK\AS2 Tutorial\Sender\bin\debug。 运行**Sender.exe**。  

   > [!NOTE]
   >  此实例中运行 Sender.exe 将发布消息 X12_00401_864-sync.edi 发送到 Contoso 虚拟目录 （BTS HTTP 接收位置）。  

7. 验证在命令窗口中显示出 MDN。 验证在 MDN 的 AS2-从是 Contoso 和 AS2-To 是 Fabrikam。  

   > [!NOTE]
   >  Sender.exe 在命令窗口中显示该 MDN。  

8. 打开创建用于接收 EDI 负载的 Contoso 本地文件夹 (**\EDI_to_Contoso**)。 检查是否存在。XML 文件的文件夹中。 打开 XML 文件并验证它包含一个 864 事务集。  

9. 在记事本中，打开测试消息 X12_00401_864-Sync.edi，并验证中的输出消息中的事务集**\EDI_to_Contoso**本地文件夹对应于 X12_00401_864-Sync.edi 输入中的事务集消息。  

## <a name="see-also"></a>请参阅  
 [开发和配置 BizTalk Server AS2 解决方案](../core/developing-and-configuring-biztalk-server-as2-solutions.md)