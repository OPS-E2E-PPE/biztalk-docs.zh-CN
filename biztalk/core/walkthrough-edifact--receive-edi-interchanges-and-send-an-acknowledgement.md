---
title: 演练 (EDIFACT):接收 EDI 交换并发送回确认 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 02751f0c-8e7e-4879-93e4-8bc475640756
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: fae5bbda87851df48daeacf116739744153fa52d
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65395963"
---
# <a name="walkthrough-edifact-receiving-edi-interchanges-and-sending-back-an-acknowledgement"></a>演练 (EDIFACT):接收 EDI 交换并发送回确认
本演练提供了一的分步过程，创建一个解决方案，为接收 EDIFACT 交换使用[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]。 在此解决方案中，EDIFACT 交换从贸易合作伙伴 （Fabrikam) 发送到另一个贸易合作伙伴 Contoso。  

## <a name="prerequisites"></a>先决条件  
 必须以成员的身份登录[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理员或[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]B2B Operators 组。  

## <a name="how-the-solution-receives-edifact-interchanges"></a>解决方案如何接收 EDIFACT 交换  
 该解决方案将执行以下操作：  

> [!NOTE]
>  显示的顺序可能不是此列表中的事件。  

1.  接收来自贸易合作伙伴 Fabrikam 的平面文件 EDIFACT 交换。  

2.  验证针对其架构的 EDIFACT 交换，将消息拆装成 XML，并将消息 XML 放置到 MessageBox 中。  

3.  为收到的 EDI 交换生成技术确认 （收到的消息） 并放置到 MessageBox 中。  

4.  生成功能确认 （接受或拒绝收到的 EDI 交换），并放置到 MessageBox 中。  

5.  提取消息 XML 通过单向 FILE 发送端口，并组装消息 EDI 交换。  

6.  将 EDI 交换发送到 Contoso 本地文件夹。  

7.  提取的技术确认的单向 FILE 发送端口，并组装交换。  

8.  将技术确认发送到 Fabrikam 本地文件夹。  

9. 选择功能确认的单向 FILE 发送端口，并组装交换。  

10. 向 Fabrikam 发送功能确认。  

## <a name="the-functionality-in-this-solution"></a>此解决方案中的功能  
 对于本演练的目的，将启用以下功能：  

- 该解决方案专用于使用 EDIFACT 编码的交换  

  > [!NOTE]
  >  有关如何创建类似的解决方案，对于 X12 交换的说明，请参阅[演练 (X12):接收 EDI 交换并发送回确认](../core/walkthrough-x12--receive-edi-interchanges-and-send-back-an-acknowledgement.md)。  

- 将传入交换上执行 EDI 类型和扩展的验证。  

- 将返回到交换的发件人为生成技术和功能确认。  

- 解决方案使用单向接收位置使用 FILE 传输类型。  

  > [!NOTE]
  >  可以使用双向要求响应接收端口和位置来接收消息，但如果这样做，您将不能为接收位置使用 FILE 传输类型。 有关详细信息，请参阅[配置为接收 EDI 消息和确认的端口](../core/configuring-a-port-to-receive-edi-messages-and-acknowledgments.md)。  

- 将启用 EDI 报告，并保存事务集以从交换状态报告进行查看。  

- 出于测试目的，解决方案使用三个发送端口将 EDIFACT 交换和 Ack 创建发送到本地文件夹。  

  下图显示了此解决方案的体系结构：  

  ![接收 EDIFACT 交换和发送确认](../core/media/edifact-walkthrough.gif "EDIFACT_Walkthrough")  

## <a name="configuring-and-testing-the-walkthrough"></a>配置和测试演练  
 此解决方案所需的过程包括：  

- 将必需的消息架构添加到 BizTalk 项目，然后生成并部署该项目，使架构可供使用[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]中处理收到的交换。  

- 创建一个单向接收端口[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]以从贸易合作伙伴接收 EDIFACT 交换，并生成确认。 此接收位置与 Fabrikam 存放要发送到 Contoso 的 EDIFACT 交换文件文件夹相关联。  

  > [!NOTE]
  >  可以使用双向要求响应接收端口和位置来接收消息，但如果这样做，您将不能为接收位置使用 FILE 传输类型。  

- 创建一个发送端口将 EDI 交换发送到一个本地 Contoso 文件夹，另一个向本地 Fabrikam 文件夹发送技术和功能确认。  

  > [!NOTE]
  >  与 X12 确认，功能和技术确认的消息类型都相同。 因此，发送端口筛选器创建使用`BTS.MessageType`上下文属性筛选这两个确认，并将它们传递到同一文件夹。  

- 为 Fabrikam 和 Contoso 创建参与方 （贸易合作伙伴）。  

- 为这两个贸易合作伙伴创建业务配置文件每个。  

- 创建通过配置要接收的消息的 EDI 属性的两个配置文件和确认之间的协议来发送。  

- 测试本演练使用 EDIFACT 交换的测试。 在本演练中，可以复制并粘贴以下内容的文本文件。 此文件的架构是 EFACT_D98A_APERAK.xsd。  

  ```  
  UNA:+,?*'  
  UNB+UNOB:1+7654321:ZZZ+1234567:ZZZ+353501:3023+UNB5'  
  UNG+INVOIC+UNG2.1:ZZZ+UNG3.1:ZZZ+060413:2314+UNG5+UN+D:98B'  
  UNH+UNH1+APERAK:D:98A:UN++13+UNH5.1+UNH6.1+UNH7.1'  
  BGM+1+C10601'  
  DTM+10'  
  FTX+AAA++C10701+C10801'  
  CNT+1:14'  
  RFF+AAA'  
  DTM+10'  
  NAD+AA+C08201+C05801+C08001+C05901'  
  CTA++C05601'  
  COM+C07601:AA'  
  ERC+C90101'  
  FTX+AAA++C10701+C10801'  
  RFF+AAA'  
  FTX+AAA++C10701+C10801'  
  UNT+15+UNH1'  
  UNE+1+UNG5'  
  UNZ+1+UNB5'  
  ```  

### <a name="configuring-the-walkthrough"></a>配置演练  
 本部分介绍配置本演练的步骤。  

##### <a name="to-deploy-the-message-schema"></a>若要部署的消息架构  

1. 在[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]，创建或打开 BizTalk 项目。  

   > [!NOTE]
   >  本主题假定你已从对 BizTalk EDI 应用程序，其中包含 EDI 架构、 管道和业务流程应用程序中添加了一个引用。 如果没有，请参阅[如何添加对 BizTalk Server EDI 应用程序的引用](http://msdn.microsoft.com/library/7af066fb-372f-4709-b566-c8d6b4a9d782)。  

2. 右键单击你的项目，指向**外**，然后单击**现有项**。 转到您的架构是中的文件夹[!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]XSD_Schema\EDI\EDIFACT\D98A，然后双击您的架构 (**EFACT_D98A_APERAK.xsd**)。  

   > [!NOTE]
   >  如果你使用本主题中提供的示例测试消息，则必须使用**EFACT_D98A_APERAK.xsd**架构。  

   > [!NOTE]
   >  如果 EDI 架构尚未解压缩到 \XSD_Schema\EDI 文件夹，则执行**MicrosoftEdiXSDTemplates.exe** \XSD_Schema\EDI 文件夹将架构解压缩到默认文件夹中的文件。  

3. 将程序集密钥文件添加到项目中，然后生成并部署该程序集。  

##### <a name="to-create-a-one-way-receive-port-for-fabrikam-to-receive-the-edi-interchange"></a>若要创建一个单向接收端口 （对于 Fabrikam) 接收 EDI 交换  

1. 在 Windows 资源管理器中，创建用于接收交换的本地文件夹。  

2. 在中[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理控制台中，右键单击**接收端口**节点下的**BizTalk Application 1**节点，指向**新建**，然后单击**单向接收端口**。  

3. 接收端口的名称，然后单击**接收位置**在控制台树中。  

4. 单击 **“新建”** 。  

5. 名称的接收位置，选择**文件**有关**类型**，然后单击**配置**。  

6. 浏览到文件夹**接收文件夹**文本框。 在此过程的步骤 1 中创建此文件夹。 输入文件掩码，如 **\*.edi**或 **\*.txt**。  

7. 单击“确定”  。  

8. 有关**接收管道**，选择**EdiReceive**。  

9. 单击**确定**中**接收位置属性**对话框。 单击**确定**中再次**接收端口属性**对话框。  

10. 在控制台树中，单击**接收位置**。 在中**接收位置**窗格中，右键单击将接收位置，然后依次**启用**。  

##### <a name="to-create-a-static-one-way-send-port-for-contoso-to-send-the-edi-interchange"></a>（为 Contoso) 创建静态单向发送端口以发送 EDI 交换  

1. 在 Windows 资源管理器中，创建一个用于接收测试交换的本地文件夹。  

2. 在中[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理控制台中，右键单击**发送端口**节点下的**BizTalk Application 1**节点，指向**新建**，然后单击**静态单向发送端口**。  

3. 在中**发送端口属性**对话框中，发送端口名称。  

4. 在中**传输**部分中，选择**文件**有关**类型**，然后单击**配置**。  

5. 有关**目标文件夹**，浏览到要接收的交换的文件夹。 在此过程的步骤 1 中创建此文件夹。 有关**文件掩码**，输入交换格式，如 **\*.edi**或 **\*.txt**。  

6. 单击“确定”  。  

7. 在中**发送管道**，选择**EdiSend**。  

8. 在控制台树中，选择**筛选器**。 输入用于订阅 EDI 交换的筛选器。 例如，对于**属性**，输入**BTS。MessageType**; 对于**运算符**，输入 **==** ; 对于**值**交换，请输入架构`http://schemas.microsoft.com/BizTalk/EDI/EDIFACT/2006#EFACT_D98A_APERAK`。  

   > [!NOTE]
   >  以上筛选器设置可确保将交换（而不是确认）发送到与此发送端口相关联的文件夹。  

9. 单击“确定”  。  

10. 在控制台树中，单击**发送端口**。 在中**发送端口**窗格中，右键单击您的发送端口，然后依次**启动**。  

##### <a name="to-create-a-static-one-way-send-port-to-send-the-acknowledgments"></a>若要创建静态单向发送端口以发送确认  

1. 在 Windows 资源管理器中，创建一个用于接收到的技术和功能确认的本地文件夹。  

2. 在中[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理控制台中，右键单击**发送端口**节点下的**BizTalk Application 1**节点，指向**新建**，然后单击**静态单向发送端口**。  

3. 在中**发送端口属性**对话框中，发送端口名称。  

4. 在中**传输**部分中，选择**文件**有关**类型**，然后单击**配置**。  

5. 有关**目标文件夹**，浏览到用于接收两个确认的文件夹。 在此过程的步骤 1 中创建此文件夹。 有关**文件掩码**，输入交换格式，如 **\*.edi**或 **\*.txt**。  

6. 单击“确定”  。  

7. 在中**发送管道**，选择**EdiSend**。  

8. 在控制台树中，选择**筛选器**。 输入用于订阅确认的筛选器。 例如，对于**属性**，输入**BTS。MessageType**; 对于**运算符**，输入 **==** ; 对于**值**确认，请输入架构`http://schemas.microsoft.com/Edi/Edifact#Efact_Contrl_Root`。  

9. 单击“确定”  。  

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

3. 从**协议**下拉列表中，选择**EDIFACT**。  

4. 在中**第二个合作伙伴**部分中，从**名称**下拉列表中，选择**Contoso**。  

5. 在中**第二个合作伙伴**部分中，从**配置文件**下拉列表中，选择**Contoso_Profile**。  

    你将注意到两个新选项卡获取旁边添加**常规**选项卡。每个选项卡用于配置一个单向协议，每个单向协议代表消息 （包括消息传输和确认传输） 的一次完整事务。  

6. 在中**常规**选项卡中，**常规属性**页上，在**公用主机设置**部分中，选择**打开报告**，，然后选择**存储消息负载以用于报告**。  

7. 在执行以下任务**Fabrikam-> Contoso**选项卡。  

   1. 上**标识符**页**交换设置**部分中，输入限定符和标识符字段的值 (**UNB2.1**， **UNB2.2**， **UNB3.1**，和**UNB3.2**) 的测试消息中这些标头字段的值相对应。  

      > [!NOTE]
      >  [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 需要发送方和接收方限定符和标识符字段才能执行协议解析。 它将匹配的值**UNB2.1**， **UNB2.2**， **UNB3.1**，以及**UNB3.2**与中的属性的交换标头中协议。 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 此外将通过匹配发送方限定符和标识符 （不接收方限定符和标识符） 来解析协议。 如果[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]不能解析协议，它将使用后备协议属性。  
      > 
      > [!NOTE]
      >  如果使用的提供作为测试消息的本主题中前面的示例消息，设置**UNB2.1**到**7654321**， **UNB2.2**到**ZZZ – 双方约定**， **UNB3.1**到**1234567**，并且**UNB3.2**到**ZZZ – 双方约定**。  

   2. 上**确认**页**交换设置**部分中，选择**预期接收消息 (CONTRL)** 和**确认 (预期的 CONTRL)** 。  

   3. 上**信封**页**交换设置**部分中，选择**应用 UNA 段 （字符串服务建议）** 和**应用 UNG 段 （功能组标头）** 。  

   4. 上**验证**页**交换设置**部分中，请确保**交换控制编号 (UNB5)** 选项处于未选中状态。  

      > [!NOTE]
      >  清除**交换控制编号 (UNB5)** 属性使您能够接收同一消息的多个实例。  

   5. 上**字符集和分隔符**页**交换设置**部分中，选择**CR LF**选项**UNA6 后缀**。  

   6. 上**本地主机设置**页**交换设置**部分中，清除**确认路由到发送管道请求-响应接收端口**选项。  

      > [!NOTE]
      >  如果使用的双向接收端口以接收交换并返回确认，您将检查**将确认路由到发送管道请求-响应接收端口**。  

   7. 上**发送端口**页**交换设置**部分中，将会接收来自 Fabrikam 的交换的发送端口和接收的发送端口相关联从 Contoso 的确认。 在中**发送端口**网格下**名称**列，再单击某个空单元格，并从下拉列表中，选择创建用于从 Fabrikam 接收 EDI 交换的发送端口。 为创建用于接收技术和功能确认的发送端口重复步骤。  

   8. 上**验证**页**事务集设置**部分中，保留**EDI 类型验证**检查，并检查**扩展类型验证**.  

   9. 如果你使用附带的标准架构之一[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]，然后在**本地主机设置**页下**事务集设置**部分中，选择要使用的架构的命名空间处理传入的交换。 如果使用自定义架构，请输入中的值**自定义目标命名空间**网格中，以便[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]可以确定命名空间使用组和事务集标头值。  

   10. 上**信封**页**事务集设置**部分中，输入在网格的第一行中的所有列的值。  


       |          使用此选项           |                                执行的操作                                 |
       |-----------------------------|---------------------------------------------------------------------------|
       |         **默认**         |                            选择**默认**。                            |
       | **对于消息类型 UNH2.1** |         选择你的测试消息的消息类型**APERAK**。         |
       |         **UNH2.2**          |                       输入 EDI 版本， **D**。                       |
       |         **UNH2.3**          |                    输入发行版号**98A**。                     |
       |         **UNH2.5**          |                         您可以将其留空。                         |
       |    **目标命名空间**     |          选择 <http://schemas.microsoft.com/Edi/Edifact>  。           |
       |          **UNG1**           |               指定功能组 ID **INVOIC**。                |
       |         **UNG2.1**          |         为应用程序发送方标识输入的值。          |
       |         **UNG2.1**          | 输入一个值，为应用程序发送方代码限定符，例如**ZZZ**。 |
       |         **UNG3.1**          |          应用程序接收方标识输入的值。           |
       |         **UNG3.2**          |  输入一个值，为应用程序接收方代码限定符，例如**ZZZ**。  |
       |          **UNG6**           |        输入控制机构的值。 示例中，**取消**。         |
       |         **UNG7.1**          |          输入消息类型版本号。 示例中， **D**。           |
       |         **UNG7.2**          |         输入消息类型发行版号。 示例中， **98A**。          |
       |         **UNG7.3**          |                         您可以将其留空。                         |
       |          **UNG8**           |                         您可以将其留空。                         |


8. 在执行以下任务**Contoso-> Fabrikam**选项卡。  

   > [!NOTE]
   >  在本演练中，我们指定的选项卡中所需的值，以便可以成功创建协议。 若要成功创建协议，两个单向协议选项卡必须具有定义为值**UNG2.1**， **UNG2.2**， **UNG3.1**，和**UNG3.2**.  

   > [!NOTE]
   >  即使确认是相同消息事务的一部分，应如何生成确认相关的属性中配置**Contoso-> Fabrikam**选项卡。这是必需的因为确认上下文属性发送方和接收方限定符设置为在指定的值相反**Contoso-> Fabrikam**选项卡。例如，如果发送方和接收方标识符设置为 7654321 和在 1234567 **Fabrikam-> Contoso**选项卡中，发送方和接收方上下文属性将设置为 1234567 和 7654321 确认中。 通常情况下，其他单向协议选项卡还会发送方和接收方的标识符分别设置为 1234567 和 7654321。 因此，确认消息将解析为该协议并将有选择地设置的属性。 因此，如果你想要让确认使用不同的元素分隔符或如果想要让确认使用 CR LF，指定的属性中**Contoso-> Fabrikam**选项卡。  
   >   
   >  从概念上讲，确认属性将有选择地从任何单向协议选项卡中具有相同的发送方和接收方限定符的确认上下文属性中设置。 但是，对于便于实际使用，可以将通常设置这在您创建该交换将解析到协议的其他单向协议选项卡中。  

   1.  上**标识符**页**交换设置**部分中，输入限定符和标识符字段的值 (**UNG2.1**， **UNG2.2**， **UNG3.1**，和**UNG3.2**) 的测试消息中这些标头字段的值相对应。  

       > [!NOTE]
       >  如果使用的提供作为测试消息的本主题中前面的示例消息，设置**UNB2.1**到**1234567**， **UNB2.2**到**ZZZ – 双方约定**， **UNB3.1**到**7654321**，并且**UNB3.2**到**ZZZ – 双方约定**。  

9. 单击 **“应用”** 。  

10. 单击“确定”  。 中列出新添加的协议**协议**一部分**参与方和业务配置文件**窗格。 默认情况下启用新添加的协议。  

### <a name="testing-the-walkthrough"></a>测试演练  
 本部分提供有关如何测试演练的信息。  

##### <a name="to-test-the-walkthrough"></a>若要测试演练  

1. 在 Windows 资源管理器拖放测试 EDI 交换到本地接收文件夹中。  

   > [!NOTE]
   >  对于测试消息，可以使用本主题中前面提供的示例消息。 将消息复制到一个文本文件并带.txt 扩展名保存文件。 如果您使用此消息，则必须部署 EFACT_D98A_APERAK.xsd 架构。 架构是可通过执行**MicrosoftEdiXSDTemplates.exe**文件 （位于 \XSD_Schema\EDI 文件夹中） 将该架构解压缩到默认文件夹。 找到 EFACT_D98A_APERAK.xsd 架构位于然后下[!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]XSD_Schema\EDI\EDIFACT\D98A。  

2. 打开与交换的发送端口关联的文件夹，并验证它包含 EDI 交换。  

3. 打开与确认的发送端口关联的文件夹，并验证它包含技术和功能确认。  

## <a name="see-also"></a>请参阅  
 [开发和配置 BizTalk Server EDI 解决方案](../core/developing-and-configuring-biztalk-server-edi-solutions.md)