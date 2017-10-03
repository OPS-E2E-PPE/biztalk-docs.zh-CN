---
title: "演练 (X12)： 接收批处理的 EDI 交换 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 1f6e6e96-39ec-469d-a845-1bfdce6cc0bf
caps.latest.revision: "34"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 94d1aa31a271f0ed88be42066abdae25be3f3e87
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="walkthrough-x12-receiving-batched-edi-interchanges"></a>演练 (X12)：接收批处理 EDI 交换
本演练将介绍一组使用 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 创建解决方案以接收 EDI 批的分步操作过程。 此解决方案演示了两种接收批处理 EDI 交换的方法：  
  
-   通过将批拆分为其组成事务集。  
  
-   通过处理交换为一个文档，而无需拆分事务保留交换的设置。  
  
 本演练演示如何配置拆分和保留批次。  
  
## <a name="prerequisites"></a>先决条件  
 必须以 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理员组或 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] B2B Operators 组成员的身份登录。  
  
## <a name="how-the-solution-splits-received-edi-batches"></a>解决方案如何拆分接收的 EDI 批  
 当将解决方案配置为将批处理交换拆分为其组成事务集时，解决方案将执行如下操作：  
  
1.  接收位置从一个团队接收包含多个交易记录集的一个批处理 EDI 交换。  
  
    > [!NOTE]
    >  此列表中的事件可能不会按所示顺序发生。  
  
2.  接收管道将接收的交换拆分为其组成事务集，并将事务集转换为内部 XML 格式。  
  
3.  接收管道将整个交换和组标头升级为从交换拆分的每个事务集的上下文。 它还会升级某些特定交换和组标头（如 ISA6、GS1 和 GS2），以便可以使用这些字段进行路由。  
  
4.  接收管道将每个事务集 XML 文件放入 MessageBox。  
  
    > [!NOTE]
    >  在此解决方案中，批包含具有相同消息类型的多个实例。  
  
5.  发送端口通过订阅适当的上下文属性来提取每个事务集。  
  
6.  发送管道将每个事务集生成一个 EDI 交换，然后将交换发送到目标。  
  
    > [!NOTE]
    >  有关详细信息如何[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]拆分事务集到批处理中，请参阅[拆分批处理的 EDI 交换](../core/splitting-a-batched-edi-interchange.md)。  
  
 下图显示了将解决方案配置为拆分批处理交换中的事务集时解决方案的体系结构和消息流。  
  
 ![拆分批处理的 EDI 交换](../core/media/ef386df6-e195-45d9-abff-4d0bd3a82a4f.gif "ef386df6-e195-45d9-abff-4d0bd3a82a4f")  
  
## <a name="how-the-solution-preserves-received-edi-batches"></a>解决方案如何保留接收的 EDI 批  
 当将解决方案配置为保留批处理交换时，解决方案将执行如下操作：  
  
1.  接收位置从该团队接收一个包含多个交易记录集的批处理 EDI 交换。  
  
2.  接收管道处理交换而不拆分事务集，并将两个事务集作为一个单位转换为内部 XML 格式。  
  
3.  接收管道除了将保留标记应用于它生成的 XML 以外，还升级相同的属性（就好像交换不是批那样）。 此标记是\<X12InterchangeXml > 的 X12 编码 EDI 交换或\<EdifactInterchangeXml > 的 EDIFACT 编码 EDI 交换。 EDI 接收管道还应用上下文属性 `ReuseEnvelope` 以将交换标识为保留。  
  
    > [!NOTE]
    >  EDI 发送管道使用\<X12InterchangeXml > 或\<EdifactInterchangeXml > 标记来标识作为保留的批次的消息。 使用 `ReuseEnvelope` 上下文属性可创建用于订阅所有保留的批处理交换的发送端口。  
  
4.  接收管道将消息 XML 文件放入 MessageBox。  
  
5.  发送端口通过订阅适当的上下文属性来提取交换。  
  
6.  发送管道将 XML 文件中的两个事务集生成一个批处理 EDI 交换，然后将交换发送到目标。  
  
    > [!NOTE]
    >  有关详细信息如何[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]处理一个保留的批处理，请参阅[保留收到批处理的 EDI 交换](../core/preserving-a-received-batched-edi-interchange.md)。  
  
## <a name="functionality-in-this-solution"></a>此解决方案中的功能  
 为进行此演练，将启用以下功能：  
  
-   该解决方案专用于使用 X12 编码而不是 EDIFACT 编码的交换。  
  
    > [!NOTE]
    >  用于 HIPAA 和 EDIFACT 编码的配置与用于 X12 编码的配置几近相同。  
  
-   将不会返回技术确认或功能确认来响应最初接收的交换或发送的任何批处理交换。  
  
    > [!NOTE]
    >  有关生成 EDI 确认信息，请参阅[演练 (X12)： 接收 EDI 交换和发送回确认](../core/walkthrough-x12--receive-edi-interchanges-and-send-back-an-acknowledgement.md)。  
  
-   该解决方案使用一个单向接收端口和一个静态单向发送端口。 将使用 FILE 传输类型配置这些端口。  
  
-   将启用 EDI 报告。  
  
-   将保存事务集以从交换状态报告进行查看。  
  
-   出于测试目的，该解决方案使用发送端口将拆分的交换或保留的批发送到本地文件夹。  
  
## <a name="configuring-and-testing-the-walkthrough"></a>配置和测试演练  
 该解决方案所需的过程包括：  
  
-   将必需的消息架构添加到 BizTalk 项目，然后生成并部署该项目，以使架构可供 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 在处理消息时使用。  
  
-   为 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 创建接收端口，以从团队接收 EDI X12 编码的 .txt 批处理输入消息。  
  
-   为 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 创建发送端口，以为接收的批中的每个事务集生成交换（如果拆分批），或者从接收的批中的事务集生成单个交换（如果保留批）。 发送端口稍后会将交换发送给目标参与方。 此发送端口将是一个静态单向发送端口。  
  
-   为参与方 A 和参与方 B 创建一个参与方（贸易合作伙伴）。  
  
-   为两个贸易合作伙伴分别创建一个业务配置文件。  
  
-   通过将 EDI 属性配置为通过拆分或保留交换来接收消息，从而在两个配置文件之间创建协议。  
  
-   将一个批处理 EDI 交换放入与接收位置关联的本地文件夹中。 然后，您可以验证 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 是否已将来自接收的批的单独交换（如果拆分批）或单个保留的批处理交换（如果保留批）放入与发送端口关联的文件夹中。  
  
    > [!NOTE]
    >  如果已经执行发送批处理交换演练中的步骤，则可以将那一解决方案的输出用作此解决方案的输入。 那一解决方案的输出是一个包含两个 850 消息的批。 有关详细信息，请参阅[演练 (X12)： 发送批处理的 EDI 交换](../core/walkthrough-x12-sending-batched-edi-interchanges.md)。  
  
 本部分介绍配置演练的步骤。  
  
##### <a name="to-deploy-the-message-schema"></a>部署消息架构  
  
1.  在 [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] 中，创建或打开 BizTalk 项目。  
  
    > [!NOTE]
    >  本主题假定你已从你的应用程序添加了对包含 EDI 架构、管道和业务流程的 BizTalk EDI 应用程序的引用。 如果没有，请参阅[如何添加对 BizTalk Server EDI 应用程序的引用](http://msdn.microsoft.com/library/7af066fb-372f-4709-b566-c8d6b4a9d782)。  
  
2.  右键单击你的项目，指向**添加**，然后单击**现有项**。 将移动到**\<驱动器 >: files\microsoft BizTalk Server 2009\XSD_Schema\EDI\X12\00401**，然后双击对应到你的测试消息的架构。  
  
    > [!NOTE]
    >  如果不具有已 EDI 架构解压缩到 XSD_SchemaEDI 文件夹中，执行**MicrosoftEdiXSDTemplates.exe** XSD_SchemaEDI 文件夹来解压缩到默认文件夹的架构中的文件。  
  
    > [!NOTE]
    >  对于测试消息，可以使用由发送批处理交换演练中的解决方案生成的批处理交换。 该解决方案的输出是一个包含两个用于 EDI 接口开发人员教程的 850 示例消息实例的批。 如果这样做，则必须使用位于架构 x12_00401_850.xsd [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]SDKEDI 接口开发人员 TutorialInbound_EDI。  
  
3.  设置程序集密钥文件，然后生成并部署该程序集。  
  
##### <a name="to-create-a-one-way-receive-port-to-receive-the-batched-edi-messages"></a>创建用于接收已批处理的 EDI 消息的单向接收端口  
  
1.  在[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理控制台中，右键单击**接收端口**节点下的**BizTalk 应用程序 1**节点，指向**新建**，然后单击**单向接收端口。**  
  
2.  将接收端口，然后单击**接收位置**在控制台树中。  
  
3.  单击 **“新建”**。  
  
4.  名称的接收位置中，选择**文件**为**类型**，然后单击**配置**。  
  
5.  输入的文件夹**接收文件夹**，和的掩码**文件掩码**，如 **\*.txt**。  
  
6.  单击 **“确定”**。  
  
7.  有关**接收管道**，选择**EdiReceive**。  
  
8.  单击 **“确定”**。  
  
9. 在控制台树中，单击**接收位置**。 在**接收位置**窗格中，右键单击你接收位置，并依次**启用**。  
  
##### <a name="to-create-a-static-one-way-send-port-to-send-the-batched-edi-interchange"></a>创建静态单向发送端口以发送批处理 EDI 交换  
  
1.  在[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理控制台中，右键单击**发送端口**节点下的**BizTalk 应用程序 1**节点，指向**新建**，然后单击**静态单向发送端口。**  
  
2.  在**发送端口属性**对话框中，名称发送端口。  
  
3.  在**传输**部分中，选择**文件**为**类型**，然后单击**配置**。  
  
4.  输入的文件夹**目标文件夹**，和的掩码**文件掩码**，如 **\*.txt**。  
  
5.  单击 **“确定”**。  
  
6.  在**发送管道**，选择**EdiSend**。  
  
7.  在控制台树中，选择**筛选器**。 上**筛选器**页上，输入将订阅到批处理中消息的筛选器表达式。 例如，选择**BTS。ReceivePortName**为**属性**，  **==** 为**运算符**，和你刚刚创建的接收端口的名称的**值**。  
  
8.  单击 **“确定”**。  
  
9. 在控制台树中，单击**发送端口**。 在**发送端口**窗格中，右键单击你发送端口，并依次**启动**。  
  
##### <a name="to-create-a-party-and-a-business-profile-for-party-a"></a>为参与方 A 创建团队和业务配置文件  
  
1.  右键单击**方**中的节点[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理控制台中，依次指向**新建**，然后单击**方**。  
  
2.  输入的名称在方**名称**文本中，然后单击**确定**。  
  
    > [!NOTE]
    >  通过选择**本地 BizTalk 处理接收的消息从该参与方发送方或支持消息**复选框，你可以指定当事方正在创建将为同一个组织还承载[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]. 此基础，某些属性将启用，或当您创建了协议时，禁用。 但是，对于本演练中，可以选中此复选框。  
  
3.  右键单击方名称，指向**新建**，然后单击**业务配置文件**。  
  
4.  在**配置文件属性**对话框中，在**常规**页上，输入**PartyA_Profile**中**名称**文本框。  
  
    > [!NOTE]
    >  在创建参与方时，也将创建一个配置文件。 你可以重命名，并使用该配置文件而不是创建一个新。 若要重命名配置文件，右键单击配置文件，然后选择**属性**。 在**常规**页上，指定配置文件的名称。  
  
##### <a name="to-create-a-party-and-a-business-profile-for-party-b"></a>为参与方 B 创建团队和业务配置文件  
  
1.  右键单击**方**中的节点[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理控制台中，依次指向**新建**，然后单击**方**。  
  
2.  输入的名称在方**名称**文本中，然后单击**确定**。  
  
    > [!NOTE]
    >  通过选择**本地 BizTalk 处理接收的消息从该参与方发送方或支持消息**复选框，你可以指定当事方正在创建将为同一个组织还承载[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]. 此基础，某些属性将启用，或当您创建了协议时，禁用。 但是，对于本演练中，可以选中此复选框。  
  
3.  右键单击方名称，指向**新建**，然后单击**业务配置文件**。  
  
4.  在**配置文件属性**对话框中，在**常规**页上，输入**PartyB_Profile**中**名称**文本框。  
  
    > [!NOTE]
    >  在创建参与方时，也将创建一个配置文件。 你可以重命名，并使用该配置文件而不是创建一个新。 若要重命名配置文件，右键单击配置文件，然后选择**属性**。 在**常规**页上，指定配置文件的名称。  
  
##### <a name="to-create-an-agreement-between-the-two-business-profiles"></a>在两个业务配置文件之间创建协议  
  
1.  右键单击**PartyA_Profile**，指向**新建**，然后单击**协议**。  
  
2.  在**常规属性**页上，为**名称**文本框中，输入协议的名称。  
  
3.  从**协议**下拉列表中，选择**X12**。  
  
4.  在**第二个合作伙伴**部分中，从**名称**下拉列表中，选择**PartyB**。  
  
5.  在**第二个合作伙伴**部分中，从**配置文件**下拉列表中，选择**PartyB_Profile**。  
  
     你将注意到两个新选项卡获取旁边添加**常规**选项卡。每个选项卡配置一个单向协议，每个单向协议代表消息的一次完整事务（包括消息传输和确认传输）。  
  
6.  在**常规**选项卡上，在**常规属性**页上，在**常见主机设置**部分中，选择**打开 reporting**，，然后选择**用于报告的应用商店消息负载**。  
  
7.  在上执行以下任务**PartyA-> PartyB**选项卡。  
  
    1.  上**标识符**下页上**交换设置**部分中，输入限定符和标识符字段的值 (**ISA5**， **ISA6**， **ISA7**，和**ISA8**) 对应于测试消息中这些标头字段的值。  
  
        > [!NOTE]
        >  [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 要求为发送方和接收方的限定符和标识符字段输入值才能执行协议解析。 它将与匹配的值**ISA5**， **ISA6**， **ISA7**，和**ISA8**与协议的属性中的交换标头中。 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]此外将匹配的发件人限定符和 （而不是收件人限定符和标识符） 的标识符来解析协议。 如果 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 无法解析协议，则将使用后备协议属性。  
  
        > [!NOTE]
        >  如果你使用"EDI 接口开发人员教程"中的 SamplePO.txt 文件作为测试消息，设置**ISA5**到**ZZ**， **ISA6**到**THEM**， **ISA7**到**ZZ**，和**ISA8**到**美国**。  
  
    2.  上**验证**下页上**交换设置**部分中，请确保**检查重复的 isa13**选项处于未选中状态。  
  
        > [!NOTE]
        >  清除**检查重复的 isa13**属性使您能够接收同一消息的多个实例。  
  
    3.  上**字符集和分隔符**下页上**交换设置**部分中，选择**CR LF**选项。  
  
    4.  上**本地主机设置**下页上**交换设置**部分中，在**入站消息处理选项**框中，选择**拆分交换为事务集-出错时暂停事务集**选项。  
  
        > [!NOTE]
        >  若要开始使用此解决方案，我们将通过选择此选项来拆分该交换。 更高版本，作为的一部分[测试演练](../core/walkthrough-x12-receiving-batched-edi-interchanges.md#BKMK_Proc)下面的过程，我们将配置解决方案以保留交换。  
  
    5.  上**发送端口**下页上**交换设置**部分中，将之前创建发送端口相关联。 在**发送端口**网格下**名称**列中，单击空单元格，然后从下拉列表列表中，选择发送端口。  
  
    6.  上**包络线**下页上**事务设置设置**部分中，输入网格的第一行中的所有列的值。  
  
        |使用此选项|执行的操作|  
        |--------------|----------------|  
        |**Default**|选择**默认**。 **注意：**当作为默认值的值选择此行**GS1**， **GS2**， **GS3**， **GS7**，和**GS8**使用即使的值**事务类型**，**版本/发行版**，和**目标命名空间**不的匹配项消息。|  
        |**事务类型**|选择你的测试消息的消息类型**850-采购订单**。|  
        |**版本/发行版**|输入的 EDI 版本中， **00401**。|  
        |**目标命名空间**|选择**http://schemas.microsoft.com/Edi/X12**。|  
        |**GS1**|验证是否已选中测试消息的消息类型， **PO-采购订单 (850)**。|  
        |**GS2**|例如，应用程序发件人，输入一个值**购买**。|  
        |**GS3**|例如，为应用程序收件人输入一个值**OrderControl**。|  
        |**GS4**|选择所需的日期格式。 **注意：**你需要在下拉列表中选择值，而不仅仅是在要显示默认值的字段中单击。 如果你仅单击字段，而没有从下拉列表中选择值，则实际上并未选择值。|  
        |**GS5**|选择所需的时间格式。|  
        |**GS7**|选择**X 的公认的标准委员会 X12**。|  
        |**GS8**|验证 EDI 版本具有输入**00401**。|  
  
        > [!NOTE]
        >  [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]将为 GS01、 GS02、 GS03、 GS04、 GS05、 GS07 和基于为输入的值的出站确认 GS08 设置值**事务类型**，**版本/发行版**，和**目标命名空间**。 发送管道尝试将事务集类型、X12 版本和目标命名空间与消息标头中的对应值相匹配。 如果成功，它将使用与关联的 GS 值**事务类型**，**版本/发行版**，和**目标命名空间**值。  
  
8.  在上执行以下任务**PartyB-> PartyA**选项卡。  
  
    > [!NOTE]
    >  在此演练中，我们将指定的选项卡中所需的值，以便可以成功创建协议。 若要成功创建了协议，这两个单向协议选项必须为定义的值**ISA5**， **ISA6**， **ISA7**，和**ISA8**。  
  
    1.  上**标识符**下页上**交换设置**部分中，输入限定符和标识符字段的值 (**ISA5**， **ISA6**， **ISA7**，和**ISA8**) 对应于测试消息中这些标头字段的值。  
  
        > [!NOTE]
        >  如果你使用"EDI 接口开发人员教程"中的 SamplePO.txt 文件作为测试消息，设置**ISA5**到**ZZ**， **ISA6**到**美国**， **ISA7**到**ZZ**，和**ISA8**到**THEM**。  
  
9. 单击 **“应用”**。  
  
10. 单击 **“确定”**。 新添加的协议被列入**协议**部分**方和业务配置文件**窗格。 默认情况下，启用新添加的协议。  
  
### <a name="testing-the-walkthrough"></a>测试演练  
 本部分提供有关如何测试演练的信息。  
  
####  <a name="BKMK_Proc"></a>若要测试演练  
  
1.  在 Windows 资源管理器中，打开与接收位置关联的本地文件夹，然后将测试批处理 EDI 交换放入该文件夹。  
  
    > [!NOTE]
    >  对于测试消息，可以使用由发送批处理交换演练中的解决方案生成的批处理交换输出。 此示例消息将包含两个事务集。  
  
2.  打开与上面创建的发送端口关联的文件夹。 验证该文件夹是否包含两个新文件，以及每个文件是否为包含测试批处理消息中的一个事务集的 850 交换。  
  
3.  在[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理控制台中，单击**方**节点，单击任何先前创建的协议的一部分的两个业务配置文件。 在**协议**部分，右键单击协议，然后单击**属性**。  
  
4.  在**协议属性**对话框中，在**本地主机设置**下页上**交换设置**部分中，在**入站消息处理选项**框中，选择**保留交换-出错时暂停交换**或**保留交换-出错时暂停事务集**单击**确定**。  
  
5.  单击**主机实例**下**平台设置**节点，右键单击**BizTalkServerApplication**，然后单击**重新启动**。  
  
6.  在 Windows 资源管理器中，打开与接收位置关联的本地文件夹，然后再次将该测试批处理 EDI 交换放入该文件夹。  
  
7.  在 Windows 资源管理器中，打开与上面创建的发送端口关联的文件夹。 验证该文件夹当前是否仅包含一个新文件，以及此文件是否为包含测试批处理消息中的两个 850 事务集的交换。  
  
## <a name="see-also"></a>另请参阅  
 [开发和配置 BizTalk Server EDI 解决方案](../core/developing-and-configuring-biztalk-server-edi-solutions.md)   
 [拆分批处理的 EDI 交换](../core/splitting-a-batched-edi-interchange.md)   
 [拆分 HIPAA 子文档](../core/splitting-hipaa-subdocuments.md)   
 [保留已收到批处理的 EDI 交换](../core/preserving-a-received-batched-edi-interchange.md)   
 [演练 (X12)： 发送批处理的 EDI 交换](../core/walkthrough-x12-sending-batched-edi-interchanges.md)   
 [演练 (X12)： 接收 EDI 交换和发送回确认](../core/walkthrough-x12--receive-edi-interchanges-and-send-back-an-acknowledgement.md)   
 [演练 (X12)： 发送 EDI 交换](../core/walkthrough-x12-sending-edi-interchanges.md)