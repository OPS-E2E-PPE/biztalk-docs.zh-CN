---
title: 接收来自 SAP 使用 BizTalk Server 的入站 RFC 调用 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- RFC calls, receiving using BizTalk Server
ms.assetid: 822fd9fb-772f-4910-a11e-25c1d5dca6e1
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 4b949ae0d6d5938493c78ed542a67d3c8bd09b48
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/28/2017
ms.locfileid: "25967747"
---
# <a name="receive-inbound-rfc-calls-from-sap-using-biztalk-server"></a>接收来自 SAP 使用 BizTalk Server 的入站 RFC 调用
在 RFC 服务器方案中，有三个实体：  
  
-   将请求发送到 SAP 调用 RFC SAP 客户端。 这也可以通过使用 SAP GUI 或使 RFC 的客户端通过调用调用[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]。  
  
-   SAP 系统，其中包含 SAP 客户端调用的 RFC 函数定义。 在请求将传递 SAP 系统给 RFC 服务器 （适配器）。 这是该适配器可用于获取 SAP 服务器所做的插入适配器的 RFC 调用的元数据。  
  
-   [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] ，充当 RFC 服务器和承载实际 RFC。  
  
 第一个实体，SAP 客户端，不是本主题中讨论的。 如果使用 SAP GUI 来调用 RFC，请参阅 SAP 文档。 如果你使用[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]若要调用 RFC，请参阅[调用中使用 BizTalk server 的 SAP 的 Rfc](../../adapters-and-accelerators/adapter-sap/invoke-rfcs-in-sap-using-biztalk-server.md)。  
  
 本部分将说明了如何使用适配器接收 RFC 服务器呼叫，一旦 RFC 调用由 SAP 客户端。 有关详细信息的适配器如何支持接收 RFC 服务器调用使用[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]，请参阅[操作中 SAP Rfc](../../adapters-and-accelerators/adapter-sap/operations-on-rfcs-in-sap.md)。  
  
## <a name="how-to-receive-an-inbound-rfc-call-from-the-sap-system"></a>如何从 SAP 系统接收的入站的 RFC 调用？  
 执行对 SAP 系统使用的操作[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]涉及过程中所述的任务[创建 SAP 应用程序的构建基块](../../adapters-and-accelerators/adapter-sap/building-blocks-to-create-sap-applications.md)。 若要接收的 RFC 调用从 SAP 系统，这些任务包括：  
  
1.  配置 SAP 系统将在此情况下发送到外部应用程序，RFC [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]。  
  
2.  创建 BizTalk 项目，并为 RFC 生成架构的[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]将接收来自 SAP 系统。  
  
3.  在用于从 SAP 系统接收消息和发送响应 BizTalk 项目中创建消息。  
  
4.  创建业务流程收到来自 SAP 系统的 RFC、 处理它，并将对 SAP 系统的响应。  
  
5.  生成和部署 BizTalk 项目。  
  
6.  配置的 BizTalk 应用程序创建的物理发送和接收端口。  
  
7.  启动 BizTalk 应用程序。  
  
 本主题提供执行这些任务的说明。  
  
## <a name="activities-on-the-sap-system"></a>SAP 系统上的活动  
 在使用之前[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]若要收到来自 SAP 系统的 RFC 的入站的调用，请确保完成以下任务 SAP 系统上的。  
  
-   SAP 适配器的 RFC 目标必须存在。 [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]接收来自通过 SAP 系统上定义的 RFC 目标 SAP 系统的 Rfc。 RFC 目标包含 SAP 网关主机，SAP 网关服务，必须在代码中指定连接 URI 中 SAP 程序 ID。 有关如何设置上 SAP 的 RFC 目标的信息，请参阅[创建 RFC、 RFC 目标和发送从 SAP 系统的 RFC](creating-an-rfc-in-an-sap-system.md)。  
  
-   你必须创建 SAP 系统定义的 RFC 函数模块。 [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]在 SAP 系统上使用 RFC 定义以检索有关 RFC （同时在设计时和在运行时） 的元数据。 有关详细信息请参阅[在 SAP 系统中创建 RFC](../../adapters-and-accelerators/adapter-sap/creating-an-rfc-in-an-sap-system.md)。  
  
     下面是源代码的在 RFC 添加两个整数并返回其结果的 SAP 系统上的示例。 该代码通过指定的目标只是调用 RFC。 函数的实现可通过 SAP 适配器客户端代码。  
  
    ```  
    FUNCTION Z_RFC_ADD.  
    *"------------------------------------------------------------------  
    *"  
    *"Local interface:  
    *"  IMPORTING  
    *"     VALUE(X) TYPE  INT4  
    *"     VALUE(Y) TYPE  INT4  
    *"     VALUE(DEST) TYPE  CHAR20 DEFAULT 'SAPADAPTER'  
    *"  EXPORTING  
    *"     VALUE(RESULT) TYPE  INT4  
    *"------------------------------------------------------------------  
    CALL FUNCTION 'Z_RFC_ADD' DESTINATION DEST  
      EXPORTING X = X  
                Y = Y  
      IMPORTING RESULT = RESULT.  
  
    ENDFUNCTION.  
    ```  
  
## <a name="sample-based-on-this-topic"></a>基于本主题的示例  
 示例中，RFCServer，基于本主题还提供与[!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)]。 有关详细信息，请参阅[SAP 适配器的示例](../../adapters-and-accelerators/adapter-sap/samples-for-the-sap-adapter.md)。  
  
## <a name="generating-the-schema"></a>生成架构  
 在本主题中，若要演示如何从 SAP 系统中，接收的入站的 RFC 调用我们生成的架构*Z_RFC_ADD* RFC。 你在上一步中创建此 RFC。 此 RFC 使用两个整数值作为输入参数。  
  
 请参阅[浏览、 搜索和 get 元数据在 SAP 中的 RFC 操作](../../adapters-and-accelerators/adapter-sap/browse-search-and-get-metadata-for-rfc-operations-in-sap.md)有关如何为特定 RFC 生成架构的说明。  
  
> [!IMPORTANT]
>  因为您正在生成的入站 RFC 调用的架构，请确保选择**服务 （入站操作）** 从**选择协定类型**下拉列表中的[!INCLUDE[consumeadapterservlong](../../includes/consumeadapterservlong-md.md)]。  
  
## <a name="defining-messages-and-message-types"></a>定义消息和消息类型  
 你先前生成的架构描述业务流程中的消息所需的"类型"。 一条消息通常是一个变量，为其类型由相应的架构定义。 你必须链接您从生成的架构中的第一步的邮件 BizTalk 项目的业务流程视图。  
  
 对于本主题中，你必须创建两条消息，另一个用于从 SAP 系统，另一个用于将响应发送到 SAP 系统接收消息。  
  
 执行以下步骤以创建消息并将它们链接到该架构：  
  
#### <a name="to-create-messages-and-link-to-schema"></a>创建消息并将链接到架构  
  
1.  向 BizTalk 项目中添加新的业务流程。  
  
2.  打开业务流程视图 BizTalk 项目中，如果不是已打开。 单击**视图**，指向**其他窗口**，然后单击**业务流程视图**。  
  
3.  在**业务流程视图**，右键单击**消息**，然后单击**新消息**。  
  
4.  右键单击新创建消息，然后选择**属性窗口**。  
  
5.  在**属性**窗格**Message_1**，执行以下操作。  
  
    |使用此选项|执行的操作|  
    |--------------|----------------|  
    |Identifier|类型**请求**。|  
    |消息类型|从下拉列表中，展开**架构**，然后选择*RFCServer.SAPBindingSchema.Z_RFC_ADD*，其中*RFCServer*是 BizTalk 项目的名称。 *SAPBindingSchema*是为 RFC 生成的架构*Z_RFC_ADD*。|  
  
6.  重复步骤 2 创建一条新消息。 在**属性**窗格中，为新的消息中，执行以下操作。  
  
    |使用此选项|执行的操作|  
    |--------------|----------------|  
    |Identifier|类型**响应**。|  
    |消息类型|从下拉列表中，展开**架构**，然后选择*RFCServer.SAPBindingSchema.Z_RFC_ADDResponse*。|  
  
## <a name="setting-up-the-orchestration"></a>设置业务流程  
 你必须创建要使用 BizTalk 业务流程[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]用于从 SAP 系统接收 RFC 服务器调用。 此示例中，请考虑 RFC 客户端将请求发送到 SAP 系统，以添加两个整数的其中一个方案。 SAP 系统采用请求的输入参数，并将其传递到由外部 RFC 服务器[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]。 [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]接收来自 SAP 系统，过程添加两个整数的请求的请求并生成响应。 [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]将传递到 SAP 系统，反过来，将传递给 RFC 客户端的响应。  
  
 若要实现此业务流程的一部分，必须包含业务流程：  
  
-   双向接收端口收到来自 SAP 系统的 RFC 服务器请求和发送响应。  
  
-   发送和接收形状。  
  
-   构造消息形状，并在其中某个消息分配形状，处理 RFC 服务器请求来自 SAP 系统。  
  
 RFC 服务器调用示例业务流程如下所示。  
  
 ![业务流程，使 RFC 服务器调用](../../adapters-and-accelerators/adapter-sap/media/f5da2947-56d6-41f0-b411-c8e6eacf68cd.gif "f5da2947-56d6-41f0-b411-c8e6eacf68cd")  
  
### <a name="adding-message-shapes"></a>添加消息形状  
 请确保为每个消息形状指定以下属性。 中列出的名称*形状*列是前面的业务流程中显示的消息形状的名称。  
  
|形状|形状类型|属性|  
|-----------|----------------|----------------|  
|ListenToSAP|Receive|-将设置**名称**到*ListenToSAP*<br />-将设置**激活**到*True*|  
|SendResponse|Send|-将设置**名称**到*SendResponse*|  
  
### <a name="adding-construct-message-shape"></a>添加构造消息形状  
 若要处理传入的 RFC 调用，以将添加两个整数值，你必须添加构造消息形状并在该消息分配形状上与您的业务流程，这两者之间发送形状。 对于此示例中，消息赋值形状将调用以添加两个整数。 消息赋值形状还将设置到 SAP 系统发送的响应的操作。  
  
 构造消息形状中，请设置**构造消息**属性**响应**。  
  
 要处理 RFC 请求的代码可能与 BizTalk 项目相同的 Visual Studio 解决方案的一部分。 添加两个整数的示例代码如下所示。  
  
```  
namespace RFCServerResponseCreator  
{  
    public class RFCServerResponseCreator  
    {  
        private static XmlDocument messageIn;  
        private static XmlDocument messageOut;  
        public static XmlDocument CreateRequest(int a, int b, string destination)  
        {  
            messageIn = new XmlDocument();  
            messageIn.LoadXml(  "<Z_RFC_ADD xmlns=\"http://Microsoft.LobServices.Sap/2007/03/Rfc/\">" +  
                                "<DEST>" + destination + "</DEST>" +  
                                "<X>" + a + "</X>" +  
                                "<Y>" + b + "</Y>" +   
                                "</Z_RFC_ADD>"  
                             );  
            return messageIn;  
        }  
        public static XmlDocument CreateResponse(int a, int b)  
        {  
            int c = a + b;  
            messageOut = new XmlDocument();  
            messageOut.LoadXml( "<Z_RFC_ADDResponse xmlns=\"http://Microsoft.LobServices.Sap/2007/03/Rfc/\">" +  
                                "<RESULT>" + c + "</RESULT>" +   
                                "</Z_RFC_ADDResponse>"  
                              );  
            return messageOut;  
        }  
    }  
}  
```  
  
> [!NOTE]
>  生成项目后，将在项目目录中创建 RFCServerResponseCreator.dll。 必须将此 DLL 添加到全局程序集缓存 (GAC) 中。  
  
 添加以下表达式来调用此代码从消息赋值形状并设置发送到 SAP 系统的响应操作。 若要添加一个表达式，双击要打开表达式编辑器中的消息分配形状。  
  
```  
Response = RFCServerResponseCreator.RFCServerResponseCreator.CreateResponse(Request.X, Request.Y);  
Response(WCF.Action) = "http://Microsoft.LobServices.Sap/2007/03/Rfc/Z_RFC_ADD/response";  
```  
  
> [!IMPORTANT]
>  在响应消息上，必须显式设置操作。 如果未设置操作，WCF 自定义适配器在通过附加到请求的操作的"响应"到达操作消息。 因此，响应消息的操作会成为`http://Microsoft.LobServices.Sap/2007/03/Rfc/Z_RFC_ADDResponse`。 但是，sapBinding 需要响应操作按追加"/ 响应"到所请求操作，例如`http://Microsoft.LobServices.Sap/2007/03/Rfc/Z_RFC_ADD/response`。  
  
### <a name="adding-ports"></a>添加端口  
 请确保指定的逻辑端口的以下属性。 中列出的名称*端口*列是端口的名称的业务流程中所示。  
  
|端口|属性|  
|----------|----------------|  
|RFCServerPort|-将设置**标识符**到*RFCServerPort*<br />-将设置**类型**到*RFCServerPortType*<br />-将设置**通信模式**到*请求-响应*<br />-将设置**通信方向**到*接收发送*|  
  
## <a name="specify-messages-for-action-shapes-and-connect-to-ports"></a>指定消息的操作形状并将连接到端口  
 下表指定的属性和它们的值设置为指定消息的操作形状并将它们链接到的端口。 中列出的名称*形状*列是前面的业务流程中显示的消息形状的名称。  
  
|形状|属性|  
|-----------|----------------|  
|ListenToSAP|-将设置**消息**到*请求*<br />-将设置**操作**到*RFCServerPort.Add.Request*|  
|SendResponse|-将设置**消息**到*FuncResponse*<br />-将设置**操作**到*RFCServerPort.Add.Response*|  
  
 指定这些属性后，连接的消息形状和端口，您的业务流程已完成。  
  
 你必须立即生成 BizTalk 解决方案，然后将其部署到 BizTalk Server。 有关详细信息，请参阅[生成和运行业务流程](../../core/building-and-running-orchestrations.md)。
  
## <a name="configuring-the-biztalk-application"></a>配置 BizTalk 应用程序  
 部署 BizTalk 项目后，业务流程之前创建下列出**业务流程**BizTalk Server 管理控制台窗格中的。 必须使用 BizTalk Server 管理控制台配置该应用程序。 有关配置应用程序的详细信息，请参阅[如何配置应用程序](../../core/how-to-configure-an-application.md)。
  
 配置应用程序涉及：  
  
-   选择应用程序的主机。  
  
-   映射到在 BizTalk Server 管理控制台中的物理端口业务流程中创建的端口。 对于此业务流程，您必须：  
  
    -   定义 WCF 自定义或 WCF SAP 接收端口。 此端口将收到来自 SAP 系统的 RFC 的入站的调用，将发送回 SAP 系统的响应。 有关如何创建端口的信息，请参阅[手动配置到 SAP 适配器的物理端口绑定](../../adapters-and-accelerators/adapter-sap/manually-configure-a-physical-port-binding-to-the-sap-adapter.md)。  
  
        > [!NOTE]
        >  生成架构使用[!INCLUDE[consumeadapterservlong](../../includes/consumeadapterservlong-md.md)]还会创建包含有关端口和要为这些端口设置的操作的信息的绑定文件。 从 BizTalk 管理控制台来创建发送端口 （对于出站调用），或接收 （对于入站调用） 的端口，可以导入此绑定文件。 有关详细信息，请参阅[配置物理端口绑定使用的端口绑定文件，以便 SAP](../../adapters-and-accelerators/adapter-sap/configure-a-physical-port-binding-using-a-port-binding-file-to-sap.md)。
  
 你还必须向 BizTalk 应用程序添加 RFCServerResponseCreator 项目的程序集。 创建此项目以处理来自 SAP 系统的 RFC 调用。 为此：  
  
1.  在 BizTalk Server 管理控制台中，你可以导入的绑定，该 BizTalk 应用程序下的左侧的控制台树中右键单击**资源**，指向**添加**，然后单击**BizTalk 程序集**。  
  
2.  在**添加资源**对话框中，单击**添加**，然后导航到包含 RFCServerResponseCreator.dll 的文件夹。 选择该文件，然后单击**打开**。  
  
3.  在**添加资源**对话框中，单击**确定**。  
  
## <a name="starting-the-application"></a>启动应用程序  
 你必须启动 BizTalk 应用程序，用于从 SAP 系统接收 RFC 的入站的调用。 有关启动 BizTalk 应用程序的说明，请参阅[如何启动 Orchestration](../../core/how-to-start-an-orchestration.md)，和[如何启动应用程序](../../core/how-to-start-and-stop-a-biztalk-application.md)。
  
 在此阶段，请确保：  
  
-   WCF 自定义或 WCF SAP 接收端口，以便接收 RFC 调用从 SAP 系统正在运行。  
  
-   BizTalk 业务流程操作正在运行。  
  
## <a name="executing-the-operation"></a>执行该操作  
 运行应用程序后，必须发送到 RFC [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]。 你可以通过 SAP 系统中执行事务 SE37 来实现。 你还必须指定的 RFC 调用的输入的参数。 适配器接收以及参数的调用、 处理它，并发送回 SAP 系统的响应。 你将能够在同一事务中发送 RFC 上看到的响应。  
  
## <a name="possible-exceptions"></a>可能的异常  
 从 SAP 系统使用 BizTalk Server 接收的 RFC 服务器调用时可能会遇到异常的信息，请参阅[异常和错误处理与 SAP 适配器](../../adapters-and-accelerators/adapter-sap/exceptions-and-error-handling-with-the-sap-adapter.md)。  
  
## <a name="best-practices"></a>最佳实践  
 已部署并配置 BizTalk 项目之后，你可以将配置设置导出到 XML 文件称为绑定文件。 一旦生成绑定文件，你可以从文件导的配置设置，以便不需要创建发送端口，接收端口等相同的业务流程。 有关绑定文件的详细信息，请参阅[重用 SAP 适配器绑定](../../adapters-and-accelerators/adapter-sap/reuse-sap-adapter-bindings.md)。
  
## <a name="see-also"></a>另请参阅  
[开发 BizTalk 应用程序](../../adapters-and-accelerators/adapter-sap/develop-biztalk-applications-using-the-sap-adapter.md)