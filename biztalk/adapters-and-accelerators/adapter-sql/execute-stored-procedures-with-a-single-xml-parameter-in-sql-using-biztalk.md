---
title: 在 SQL Server 使用 BizTalk Server 中执行使用单个 XML 参数的存储的过程 |Microsoft Docs
description: 在 BizTalk 中使用 WCF 自定义端口和 SQL 适配器存储过程中传递单个参数
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
ms.openlocfilehash: a71ee5be554393db10e65adb49694e7104bb011b
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36976920"
---
# <a name="execute-stored-procedures-with-a-single-xml-parameter-in-sql-server-using-biztalk-server"></a>在 SQL Server 使用 BizTalk Server 中执行使用单个 XML 参数的存储的过程
执行存储的过程采用单个参数是类似于执行任何其他存储的过程中所述[SQL Server 使用 BizTalk Server 中执行存储过程](execute-stored-procedures-in-sql-server-using-biztalk-server.md)。 但是，上述链接中所述的方法，你必须在设计时生成存储过程的元数据并创建一个业务流程在运行时调用该过程。  
  
 假设只是想要将一个单一值传递给存储过程，而无需执行任何处理此值。 在这种情况下，您不希望生成元数据、 创建业务流程、 部署业务流程，并执行该操作的开销。 相反，你可以配置 WCF 自定义或 WCF-SQL 发送端口来直接调用存储的过程。 本主题演示如何使用执行这些任务[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理控制台。  
  
> [!NOTE]
>  本主题提供有关如何配置 WCF 自定义发送端口执行采用单个参数的存储的过程。 可以通过配置 WCF SQL 端口执行相同的步骤。 有关如何配置 WCF SQL 端口的说明，请参阅[使用 WCF-SQL 适配器配置端口](configure-a-port-using-the-wcf-sql-adapter.md)。  
  
## <a name="invoke-stored-procedures-without-orchestration"></a>调用存储的过程，而无需业务流程  
 若要演示如何执行存储的过程使用单个参数而无需业务流程，本主题使用 ADD_LAST_EMP_XML_INFO 存储过程。 此过程采用 XML 值作为参数，并将其插入到**地址**的列**员工**表。 必须具有 XML 值将传递给存储过程。 但是，若要执行存储的过程使用的适配器，必须将发送请求消息的过程的架构符合和包含的 XML 值**地址**字段中，为 SQL Server。 因此，必须创建由该请求消息：  
  
- 使用**模板**中使用可创建使用消息模板的请求消息的发送端口配置选项。  
  
- 将 XML 值**地址**字段到消息。  
  
  本主题中详细介绍所有这些步骤。 您必须执行以下一组任务：  
  
1. 创建文件接收的端口将插入到 XML 文件将存放**地址**的 XML 字段**员工**表。 假设此端口被称为**MessageIn**端口。  
  
2. 创建一个 WCF 自定义单向发送端口提取 XML 文件从文件接收端口、 构造消息使用消息模板，并将其发送到 SQL Server 以执行该存储的过程。  
  
   主题的此部分介绍如何配置 WCF 自定义发送端口与消息模板。  
  
> [!NOTE]
>  尽管本主题中的信息演示如何执行存储的过程与单个 XML 参数，可以执行的任务执行任何操作，采用单个参数的任何数据类型。 唯一的区别是在创建针对特定操作的消息模板的方式。 可以通过将使用以执行此操作的请求消息创建的消息模板使用业务流程和参数的值替换为 BizTalk 消息正文。  
  
##  <a name="BKMK_OneWay"></a> 配置 Wcf-custom 发送端口  
 创建 WCF 自定义之前发送端口，请确保已创建文件接收端口中， **MessageIn**。  
  
1. 启动[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理控制台。  
  
2. 在控制台树中，展开**BizTalk 组**，然后展开**应用程序**。  
  
3. 展开你想要部署的应用程序[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]。  
  
4. 右键单击**发送端口**，依次指向**新建**，然后指向**静态单向发送端口**。  
  
5. 在中**发送端口属性**对话框中，在**常规**选项卡上，键入发送端口的名称。  
  
6. 配置端口以接收所有消息在该文件删除接收端口中， **MessageIn**。  
  
   1.  在中**发送端口属性**对话框中，从左窗格中，单击**筛选器**。  
  
   2.  在右窗格中下,**属性**列中，单击网格中，并选择**BTS。ReceivePortName**属性。  
  
   3.  有关**运算符**列中，选择"**==**"。  
  
   4.  有关**值**列中，指定的文件的名称的接收端口， `MessageIn`。  
  
7. 在中**发送端口属性**对话框中，在**常规**选项卡上，从**类型**下拉列表中，选择**WCF 自定义**，然后单击**配置**。  
  
8. 在中**Wcf-custom 传输属性**对话框框中，执行以下操作：  
  
   1. 单击**常规**选项卡上，然后在**地址 (URI)** 字段中，指定 SQL Server 的连接 URI。 有关连接 URI 的详细信息，请参阅[创建 SQL Server 连接 URI](../../adapters-and-accelerators/adapter-sql/create-the-sql-server-connection-uri.md)。  
  
   2. 上**常规**选项卡上，在**操作**文字框中，键入操作的操作。 请参阅[消息和消息架构](messages-and-message-schemas-for-biztalk-adapter-for-sql-server.md)有关每个操作的操作的列表。 例如，要调用 ADD_LAST_EMP_XML_INFO 的操作是：  
  
      ```  
      Procedure/dbo/ADD_LAST_EMP_XML_INFO  
      ```  
  
   3. 单击**绑定**选项卡上，并从**绑定类型**列表中，选择**sqlBinding**。 您可以指定不同的绑定属性公开的[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]。 有关绑定属性的详细信息，请参阅[了解关于 BizTalk Adapter for SQL Server 适配器绑定属性](../../adapters-and-accelerators/adapter-sql/read-about-the-biztalk-adapter-for-sql-server-adapter-binding-properties.md)。  
  
   4. 单击**凭据**选项卡，然后再执行下列操作之一：  
  
      -   选择**不使用单一登录**选项，以及指定的用户名和密码以连接到 SQL Server。 请注意，用户名和密码区分大小写。  
  
          > [!NOTE]
          >  如果你想要连接到 SQL Server 使用 Windows 身份验证，则指定空的用户名和密码。  
  
      -   选择**使用单一登录**选项，，然后指定附属机构企业单一登录 (SSO) 应用程序。  
  
           有关与 BizTalk Server 相关的安全性的详细信息，请参阅[SQL 适配器与 BizTalk Server 安全性](../../adapters-and-accelerators/adapter-sql/security-with-the-sql-adapter-and-biztalk-server.md)。
  
   5. 单击**消息**选项卡上，然后在**出站 WCF 消息正文**部分中，选择**模板**选项。  
  
   6. 在中**XML**文字框中，指定将用于构造 WCF 消息的模板。 通过此操作，创建一条消息，符合基于 WCF 的 ADD_LAST_EMP_XML_INFO 操作[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]。  
  
       ![指定出站 WCF 消息的模板](../../adapters-and-accelerators/adapter-sql/media/012e9ff0-b78f-4a1d-8a3a-a7b8e3850d55.gif "012e9ff0-b78f-4a1d-8a3a-a7b8e3850d55")  
  
       有关 ADD_LAST_EMP_XML_INFO 存储过程中，您必须指定以下模板：  
  
      ```  
      <ADD_LAST_EMP_XML_INFO xmlns="http://schemas.microsoft.com/Sql/2008/05/Procedures/dbo">  
      <xml_info>  
      <bts-msg-body xmlns="http://www.microsoft.com/schemas/bts2007" encoding="string"/>  
      </xml_info>  
      </ADD_LAST_EMP_XML_INFO>  
      ```  
  
      > [!IMPORTANT]
      >  消息模板中的编码必须始终为"string"而不考虑将使用发送端口调用的操作参数的类型。 例如，ADD_LAST_EMP_XML_INFO 采用一个参数的类型为 XML，但在消息模板中编码为字符串。  
      > 
      > [!NOTE]
      >  可以通过复制存储过程的请求消息并使用 BizTalk 消息正文替换 < xml_info > 标记内的值来创建此消息模板。 可以通过生成过程使用的架构的存储过程获取请求消息[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]，然后生成要获取请求 XML 的架构的实例。  
  
   7. 若要返回到**发送端口属性**对话框中，单击**确定**。  
  
9. 从**发送处理程序**列表中，选择**BizTalkServerApplication**。  
  
10. 从**发送管道**列表中，选择对应于管道**PassThruTransmit**。  
  
11. 单击“确定” 。  
  
## <a name="start-the-application"></a>启动应用程序  
 若要启动的 BizTalk 应用程序，可以启动这两个文件接收位置和 WCF 自定义单独发送端口。 你必须现在复制该文件夹映射到该文件的 XML 文件接收位置。 BizTalk 应用程序使用该文件，并在 Employee 表的地址列中插入的 XML 值。 可以通过使用 SQL Server 客户端并从 Employee 表中选择记录对此进行验证。  
  
## <a name="using-a-two-way-wcf-custom-send-port"></a>使用双向 WCF 自定义发送端口  
 本主题中下一节, 中的说明[如何配置 Wcf-custom 发送端口](../../core/how-to-configure-a-wcf-custom-send-port.md)，演示了如何配置用于执行带一个参数的存储的过程，而不使用 BizTalk 的单向 WCF 自定义发送端口业务流程。 但是，在这种情况下，若要验证是否执行该存储的过程已成功将必须验证 SQL Server 数据库中是否更新员工表中的地址列。  
  
 相反，您可以创建双向 Wcf-custom 发送端口还从 SQL Server 获取响应，如果成功执行存储的过程。 如果创建一个双向的 WCF 自定义端口，则必须执行一些附加步骤。 请注意，您仍需要一个文件接收位置，如前面的说明中所述。  
  
1. 例如，创建一个双向的 Wcf-custom 发送端口， **ExecProcedure**。 若要配置的发送端口的步骤是类似于单向发送端口。 唯一的区别是双向的端口，还必须指定接收管道。 请确保选择**PassThruReceive**接收管道。  
  
2. 创建 FILE 发送端口。 此端口将响应消息从数据库中删除 SQL Server 到的文件夹。 使用**筛选器**选项卡的端口属性对话框中，配置 FILE 发送端口以接收来自 WCF 自定义发送端口的所有响应消息。  
  
   1.  在中**发送端口属性**对话框中，从左窗格中，单击**筛选器**。  
  
   2.  在右窗格中下,**属性**列中，单击网格中，并选择**BTS。SPName**属性。  
  
   3.  有关**运算符**列中，选择"**==**"。  
  
   4.  有关**值**列中，指定发送端口的 WCF 自定义名称`ExecProcedure`。  
  
   启动所有三个端口。 复制文件夹映射到该文件的 XML 文件接收位置。 查找映射到 FILE 发送端口的文件夹中的响应。  
  
## <a name="see-also"></a>请参阅  
[使用 SQL 适配器开发 BizTalk 应用程序](../../adapters-and-accelerators/adapter-sql/develop-biztalk-applications-using-the-sql-adapter.md)