---
title: 演练 (X12)： 发送批处理 EDI 交换 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: b80ea79b-6112-49bd-90e8-9a0a0e604df8
caps.latest.revision: 54
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 25a17a950cf857c21fe9f7d913ba58a5a68c4512
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36973214"
---
# <a name="walkthrough-x12-sending-batched-edi-interchanges"></a>演练 (X12)：发送批处理 EDI 交换
本演练提供了一组使用 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 为在参与方间发送批处理 EDI 交换创建解决方案的分步操作过程。  

## <a name="prerequisites"></a>必要條件  
 必须以 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理员组或 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] B2B Operators 组成员的身份登录。  

## <a name="how-the-solution-sends-batched-edi-interchanges"></a>解决方案如何发送批处理 EDI 交换  
 该解决方案将执行以下操作：  

1. 接收位置接收 EDI 交换**参与方 A**。  

   > [!NOTE]
   >  此列表中的事件可能不会按所示顺序发生。  

2. 接收管道将 EDI 格式的交换转换为内部 XML 格式。 接收管道确定要对交换进行批处理。 因此，BatchMarkerReceivePipeline 组件会升级 `EDI.ToBeBatched==True` 和 `EDI.BatchId` 属性。 然后，它将交换放入 MessageBox 中。  

3. 批处理业务流程从 MessageBox 检索收到的交换，因为它基于 `EDI.ToBeBatched==True` 和 `EDI.BatchId==%BatchID%` 订阅该消息。  

4. 接收位置接收来自发送第一个交换的同一参与方的第二个 EDI 交换。  

5. 接收位置按照第 2 步中的说明处理交换，然后将交换放入 MessageBox 中。  

6. 批处理业务流程按照第 3 步中的说明检索交换。  

7. 在满足释放条件之后（释放条件定义了交换是如何匹配的），批处理业务流程就会组装包含所有交换的交换，然后升级 `EDI.ToBeBatched==False`、`EDI.BatchName` 和 `EDI.DestinationPartyName` 上下文属性。 它将批处理交换放入 MessageBox 中。  

8. 发送端口通过订阅上下文属性 `EDI.ToBeBatched`==False、`EDI.BatchName` 和 `EDI.DestinationPartyName` 来提取批处理交换。  

9. 发送管道对批处理交换的信封应用其他属性，然后将交换发送到目标参与方**参与方 B**。  

    > [!NOTE]
    >  有关详细信息，请参阅[装配批处理的 EDI 交换](../core/assembling-a-batched-edi-interchange.md)。  

   下图显示出此解决方案的结构。  

   ![发送批处理 EDI 交换](../core/media/93a09e3c-476d-4bd2-a0e3-b5b219858791.gif "93a09e3c-476d-4bd2-a0e3-b5b219858791")  

## <a name="the-functionality-in-this-solution"></a>此解决方案中的功能  
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

## <a name="configuring-and-testing-the-walkthrough"></a>配置和测试演练  
 该解决方案所需的过程包括：  

- 将必需的消息架构添加到 BizTalk 项目，然后生成并部署该项目，以使架构可供 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 在处理消息时使用。  

- 更新中的 SQL 适配器的轮询间隔**BatchControlMessageReccvLoc**接收位置，以便批处理业务流程将立即激活单击时**启动**按钮发送将激活批处理业务流程实例的控制消息。  

- 为 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 创建一个接收端口，以从参与方接收 EDI X12 编码的 .txt 输入消息。  

- 为参与方 A 和参与方 B 创建一个参与方（贸易合作伙伴）。  

- 为两个贸易合作伙伴分别创建一个业务配置文件。  

- 通过配置要接收的消息的 EDI 属性，在两个配置文件之间创建一个协议。 为要发送的批处理消息配置 EDI 属性。 对于此解决方案，只要收到两个 850 交换，就会配置这些协议，以便 BizTalk Server 向参与方 B 发送批。  

- 为 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 创建一个发送端口来将批处理 EDI 交换发送到贸易合作伙伴。 此发送端口将是一个静态单向发送端口。  

- 将发送端口与处理交换并对其进行批量处理的协议相关联。  

- 将两个测试 EDI 交换放入与接收位置关联的本地文件夹，并验证 BizTalk Server 是否已将批处理交换放入与发送端口关联的文件夹。  

### <a name="configuring-the-walkthrough"></a>配置演练  
 本部分介绍配置本演练的步骤。  

##### <a name="to-deploy-the-message-schema"></a>部署消息架构  

1. 在 [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] 中，创建或打开 BizTalk 项目。  

   > [!NOTE]
   >  本主题假定你已从你的应用程序添加了对包含 EDI 架构、管道和业务流程的 BizTalk EDI 应用程序的引用。 如果没有，请参阅[如何添加对 BizTalk Server EDI 应用程序的引用](http://msdn.microsoft.com/library/7af066fb-372f-4709-b566-c8d6b4a9d782)。  

2. 右键单击你的项目，指向**外**，然后单击**现有项**。 移动到 [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]XSD_Schema\EDI\X12\00401，然后双击与测试消息对应的架构。  

   > [!NOTE]
   >  如果 EDI 架构尚未解压缩到 \XSD_Schema\EDI 文件夹，则执行**MicrosoftEdiXSDTemplates.exe** \XSD_Schema\EDI 文件夹将架构解压缩到默认文件夹中的文件。  
   > 
   > [!NOTE]
   >  对于测试消息，您可以使用在 EDI 接口开发人员教程中使用的 850 示例消息。 此文件是中的 SamplePO.txt [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]SDK\EDI Interface Developer Tutorial\\。 如果要这样做，您必须使用位于 [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]SDK\EDI Interface Developer Tutorial\Inbound_EDI 的架构 x12_00401_850.xsd。  

3. 设置程序集密钥文件，然后生成并部署该程序集。  

##### <a name="to-update-the-polling-interval"></a>更新轮询间隔  

1. 在中[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理控制台中，打开**BizTalk 组**，**应用程序**， **BizTalk EDI 应用程序**节点，和**接收位置**节点。 下**接收位置**节点，右键单击**BatchControlMessageRecvLoc**，然后单击**属性**。  

2. 对于 SQL 传输类型，请单击**配置**。  

3. 在中**SQL 传输属性**对话框框中，将轮询间隔设置为较小的值。 例如，可以更改**轮询度量单位**到**秒**，而不是分，若要更改的轮询间隔为 5 秒。  

   > [!NOTE]
   >  更改轮询间隔可确保将立即激活批处理业务流程。  

4. 单击**确定**，然后单击**确定**试。  

##### <a name="to-create-a-one-way-receive-port-to-receive-the-edi-messages-to-be-batched"></a>创建接收要进行批处理的 EDI 消息的单向接收端口  

1. 创建用于接收要进行批处理的 EDI 消息的本地文件夹。  

2. 在中[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理控制台中，右键单击**接收端口**节点下的**BizTalk Application 1**节点，指向**新建**，然后单击**单向接收端口。**  

3. 接收端口的名称，然后单击**接收位置**在控制台树中。  

4. 单击 **“新建”**。  

5. 名称的接收位置，选择**文件**有关**类型**，然后单击**配置**。  

6. 输入一个文件夹**接收文件夹**，和一个掩码**文件掩码**，如 **\*.txt**。  

7. 单击“确定” 。  

8. 有关**接收管道**，选择**EdiReceive**。  

9. 单击**确定**，然后单击**确定**试。  

10. 在控制台树中，单击**接收位置**。 在中**接收位置**窗格中，右键单击将接收位置，然后依次**启用**。  

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

   4. 上**批配置**页**交换设置**部分中，执行以下操作：  

      1.  单击**新的批处理**。  

      2.  下**标识**部分中，对于**批处理名称**文本输入`Batch1`。  

      3.  下**筛选器**部分中，单击**筛选器**按钮，然后在**批处理筛选器**对话框框中，执行以下操作：  

          1.  单击下的空单元格**属性**列并选择**BTS。ReceivePortName**。  

          2.  单击下的空单元格**运算符**列并选择**==**。  

          3.  单击下的空单元格**值**列并输入之前创建的接收端口的名称。  

          4.  单击“确定” 。  

      4.  下**发行**部分中，选择**的最大数量的事务集**选项，从下拉列表中选择**交换**，并在文本框中输入的数将进行批处理的交换。 在此解决方案中，您将批处理两个交换，因此在文本框中，输入`2`。  

      5.  下**激活**部分中，选择**立即启动**。  

   5. 上**信封**页**事务集设置**部分中，输入在网格的第一行中的所有列的值。  


      |       使用此选项       |                                                                                                                                    执行的操作                                                                                                                                    |
      |----------------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
      |     **Default**      |   选择**默认**。 **注意：** 选择此行作为默认值的值**GS1**， **GS2**， **GS3**， **GS7**，和**GS8**使用即使的值**事务类型**，**版本/发行版**，并且**目标命名空间**不是消息的匹配项。    |
      | **事务类型** |                                                                                                     选择你的测试消息的消息类型**850 – 采购订单**。                                                                                                      |
      | **版本/发行版**  |                                                                                                                        输入 EDI 版本， **00401**。                                                                                                                         |
      | **目标命名空间** |                                                                                                         选择**<http://schemas.microsoft.com/BizTalk/Edi/X12/2006>**。                                                                                                          |
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

##### <a name="to-create-a-static-one-way-send-port-to-send-the-batched-edi-interchange"></a>创建静态单向发送端口以发送批处理 EDI 交换  

1. 创建要将批处理 EDI 消息发送到的本地文件夹。  

2. 在中[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理控制台中，右键单击**发送端口**节点下的**BizTalk Application 1**节点，指向**新建**，然后单击**静态单向发送端口。**  

3. 在中**发送端口属性**对话框中，发送端口名称。  

4. 在中**传输**部分中，选择**文件**有关**类型**，然后单击**配置**。  

5. 输入一个文件夹**目标文件夹**，和一个**文件名**，如 **%MessageID%.txt**。  

6. 单击“确定” 。  

7. 在中**发送管道**，选择**EdiSend**。  

8. 在控制台树中，选择**筛选器**。 上**筛选器**页上，执行以下操作：  

   1.  在网格的第一行中，选择**EDI。DestinationPartyName**有关**属性**， **==** 有关**运算符**，为发送到用于的批处理的参与方选择的名称**值**，并**并**有关**分组依据**。  

   2.  在第二行中，选择**EDI。ToBeBatched**有关**属性**， **==** 有关**运算符**，并**False**为**值**，并**并**有关**分组依据**。  

   3.  在第三行中，选择**EDI。BatchName**有关**属性**， **==** 有关**运算符**，和用于批处理的名称**值**。  

9. 单击“确定” 。  

10. 在控制台树中，单击**发送端口**。 在中**发送端口**窗格中，右键单击您的发送端口，然后依次**启动**。  

##### <a name="to-associate-the-send-port-with-the-agreement-created-for-batching"></a>将发送端口与为进行批处理创建的协议相关联  

1.  右键单击先前创建的协议，然后单击**属性**。  

2.  在中**协议属性**对话框中，在**PartyA-> 参与**选项卡上，单击**发送端口**的左窗格中。  

3.  上**发送端口**页**交换设置**部分中，将前面创建的发送端口相关联。 在中**发送端口**网格下**名称**列，再单击某个空单元格，并从下拉列表中，选择发送端口。  

4.  单击“确定” 。  

### <a name="testing-the-walkthrough"></a>测试演练  
 本部分提供有关如何测试演练的信息。  

##### <a name="to-test-the-walkthrough"></a>若要测试演练  

1. 在 Windows 资源管理器中，打开与接收位置关联的本地文件夹，然后将测试 EDI 交换放入该文件夹。  

   > [!NOTE]
   >  对于测试消息，您可以使用在 EDI 接口开发人员教程中使用的 850 示例消息。 此文件是中的 SamplePO.txt [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]SDK\EDI Interface Developer Tutorial\\。 如果要这样做，您必须使用位于 [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]SDK\EDI Interface Developer Tutorial\Inbound_EDI 的架构 x12_00401_850.xsd。  

2. 测试 EDI 交换的第二个副本放入该文件夹中。  

3. 打开与交换的发送端口关联的文件夹，并打开批处理交换。 验证交换是否包含一组 ISA 和 GS 标头以及两个事务集。  

## <a name="see-also"></a>请参阅  
 [开发和配置 BizTalk Server EDI 解决方案](../core/developing-and-configuring-biztalk-server-edi-solutions.md)   
 [配置传出批](../core/configuring-an-outgoing-batch.md)   
 [装配批处理的 EDI 交换](../core/assembling-a-batched-edi-interchange.md)   
 [装配批处理的 EDI 交换](../core/assembling-a-batched-edi-interchange.md)   
 [演练 (X12)： 接收 EDI 交换并发送回确认信息](../core/walkthrough-x12--receive-edi-interchanges-and-send-back-an-acknowledgement.md)   
 [演练 (X12)：发送 EDI 交换](../core/walkthrough-x12-sending-edi-interchanges.md)