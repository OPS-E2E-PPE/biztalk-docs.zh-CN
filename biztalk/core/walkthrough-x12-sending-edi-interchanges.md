---
title: 演练 (X12)： 发送 EDI 交换 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 05533821-b9eb-44bc-af65-b6fb0b545137
caps.latest.revision: 36
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 032fffbe22d397597288d11590995ec5c74708d5
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "37007558"
---
# <a name="walkthrough-x12-sending-edi-interchanges"></a>演练 (X12)：发送 EDI 交换
本演练将介绍使用 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 为发送 EDI 交换创建解决方案的分步操作过程。  

## <a name="prerequisites"></a>必要條件  
 必须以 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理员组或 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] B2B Operators 组成员的身份登录。  

## <a name="how-the-solution-sends-edi-interchanges"></a>解决方案如何发送 EDI 交换  
 该解决方案将执行以下操作：  

1.  一个单向 FILE 接收端口从 Fabrikam 接收 EDI 消息。  

2.  使用 EdiReceive 管道，接收端口将检查消息，并将其转换为 XML。 该接收端口随后将测试消息放入 MeassageBox。  

3.  一个静态单向发送端口从 MessageBox 提取 XML 消息。  

4.  该静态单向发送端口根据消息架构验证 EDI 消息、将 EDI 消息序列化为 EDI 交换，然后将 EDI 消息发送到贸易合作伙伴 Contoso 的本地文件夹。  

## <a name="the-functionality-in-this-solution"></a>此解决方案中的功能  
 本演练中使用了下列功能：  

- 本演练中并不测试接收确认。 若要了解如何接收确认，请参阅演示[演练 (X12)： 接收 EDI 交换并发送回确认信息](../core/walkthrough-x12--receive-edi-interchanges-and-send-back-an-acknowledgement.md)  

- 该解决方案专用于使用 X12 编码而不是 EDIFACT 编码的交换。  

  > [!NOTE]
  >  用于 HIPAA 和 EDIFACT 编码的配置与用于 X12 编码的配置几近相同。  

- EDI 类型和扩展的验证将在传出交换上执行。  

- 该解决方案使用传输类型为“FILE”的静态单向发送端口。  

  > [!NOTE]
  >  除了使用静态单向发送端口外，您也可使用静态双向发送端口来发送交换和接收确认。 此外，您还可使用动态单向发送端口来发送交换。 使用动态发送端口的详细信息，请参阅[配置为发送 EDI 交换和确认的动态发送端口](../core/configuring-a-dynamic-send-port-to-send-edi-interchanges-and-acknowledgments.md)。  

  > [!NOTE]
  >  您可使用一个 HTTP 适配器和 AS2 传输类型。 有关执行此操作的详细信息，请参阅[演练 (AS2): 使用同步 MDN 通过 AS2 发送 EDI](../core/walkthrough-as2-sending-edi-over-as2-with-a-synchronous-mdn.md)或[演练 (AS2): 使用异步 MDN 通过 AS2 发送 EDI](../core/walkthrough-as2-sending-edi-over-as2-with-an-asynchronous-mdn.md)。  

- 系统将启用 EDI 报告功能，并保存事务集以便从交换状态报告进行查看。  

- 出于方便目的，该解决方案使用一个接收位置来接收测试消息。  

  下图显示使用静态单向发送端口的该解决方案的结构。  

  ![发送 EDI 交换](../core/media/6915024c-687c-4076-a730-3f7b9d2db7fb.gif "6915024c-687c-4076-a730-3f7b9d2db7fb")  

## <a name="configuring-and-testing-the-walkthrough"></a>配置和测试演练  
 该解决方案所需的过程包括：  

- 将必需的消息架构添加到 BizTalk 项目，然后生成并部署该项目，使 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 在处理出站交换时可以使用相应架构。  

- 为 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 创建接收端口和位置以接收 EDI 交换。 此接收位置与 Fabrikam 存放要发送到 Contoso 的 EDI 交换的 file 文件夹相关联。 接收位置将使用 EdiReceive 接收管道。  

- 为 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 创建发送端口以将 EDI 交换发送到 Contoso。 在本演练中，您将创建一个静态单向发送端口。  

- 为 Fabrikam 和 Contoso 创建参与方（贸易合作伙伴）。  

- 为两个贸易合作伙伴分别创建一个业务配置文件。  

- 通过配置要接收的消息的 EDI 属性，在两个配置文件之间创建一个协议。  

- 使用测试 EDI 交换测试演练。  

  > [!NOTE]
  >  对于测试消息，您可以使用在 EDI 接口开发人员教程中使用的 SamplePO.txt 文件。 该文件位于 [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)] SDK\EDI Interface Developer Tutorial\ 文件夹。 这是一个 X12 850 消息。  

### <a name="configuring-the-walkthrough"></a>配置演练  
 本部分介绍配置本演练的步骤。  

##### <a name="to-deploy-the-message-schema"></a>部署消息架构  

1. 在 [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] 中，创建或打开 BizTalk 项目。  

   > [!NOTE]
   >  本主题假定你已从你的应用程序添加了对包含 EDI 架构、管道和业务流程的 BizTalk EDI 应用程序的引用。 如果没有，请参阅[如何添加对 BizTalk Server EDI 应用程序的引用](http://msdn.microsoft.com/library/7af066fb-372f-4709-b566-c8d6b4a9d782)。  

2. 右键单击你的项目，指向**外**，然后单击**现有项**。 移动到您架构所在的 [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)] XSD_Schema\EDI 文件夹中，然后双击架构。  

   > [!NOTE]
   >  如果 EDI 架构尚未解压缩到 \XSD_Schema\EDI 文件夹，则执行**MicrosoftEdiXSDTemplates.exe** \XSD_Schema\EDI 文件夹将架构解压缩到默认文件夹中的文件。  
   > 
   > [!NOTE]
   >  如果您使用 EDI 接口开发人员教程中使用的 SamplePO.txt 文件，则必须使用 X12_00401_850.xsd 架构，该架构位于 [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]SDK\EDI Interface Developer Tutorial\Inbound_EDI 文件夹中。 不能使用位于 [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)] XSD_Schema 文件夹的 X12 850 架构。  

3. 将程序集密钥文件添加到项目中，然后生成并部署该程序集。  

##### <a name="to-create-a-one-way-receive-port-for-fabrikam-to-receive-the-edi-interchange"></a>若要创建一个单向接收端口 （对于 Fabrikam) 接收 EDI 交换  

1. 在 Windows 资源管理器中，创建一个用于接收交换的本地文件夹。  

2. 在中[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理控制台中，右键单击**接收端口**节点下的**BizTalk Application 1**节点，指向**新建**，然后单击**单向接收端口**。  

3. 接收端口的名称，然后单击**接收位置**在控制台树中。  

4. 单击 **“新建”**。  

5. 名称的接收位置，选择**文件**有关**类型**，然后单击**配置**。  

6. 输入一个文件夹**接收文件夹**，并输入 **\*.txt**文件掩码。  

7. 单击“确定” 。  

8. 有关**接收管道**，选择**EdiReceive**。  

9. 单击**确定**，然后单击**确定**试。  

10. 在控制台树中，单击**接收位置**。 在中**接收位置**窗格中，右键单击将接收位置，然后依次**启用**。  

##### <a name="to-create-a-static-one-way-send-port-for-contoso-to-send-the-edi-interchange"></a>（为 Contoso) 创建静态单向发送端口以发送 EDI 交换  

1. 在 Windows 资源管理器中，创建一个用于接收 EDI 交换的本地文件夹。  

2. 在中[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理控制台中，右键单击**发送端口**节点下的**BizTalk Application 1**节点，指向**新建**，然后单击**静态单向发送端口**。  

3. 在中**发送端口属性**对话框中，发送端口名称。  

4. 在中**传输**部分中，选择**类型**，例如，**文件**。  

5. 如果使用的文件类型，请单击**配置**。 在中**目标文件夹**，浏览到要接收交换的文件夹。 有关**文件名**，输入 **%MessageID%.edi**。 单击“确定” 。  

6. 在中**发送管道**，选择**EdiSend**。  

7. 在控制台树中，选择**筛选器**，并输入要用于订阅消息的发送端口的筛选器表达式。 例如，您可将接收原始测试消息的接收位置用作筛选器表达式。 为此，对于**属性**，输入**BTS。ReceivePortName**; 对于**运算符**，输入**==**; 对于**值**输入到创建的接收端口的名称从 Fabrikam 接收 XML 消息。  

   > [!NOTE]
   >  您可用所选的另一个属性进行筛选，例如，用 BTS.MessageType 进行筛选。  

8. 单击“确定” 。  

9. 单击**发送端口**节点中管理控制台中，右键单击您的发送端口，然后依次**启动**。  

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

##### <a name="to-create-an-agreement-between-the-two-business-profiles"></a>在两个业务配置文件之间创建协议  

1. 右键单击**Fabrikam_Profile**，依次指向**新建**，然后单击**协议**。  

2. 在**常规属性**页上，对于**名称**文字框中，输入协议的名称。  

3. 从**协议**下拉列表中，选择**X12**。  

4. 在中**第二个合作伙伴**部分中，从**名称**下拉列表中，选择**Contoso**。  

5. 在中**第二个合作伙伴**部分中，从**配置文件**下拉列表中，选择**Contoso_Profile**。  

    你将注意到两个新选项卡获取旁边添加**常规**选项卡。每个选项卡配置一个单向协议，每个单向协议代表消息的一次完整事务（包括消息传输和确认传输）。  

6. 在中**常规**选项卡中，**常规属性**页上，在**公用主机设置**部分中，选择**打开报告**，，然后选择**存储消息负载以用于报告**。  

7. 在执行以下任务**Fabrikam-> Contoso**选项卡。  

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

   4. 上**发送端口**页**交换设置**部分中，关联将从 Fabrikam 接收 EDI 交换的发送端口。 在中**发送端口**网格下**名称**列，再单击某个空单元格，并从下拉列表中，选择创建用于从 Fabrikam 接收 EDI 交换的发送端口。  

   5. 上**验证**页**事务集设置**部分中，保留**EDI 类型验证**检查，并检查**扩展验证**.  

   6. 如果你使用附带的标准架构之一[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]，然后在**本地主机设置**页下**事务集设置**部分中，选择要使用的架构的命名空间处理传入的交换。  


      |       使用此选项       |                           执行的操作                            |
      |----------------------|-----------------------------------------------------------------|
      |     **Default**      |                选中列中的复选框                |
      |     **对于 ST1**      |                选择**850 – 采购订单**。                 |
      |       **GS2**        |                         输入**THEM**。                         |
      | **目标 Namespace** | 选择**<http://schemas.microsoft.com/BizTalk/EDI/X12/2006>**。 |

      > [!NOTE]
      >  设置属性可以使 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 确定处理传入 850 交换时使用的架构。 如果某一交换的 GS02 和 ST01 的值是在网格行上输入的，则将使用同一行的目标命名空间来确定要使用的架构。  

   7. 上**信封**页**事务集设置**部分中，输入在网格的第一行中的所有列的值。  


      |       使用此选项       |                                                                                                                                               执行的操作                                                                                                                                               |
      |----------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
      |     **Default**      | 选择中的复选框**默认**列。 **注意：** 选择此行作为默认值的值**GS1**， **GS2**， **GS3**， **GS7**，和**GS8**使用即使的值**事务类型**，**版本/发行版**，并且**目标命名空间**不是消息的匹配项。 |
      | **事务类型** |                                                                                                                选择你的测试消息的消息类型**850 – 采购订单**。                                                                                                                 |
      | **版本/发行版**  |                                                                                                                                   输入 EDI 版本， **00401**。                                                                                                                                    |
      | **目标命名空间** |                                                                                                                    选择**<http://schemas.microsoft.com/BizTalk/Edi/X12/2006>**。                                                                                                                     |
      |       **GS1**        |                                                                                                      验证是否已选中的测试消息的消息类型， **PO-采购订单 (850)**。                                                                                                      |
      |       **GS2**        |                                                                                                                               输入应用程序发送方的值。                                                                                                                                |
      |       **GS3**        |                                                                                                                              输入应用程序接收方的值。                                                                                                                               |
      |       **GS4**        |            选择所需的日期格式。 **注意：** 需要下拉列表中选择一个值，而不仅仅是单击该字段以显示默认值。 如果你仅单击字段，而没有从下拉列表中选择值，则实际上并未选择值。            |
      |       **GS5**        |                                                                                                                                 选择所需的时间格式。                                                                                                                                  |
      |       **GS7**        |                                                                                                                           选择**X-公认的标准委员会 X12**。                                                                                                                           |
      |       **GS8**        |                                                                                                                        验证已输入 EDI 版本， **00401**。                                                                                                                        |

      > [!NOTE]
      >  [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 将设置 GS01、 GS02、 GS03、 GS04、 GS05、 GS07 和基于为输入的值对出站确认的 GS08**事务类型**，**版本/发行版**，和**目标命名空间**。 发送管道尝试将事务集类型、X12 版本和目标命名空间与消息标头中的对应值相匹配。 如果成功，它将使用与关联的 GS 值**事务类型**，**版本/发行版**，并**目标命名空间**值。  

8. 在执行以下任务**Contoso-> Fabrikam**选项卡。  

   > [!NOTE]
   >  在本演练中，我们指定的选项卡中所需的值，以便可以成功创建协议。 若要成功创建协议，两个单向协议选项卡必须具有定义为值**ISA5**， **ISA6**， **ISA7**，以及**ISA8**。  

   1.  上**标识符**页**交换设置**部分中，输入限定符和标识符字段的值 (**ISA5**， **ISA6**， **ISA7**，并**ISA8**) 的测试消息中这些标头字段的值相对应。  

       > [!NOTE]
       >  如果将"EDI 接口开发人员教程"中的 SamplePO.txt 文件用作测试消息，设置**ISA5**到**ZZ**， **ISA6**到**美国**， **ISA7**到**ZZ**，并**ISA8**到**THEM**。  

9. 单击 **“应用”**。  

10. 单击“确定” 。 中列出新添加的协议**协议**一部分**参与方和业务配置文件**窗格。 默认情况下，启用新添加的协议。  

### <a name="testing-the-walkthrough"></a>测试演练  
 本部分提供有关如何测试演练的信息。  

##### <a name="to-test-the-walkthrough"></a>若要测试演练  

1. 在 Windows 资源管理器中，将测试 EDI 交换放置到本地接收文件夹中。  

   > [!NOTE]
   >  对于测试消息，您可以使用在 EDI 接口开发人员教程中使用的 SamplePO.txt 文件。 该文件位于 [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]SDK\EDI Interface Developer Tutorial 文件夹。 这是一个 X12 850 消息。 如果您使用此消息，则必须已经部署了 X12_00401_850.xsd 架构，该架构位于 [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]SDK\EDI Interface Developer Tutorial\Inbound_EDI 文件夹中。 不能使用位于 [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)] XSD_Schema 文件夹的 X12 850 架构。  

2. 在 Windows 资源管理器中，打开为发送端口指定的目标文件夹。 验证该文件夹包含符合以下条件的输出 EDI 交换：此交换的 ISA、GS 和 ST 标头与您在协议属性中输入的值相匹配。  

## <a name="see-also"></a>请参阅  
 [开发和配置 BizTalk Server EDI 解决方案](../core/developing-and-configuring-biztalk-server-edi-solutions.md)