---
title: 在 SQL Server 使用 BizTalk Server 中执行存储的过程使用单个 XML 参数 |Microsoft 文档
description: 在使用中 BizTalk WCF 自定义端口和 SQL 适配器的存储过程传递单个参数
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: deb9333a-5e28-4e8d-8e0b-07b5a97a111b
caps.latest.revision: 16
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 02c5f239300140022b1d26f35664add744b630c2
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/28/2017
ms.locfileid: "25964595"
---
# <a name="execute-stored-procedures-with-a-single-xml-parameter-in-sql-server-using-biztalk-server"></a>在 SQL Server 使用 BizTalk Server 中执行存储的过程使用单个 XML 参数
执行具有一个参数的存储的过程是类似于执行任何其他存储的过程中所述[中使用 BizTalk Server 的 SQL Server 执行存储过程](execute-stored-procedures-in-sql-server-using-biztalk-server.md)。 但是，对于上述链接中所述的方法，你需要在设计时生成的存储过程的元数据并创建业务流程以在运行时调用过程。  
  
 请考虑其中你只是想要将一个单个值传递给存储过程，而无需执行任何处理对该值的方案。 在这种情况下，你不希望生成元数据、 创建业务流程、 部署业务流程，和执行该操作的开销。 相反，你可以配置 WCF 自定义或 WCF SQL 发送端口来直接调用存储的过程。 本主题演示如何执行这些任务使用[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理控制台。  
  
> [!NOTE]
>  本主题提供有关如何配置 WCF 自定义发送端口用于执行存储的过程采用单个参数。 可以通过配置 WCF SQL 端口执行相同的步骤。 有关配置 WCF SQL 端口的说明，请参阅[配置使用 WCF SQL 适配器的端口](configure-a-port-using-the-wcf-sql-adapter.md)。  
  
## <a name="invoke-stored-procedures-without-orchestration"></a>调用存储的过程，而无需业务流程  
 为了演示如何执行具有单个参数而无需业务流程的存储的过程，本主题，请使用 ADD_LAST_EMP_XML_INFO 存储过程。 此过程采用 XML 值作为参数并将其插入到**地址**列**员工**表。 你必须将传递到存储过程的 XML 值。 但是，若要执行存储的过程使用适配器，必须发送符合架构的过程中，请求消息和包含的 XML 值**地址**字段中，到 SQL Server。 因此，你必须创建由该请求消息：  
  
-   使用**模板**中使用该可以创建使用消息模板的请求消息的发送端口配置选项。  
  
-   将 XML 值**地址**插入到消息中的字段。  
  
 在本主题中详细描述了所有这些步骤。 你必须执行以下一组任务：  
  
1.  创建一个文件接收的端口将放置将插入到 XML 文件的位置**地址**的 XML 字段**员工**表。 假设此端口称为**MessageIn**端口。  
  
2.  创建一个 WCF 自定义单向发送端口的 XML 文件从文件选取接收端口，构造使用消息模板中，消息并将其发送到 SQL Server 来执行存储的过程。  
  
 本主题的这一部分提供了配置 WCF 自定义的说明发送的邮件模板使用的端口。  
  
> [!NOTE]
>  即使此主题中的信息演示如何执行存储的过程使用单个 XML 参数，你可以执行要执行的任何操作都具有一个参数的任何数据类型的任务。 唯一的区别将在创建消息模板针对特定操作的方式。 你可以通过获取你将使用它来执行该操作的请求消息创建消息模板使用业务流程和参数的值替换为 BizTalk 消息正文。  
  
##  <a name="BKMK_OneWay"></a>配置 WCF 自定义发送端口  
 在创建 WCF 自定义之前发送端口，请确保你创建文件接收端口， **MessageIn**。  
  
1.  启动[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理控制台。  
  
2.  在控制台树中，展开**BizTalk 组**，然后展开**应用程序**。  
  
3.  展开你想要部署的应用程序[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]。  
  
4.  右键单击**发送端口**，指向**新建**，然后指向**静态单向发送端口**。  
  
5.  在**发送端口属性**对话框中，在**常规**选项卡上，键入发送端口的名称。  
  
6.  配置端口以接收所有消息文件在删除接收端口， **MessageIn**。  
  
    1.  在**发送端口属性**对话框中，从左窗格中，单击**筛选器**。  
  
    2.  在右窗格中，在**属性**列中，单击网格中，然后选择**BTS。ReceivePortName**属性。  
  
    3.  有关**运算符**列中，选择"**==**"。  
  
    4.  有关**值**列中，指定文件的名称接收端口， `MessageIn`。  
  
7.  在**发送端口属性**对话框中，在**常规**选项卡上，从**类型**下拉列表中，选择**WCF 自定义**，然后单击**配置**。  
  
8.  在**WCF 自定义传输属性**对话框框中，执行以下操作：  
  
    1.  单击**常规**选项卡上，然后在**地址 (URI)** 字段中，指定 SQL Server 连接 URI。 有关连接 URI 的详细信息，请参阅[创建 SQL Server 连接 URI](../../adapters-and-accelerators/adapter-sql/create-the-sql-server-connection-uri.md)。  
  
    2.  上**常规**选项卡上，在**操作**文本框中，键入操作的操作。 请参阅[消息和消息架构](messages-and-message-schemas-for-biztalk-adapter-for-sql-server.md)有关每个操作的操作的列表。 例如，要调用 ADD_LAST_EMP_XML_INFO 的操作是：  
  
        ```  
        Procedure/dbo/ADD_LAST_EMP_XML_INFO  
        ```  
  
    3.  单击**绑定**选项卡上，并从**绑定类型**列表中，选择**sqlBinding**。 你可以指定不同的绑定属性公开的[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]。 有关绑定属性的详细信息，请参阅[了解针对 SQL Server 适配器绑定属性的 BizTalk 适配器](../../adapters-and-accelerators/adapter-sql/read-about-the-biztalk-adapter-for-sql-server-adapter-binding-properties.md)。  
  
    4.  单击**凭据**选项卡，，然后执行下列操作之一：  
  
        -   选择**不使用单一登录**选项，以及指定的用户名和密码以连接到 SQL Server。 请注意，用户名和密码区分大小写。  
  
            > [!NOTE]
            >  如果你想要连接到 SQL Server 使用 Windows 身份验证，则指定空白的用户名和密码。  
  
        -   选择**使用单一登录**选项，，然后指定关联企业单一登录 (SSO) 应用程序。  
  
             有关与 BizTalk Server 安全性的详细信息，请参阅[SQL 适配器与 BizTalk Server 的安全](../../adapters-and-accelerators/adapter-sql/security-with-the-sql-adapter-and-biztalk-server.md)。
  
    5.  单击**消息**选项卡上，然后在**出站 WCF 消息正文**部分中，选择**模板**选项。  
  
    6.  在**XML**文本框中，指定将用于构造 WCF 消息的模板。 通过这样做，你创建一条消息，符合基于 WCF 的 ADD_LAST_EMP_XML_INFO 操作[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]。  
  
         ![为出站 WCF 消息指定模板](../../adapters-and-accelerators/adapter-sql/media/012e9ff0-b78f-4a1d-8a3a-a7b8e3850d55.gif "012e9ff0-b78f-4a1d-8a3a-a7b8e3850d55")  
  
         有关 ADD_LAST_EMP_XML_INFO 存储过程中，你必须指定以下模板：  
  
        ```  
        <ADD_LAST_EMP_XML_INFO xmlns="http://schemas.microsoft.com/Sql/2008/05/Procedures/dbo">  
        <xml_info>  
        <bts-msg-body xmlns="http://www.microsoft.com/schemas/bts2007" encoding="string"/>  
        </xml_info>  
        </ADD_LAST_EMP_XML_INFO>  
        ```  
  
        > [!IMPORTANT]
        >  消息模板中的编码必须始终为"string"而不考虑将使用发送端口调用该操作的参数的类型。 例如，ADD_LAST_EMP_XML_INFO 采用 XML，类型参数，但消息模板中的编码为字符串。  
  
        > [!NOTE]
        >  你可以通过复制存储过程的请求消息并将替换为 BizTalk 消息正文的 < xml_info > 标记内的值创建此邮件模板。 你可以获得请求消息个存储过程的生成过程使用的架构[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]，然后生成的架构，以获取请求 XML 实例。  
  
    7.  若要返回到**发送端口属性**对话框中，单击**确定**。  
  
9. 从**发送处理程序**列表中，选择**BizTalkServerApplication**。  
  
10. 从**发送管道**列表中，选择对应于管道**PassThruTransmit**。  
  
11. 单击 **“确定”**。  
  
## <a name="start-the-application"></a>启动应用程序  
 若要启动 BizTalk 应用程序，你可以启动这两个文件接收位置和 WCF 自定义单独发送端口。 你必须现在将 XML 文件映射到文件的文件夹复制接收位置。 BizTalk 应用程序使用文件，并在员工表的地址列中插入的 XML 值。 可以通过使用 SQL Server 客户端并从员工表选择记录对此进行验证。  
  
## <a name="using-a-two-way-wcf-custom-send-port"></a>使用双向的 WCF 自定义发送端口  
 本主题中下一节, 中的说明[如何配置 WCF 自定义发送端口](../../core/how-to-configure-a-wcf-custom-send-port.md)，演示如何配置单向的 WCF 自定义发送端口，而无需使用 BizTalk 执行存储的过程使用单个参数业务流程。 但是，在这种情况下，若要验证是否在执行存储的过程已成功将必须验证 SQL Server 数据库中员工表中的地址列是否将更新。  
  
 相反，你可以创建双向 WCF 自定义发送端口还从 SQL Server 获取响应，如果成功执行存储的过程。 如果创建双向的 WCF 自定义端口，则必须执行一些附加步骤。 请注意，你仍将需要一个文件接收位置，如前面的说明操作中所述。  
  
1.  例如，创建双向的 WCF 自定义发送端口， **ExecProcedure**。 配置发送端口的步骤是类似于单向发送端口。 唯一的区别是双向端口你还必须指定接收管道。 请确保选择**PassThruReceive**接收管道。  
  
2.  创建文件发送端口。 此端口将响应消息从数据库中删除 SQL Server 到的文件夹。 使用**筛选器**选项卡上的端口属性对话框中，配置文件发送端口来接收所有响应消息的 WCF 自定义发送端口。  
  
    1.  在**发送端口属性**对话框中，从左窗格中，单击**筛选器**。  
  
    2.  在右窗格中，在**属性**列中，单击网格中，然后选择**BTS。SPName**属性。  
  
    3.  有关**运算符**列中，选择"**==**"。  
  
    4.  有关**值**列中，指定的名称的 WCF 自定义发送端口， `ExecProcedure`。  
  
 启动所有三个端口。 将 XML 文件映射到文件的文件夹复制接收位置。 查找映射到文件的文件夹中的响应发送端口。  
  
## <a name="see-also"></a>另请参阅  
[使用 SQL 适配器开发 BizTalk 应用程序](../../adapters-and-accelerators/adapter-sql/develop-biztalk-applications-using-the-sql-adapter.md)