---
title: '演练 (X12): 接收批处理的 EDI 交换 |Microsoft Docs'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 1f6e6e96-39ec-469d-a845-1bfdce6cc0bf
caps.latest.revision: 34
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 4afc640671828bfef194f851f94bd412a00dbd7c
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36979254"
---
# <a name="walkthrough-x12-receiving-batched-edi-interchanges"></a>演练 (X12)：接收批处理 EDI 交换
本演练将介绍一组使用 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 创建解决方案以接收 EDI 批的分步操作过程。 此解决方案演示了两种接收批处理 EDI 交换的方法：  

- 通过将批拆分为其组成事务集。  

- 通过保留交换的交换作为一个文档处理而不拆分事务设置。  

  本演练演示如何配置拆分和保留批。  

## <a name="prerequisites"></a>必要條件  
 必须以 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理员组或 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] B2B Operators 组成员的身份登录。  

## <a name="how-the-solution-splits-received-edi-batches"></a>解决方案如何拆分接收的 EDI 批  
 当将解决方案配置为将批处理交换拆分为其组成事务集时，解决方案将执行如下操作：  

1. 接收位置从一个团队接收包含多个交易记录集的一个批处理 EDI 交换。  

   > [!NOTE]
   >  此列表中的事件可能不会按所示顺序发生。  

2. 接收管道将接收的交换拆分为其组成事务集，并将事务集转换为内部 XML 格式。  

3. 接收管道将整个交换和组标头升级为从交换拆分的每个事务集的上下文。 它还会升级某些特定交换和组标头（如 ISA6、GS1 和 GS2），以便可以使用这些字段进行路由。  

4. 接收管道将每个事务集 XML 文件放入 MessageBox。  

   > [!NOTE]
   >  在此解决方案中，批包含具有相同消息类型的多个实例。  

5. 发送端口通过订阅适当的上下文属性来提取每个事务集。  

6. 发送管道将每个事务集生成一个 EDI 交换，然后将交换发送到目标。  

   > [!NOTE]
   >  详细了解如何[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]拆分事务集在一个批处理中，请参阅[拆分批处理的 EDI 交换](../core/splitting-a-batched-edi-interchange.md)。  

   下图显示了将解决方案配置为拆分批处理交换中的事务集时解决方案的体系结构和消息流。  

   ![拆分成批的 EDI 交换](../core/media/ef386df6-e195-45d9-abff-4d0bd3a82a4f.gif "ef386df6-e195-45d9-abff-4d0bd3a82a4f")  

## <a name="how-the-solution-preserves-received-edi-batches"></a>解决方案如何保留接收的 EDI 批  
 当将解决方案配置为保留批处理交换时，解决方案将执行如下操作：  

1. 接收位置从该团队接收一个包含多个交易记录集的批处理 EDI 交换。  

2. 接收管道处理交换而不拆分事务集，并将两个事务集作为一个单位转换为内部 XML 格式。  

3. 接收管道除了将保留标记应用于它生成的 XML 以外，还升级相同的属性（就好像交换不是批那样）。 此标记\<X12InterchangeXml\>对于 X12 编码的 EDI 交换或\<EdifactInterchangeXml\>对于 EDIFACT 编码的 EDI 交换。 EDI 接收管道还应用上下文属性 `ReuseEnvelope` 以将交换标识为保留。  

   > [!NOTE]
   >  EDI 发送管道使用\<X12InterchangeXml\>或\<EdifactInterchangeXml\>标记来标识为保留批的消息。 使用 `ReuseEnvelope` 上下文属性可创建用于订阅所有保留的批处理交换的发送端口。  

4. 接收管道将消息 XML 文件放入 MessageBox。  

5. 发送端口通过订阅适当的上下文属性来提取交换。  

6. 发送管道将 XML 文件中的两个事务集生成一个批处理 EDI 交换，然后将交换发送到目标。  

   > [!NOTE]
   >  详细了解如何[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]处理保留的批，请参阅[保留接收批处理 EDI 交换](../core/preserving-a-received-batched-edi-interchange.md)。  

## <a name="functionality-in-this-solution"></a>在此解决方案中的功能  
 为进行此演练，将启用以下功能：  

-   该解决方案专用于使用 X12 编码而不是 EDIFACT 编码的交换。  

    > [!NOTE]
    >  用于 HIPAA 和 EDIFACT 编码的配置与用于 X12 编码的配置几近相同。  

-   将不会返回技术确认或功能确认来响应最初接收的交换或发送的任何批处理交换。  

    > [!NOTE]
    >  有关生成 EDI 确认的信息，请参阅[演练 (X12)： 接收 EDI 交换并发送回确认信息](../core/walkthrough-x12--receive-edi-interchanges-and-send-back-an-acknowledgement.md)。  

-   该解决方案使用一个单向接收端口和一个静态单向发送端口。 将使用 FILE 传输类型配置这些端口。  

-   将启用 EDI 报告。  

-   将保存事务集以从交换状态报告进行查看。  

-   出于测试目的，该解决方案使用发送端口将拆分的交换或保留的批发送到本地文件夹。  

## <a name="configuring-and-testing-the-walkthrough"></a>配置和测试演练  
 该解决方案所需的过程包括：  

- 将必需的消息架构添加到 BizTalk 项目，然后生成并部署该项目，以使架构可供 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 在处理消息时使用。  

- 为 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 创建接收端口，以从团队接收 EDI X12 编码的 .txt 批处理输入消息。  

- 为 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 创建发送端口，以为接收的批中的每个事务集生成交换（如果拆分批），或者从接收的批中的事务集生成单个交换（如果保留批）。 发送端口稍后会将交换发送给目标参与方。 此发送端口将是一个静态单向发送端口。  

- 为参与方 A 和参与方 B 创建一个参与方（贸易合作伙伴）。  

- 为两个贸易合作伙伴分别创建一个业务配置文件。  

- 通过将 EDI 属性配置为通过拆分或保留交换来接收消息，从而在两个配置文件之间创建协议。  

- 将一个批处理 EDI 交换放入与接收位置关联的本地文件夹中。 然后，您可以验证 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 是否已将来自接收的批的单独交换（如果拆分批）或单个保留的批处理交换（如果保留批）放入与发送端口关联的文件夹中。  

  > [!NOTE]
  >  如果已经执行发送批处理交换演练中的步骤，则可以将那一解决方案的输出用作此解决方案的输入。 那一解决方案的输出是一个包含两个 850 消息的批。 有关详细信息，请参阅[演练 (X12)： 发送批处理 EDI 交换](../core/walkthrough-x12-sending-batched-edi-interchanges.md)。  

  本部分介绍配置本演练的步骤。  

##### <a name="to-deploy-the-message-schema"></a>部署消息架构  

1. 在 [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] 中，创建或打开 BizTalk 项目。  

   > [!NOTE]
   >  本主题假定你已从你的应用程序添加了对包含 EDI 架构、管道和业务流程的 BizTalk EDI 应用程序的引用。 如果没有，请参阅[如何添加对 BizTalk Server EDI 应用程序的引用](http://msdn.microsoft.com/library/7af066fb-372f-4709-b566-c8d6b4a9d782)。  

2. 右键单击你的项目，指向**外**，然后单击**现有项**。 将移动到**\<驱动器\>: \Program Files\Microsoft BizTalk Server 2009\XSD_Schema\EDI\X12\00401**，然后双击与测试消息对应的架构。  

   > [!NOTE]
   >  如果 EDI 架构尚未解压缩到 XSD_SchemaEDI 文件夹，则执行**MicrosoftEdiXSDTemplates.exe** XSD_SchemaEDI 文件夹将架构解压缩到默认文件夹中的文件。  
   > 
   > [!NOTE]
   >  对于测试消息，可以使用由发送批处理交换演练中的解决方案生成的批处理交换。 该解决方案的输出是一个包含两个用于 EDI 接口开发人员教程的 850 示例消息实例的批。 如果这样做，则必须使用 x12_00401_850.xsd 架构位于[!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]SDKEDI 接口开发人员 TutorialInbound_EDI。  

3. 设置程序集密钥文件，然后生成并部署该程序集。  

##### <a name="to-create-a-one-way-receive-port-to-receive-the-batched-edi-messages"></a>创建用于接收已批处理的 EDI 消息的单向接收端口  

1. 在中[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理控制台中，右键单击**接收端口**节点下的**BizTalk Application 1**节点，指向**新建**，然后单击**单向接收端口。**  

2. 接收端口的名称，然后单击**接收位置**在控制台树中。  

3. 单击 **“新建”**。  

4. 名称的接收位置，选择**文件**有关**类型**，然后单击**配置**。  

5. 输入一个文件夹**接收文件夹**，和一个掩码**文件掩码**，如 **\*.txt**。  

6. 单击“确定” 。  

7. 有关**接收管道**，选择**EdiReceive**。  

8. 单击“确定” 。  

9. 在控制台树中，单击**接收位置**。 在中**接收位置**窗格中，右键单击将接收位置，然后依次**启用**。  

##### <a name="to-create-a-static-one-way-send-port-to-send-the-batched-edi-interchange"></a>创建静态单向发送端口以发送批处理 EDI 交换  

1. 在中[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理控制台中，右键单击**发送端口**节点下的**BizTalk Application 1**节点，指向**新建**，然后单击**静态单向发送端口。**  

2. 在中**发送端口属性**对话框中，发送端口名称。  

3. 在中**传输**部分中，选择**文件**有关**类型**，然后单击**配置**。  

4. 输入一个文件夹**目标文件夹**，和一个掩码**文件掩码**，如 **\*.txt**。  

5. 单击“确定” 。  

6. 在中**发送管道**，选择**EdiSend**。  

7. 在控制台树中，选择**筛选器**。 上**筛选器**页上，输入将订阅批中消息的筛选器表达式。 例如，选择**BTS。ReceivePortName**有关**属性**， **==** 有关**运算符**，和刚创建的用于的接收端口的名称**值**。  

8. 单击“确定” 。  

9. 在控制台树中，单击**发送端口**。 在中**发送端口**窗格中，右键单击您的发送端口，然后依次**启动**。  

##### <a name="to-create-a-party-and-a-business-profile-for-party-a"></a>为参与方 A 创建团队和业务配置文件  

1. 右键单击**参与方**中的节点[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理控制台中，依次指向**新建**，然后单击**方**。  

2. 输入中的参与方的名称**名称**文本框中，，然后单击**确定**。  

   > [!NOTE]
   >  通过选择**本地 BizTalk 处理接收的来自此参与方发送消息的参与方或支持消息**复选框，可以指定要创建的参与方是为同一组织与托管[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]. 此基础，某些属性将启用，或禁用在创建协议时。 但是，对于此演练中，可以选中此复选框。  

3. 右键单击参与方名称，指向**新建**，然后单击**业务配置文件**。  

4. 在中**配置文件属性**对话框中，在**常规**页上，输入**PartyA_Profile**中**名称**文本框。  

   > [!NOTE]
   >  创建一个参与方时，还创建配置文件。 可以重命名，并使用该配置文件而不是创建一个新。 若要重命名配置文件，请右键单击该配置文件，然后选择**属性**。 在中**常规**页上，指定配置文件的名称。  

##### <a name="to-create-a-party-and-a-business-profile-for-party-b"></a>为参与方 B 创建团队和业务配置文件  

1. 右键单击**参与方**中的节点[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理控制台中，依次指向**新建**，然后单击**方**。  

2. 输入中的参与方的名称**名称**文本框中，，然后单击**确定**。  

   > [!NOTE]
   >  通过选择**本地 BizTalk 处理接收的来自此参与方发送消息的参与方或支持消息**复选框，可以指定要创建的参与方是为同一组织与托管[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]. 此基础，某些属性将启用，或禁用在创建协议时。 但是，对于此演练中，可以选中此复选框。  

3. 右键单击参与方名称，指向**新建**，然后单击**业务配置文件**。  

4. 在中**配置文件属性**对话框中，在**常规**页上，输入**PartyB_Profile**中**名称**文本框。  

   > [!NOTE]
   >  创建一个参与方时，还创建配置文件。 可以重命名，并使用该配置文件而不是创建一个新。 若要重命名配置文件，请右键单击该配置文件，然后选择**属性**。 在中**常规**页上，指定配置文件的名称。  

##### <a name="to-create-an-agreement-between-the-two-business-profiles"></a>在两个业务配置文件之间创建协议  

1. 右键单击**PartyA_Profile**，依次指向**新建**，然后单击**协议**。  

2. 在**常规属性**页上，对于**名称**文字框中，输入协议的名称。  

3. 从**协议**下拉列表中，选择**X12**。  

4. 在中**第二个合作伙伴**部分中，从**名称**下拉列表中，选择**参与**。  

5. 在中**第二个合作伙伴**部分中，从**配置文件**下拉列表中，选择**PartyB_Profile**。  

    你将注意到两个新选项卡获取旁边添加**常规**选项卡。每个选项卡配置一个单向协议，每个单向协议代表消息的一次完整事务（包括消息传输和确认传输）。  

6. 在中**常规**选项卡中，**常规属性**页上，在**公用主机设置**部分中，选择**打开报告**，，然后选择**存储消息负载以用于报告**。  

7. 在执行以下任务**PartyA-> 参与**选项卡。  

   1. 上**标识符**页**交换设置**部分中，输入限定符和标识符字段的值 (**ISA5**， **ISA6**， **ISA7**，并**ISA8**) 的测试消息中这些标头字段的值相对应。  

      > [!NOTE]
      >  [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 要求为发送方和接收方的限定符和标识符字段输入值才能执行协议解析。 它将匹配的值**ISA5**， **ISA6**， **ISA7**，以及**ISA8**与协议属性中的交换标头中。 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 此外将通过匹配发送方限定符和标识符 （不接收方限定符和标识符） 来解析协议。 如果 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 无法解析协议，则将使用后备协议属性。  
      > 
      > [!NOTE]
      >  如果将"EDI 接口开发人员教程"中的 SamplePO.txt 文件用作测试消息，设置**ISA5**到**ZZ**， **ISA6**到**THEM**， **ISA7**到**ZZ**，并**ISA8**到**美国**。  

   2. 上**验证**页**交换设置**部分中，请确保**检查重复的 isa13**选项处于未选中状态。  

      > [!NOTE]
      >  清除**检查重复的 isa13**属性使您能够接收同一消息的多个实例。  

   3. 上**字符集和分隔符**页**交换设置**部分中，选择**CR LF**选项。  

   4. 上**本地主机设置**页**交换设置**部分的**入站消息处理选项**框中，选择**拆分交换为事务集-出错时挂起事务集**选项。  

      > [!NOTE]
      >  若要开始使用此解决方案，我们将通过选择此选项来拆分该交换。 更高版本，作为的一部分[测试演练](../core/walkthrough-x12-receiving-batched-edi-interchanges.md#BKMK_Proc)下面的过程，我们将配置解决方案以保留该交换。  

   5. 上**发送端口**页**交换设置**部分中，将前面创建的发送端口相关联。 在中**发送端口**网格下**名称**列，再单击某个空单元格，并从下拉列表中，选择发送端口。  

   6. 上**信封**页**事务集设置**部分中，输入在网格的第一行中的所有列的值。  


      |       使用此选项       |                                                                                                                                    执行的操作                                                                                                                                    |
      |----------------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
      |     **Default**      |   选择**默认**。 **注意：** 选择此行作为默认值的值**GS1**， **GS2**， **GS3**， **GS7**，和**GS8**使用即使的值**事务类型**，**版本/发行版**，并且**目标命名空间**不是消息的匹配项。    |
      | **事务类型** |                                                                                                     选择你的测试消息的消息类型**850 – 采购订单**。                                                                                                      |
      | **版本/发行版**  |                                                                                                                        输入 EDI 版本， **00401**。                                                                                                                         |
      | **目标命名空间** |                                                                                                                选择**<http://schemas.microsoft.com/Edi/X12>**。                                                                                                                |
      |       **GS1**        |                                                                                           验证是否已选中的测试消息的消息类型， **PO-采购订单 (850)**。                                                                                           |
      |       **GS2**        |                                                                                                      例如，应用程序发送方输入的值**Purchasing**。                                                                                                      |
      |       **GS3**        |                                                                                                    例如，应用程序接收方输入的值**OrderControl**。                                                                                                    |
      |       **GS4**        | 选择所需的日期格式。 **注意：** 需要下拉列表中选择一个值，而不仅仅是单击该字段以显示默认值。 如果你仅单击字段，而没有从下拉列表中选择值，则实际上并未选择值。 |
      |       **GS5**        |                                                                                                                      选择所需的时间格式。                                                                                                                       |
      |       **GS7**        |                                                                                                                选择**X-公认的标准委员会 X12**。                                                                                                                |
      |       **GS8**        |                                                                                                             验证已输入 EDI 版本， **00401**。                                                                                                             |

      > [!NOTE]
      >  [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 将设置 GS01、 GS02、 GS03、 GS04、 GS05、 GS07 和基于为输入的值对出站确认的 GS08**事务类型**，**版本/发行版**，和**目标命名空间**。 发送管道尝试将事务集类型、X12 版本和目标命名空间与消息标头中的对应值相匹配。 如果成功，它将使用与关联的 GS 值**事务类型**，**版本/发行版**，并**目标命名空间**值。  

8. 在执行以下任务**参与-> PartyA**选项卡。  

   > [!NOTE]
   >  在本演练中，我们指定的选项卡中所需的值，以便可以成功创建协议。 若要成功创建协议，两个单向协议选项卡必须具有定义为值**ISA5**， **ISA6**， **ISA7**，以及**ISA8**。  

   1.  上**标识符**页**交换设置**部分中，输入限定符和标识符字段的值 (**ISA5**， **ISA6**， **ISA7**，并**ISA8**) 的测试消息中这些标头字段的值相对应。  

       > [!NOTE]
       >  如果将"EDI 接口开发人员教程"中的 SamplePO.txt 文件用作测试消息，设置**ISA5**到**ZZ**， **ISA6**到**美国**， **ISA7**到**ZZ**，并**ISA8**到**THEM**。  

9. 单击 **“应用”**。  

10. 单击“确定” 。 中列出新添加的协议**协议**一部分**参与方和业务配置文件**窗格。 默认情况下，启用新添加的协议。  

### <a name="testing-the-walkthrough"></a>测试演练  
 本部分提供有关如何测试演练的信息。  

####  <a name="BKMK_Proc"></a> 若要测试演练  

1. 在 Windows 资源管理器中，打开与接收位置关联的本地文件夹，然后将测试批处理 EDI 交换放入该文件夹。  

   > [!NOTE]
   >  对于测试消息，可以使用由发送批处理交换演练中的解决方案生成的批处理交换输出。 此示例消息将包含两个事务集。  

2. 打开与上面创建的发送端口关联的文件夹。 验证该文件夹是否包含两个新文件，以及每个文件是否为包含测试批处理消息中的一个事务集的 850 交换。  

3. 在中[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理控制台中，单击**方**节点，单击任何先前创建的协议的一部分的两个业务配置文件。 在中**协议**部分中，右键单击协议，然后单击**属性**。  

4. 在中**协议属性**对话框中，在**本地主机设置**页**交换设置**部分的**入站消息处理选项**框中，选择**保留交换-出错时挂起交换**或**保留交换-出错时挂起事务集**单击**确定**。  

5. 单击**主机实例**下**平台设置**节点，右键单击**BizTalkServerApplication**，然后单击**重启**。  

6. 在 Windows 资源管理器中，打开与接收位置关联的本地文件夹，然后再次将该测试批处理 EDI 交换放入该文件夹。  

7. 在 Windows 资源管理器中，打开与上面创建的发送端口关联的文件夹。 验证该文件夹当前是否仅包含一个新文件，以及此文件是否为包含测试批处理消息中的两个 850 事务集的交换。  

## <a name="see-also"></a>请参阅  
 [开发和配置 BizTalk Server EDI 解决方案](../core/developing-and-configuring-biztalk-server-edi-solutions.md)   
 [拆分批处理的 EDI 交换](../core/splitting-a-batched-edi-interchange.md)   
 [拆分 HIPAA 子文档](../core/splitting-hipaa-subdocuments.md)   
 [保留收到的批处理 EDI 交换](../core/preserving-a-received-batched-edi-interchange.md)   
 [演练 (X12)： 发送批处理的 EDI 交换](../core/walkthrough-x12-sending-batched-edi-interchanges.md)   
 [演练 (X12)： 接收 EDI 交换并发送回确认信息](../core/walkthrough-x12--receive-edi-interchanges-and-send-back-an-acknowledgement.md)   
 [演练 (X12)：发送 EDI 交换](../core/walkthrough-x12-sending-edi-interchanges.md)