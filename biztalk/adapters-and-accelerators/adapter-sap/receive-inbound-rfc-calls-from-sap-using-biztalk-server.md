---
title: 接收来自 SAP 使用 BizTalk Server 的入站 RFC 调用 |Microsoft Docs
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
ms.openlocfilehash: c8e92d79aff5984517190f3f66382ec5d33caaed
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65373077"
---
# <a name="receive-inbound-rfc-calls-from-sap-using-biztalk-server"></a>接收来自 SAP 使用 BizTalk Server 的入站 RFC 调用
在 RFC 服务器方案中，有三个实体：  
  
- 将请求发送到 SAP 调用 RFC SAP 客户端。 这可以在使用 SAP GUI 或通过调用 RFC 客户端进行调用[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]。  
  
- SAP 系统，其中包含 SAP 客户端调用的 RFC 函数定义。 在请求将传递该 SAP 系统到 RFC 服务器 （适配器）。 这用于在适配器获取 SAP 服务器使该适配器为 RFC 调用的元数据。  
  
- [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] ，充当 RFC 服务器和承载实际的 RFC。  
  
  第一个实体，SAP 客户端，不是本主题中讨论的。 如果使用 SAP GUI 来调用 RFC，请参阅 SAP 文档。 如果使用的[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]若要调用 RFC，请参阅[调用中使用 BizTalk server 的 SAP 的 Rfc](../../adapters-and-accelerators/adapter-sap/invoke-rfcs-in-sap-using-biztalk-server.md)。  
  
  本部分将说明了如何使用适配器来接收 RFC 服务器调用，RFC 调用由 SAP 客户端之后。 有关详细信息的适配器如何支持接收 RFC 服务器调用使用[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]，请参阅[Rfc 在 SAP 中的操作](../../adapters-and-accelerators/adapter-sap/operations-on-rfcs-in-sap.md)。  
  
## <a name="how-to-receive-an-inbound-rfc-call-from-the-sap-system"></a>如何从 SAP 系统接收的入站的 RFC 调用？  
 对 SAP 系统使用执行操作[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]涉及过程中所述的任务[生成块以创建 SAP 应用程序](../../adapters-and-accelerators/adapter-sap/building-blocks-to-create-sap-applications.md)。 若要从 SAP 系统接收 RFC 调用，这些任务包括：  
  
1. 配置 SAP 系统将在这种情况下发送到外部应用程序，RFC [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]。  
  
2. 创建 BizTalk 项目和生成的在 RFC 架构的[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]将接收来自 SAP 系统。  
  
3. 创建在 BizTalk 项目中为接收来自 SAP 系统的消息和发送响应消息。  
  
4. 创建业务流程，以便接收来自 SAP 系统的 RFC、 处理它，并发送到 SAP 系统的响应。  
  
5. 生成并部署 BizTalk 项目。  
  
6. 配置的 BizTalk 应用程序通过创建物理发送端口和接收端口。  
  
7. 启动 BizTalk 应用程序。  
  
   本主题介绍如何执行这些任务。  
  
## <a name="activities-on-the-sap-system"></a>SAP 系统上的活动  
 使用之前[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]要接收来自 SAP 系统的入站的 RFC 调用，请确保完成 SAP 系统上的以下任务。  
  
- SAP 适配器的 RFC 目标必须存在。 [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]接收来自 SAP 系统通过 SAP 系统上定义的 RFC 目标的 Rfc。 RFC 目标包含 SAP 网关主机、 SAP 网关服务和 SAP 程序 ID，必须在代码中指定连接 URI 中。 有关如何设置上 SAP 的 RFC 目标的信息，请参阅[创建 RFC、 RFC 目标和发送从 SAP 系统的 RFC](creating-an-rfc-in-an-sap-system.md)。  
  
- 必须创建 SAP 系统定义的 RFC 函数模块。 [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] SAP 系统上使用 RFC 定义来检索有关 RFC （两者均在设计时和运行时） 的元数据。 有关详细信息请参阅[在 SAP 系统中创建 RFC](../../adapters-and-accelerators/adapter-sap/creating-an-rfc-in-an-sap-system.md)。  
  
   下面是源代码的添加两个整数并返回其结果的 RFC SAP 系统上的示例。 该代码通过指定的目标只是调用 RFC。 函数的实现是通过 SAP 适配器客户端代码。  
  
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
 示例中，RFCServer，根据本主题还提供与[!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)]。 有关详细信息，请参阅[SAP 适配器的示例](../../adapters-and-accelerators/adapter-sap/samples-for-the-sap-adapter.md)。  
  
## <a name="generating-the-schema"></a>生成架构  
 在本主题中，若要演示如何从 SAP 系统中，接收的入站的 RFC 调用我们生成的架构*Z_RFC_ADD* RFC。 在上一步中创建此 RFC。 此 RFC 使用两个整数值作为输入参数。  
  
 请参阅[浏览、 搜索和获取元数据中 SAP RFC 操作](../../adapters-and-accelerators/adapter-sap/browse-search-and-get-metadata-for-rfc-operations-in-sap.md)有关如何为特定 RFC 生成架构的说明。  
  
> [!IMPORTANT]
>  因为您正在生成的入站 RFC 调用的架构，请确保选择**服务 （入站操作）** 从**选择协定类型**下拉列表中的[!INCLUDE[consumeadapterservlong](../../includes/consumeadapterservlong-md.md)]。  
  
## <a name="defining-messages-and-message-types"></a>定义消息和消息类型  
 先前生成的架构描述业务流程中的消息所需的"类型"。 一条消息通常是一个变量，要为其类型定义由相应的架构。 必须链接生成的架构，第一步中的消息从 BizTalk 项目的业务流程视图。  
  
 对于本主题中，您必须创建两条消息，另一个用于接收来自 SAP 系统，另一个将发送到 SAP 系统的响应消息。  
  
 执行以下步骤以创建消息并将其链接到该架构：  
  
#### <a name="to-create-messages-and-link-to-schema"></a>若要创建消息并将链接到架构  
  
1.  将新的业务流程添加到 BizTalk 项目。  
  
2.  打开业务流程视图 BizTalk 项目中，如果还没有打开。 单击**视图**，依次指向**其他 Windows**，然后单击**业务流程视图**。  
  
3.  在中**业务流程视图**，右键单击**消息**，然后单击**新消息**。  
  
4.  右键单击新创建消息，然后选择**属性窗口**。  
  
5.  在中**属性**窗格**Message_1**，执行以下操作。  
  
    |使用此选项|执行的操作|  
    |--------------|----------------|  
    |Identifier|类型**请求**。|  
    |消息类型|从下拉列表中，展开**架构**，然后选择*RFCServer.SAPBindingSchema.Z_RFC_ADD*，其中*RFCServer*是 BizTalk 项目的名称。 *SAPBindingSchema*是为 RFC 生成的架构*Z_RFC_ADD*。|  
  
6.  重复步骤 2，以创建新的消息。 在中**属性**窗格中的新消息，执行以下操作。  
  
    |使用此选项|执行的操作|  
    |--------------|----------------|  
    |Identifier|类型**响应**。|  
    |消息类型|从下拉列表中，展开**架构**，然后选择*RFCServer.SAPBindingSchema.Z_RFC_ADDResponse*。|  
  
## <a name="setting-up-the-orchestration"></a>设置业务流程  
 必须创建 BizTalk 业务流程使用[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]，接收来自 SAP 系统的 RFC 服务器调用。 此示例中，请考虑其中 RFC 客户端将请求发送到 SAP 系统，以添加两个整数的方案。 SAP 系统接受请求，使用输入参数，并将其传递到托管的外部 RFC 服务器[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]。 [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]接收来自 SAP 系统、 过程添加两个整数的请求的请求，并生成响应。 [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]将传递到 SAP 系统，反过来，传递到 RFC 客户端的响应。  
  
 若要实现此业务流程的一部分，必须包含该业务流程：  
  
- 一个双向接收端口以接收来自 SAP 系统的 RFC 服务器请求并发送响应。  
  
- 发送和接收形状。  
  
- 构造消息形状，以及在其中消息赋值形状，以处理 RFC 服务器请求来自 SAP 系统。  
  
  RFC 服务器调用的示例业务流程如下所示。  
  
  ![用于发出 RFC 服务器调用的业务流程](../../adapters-and-accelerators/adapter-sap/media/f5da2947-56d6-41f0-b411-c8e6eacf68cd.gif "f5da2947-56d6-41f0-b411-c8e6eacf68cd")  
  
### <a name="adding-message-shapes"></a>添加消息形状  
 请确保为每个消息形状中指定以下属性。 中列出的名称*形状*列是消息形状的名称，前面的业务流程中所示。  
  
|形状|形状类型|属性|  
|-----------|----------------|----------------|  
|ListenToSAP|Receive|-设置**名称**到*ListenToSAP*<br />-设置**激活**到 *，则返回 True*|  
|SendResponse|Send|-设置**名称**到*SendResponse*|  
  
### <a name="adding-construct-message-shape"></a>添加构造消息形状  
 若要处理传入的 RFC 调用，以添加两个整数值，必须添加构造消息形状和在其中向业务流程，两者之间的消息赋值形状发送形状。 此示例中，为消息赋值形状调用以添加两个整数。 消息赋值形状也设置为要发送到 SAP 系统的响应的操作。  
  
 对于构造消息形状中，请设置**构造的消息**属性设置为**响应**。  
  
 用于处理 RFC 请求的代码可能与您的 BizTalk 项目相同的 Visual Studio 解决方案的一部分。 添加两个整数的示例代码如下所示。  
  
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
  
 添加以下表达式调用来调用此代码从消息赋值形状以及设置发送到 SAP 系统的响应的操作。 若要添加一个表达式，请双击消息赋值形状以打开表达式编辑器。  
  
```  
Response = RFCServerResponseCreator.RFCServerResponseCreator.CreateResponse(Request.X, Request.Y);  
Response(WCF.Action) = "http://Microsoft.LobServices.Sap/2007/03/Rfc/Z_RFC_ADD/response";  
```  
  
> [!IMPORTANT]
>  在响应消息，必须显式设置该操作。 如果未设置操作，WCF 自定义适配器到达的操作消息，通过追加到请求的操作的"响应"。 因此，响应消息的操作变得`http://Microsoft.LobServices.Sap/2007/03/Rfc/Z_RFC_ADDResponse`。 但是，sapBinding 要求响应操作通过追加"/ 响应"到请求的操作，例如`http://Microsoft.LobServices.Sap/2007/03/Rfc/Z_RFC_ADD/response`。  
  
### <a name="adding-ports"></a>添加端口  
 请确保指定的逻辑端口的以下属性。 中列出的名称*端口*列是在业务流程中显示的端口的名称。  
  
|Port|属性|  
|----------|----------------|  
|RFCServerPort|-设置**标识符**到*RFCServerPort*<br />-设置**类型**到*RFCServerPortType*<br />-设置**通信模式**到*请求-响应*<br />-设置**通信方向**到*接收发送*|  
  
## <a name="specify-messages-for-action-shapes-and-connect-to-ports"></a>为操作形状指定消息并将连接到端口  
 下表指定的属性和它们的值设置为指定的操作形状并将它们链接到的端口的消息。 中列出的名称*形状*列是消息形状的名称，前面的业务流程中所示。  
  
|形状|属性|  
|-----------|----------------|  
|ListenToSAP|-设置**消息**到*请求*<br />-设置**操作**到*RFCServerPort.Add.Request*|  
|SendResponse|-设置**消息**到*FuncResponse*<br />-设置**操作**到*RFCServerPort.Add.Response*|  
  
 指定这些属性后，消息形状和端口进行连接，您的业务流程已完成。  
  
 你必须现在生成 BizTalk 解决方案，然后将其部署到 BizTalk Server。 有关详细信息，请参阅[构建和运行业务流程](../../core/building-and-running-orchestrations.md)。
  
## <a name="configuring-the-biztalk-application"></a>配置 BizTalk 应用程序  
 部署 BizTalk 项目后，将前面创建的业务流程下列出**业务流程**BizTalk Server 管理控制台窗格中的。 必须使用 BizTalk Server 管理控制台来配置应用程序。 有关配置应用程序的详细信息，请参阅[如何配置应用程序](../../core/how-to-configure-an-application.md)。
  
 配置应用程序包括：  
  
- 选择应用程序的主机。  
  
- 映射到 BizTalk Server 管理控制台中的物理端口在业务流程中创建的端口。 对于此业务流程，您必须：  
  
  - 定义 WCF 自定义或 WCF SAP 接收端口。 此端口将收到来自 SAP 系统的入站的 RFC 调用，将发送到 SAP 系统的响应。 有关如何创建端口的信息，请参阅[手动配置到 SAP 适配器的物理端口绑定](../../adapters-and-accelerators/adapter-sap/manually-configure-a-physical-port-binding-to-the-sap-adapter.md)。  
  
    > [!NOTE]
    >  生成架构使用[!INCLUDE[consumeadapterservlong](../../includes/consumeadapterservlong-md.md)]还会创建包含有关端口和要为这些端口设置的操作信息的绑定文件。 从 BizTalk 管理控制台来创建 （对于出站调用） 的发送端口或接收端口 （对于入站调用），可以导入此绑定文件。 有关详细信息，请参阅[配置物理端口绑定使用的端口绑定文件与 SAP](../../adapters-and-accelerators/adapter-sap/configure-a-physical-port-binding-using-a-port-binding-file-to-sap.md)。
  
  您还必须将 RFCServerResponseCreator 项目的程序集添加到 BizTalk 应用程序。 创建此项目以处理来自 SAP 系统的 RFC 调用。 为此，请执行以下操作：  
  
1.  在下导入绑定，其中的 BizTalk 应用程序的 BizTalk Server 管理控制台左侧的控制台树中右键单击**资源**，依次指向**添加**，然后单击**BizTalk 程序集**。  
  
2.  在中**添加资源**对话框中，单击**添加**，然后导航到包含 RFCServerResponseCreator.dll 的文件夹。 选择该文件，然后单击**打开**。  
  
3.  在中**添加资源**对话框中，单击**确定**。  
  
## <a name="starting-the-application"></a>启动应用程序  
 必须启动用于接收来自 SAP 系统的入站的 RFC 调用的 BizTalk 应用程序。 在启动 BizTalk 应用程序的说明，请参阅[如何启动业务流程](../../core/how-to-start-an-orchestration.md)，并[如何启动应用程序](../../core/how-to-start-and-stop-a-biztalk-application.md)。
  
 在此阶段，请确保：  
  
-   WCF 自定义或 WCF SAP 接收端口以接收 RFC 调用从 SAP 系统正在运行。  
  
-   该操作的 BizTalk 业务流程正在运行。  
  
## <a name="executing-the-operation"></a>执行该操作  
 在运行该应用程序后，必须将发送到 RFC [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]。 可以通过 SAP 系统上执行事务 SE37 来执行操作。 此外必须指定的输入的参数的 RFC 调用。 适配器接收的调用以及参数、 其进行处理，并将发送到 SAP 系统的响应。 你将能够从发送 RFC 位置在同一事务上看到的响应。  
  
## <a name="possible-exceptions"></a>可能的异常  
 从 SAP 系统使用 BizTalk Server 接收 RFC 服务器调用时可能会遇到异常的信息，请参阅[异常和错误处理与 SAP 适配器](../../adapters-and-accelerators/adapter-sap/exceptions-and-error-handling-with-the-sap-adapter.md)。  
  
## <a name="best-practices"></a>最佳实践  
 部署和配置 BizTalk 项目后，你可以配置设置导出到名为绑定文件的 XML 文件。 一旦生成绑定文件，可以以便不需要创建发送端口、 接收端口，等等。 对于同一业务流程从文件导的配置设置。 有关绑定文件的详细信息，请参阅[重复使用 SAP 适配器绑定](../../adapters-and-accelerators/adapter-sap/reuse-sap-adapter-bindings.md)。
  
## <a name="see-also"></a>请参阅  
[开发 BizTalk 应用程序](../../adapters-and-accelerators/adapter-sap/develop-biztalk-applications-using-the-sap-adapter.md)