---
title: "演练 (EDIFACT): 接收 EDI 交换和发回确认 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 02751f0c-8e7e-4879-93e4-8bc475640756
caps.latest.revision: "4"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 566a1c5eec4fe6800f0c1906ed31c35391b23333
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="walkthrough-edifact-receiving-edi-interchanges-and-sending-back-an-acknowledgement"></a>演练 (EDIFACT)：接收 EDI 交换并发送回确认信息
本演练将介绍使用 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 为接收 EDIFACT 交换创建解决方案的分步操作过程。 此解决方案中的 EDIFACT 交换从贸易合作伙伴，Fabrikam，发送到另一个贸易合作伙伴，Contoso。  
  
## <a name="prerequisites"></a>先决条件  
 必须以 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理员组或 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] B2B Operators 组成员的身份登录。  
  
## <a name="how-the-solution-receives-edifact-interchanges"></a>该解决方案如何接收 EDIFACT 交换  
 该解决方案将执行以下操作：  
  
> [!NOTE]
>  此列表中的事件可能不会按所示顺序发生。  
  
1.  从贸易合作伙伴 Fabrikam 接收平面文件 EDIFACT 交换。  
  
2.  验证 EDIFACT 交换对照其架构，通过将反汇编消息转换为 XML，然后放到 MessageBox 消息 XML。  
  
3.  收到的 EDI 交换中，生成技术确认 （收到的消息） 并将其放在消息框。  
  
4.  生成功能确认 （接受或拒绝收到的 EDI 交换），并将其放在消息框。  
  
5.  选取消息 XML 通过单向的文件发送端口，并且组合 EDI 交换的消息。  
  
6.  发送到 Contoso 本地文件夹的 EDI 交换。  
  
7.  选取技术确认通过单向的文件发送端口，并且组合交换。  
  
8.  将技术确认发送到 Fabrikam 的本地文件夹。  
  
9. 通过单向的文件发送端口，功能确认选取并且组建交换。  
  
10. 将功能确认发送到 Fabrikam。  
  
## <a name="the-functionality-in-this-solution"></a>此解决方案中的功能  
 为进行此演练，将启用以下功能：  
  
-   该解决方案专用于交换使用 EDIFACT 编码  
  
    > [!NOTE]
    >  有关如何创建 X12 交换类似的解决方案的说明，请参阅[演练 (X12)： 接收 EDI 交换和发送回确认](../core/walkthrough-x12--receive-edi-interchanges-and-send-back-an-acknowledgement.md)。  
  
-   EDI 类型和扩展的验证将在传入交换上执行。  
  
-   将生成技术确认和功能确认，以返回给交换的发送方。  
  
-   该解决方案使用传输类型为 FILE 的单向接收位置。  
  
    > [!NOTE]
    >  您可以使用双向要求响应接收端口和位置来接收消息，但如果这样，接收位置将无法使用 FILE 传输类型。 有关详细信息，请参阅[配置端口以接收 EDI 消息以及确认](../core/configuring-a-port-to-receive-edi-messages-and-acknowledgments.md)。  
  
-   系统将启用 EDI 报告功能，并保存事务集以便从交换状态报告进行查看。  
  
-   出于测试目的，解决方案使用三个发送端口将 EDIFACT 交换和创建的确认发送到本地文件夹。  
  
 下图显示了此解决方案的结构：  
  
 ![接收 EDIFACT 交换和发送 ACK](../core/media/edifact-walkthrough.gif "EDIFACT_Walkthrough")  
  
## <a name="configuring-and-testing-the-walkthrough"></a>配置和测试演练  
 该解决方案所需的过程包括：  
  
-   将必需的消息架构添加到 BizTalk 项目，然后生成并部署该项目，使 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 在处理收到的交换时可以使用相应架构。  
  
-   为 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 创建一个单向接收端口，以便接收来自贸易合作伙伴的 EDIFACT 交换，并生成确认。 此接收位置与 Fabrikam 存放要发送到 Contoso 的 EDIFACT 交换的 file 文件夹相关联。  
  
    > [!NOTE]
    >  你可以使用的双向请求作出响应接收端口和位置，以便接收该消息，但如果这样做，你将不能用于接收位置的文件传输类型。  
  
-   创建一个用于向地 Contoso 文件夹发送 EDI 交换的发送端口，以及一个用于向本地 Fabrikam 文件夹发送技术和功能确认的发送端口。  
  
    > [!NOTE]
    >  与 X12 确认不同，功能确认和技术确认的消息类型相同。 因此，使用 `BTS.MessageType` 上下文属性创建的发送端口筛选器将筛选这两种确认，并将其传递到同一文件夹。  
  
-   为 Fabrikam 和 Contoso 创建参与方（贸易合作伙伴）。  
  
-   为两个贸易合作伙伴分别创建一个业务配置文件。  
  
-   创建通过配置接收消息的 EDI 属性的两个配置文件和确认之间发送的协议。  
  
-   测试使用测试 EDIFACT 交换演练。 对于本演练，你可以复制粘贴到一个文本文件以下。 此文件的架构是 EFACT_D98A_APERAK.xsd。  
  
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
 本部分介绍配置演练的步骤。  
  
##### <a name="to-deploy-the-message-schema"></a>部署消息架构  
  
1.  在 [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] 中，创建或打开 BizTalk 项目。  
  
    > [!NOTE]
    >  本主题假定你已从你的应用程序添加了对包含 EDI 架构、管道和业务流程的 BizTalk EDI 应用程序的引用。 如果没有，请参阅[如何添加对 BizTalk Server EDI 应用程序的引用](http://msdn.microsoft.com/library/7af066fb-372f-4709-b566-c8d6b4a9d782)。  
  
2.  右键单击你的项目，指向**添加**，然后单击**现有项**。 移至你的架构是否在文件夹[!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]XSD_Schema\EDI\EDIFACT\D98A，然后双击你的架构 (**EFACT_D98A_APERAK.xsd**)。  
  
    > [!NOTE]
    >  如果你使用本主题中提供的示例测试消息，则必须使用**EFACT_D98A_APERAK.xsd**架构。  
  
    > [!NOTE]
    >  如果不具有已 EDI 架构解压缩到 \XSD_Schema\EDI 文件夹中，执行**MicrosoftEdiXSDTemplates.exe** \XSD_Schema\EDI 文件夹来解压缩到默认文件夹的架构中的文件。  
  
3.  将程序集密钥文件添加到项目中，然后生成并部署程序集。  
  
##### <a name="to-create-a-one-way-receive-port-for-fabrikam-to-receive-the-edi-interchange"></a>若要创建单向接收端口 （对于 Fabrikam) 接收 EDI 交换  
  
1.  在 Windows 资源管理器，创建要接收该交换的本地文件夹。  
  
2.  在[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理控制台中，右键单击**接收端口**节点下的**BizTalk 应用程序 1**节点，指向**新建**，然后单击**单向接收端口**。  
  
3.  将接收端口，然后单击**接收位置**在控制台树中。  
  
4.  单击 **“新建”**。  
  
5.  名称的接收位置中，选择**文件**为**类型**，然后单击**配置**。  
  
6.  浏览到文件夹**接收文件夹**文本框。 在此过程中的步骤 1 中创建此文件夹。 输入文件掩码，如 **\*.edi**或 **\*.txt**。  
  
7.  单击 **“确定”**。  
  
8.  有关**接收管道**，选择**EdiReceive**。  
  
9. 单击**确定**中**接收位置属性**对话框。 单击**确定**再次在**接收端口属性**对话框。  
  
10. 在控制台树中，单击**接收位置**。 在**接收位置**窗格中，右键单击你接收位置，并依次**启用**。  
  
##### <a name="to-create-a-static-one-way-send-port-for-contoso-to-send-the-edi-interchange"></a>若要创建静态单向发送端口 （对于 Contoso) 发送 EDI 交换  
  
1.  在 Windows 资源管理器中，创建一个用于接收测试交换的本地文件夹。  
  
2.  在[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理控制台中，右键单击**发送端口**节点下的**BizTalk 应用程序 1**节点，指向**新建**，然后单击**静态单向发送端口**。  
  
3.  在**发送端口属性**对话框中，名称发送端口。  
  
4.  在**传输**部分中，选择**文件**为**类型**，然后单击**配置**。  
  
5.  有关**目标文件夹**，浏览到要接收该交换的文件夹。 在此过程中的步骤 1 中创建此文件夹。 有关**文件掩码**，输入交换格式，如 **\*.edi**或 **\*.txt**。  
  
6.  单击 **“确定”**。  
  
7.  在**发送管道**，选择**EdiSend**。  
  
8.  在控制台树中，选择**筛选器**。 输入用于订阅 EDI 交换的筛选器。 例如，对于**属性**，输入**BTS。MessageType**; 对于**运算符**，输入 **==** ; 以及**值**的交换，输入架构`http://schemas.microsoft.com/BizTalk/EDI/EDIFACT/2006#EFACT_D98A_APERAK`。  
  
    > [!NOTE]
    >  以上筛选器设置可确保将交换（而不是确认）发送到与此发送端口相关联的文件夹。  
  
9. 单击 **“确定”**。  
  
10. 在控制台树中，单击**发送端口**。 在**发送端口**窗格中，右键单击你发送端口，并依次**启动**。  
  
##### <a name="to-create-a-static-one-way-send-port-to-send-the-acknowledgments"></a>若要创建单向静态发送端口发送确认  
  
1.  在 Windows 资源管理器，创建要发送到的技术和功能确认的本地文件夹。  
  
2.  在[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理控制台中，右键单击**发送端口**节点下的**BizTalk 应用程序 1**节点，指向**新建**，然后单击**静态单向发送端口**。  
  
3.  在**发送端口属性**对话框中，名称发送端口。  
  
4.  在**传输**部分中，选择**文件**为**类型**，然后单击**配置**。  
  
5.  有关**目标文件夹**，浏览到要接收的两个确认的文件夹。 在此过程中的步骤 1 中创建此文件夹。 有关**文件掩码**，输入交换格式，如 **\*.edi**或 **\*.txt**。  
  
6.  单击 **“确定”**。  
  
7.  在**发送管道**，选择**EdiSend**。  
  
8.  在控制台树中，选择**筛选器**。 输入一个筛选器以确认订阅。 例如，对于**属性**，输入**BTS。MessageType**; 对于**运算符**，输入 **==** ; 以及**值**架构输入该确认， `http://schemas.microsoft.com/Edi/Edifact#Efact_Contrl_Root`。  
  
9. 单击 **“确定”**。  
  
10. 在控制台树中，单击**发送端口**。 在**发送端口**窗格中，右键单击你发送端口，并依次**启动**。  
  
##### <a name="to-create-a-party-and-a-business-profile-for-fabrikam"></a>若要为 Fabrikam 创建方和业务配置文件  
  
1.  右键单击**方**中的节点[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理控制台中，依次指向**新建**，然后单击**方**。  
  
2.  输入的名称在方**名称**文本中，然后单击**确定**。  
  
    > [!NOTE]
    >  通过选择**本地 BizTalk 处理接收的消息从该参与方发送方或支持消息**复选框，你可以指定当事方正在创建将为同一个组织还承载[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]. 此基础，某些属性将启用，或当您创建了协议时，禁用。 但是，对于本演练中，可以选中此复选框。  
  
3.  右键单击方名称，指向**新建**，然后单击**业务配置文件**。  
  
4.  在**配置文件属性**对话框中，在**常规**页上，输入**Fabrikam_Profile**中**名称**文本框。  
  
    > [!NOTE]
    >  在创建参与方时，也将创建一个配置文件。 你可以重命名，并使用该配置文件而不是创建一个新。 若要重命名配置文件，右键单击配置文件，然后选择**属性**。 在**常规**页上，指定配置文件的名称。  
  
##### <a name="to-create-a-party-and-a-business-profile-for-contoso"></a>为 Contoso 创建参与方和业务配置文件  
  
1.  右键单击**方**中的节点[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理控制台中，依次指向**新建**，然后单击**方**。  
  
2.  输入的名称在方**名称**文本中，然后单击**确定**。  
  
    > [!NOTE]
    >  通过选择**本地 BizTalk 处理接收的消息从该参与方发送方或支持消息**复选框，你可以指定当事方正在创建将为同一个组织还承载[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]. 此基础，某些属性将启用，或当您创建了协议时，禁用。 但是，对于本演练中，可以选中此复选框。  
  
3.  右键单击方名称，指向**新建**，然后单击**业务配置文件**。  
  
4.  在**配置文件属性**对话框中，在**常规**页上，输入**Contoso_Profile**中**名称**文本框。  
  
    > [!NOTE]
    >  在创建参与方时，也将创建一个配置文件。 你可以重命名，并使用该配置文件而不是创建一个新。 若要重命名配置文件，右键单击配置文件，然后选择**属性**。 在**常规**页上，指定配置文件的名称。  
  
##### <a name="to-create-an-agreement-between-the-two-business-profiles"></a>在两个业务配置文件之间创建协议  
  
1.  右键单击**Fabrikam_Profile**，指向**新建**，然后单击**协议**。  
  
2.  在**常规属性**页上，为**名称**文本框中，输入协议的名称。  
  
3.  从**协议**下拉列表中，选择**EDIFACT**。  
  
4.  在**第二个合作伙伴**部分中，从**名称**下拉列表中，选择**Contoso**。  
  
5.  在**第二个合作伙伴**部分中，从**配置文件**下拉列表中，选择**Contoso_Profile**。  
  
     你将注意到两个新选项卡获取旁边添加**常规**选项卡。每个选项卡配置一个单向协议，每个单向协议代表消息的一次完整事务（包括消息传输和确认传输）。  
  
6.  在**常规**选项卡上，在**常规属性**页上，在**常见主机设置**部分中，选择**打开 reporting**，，然后选择**用于报告的应用商店消息负载**。  
  
7.  在上执行以下任务**Fabrikam-> Contoso**选项卡。  
  
    1.  上**标识符**下页上**交换设置**部分中，输入限定符和标识符字段的值 (**UNB2.1**， **UNB2.2**， **UNB3.1**，和**UNB3.2**) 对应于测试消息中这些标头字段的值。  
  
        > [!NOTE]
        >  [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 要求为发送方和接收方的限定符和标识符字段输入值才能执行协议解析。 它将与匹配的值**UNB2.1**， **UNB2.2**， **UNB3.1**，和**UNB3.2**中包含的属性中的交换标头协议。 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]此外将匹配的发件人限定符和 （而不是收件人限定符和标识符） 的标识符来解析协议。 如果 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 无法解析协议，则将使用后备协议属性。  
  
        > [!NOTE]
        >  如果你使用的测试消息作为本主题中前面提供的示例消息，设置**UNB2.1**到**7654321**， **UNB2.2**到**ZZZ-双方约定**， **UNB3.1**到**1234567**，和**UNB3.2**到**ZZZ-双方约定**。  
  
    2.  上**确认**下页上**交换设置**部分，选中**收到预期消息 (CONTRL)**和**确认 (CONTRL) 预期**。  
  
    3.  上**包络线**下页上**交换设置**部分，选中**应用 UNA 段 （字符串服务建议）**和**应用 UNG 段 （功能组标头）**。  
  
    4.  上**验证**下页上**交换设置**部分中，请确保**交换控制编号 (UNB5)**选项处于未选中状态。  
  
        > [!NOTE]
        >  清除**交换控制编号 (UNB5)**属性使您能够接收同一消息的多个实例。  
  
    5.  上**字符集和分隔符**下页上**交换设置**部分中，选择**CR LF**选项**UNA6 后缀**。  
  
    6.  上**本地主机设置**下页上**交换设置**部分中，清除**路由 ACK 发送管道请求-响应接收端口**选项。  
  
        > [!NOTE]
        >  如果你使用的双向接收端口以接收交换并返回该确认，您需要检查**路由 ACK 发送管道请求-响应接收端口**。  
  
    7.  上**发送端口**下页上**交换设置**部分中，将从 Fabrikam 交换将接收发送端口和将接收发送端口相关联从 Contoso 的确认。 在**发送端口**网格下**名称**列中，单击空单元格，然后从下拉列表中，选择创建用于从 Fabrikam 接收 EDI 交换发送端口。 为发送端口用于接收技术和功能确认创建重复步骤。  
  
    8.  上**验证**下页上**事务设置设置**部分中，保留**EDI 类型验证**检查并检查**扩展的类型验证**.  
  
    9. 如果你使用其中一个标准架构附带[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]上**本地主机设置**下页上**事务设置设置**部分中，选择要用于对架构的命名空间处理传入的交换。 如果使用自定义架构，输入中的值**自定义目标命名空间**网格中，以便[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]可以确定使用组和事务的命名空间设置标头值。  
  
    10. 上**包络线**下页上**事务设置设置**部分中，输入网格的第一行中的所有列的值。  
  
        |使用此选项|执行的操作|  
        |--------------|----------------|  
        |**Default**|选择**默认**。|  
        |**消息类型 UNH2.1**|选择你的测试消息的消息类型**应用错误确认**。|  
        |**UNH2.2**|输入的 EDI 版本中， **D**。|  
        |**UNH2.3**|输入版本号， **98A**。|  
        |**UNH2.5**|你可以将其留空。|  
        |**目标命名空间**|选择**http://schemas.microsoft.com/Edi/Edifact**。|  
        |**UNG1**|指定功能组 ID， **INVOIC**。|  
        |**UNG2.1**|输入应用程序发件人标识值。|  
        |**UNG2.1**|应用程序发件人代码限定符，输入一个值，如**ZZZ**。|  
        |**UNG3.1**|输入应用程序接收方标识的值。|  
        |**UNG3.2**|应用程序接收方代码限定符，输入一个值，如**ZZZ**。|  
        |**UNG6**|对控制一家旅行社中输入的值。 示例中，**取消**。|  
        |**UNG7.1**|输入消息类型版本号。 示例中， **D**。|  
        |**UNG7.2**|输入消息类型发行版号。 示例中， **98A**。|  
        |**UNG7.3**|你可以将其留空。|  
        |**UNG8**|你可以将其留空。|  
  
8.  在上执行以下任务**Contoso-> Fabrikam**选项卡。  
  
    > [!NOTE]
    >  在此演练中，我们将指定的选项卡中所需的值，以便可以成功创建协议。 若要成功创建了协议，这两个单向协议选项必须为定义的值**UNG2.1**， **UNG2.2**， **UNG3.1**，和**UNG3.2**.  
  
    > [!NOTE]
    >  即使确认信息是相同的消息事务的一部分，在中配置应如何生成确认与相关属性**Contoso-> Fabrikam**选项卡。这是必需的因为确认上下文属性为发送者和接收者限定符设置为与中指定的值的符号相反**Contoso-> Fabrikam**选项卡。例如，如果发送方和接收方标识符设置为 7654321 和中的 1234567 **Fabrikam-> Contoso**选项卡、 发送和接收上下文属性将设置为 1234567 和 7654321 在确认消息。 通常情况下，其他单向协议选项卡还必须发件人和收件人标识符分别设置为 1234567 和 7654321。 因此，确认消息将解析为该协议，并且将提取属性设置。 因此，如果你想要使用不同的元素分隔符或如果你想要使用 CR LF 确认的确认，将指定的属性中**Contoso-> Fabrikam**选项卡。  
    >   
    >  从概念上讲，将从任何单向协议选项卡上提取具有与确认上下文属性中设置的相同发件人和接收方限定符的确认的属性。 但是，为了便于实际使用，你通常会在你创建的交换将解析为的协议的其他单向协议选项卡中设置此属性。  
  
    1.  上**标识符**下页上**交换设置**部分中，输入限定符和标识符字段的值 (**UNG2.1**， **UNG2.2**， **UNG3.1**，和**UNG3.2**) 对应于测试消息中这些标头字段的值。  
  
        > [!NOTE]
        >  如果你使用的测试消息作为本主题中前面提供的示例消息，设置**UNB2.1**到**1234567**， **UNB2.2**到**ZZZ-双方约定**， **UNB3.1**到**7654321**，和**UNB3.2**到**ZZZ-双方约定**。  
  
9. 单击 **“应用”**。  
  
10. 单击 **“确定”**。 新添加的协议被列入**协议**部分**方和业务配置文件**窗格。 默认情况下，启用新添加的协议。  
  
### <a name="testing-the-walkthrough"></a>测试演练  
 本部分提供有关如何测试演练的信息。  
  
##### <a name="to-test-the-walkthrough"></a>若要测试演练  
  
1.  在 Windows 资源管理器中，将测试 EDI 交换放置到本地接收文件夹中。  
  
    > [!NOTE]
    >  对于测试消息，您可以使用本主题前面提供的示例消息。 将消息复制到文本文件，并使用 .txt 扩展名保存文件。 如果使用此消息，则必须部署 EFACT_D98A_APERAK.xsd 架构。 架构可通过执行**MicrosoftEdiXSDTemplates.exe**文件 （位于 \XSD_Schema\EDI 文件夹中） 来解压缩到默认文件夹的架构。 然后可以在 [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]XSD_Schema\EDI\EDIFACT\D98A 下找到 EFACT_D98A_APERAK.xsd 架构。  
  
2.  打开与交换的发送端口关联的文件夹，并验证该文件夹是否包含 EDI 交换。  
  
3.  打开与确认的发送端口关联的文件夹，并验证该文件夹是否包含技术确认和功能确认。  
  
## <a name="see-also"></a>另请参阅  
 [开发和配置 BizTalk Server EDI 解决方案](../core/developing-and-configuring-biztalk-server-edi-solutions.md)