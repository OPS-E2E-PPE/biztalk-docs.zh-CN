---
title: 演练 (X12):接收 EDI 交换并发送回确认 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 25d2b5f3-6bd1-413c-aace-e4dd71f80403
caps.latest.revision: 45
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 2c315300a8ca7df2e27c2846344a5c68b7b38596
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65397130"
---
# <a name="walkthrough-x12-receiving-edi-interchanges-and-sending-back-an-acknowledgement"></a>演练 (X12):接收 EDI 交换并发送回确认
本演练提供了为使用接收 EDI 交换创建解决方案的分步操作过程一[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]。 在此解决方案中，EDI 交换从贸易合作伙伴 （Fabrikam) 发送到另一个贸易合作伙伴 Contoso。  

## <a name="prerequisites"></a>先决条件  
 必须以成员的身份登录[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理员或[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]B2B Operators 组。  

## <a name="how-the-solution-receives-edi-interchanges"></a>解决方案如何接收 EDI 交换  
 该解决方案将执行以下操作：  

> [!NOTE]
>  显示的顺序可能不是此列表中的事件。  

1.  接收来自贸易合作伙伴 Fabrikam 的平面文件 EDI 交换。  

2.  验证针对其架构的 EDI 交换，将消息拆装成 XML，并将消息 XML 放置到 MessageBox 中。  

3.  生成一个 997 确认已接收的 EDI 交换，并放置到 MessageBox 中。  

4.  生成 TA1 确认已接收的 EDI 交换，并放置到 MessageBox 中。  

5.  提取消息 XML 通过单向发送端口，并组装消息 EDI 交换。  

6.  向 Contoso 发送 EDI 交换。  

7.  提取 997 XML 通过单向发送端口，并组装 997 EDI 交换。  

8.  将 997 交换发送至 Fabrikam。  

9. 提取 TA1 XML 通过单向发送端口，并组装 TA1 EDI 交换。  

10. 将 TA1 交换发送至 Fabrikam。  

## <a name="the-functionality-in-this-solution"></a>此解决方案中的功能  
 对于本演练的目的，将启用以下功能：  

- 该解决方案专用于使用 X12 编码而不是 EDIFACT 交换编码。  

  > [!NOTE]
  >  配置用于 HIPAA 近与用于 X12 编码。 有关如何为 EDIFACT 创建类似解决方案的说明，请参阅[演练 (EDIFACT):接收 EDI 交换并发送回确认](../core/walkthrough-edifact--receive-edi-interchanges-and-send-an-acknowledgement.md)。  

- 将传入交换上执行 EDI 类型和扩展的验证。  

- 将返回到交换的发件人为生成技术和功能确认。  

- 解决方案使用单向接收位置使用 FILE 传输类型。  

  > [!NOTE]
  >  可以使用双向要求响应接收端口和位置来接收消息，但如果这样做，您将不能为接收位置使用 FILE 传输类型。 有关详细信息，请参阅[配置为接收 EDI 消息和确认的端口](../core/configuring-a-port-to-receive-edi-messages-and-acknowledgments.md)。  

- 将启用 EDI 报告，并保存事务集以从交换状态报告进行查看。  

- 出于测试目的，解决方案使用三个发送端口将 EDI 交换和 Ack 创建发送到本地文件夹。  

  下图显示了此解决方案的体系结构：  

  ![接收 EDI 交换](../core/media/c54cca56-c658-4081-9e2f-bf28ba647cda.gif "c54cca56-c658-4081-9e2f-bf28ba647cda")  

## <a name="configuring-and-testing-the-walkthrough"></a>配置和测试演练  
 此解决方案所需的过程包括：  

- 将必需的消息架构添加到 BizTalk 项目，然后生成并部署该项目，使架构可供使用[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]中处理收到的交换。  

- 创建一个单向接收端口[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]以从贸易合作伙伴接收 EDI 交换并生成确认。 此接收位置与 Fabrikam 存放要发送到 Contoso 的 EDI 交换文件文件夹相关联。  

  > [!NOTE]
  >  可以使用双向要求响应接收端口和位置来接收消息，但如果这样做，您将不能为接收位置使用 FILE 传输类型。  

- 创建一个发送端口将 EDI 交换发送到一个本地 Contoso 文件夹，另一个向本地 Fabrikam 文件夹发送 997 确认，另一个向本地 Fabrikam 文件夹发送 TA1 确认。  

- 为 Fabrikam 和 Contoso 创建参与方 （贸易合作伙伴）。  

- 为这两个贸易合作伙伴创建业务配置文件每个。  

- 创建通过配置要接收的消息的 EDI 属性的两个配置文件和确认之间的协议来发送。  

- 测试使用测试 EDI 交换演练。  

  > [!NOTE]
  >  对于测试消息，可以使用在 EDI 接口开发人员教程中使用的 SamplePO.txt 文件。 该文件中都随附[!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]SDK\EDI Interface Developer Tutorial\ 文件夹。 这是一个 X12 850 消息。  

### <a name="configuring-the-walkthrough"></a>配置演练  
 本部分介绍配置本演练的步骤。  

##### <a name="to-deploy-the-message-schema"></a>若要部署的消息架构  

1. 在[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]，创建或打开 BizTalk 项目。  

   > [!NOTE]
   >  本主题假定你已从对 BizTalk EDI 应用程序，其中包含 EDI 架构、 管道和业务流程应用程序中添加了一个引用。 如果没有，请参阅[如何添加对 BizTalk Server EDI 应用程序的引用](http://msdn.microsoft.com/library/7af066fb-372f-4709-b566-c8d6b4a9d782)。  

2. 右键单击你的项目，指向**外**，然后单击**现有项**。 转到您的架构是中的文件夹[!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]XSD_Schema\EDI，然后双击您的架构。  

   > [!NOTE]
   >  如果 EDI 架构尚未解压缩到 \XSD_Schema\EDI 文件夹，则执行**MicrosoftEdiXSDTemplates.exe** \XSD_Schema\EDI 文件夹将架构解压缩到默认文件夹中的文件。  
   > 
   > [!NOTE]
   >  如果您使用 EDI 接口开发人员教程中使用的 SamplePO.txt 文件，则必须使用 X12_00401_850.xsd 架构，在该架构[!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]SDK\EDI Interface Developer Tutorial\Inbound_EDI 文件夹。 必须使用 X12 850 性架构中的[!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]XSD_Schema 文件夹。  

3. 将程序集密钥文件添加到项目中，然后生成并部署该程序集。  

##### <a name="to-create-a-one-way-receive-port-for-fabrikam-to-receive-the-edi-interchange"></a>若要创建一个单向接收端口 （对于 Fabrikam) 接收 EDI 交换  

1. 在 Windows 资源管理器中，创建用于接收交换的本地文件夹。  

2. 在中[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理控制台中，右键单击**接收端口**节点下的**BizTalk Application 1**节点，指向**新建**，然后单击**单向接收端口**。  

3. 接收端口的名称，然后单击**接收位置**在控制台树中。  

4. 单击 **“新建”**。  

5. 名称的接收位置，选择**文件**有关**类型**，然后单击**配置**。  

6. 浏览到文件夹**接收文件夹**文本框。 在此过程的步骤 1 中创建此文件夹。 输入文件掩码，如 **\*.edi**或 **\*.txt**。  

7. 单击“确定” 。  

8. 有关**接收管道**，选择**EdiReceive**。  

9. 单击**确定**中**接收位置属性**对话框。 单击**确定**中再次**接收端口属性**对话框。  

10. 在控制台树中，单击**接收位置**。 在中**接收位置**窗格中，右键单击将接收位置，然后依次**启用**。  

##### <a name="to-create-a-static-one-way-send-port-for-contoso-to-send-the-edi-interchange"></a>（为 Contoso) 创建静态单向发送端口以发送 EDI 交换  

1. 在 Windows 资源管理器中，创建一个用于接收测试交换的本地文件夹。  

2. 在中[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理控制台中，右键单击**发送端口**节点下的**BizTalk Application 1**节点，指向**新建**，然后单击**静态单向发送端口**。  

3. 在中**发送端口属性**对话框中，发送端口名称。  

4. 在中**传输**部分中，选择**文件**有关**类型**，然后单击**配置**。  

5. 有关**目标文件夹**，浏览到要接收的交换的文件夹。 在此过程的步骤 1 中创建此文件夹。 有关**文件掩码**，输入交换格式，如 **\*.edi**或 **\*.xml**。  

6. 单击“确定” 。  

7. 在中**发送管道**，选择**EdiSend**。  

8. 在控制台树中，选择**筛选器**。 输入用于订阅 EDI 交换的筛选器。 例如，对于**属性**，输入**BTS。MessageType**; 对于**运算符**，输入**==**; 对于**值**交换，例如，输入的架构 http://schemas.microsoft.com/BizTalk/Edi/X12/2006#X12_00401_850 .  

   > [!NOTE]
   >  以上筛选器设置可确保将交换（而不是确认）发送到与此发送端口相关联的文件夹。  

9. 单击“确定” 。  

10. 在控制台树中，单击**发送端口**。 在中**发送端口**窗格中，右键单击您的发送端口，然后依次**启动**。  

##### <a name="to-create-a-static-one-way-send-port-to-send-the-997n-acknowledgment"></a>若要创建静态单向发送端口以发送 997 确认  

1. 在 Windows 资源管理器中，创建一个用于接收 997 确认的本地文件夹。  

2. 在中[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理控制台中，右键单击**发送端口**节点下的**BizTalk Application 1**节点，指向**新建**，然后单击**静态单向发送端口**。  

3. 在中**发送端口属性**对话框中，发送端口名称。  

4. 在中**传输**部分中，选择**文件**有关**类型**，然后单击**配置**。  

5. 有关**目标文件夹**，浏览到用于接收 997 确认的文件夹。 在此过程的步骤 1 中创建此文件夹。 有关**文件掩码**，输入交换格式，如 **\*.edi**或 **\*.txt**。  

6. 单击“确定” 。  

7. 在中**发送管道**，选择**EdiSend**。  

8. 在控制台树中，选择**筛选器**。 输入用于订阅 997 确认的筛选器。 例如，对于**属性**，输入**BTS。MessageType**; 对于**运算符**，输入**==**; 对于**值**例如，输入确认的架构`http://schemas.microsoft.com/Edi/X12#X12_997_Root`.  

9. 单击“确定” 。  

10. 在控制台树中，单击**发送端口**。 在中**发送端口**窗格中，右键单击您的发送端口，然后依次**启动**。  

##### <a name="to-create-a-static-one-way-send-port-to-send-the-ta1-acknowledgment"></a>若要创建静态单向发送端口以发送 TA1 确认  

1. 在 Windows 资源管理器中，创建一个用于接收 TA1 确认的本地文件夹。  

2. 在中[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理控制台中，右键单击**发送端口**节点下的**BizTalk Application 1**节点，指向**新建**，然后单击**静态单向发送端口**。  

3. 在中**发送端口属性**对话框中，发送端口名称。  

4. 在中**传输**部分中，选择**文件**有关**类型**，然后单击**配置**。  

5. 有关**目标文件夹**，浏览到用于接收 TA1 确认的文件夹。 在此过程的步骤 1 中创建此文件夹。 有关**文件掩码**，输入交换格式，如 **\*.edi**或 **\*.txt**。  

6. 单击“确定” 。  

7. 在中**发送管道**，选择**EdiSend**。  

8. 在控制台树中，选择**筛选器**。 输入用于订阅 TA1 确认的筛选器。 例如，对于**属性**，输入**BTS。MessageType**; 对于**运算符**，输入**==**; 对于**值**例如，输入确认的架构 http://schemas.microsoft.com/Edi/X12#X12_TA1_Root.  

9. 单击“确定” 。  

10. 在控制台树中，单击**发送端口**。 在中**发送端口**窗格中，右键单击您的发送端口，然后依次**启动**。  

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

##### <a name="to-create-an-agreement-between-the-two-business-profiles"></a>若要创建的两个业务配置文件之间的协议  

1. 右键单击**Fabrikam_Profile**，依次指向**新建**，然后单击**协议**。  

2. 在**常规属性**页上，对于**名称**文字框中，输入协议的名称。  

3. 从**协议**下拉列表中，选择**X12**。  

4. 在中**第二个合作伙伴**部分中，从**名称**下拉列表中，选择**Contoso**。  

5. 在中**第二个合作伙伴**部分中，从**配置文件**下拉列表中，选择**Contoso_Profile**。  

    你将注意到两个新选项卡获取旁边添加**常规**选项卡。每个选项卡用于配置一个单向协议，每个单向协议代表消息 （包括消息传输和确认传输） 的一次完整事务。  

6. 在中**常规**选项卡中，**常规属性**页上，在**公用主机设置**部分中，选择**打开报告**，，然后选择**存储消息负载以用于报告**。  

7. 在执行以下任务**Fabrikam-> Contoso**选项卡。  

   1. 上**标识符**页**交换设置**部分中，输入限定符和标识符字段的值 (**ISA5**， **ISA6**， **ISA7**，并**ISA8**) 的测试消息中这些标头字段的值相对应。  

      > [!NOTE]
      >  [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 需要发送方和接收方限定符和标识符字段才能执行协议解析。 它将匹配的值**ISA5**， **ISA6**， **ISA7**，以及**ISA8**与协议属性中的交换标头中。 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 此外将通过匹配发送方限定符和标识符 （不接收方限定符和标识符） 来解析协议。 如果[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]不能解析协议，它将使用后备协议属性。  
      > 
      > [!NOTE]
      >  如果将"EDI 接口开发人员教程"中的 SamplePO.txt 文件用作测试消息，设置**ISA5**到**ZZ**， **ISA6**到**THEM**， **ISA7**到**ZZ**，并**ISA8**到**美国**。  

   2. 上**确认**页**交换设置**部分中，选择**预期的 TA1**并**预期的 997**。  

   3. 上**验证**页**交换设置**部分中，请确保**检查重复的 isa13**选项处于未选中状态。  

      > [!NOTE]
      >  清除**检查重复的 isa13**属性使您能够接收同一消息的多个实例。  

   4. 上**字符集和分隔符**页**交换设置**部分中，选择**CR LF**选项。  

   5. 上**本地主机设置**页**交换设置**部分中，清除**确认路由到发送管道请求-响应接收端口**选项。  

      > [!NOTE]
      >  如果使用的双向接收端口以接收交换并返回确认，您将检查**将确认路由到发送管道请求-响应接收端口**。  

   6. 上**发送端口**页**交换设置**部分中，将会接收来自 Fabrikam 的交换的发送端口和接收的发送端口相关联从 Contoso 的确认。 在中**发送端口**网格下**名称**列，再单击某个空单元格，并从下拉列表中，选择创建用于从 Fabrikam 接收 EDI 交换的发送端口。 创建用于接收 TA1 确认的发送端口和创建用于接收 997 确认的发送端口重复步骤。  

   7. 上**验证**页**事务集设置**部分中，保留**EDI 类型验证**检查，并检查**扩展验证**.  

   8. 如果你使用附带的标准架构之一[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]，然后在**本地主机设置**页下**事务集设置**部分中，选择要使用的架构的命名空间处理传入的交换。 如果使用自定义架构，请输入中的值**自定义目标命名空间**网格中，以便[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]可以确定命名空间使用组和事务集标头值。  

   9. 上**信封**页**事务集设置**部分中，输入在网格的第一行中的所有列的值。  


      |       使用此选项       |                                                                                                                                    执行的操作                                                                                                                                    |
      |----------------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
      |     **默认**      |   选择**默认**。 **注意：** 选择此行作为默认值的值**GS1**， **GS2**， **GS3**， **GS7**，并**GS8**是即使使用的值**事务类型**，**版本/发行版**，并**目标命名空间**不是消息的匹配项。   |
      | **事务类型** |                                                                                                     选择你的测试消息的消息类型**850 – 采购订单**。                                                                                                      |
      | **版本/发行版**  |                                                                                                                        输入 EDI 版本， **00401**。                                                                                                                         |
      | **目标命名空间** |                                                                                                                选择 <http://schemas.microsoft.com/Edi/X12>。                                                                                                                |
      |       **GS1**        |                                                                                           验证是否已选中的测试消息的消息类型， **PO-采购订单 (850)**。                                                                                           |
      |       **GS2**        |                                                                                                                    输入应用程序发送方的值。                                                                                                                     |
      |       **GS3**        |                                                                                                                   输入应用程序接收方的值。                                                                                                                    |
      |       **GS4**        | 选择所需的日期格式。 **注意：** 您必须下拉列表中选择一个值，而不仅仅是单击该字段以显示默认值。 如果您单击字段而无需从下拉列表中选择值，该值将不实际选择。 |
      |       **GS5**        |                                                                                                                      选择所需的时间格式。                                                                                                                       |
      |       **GS7**        |                                                                                                                选择**X-公认的标准委员会 X12**。                                                                                                                |
      |       **GS8**        |                                                                                                             验证已输入 EDI 版本， **00401**。                                                                                                             |

      > [!NOTE]
      >  [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 将设置 GS01、 GS02、 GS03、 GS04、 GS05、 GS07 和基于为输入的值对出站确认的 GS08**事务类型**，**版本/发行版**，和**目标命名空间**。 发送管道将尝试匹配事务集类型、 X12 版本和消息的标头中的相应值的目标命名空间。 如果成功，它将使用与关联的 GS 值**事务类型**，**版本/发行版**，并**目标命名空间**值。  

8. 在执行以下任务**Contoso-> Fabrikam**选项卡。  

   > [!NOTE]
   >  在本演练中，我们指定的选项卡中所需的值，以便可以成功创建协议。 若要成功创建协议，两个单向协议选项卡必须具有定义为值**ISA5**， **ISA6**， **ISA7**，以及**ISA8**。  

   > [!NOTE]
   >  即使确认是相同消息事务的一部分，应如何生成确认相关的属性中配置**Contoso-> Fabrikam**选项卡。这是必需的因为确认上下文属性发送方和接收方限定符设置为在指定的值相反**Contoso-> Fabrikam**选项卡。例如，如果发送方和接收方标识符设置为 THEM 和 US 中的**Fabrikam-> Contoso**选项卡中，发送方和接收方上下文属性将该确认中设置为 US 和 THEM。 通常情况下，其他单向协议选项卡还会发送方和接收方的标识符分别设置为 US 和 THEM。 因此，确认消息将解析为该协议并将有选择地设置的属性。 因此，如果你想要让确认使用不同的元素分隔符或如果想要让确认使用 CR LF，指定的属性中**Contoso-> Fabrikam**选项卡。  
   >   
   >  从概念上讲，确认属性将有选择地从任何单向协议选项卡中具有相同的发送方和接收方限定符的确认上下文属性中设置。 但是，对于便于实际使用，可以将通常设置这在您创建该交换将解析到协议的其他单向协议选项卡中。  

   1.  上**标识符**页**交换设置**部分中，输入限定符和标识符字段的值 (**ISA5**， **ISA6**， **ISA7**，并**ISA8**) 的测试消息中这些标头字段的值相对应。  

       > [!NOTE]
       >  如果将"EDI 接口开发人员教程"中的 SamplePO.txt 文件用作测试消息，设置**ISA5**到**ZZ**， **ISA6**到**美国**， **ISA7**到**ZZ**，并**ISA8**到**THEM**。  

9. 单击 **“应用”**。  

10. 单击“确定” 。 中列出新添加的协议**协议**一部分**参与方和业务配置文件**窗格。 默认情况下启用新添加的协议。  

### <a name="testing-the-walkthrough"></a>测试演练  
 本部分提供有关如何测试演练的信息。  

##### <a name="to-test-the-walkthrough"></a>若要测试演练  

1. 在 Windows 资源管理器拖放测试 EDI 交换到本地接收文件夹中。  

   > [!NOTE]
   >  对于测试消息，可以使用在 EDI 接口开发人员教程中使用的 SamplePO.txt 文件。 该文件中都随附[!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]SDK\EDI Interface Developer Tutorial 文件夹。 这是一个 X12 850 消息。 如果您使用此消息，则必须已经部署 X12_00401_850.xsd 架构，在该架构[!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]SDK\EDI Interface Developer Tutorial\Inbound_EDI 文件夹。 必须使用 X12 850 性架构中的[!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]XSD_Schema 文件夹。  

2. 打开与交换的发送端口关联的文件夹，并验证它包含 EDI 交换。  

3. 打开与 997 确认的发送端口关联的文件夹并验证它包含 997 确认。  

4. 打开与 TA1 确认的发送端口关联的文件夹，并验证它包含 TA1 确认。  

## <a name="see-also"></a>请参阅  
 [开发和配置 BizTalk Server EDI 解决方案](../core/developing-and-configuring-biztalk-server-edi-solutions.md)