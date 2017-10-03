---
title: "接收 Oracle E-business Suite 更改通知以增量方式使用 BizTalk Server |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 63dbeacc-ecde-497d-b12d-d5f9944a33f0
caps.latest.revision: "19"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 217a34ad256886b945bb0db43edb8fdcbe875ccc
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="receive-oracle-e-business-suite-change-notifications-incrementally-using-biztalk-server"></a>接收以增量方式使用 BizTalk Server 的 Oracle E-business Suite 更改通知
> [!IMPORTANT]
>  为了简便起见，本主题仅介绍如何以增量方式接收通知。 在业务方案中，业务流程理想情况下必须包含提取的收到的通知消息的种类，然后执行所有后续操作的逻辑。 换而言之，本主题中所述的业务流程必须基于业务流程中所述[Oracle E-business Suite 中完成特定任务的进程通知消息](../../adapters-and-accelerators/adapter-oracle-ebs/process-notification-messages-to-complete-specific-tasks-in-oracle-ebs.md)。  
  
 本主题演示如何配置[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]要接收来自 Oracle 增量查询通知邮件。 为了演示增量通知，我们认为，ACCOUNTACTIVITY，具有列的表"处理"。 一条新记录插入到此表时，"处理"列的值设置为 ' n '。 你可以配置适配器后，通过执行以下操作中接收增量通知：  
  
-   注册通知使用检索到的具有"处理"列的所有记录的 SELECT 语句 ' n '。 你可以通过指定的 SELECT 语句来实现**NotificationStatement**绑定属性。  
  
-   对于已接到通知有关的行，更新为 y 的"处理"列。  
  
 本主题演示如何创建 BizTalk 业务流程和配置 BizTalk 应用程序来实现此目的。  
  
## <a name="configuring-notifications-with-the-oracle-e-business-adapter-binding-properties"></a>与 Oracle E-business 适配器绑定属性中配置通知  
 下表总结了[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]绑定属性，用于配置从 Oracle E-business Suite 接收通知。 配置中的接收端口时，必须指定这些绑定属性[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理控制台。  
  
> [!NOTE]
>  你可以选择在生成的架构时指定这些绑定属性**通知**操作，即使它不是强制性。 如果这样做，端口绑定文件[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]生成元数据生成的一部分还包含你指定的绑定属性的值。 你稍后导入中的此绑定文件[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理控制台来创建 WCF 自定义或 WCF OracleEBS 接收属性已设置对绑定的端口。 有关创建接收端口使用绑定文件的详细信息，请参阅[物理端口绑定使用端口绑定文件到 Oracle E-business Suite 配置](../../adapters-and-accelerators/adapter-oracle-ebs/configure-a-physical-port-binding-using-a-port-binding-file-to-oracle-ebs.md)。  
  
|绑定属性|Description|  
|----------------------|-----------------|  
|**InboundOperationType**|指定你想要执行的入站的操作。 若要接收通知消息，请将此设置为**通知**。|  
|**NotificationPort**|指定 ODP.NET 必须打开侦听从 Oracle 数据库的数据库更改通知的端口号。|  
|**NotificationStatement**|指定用来注册查询通知的 SELECT 语句。 仅当指定的 SELECT 语句更改的结果集时，适配器获取一条通知消息。|  
|**NotifyOnListenerStart**|指定启动侦听器时，适配器是否发送到适配器客户端通知。|  
  
 有关这些属性的更完整说明，请参阅[了解针对 Oracle E-business Suite 绑定属性的 BizTalk 适配器](../../adapters-and-accelerators/adapter-oracle-ebs/read-about-the-biztalk-adapter-for-oracle-e-business-suite-binding-properties.md)。 有关如何使用的完整说明[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]若要从 Oracle E-business Suite 接收通知，请阅读更多。  
  
## <a name="how-this-topic-demonstrates-receiving-notification-messages"></a>本主题演示接收通知消息的方式  
 在此主题中，以演示如何[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]支持从 Oracle E-business Suite 接收增量数据库更改通知消息的功能，我们将配置的适配器接收到 ACCOUNTACTIVTY 表的更改的通知。 让我们假定 ACCOUNTACTIVITY 表具有"TID"、"帐户"和"处理"的列。 每当添加一条新记录，"处理"列的值设置为 ' n '。 因此，若要获取增量通知并将需要作为 BizTalk 业务流程的一部分执行以下任务：  
  
-   获取"处理"所在的所有记录的通知 ' n '。 你可以指定为通知语句的 SELECT 语句来执行此操作。  
  
-   对于某些记录收到通知后，设置为 y 的"处理"。 可以通过执行存储的过程，PROCESS_RECORDS，这将更新的"处理"列来执行此操作。  
  
 为了演示接收增量通知，我们执行以下操作：  
  
-   生成架构**通知**（入站操作），和**PROCESS_RECORDS** （出站操作） ACCOUNTACTIVITY 表。  
  
-   创建具有以下业务流程：  
  
    -   接收位置接收通知消息。 可通过指定为 SELECT 语句来配置通知：  
  
        ```  
        SELECT TID,ACCOUNT,PROCESSED FROM SCOTT.ACCOUNTACTIVITY WHERE PROCESSED = ‘n’  
        ```  
  
        > [!NOTE]
        >  您必须指定架构名称以及表名称。 例如， `SCOTT.ACCOUNTACTIVITY`。  
  
    -   若要更新已为其发送通知的行发送端口。 在此端口设置为 y 收到通知时的记录的"处理"列的值，则将执行 PROCESS_RECORDS 存储过程。  
  
         请注意后接收通知消息，以便这些已处理的行进行更新，必须执行此操作。 若要使用正在等待获取通知响应，然后手动删除要执行 PROCESS_RECORDS 过程的请求消息的开销，执行操作时，将生成 PROCESS_RECORDS 过程中业务流程本身的请求消息。 你可以通过使用来实现**构造消息**形状中业务流程。  
  
## <a name="how-to-receive-notification-messages-from-oracle-e-business-suite"></a>如何从 Oracle E-business Suite 接收通知消息  
 执行对 Oracle E-business Suite 使用的操作[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]与[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]涉及过程中所述的任务[创建 Oracle E-business Suite 应用程序的构建基块](../../adapters-and-accelerators/adapter-oracle-ebs/building-blocks-to-create-oracle-e-business-suite-applications.md)。 若要配置的适配器以接收通知消息，这些任务包括：  
  
1.  创建 BizTalk 项目，然后生成架构**通知**（入站操作） 和**PROCESS_RECORDS** ACCOUNTACTIVITY 表上的过程 （出站操作）。 （可选） 你可以为指定值**InboundOperationType**， **NotificationPort**，和**NotificationStatement**绑定属性。  
  
2.  在从 Oracle E-business Suite 接收通知的 BizTalk 项目中创建一条消息。  
  
3.  创建 BizTalk 项目用于执行 PROCESS_RECORDS 存储过程和接收响应消息中的消息。  
  
4.  创建业务流程中执行以下任务：  
  
    -   从 Oracle E-business Suite 接收通知消息。  
  
    -   创建消息，以执行 PROCESS_RECORDS 过程。  
  
    -   将此消息发送到 Oracle E-business Suite 选择和更新的记录，收到的响应。  
  
5.  生成和部署 BizTalk 项目。  
  
6.  配置的 BizTalk 应用程序创建的物理发送和接收端口。  
  
    > [!NOTE]
    >  对于入站操作，如接收通知消息，你必须仅配置单向的 WCF 自定义或 WCF OracleEBS 接收端口。 双向接收入站操作不支持端口。  
  
7.  启动 BizTalk 应用程序。  
  
 本主题提供执行这些任务的说明。  
  
## <a name="generating-schema"></a>生成架构  
 必须生成的架构**通知**操作和**PROCESS_RECORDS**过程。 请参阅[检索用于 Oracle E-business Suite 操作 Visual Studio 中的元数据](../../adapters-and-accelerators/adapter-oracle-ebs/get-metadata-for-oracle-e-business-suite-operations-in-visual-studio.md)有关如何生成架构的详细信息。 生成架构时，请执行以下任务。 如果你不想要指定的绑定属性在设计时，跳过的第一步。  
  
1.  为指定值**InboundOperationType**， **NotificationPort**，和**NotificationStatement**生成架构时绑定属性。 有关此绑定属性的详细信息，请参阅[了解针对 Oracle E-business Suite 绑定属性的 BizTalk 适配器](../../adapters-and-accelerators/adapter-oracle-ebs/read-about-the-biztalk-adapter-for-oracle-e-business-suite-binding-properties.md)。 有关如何指定绑定属性的说明，请参阅[配置的 Oracle E-business Suite 绑定属性](../../adapters-and-accelerators/adapter-oracle-ebs/configure-the-binding-properties-for-oracle-e-business-suite.md)。  
  
2.  选择与具有协定类型**服务 （入站操作）**。  
  
3.  生成架构**通知**操作。  
  
4.  选择与具有协定类型**客户端 （出站操作）**。  
  
5.  生成架构**PROCESS_RECORDS**过程。 此过程位于下**ACCOUNT_PKG**包。  
  
## <a name="defining-messages-and-message-types"></a>定义消息和消息类型  
 你先前生成的架构描述业务流程中的消息所需的"类型"。 一条消息通常是一个变量，为其类型由相应的架构定义。 后生成架构，你必须将其从 BizTalk 项目的业务流程视图链接到消息中。  
  
 对于本主题中，你必须创建三个消息 — 一个用于从 Oracle E-business Suite 接收通知，一个另一个执行 PROCESS_RECORDS 过程中，接收过程的响应。  
  
 执行以下步骤以创建消息并将它们链接到架构。  
  
#### <a name="to-create-messages-and-link-to-schema"></a>创建消息并将链接到架构  
  
1.  BizTalk 项目中添加业务流程。 从解决方案资源管理器，右键单击 BizTalk 项目名称，指向**添加**，然后单击**新项**。 键入 BizTalk 业务流程的名称，然后单击**添加**。  
  
2.  如果尚未打开，请打开 BizTalk 项目的业务流程视图窗口。 单击**视图**，指向**其他窗口**，然后单击**业务流程视图**。  
  
3.  在**业务流程视图**，右键单击**消息**，然后单击**新消息**。  
  
4.  右键单击新创建的消息中，，然后选择**属性窗口**。  
  
5.  在**属性**窗格**Message_1**，执行以下操作：  
  
    |使用此选项|执行的操作|  
    |--------------|----------------|  
    |Identifier|键入 `NotifyReceive`。|  
    |消息类型|从下拉列表中，展开**架构**，然后选择*OracleNotifyIncremental.OracleEBSBinding.Notification*，其中*OracleNotifyIncremental*是的名称你的 BizTalk 项目。 *OracleEBSBinding*是为生成的架构**通知**操作。|  
  
6.  重复步骤 3 以创建两条新消息。 在**属性**窗格中，为新的消息中，执行以下操作：  
  
    |设置为标识符|将消息类型设置为|  
    |-----------------------|-------------------------|  
    |过程|*OracleNotifyIncremental.OracleEBSBinding1.PROCESS_RECORDS*，其中*OracleEBSBinding1*是为生成的架构**PROCESS_RECORDS**过程。|  
    |ProcedureResponse|*OracleNotifyIncremental.OracleEBSBinding1.PROCESS_RECORDSResponse*|  
  
## <a name="setting-up-the-orchestration"></a>设置业务流程  
 你必须创建要使用 BizTalk 业务流程[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]为 Oracle E-business Suite 从接收通知消息，然后更新为其接收到通知的行。 在此业务流程，适配器接收基于 SELECT 语句为指定的通知消息**NotificationStatement**绑定属性。 在文件位置接收通知消息。 一旦收到响应，业务流程将构造一条消息，调用 PROCESS_RECORDS 过程中，将更新为其接收通知的行。 在相同的文件位置还收到此消息的响应。  
  
 因此，您的业务流程必须包含以下信息：  
  
-   单向的 WCF 自定义或 WCF OracleEBS 接收端口以接收通知消息。  
  
-   双向的 WCF 自定义或 WCF OracleEBS 发送端口发送消息，以执行 PROCESS_RECORDS 过程。  
  
-   A**构造消息**构造消息，以执行 PROCESS_RECORDS 过程，业务流程中的形状。  
  
-   文件发送端口以保存通知消息并 PROCESS_RECORDS 过程的响应。  
  
-   接收和发送形状。  
  
 示例业务流程如下所示。  
  
 ![要从 Oracle 接收通知的业务流程](../../adapters-and-accelerators/adapter-oracle-database/media/cef49414-490a-4bd5-a32d-b3f4cde5950a.gif "cef49414-490a-4bd5-a32d-b3f4cde5950a")  
  
### <a name="adding-message-shapes"></a>添加消息形状  
 请确保为每个消息形状指定以下属性。 刚提到业务流程中所示，形状列中列出的名称将是消息形状的名称。  
  
|形状|形状类型|属性|  
|-----------|----------------|----------------|  
|ReceiveNotification|Receive|-将设置**名称**到*ReceiveNotification*<br /><br /> -将设置**激活**到*True*|  
|SaveNotification|Send|-将设置**名称**到*SaveNotification*|  
|SendProcMessage|Send|-将设置**名称**到*SendProcMessage*|  
|ReceiveProcResponse|Receive|-将设置**名称**到*ReceiveProcResponse*|  
|SaveProcResponse|Send|-将设置**名称**到*SaveProcResponse*|  
  
### <a name="adding-construct-message-shape"></a>添加构造消息形状  
 你可以使用**构造消息**形状以生成请求消息中业务流程执行 PROCESS_RECORDS 过程。 若要执行此操作，你必须添加**构造消息**形状和在其中**消息分配**形状上与您的业务流程。 对于此示例，**消息分配**形状调用生成一条消息，发送到 Oracle E-business Suite 执行过程的代码。 **消息分配**形状还设置用于消息发送到 Oracle E-business Suite 的操作。  
  
 构造消息形状，请设置**构造消息**属性**过程**。  
  
 用于生成响应的代码可能与 BizTalk 项目相同的 Visual Studio 解决方案的一部分。 示例代码，用于生成响应消息如下所示。  
  
```  
namespace MessageCreator  
{  
    public class MessageCreator  
    {  
        private static XmlDocument Message;  
        private static string XmlFileLocation;  
        private static string ResponseDoc;  
  
        public static XmlDocument XMLMessageCreator()  
        {  
            XmlFileLocation = "C:\\TestLocation\\MessageIn";  
            try  
            {  
                ResponseDoc = (Directory.GetFiles(XmlFileLocation, "*.xml", SearchOption.TopDirectoryOnly))[0];  
            }  
            catch (Exception ex)  
            {  
                Console.WriteLine("Trying to get XML from: " + XmlFileLocation);  
                Console.WriteLine("EXCEPTION: " + ex.ToString());  
                throw ex;  
            }  
            //Create Message From XML  
            Message = new XmlDocument();  
            Message.PreserveWhitespace = true;  
            Message.Load(ResponseDoc);  
            return Message;  
        }   
    }  
}  
```  
  
 对于上述代码摘录中能够生成请求消息，你必须为指定的位置中具有 XML 请求消息 （针对 PROCESS_RECORDS 过程中）`XmlFileLocation`变量。  
  
> [!NOTE]
>  生成项目后，将在项目目录中创建 MessageCreator.dll。 必须将此 DLL 添加到全局程序集缓存 (GAC) 中。 此外，你必须添加 MessageCreator.dll 作为 BizTalk 项目中的引用。  
  
 添加以下表达式来调用此代码从**消息分配**形状以及设置用于消息的操作。 若要添加一个表达式，请双击**消息分配**形状以打开表达式编辑器中。  
  
```  
Procedure = MessageCreator.MessageCreator.XMLMessageCreator();  
Procedure(WCF.Action) = "PackageApis/SCOTT/ACCOUNT_PKG/PROCESS_RECORDS";  
```  
  
### <a name="adding-ports"></a>添加端口  
 请确保为每个逻辑端口指定以下属性。 端口列中列出的名称是在业务流程中显示的端口的名称。  
  
|端口|属性|  
|----------|----------------|  
|OracleNotifyPort|-将设置**标识符**到*OracleNotifyPort*<br /><br /> -将设置**类型**到*OracleNotifyPortType*<br /><br /> -将设置**通信模式**到*单向*<br /><br /> -将设置**通信方向**到*接收*|  
|SaveMessagePort|-将设置**标识符**到*SaveMessagePort*<br /><br /> -将设置**类型**到*SaveMessagePortType*<br /><br /> -将设置**通信模式**到*单向*<br /><br /> -将设置**通信方向**到*发送*<br /><br /> -创建一个操作*通知*。 此操作用于通知消息。<br /><br /> -创建一个操作*过程*。 选择响应消息将要使用此操作。|  
|OracleOutboundPort|-将设置**标识符**到*OracleOutboundPort*<br /><br /> -将设置**类型**到*OracleOutboundPortType*<br /><br /> -将设置**通信模式**到*请求-响应*<br /><br /> -将设置**通信方向**到*发送接收*|  
  
### <a name="specify-messages-for-action-shapes-and-connect-to-ports"></a>指定消息的操作形状并将连接到端口  
 下表指定的属性和用于指定操作形状的消息，并链接到的端口的消息应设置其值。 前面提到的业务流程中所示，形状列中列出的名称将是消息形状的名称。  
  
|形状|属性|  
|-----------|----------------|  
|ReceiveNotification|-将设置**消息**到*NotifyReceive*<br /><br /> -将设置**操作**到*OracleNotifyPort.Notify.Request*|  
|SaveNotification|-将设置**消息**到*NotifyReceive*<br /><br /> -将设置**操作**到*SaveMessagePort.Notify.Request*|  
|SendProcMessage|-将设置**消息**到*过程*<br /><br /> -将设置**操作**到*OracleOutboundPort.Procedure.Request*|  
|ReceiveProcResponse|-将设置**消息**到*ProcedureResponse*<br /><br /> -将设置**操作**到*OracleOutboundPort.Procedure.Response*|  
|SaveProcResponse|-将设置**消息**到*ProedureResponse*<br /><br /> -将设置**操作**到*SaveMessagePort.Procedure.Request*|  
  
 指定这些属性后，连接的消息形状和端口，您的业务流程已完成。  
  
 现在必须生成 BizTalk 解决方案，并将其部署到[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]。 有关详细信息，请参阅"生成和运行业务流程" [http://go.microsoft.com/fwlink/?LinkId=102359](http://go.microsoft.com/fwlink/?LinkId=102359)。  
  
## <a name="configuring-the-biztalk-application"></a>配置 BizTalk 应用程序  
 部署 BizTalk 项目后，业务流程之前创建下列出**业务流程**窗格中的[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理控制台。 必须使用[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理控制台配置该应用程序。 有关配置应用程序的详细信息，请参阅"如何为配置应用程序"在[http://go.microsoft.com/fwlink/?LinkID=196961](http://go.microsoft.com/fwlink/?LinkID=196961)。  
  
 配置应用程序涉及：  
  
-   选择应用程序的主机。  
  
-   映射到中的物理端口业务流程中创建的端口[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理控制台。 对于此业务流程，您必须：  
  
    -   定义一个物理 WCF 自定义或 WCF OracleEBS 单向接收端口。 此端口侦听来自 Oracle E-business Suite 的通知。 有关如何创建接收端口，请参阅[手动配置到 Oracle E-business 适配器的物理端口绑定](../../adapters-and-accelerators/adapter-oracle-ebs/manually-configure-a-physical-port-binding-to-the-oracle-e-business-adapter.md)。 请确保指定的接收端口的以下绑定属性。  
  
        > [!IMPORTANT]
        >  不需要执行此步骤中，如果指定在设计时绑定属性。 在这种情况下，你可以创建接收端口，将设置所需的绑定的属性，通过导入所创建绑定文件[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]。 有关详细信息请参阅[物理端口绑定使用端口绑定文件配置到 Oracle E-business Suite](../../adapters-and-accelerators/adapter-oracle-ebs/configure-a-physical-port-binding-using-a-port-binding-file-to-oracle-ebs.md)。  
  
        |绑定属性|值|  
        |----------------------|-----------|  
        |**InboundOperationType**|将其设置为**通知**。|  
        |**NotificationPort**|指定 ODP.NET 必须打开侦听从 Oracle 数据库的数据库更改通知的端口号。 将其设置为相同的端口号必须已添加到 Windows 防火墙例外列表。 有关如何将端口添加到 Windows 防火墙例外列表的说明，请参阅[http://go.microsoft.com/fwlink/?LinkID=196959](http://go.microsoft.com/fwlink/?LinkID=196959)。<br /><br /> **重要说明：**如果设置为默认值为-1，则你将需要完全禁用 Windows 防火墙，以接收通知消息。|  
        |**NotificationStatement**|将其设置为：<br /><br /> `SELECT TID,ACCOUNT,PROCESSED FROM SCOTT.ACCOUNTACTIVITY WHERE PROCESSED = ‘n’`<br /><br /> **注意：**必须指定表名称以及架构名称。 例如， `SCOTT.ACCOUNTACTIVITY`。|  
        |**NotifyOnListenerStart**|将其设置为**True**。|  
  
         有关不同的绑定属性的详细信息，请参阅[了解针对 Oracle E-business Suite 绑定属性的 BizTalk 适配器](../../adapters-and-accelerators/adapter-oracle-ebs/read-about-the-biztalk-adapter-for-oracle-e-business-suite-binding-properties.md)。  
  
        > [!IMPORTANT]
        >  如果你要配置为接口表的通知，您必须通过指定所需的绑定属性中设置应用程序上下文。 有关设置应用程序上下文的详细信息请参阅[设置应用程序上下文](../../adapters-and-accelerators/adapter-oracle-ebs/set-application-context.md)。  
  
        > [!NOTE]
        >  我们建议在执行使用的入站的操作时配置的事务隔离级别和事务超时[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]。 你可以通过配置 WCF 自定义时添加的服务行为来实现或 WCF OracleEBS 接收端口。 有关如何添加服务行为的说明，请参阅[配置事务隔离级别和与 Oracle E-business Suite 的事务超时](../../adapters-and-accelerators/adapter-oracle-ebs/configure-transaction-isolation-level-and-transaction-timeout-with-oracle-ebs.md)。  
  
    -   定义一个物理 WCF 自定义或 WCF OracleEBS 发送端口将消息发送到 Oracle E-business Suite 执行 PROCESS_REOCRDS 过程。 你必须在发送端口中指定的操作。  
  
    -   硬盘和其中 BizTalk 业务流程将从 Oracle E-business Suite 中删除消息的相应文件端口上定义的位置。 这些将是从 Oracle E-business Suite 收到的通知消息和执行通过 WCF 自定义或 WCF OracleEBS PROCESS_RECORDS 过程的消息发送端口。  
  
## <a name="starting-the-application"></a>启动应用程序  
 你必须启动 BizTalk 应用程序用于 Oracle E-business Suite 从接收通知消息以及用于执行 PROCESS_RECORDS 过程。 说明在启动 BizTalk 应用程序，请参阅"如何为启动 Orchestration"，网址为[http://go.microsoft.com/fwlink/?LinkId=102387](http://go.microsoft.com/fwlink/?LinkId=102387)。  
  
 在此阶段，请确保：  
  
-   WCF 自定义或 WCF OracleEBS 单向接收端口，后者从 Oracle E-business Suite 接收通知消息正在运行。  
  
-   WCF 自定义或 WCF OracleEBS 发送端口执行 PROCESS_RECORDS 过程正在运行。  
  
-   文件发送端口，从而从 Oracle E-business Suite 接收消息，正在运行。  
  
-   BizTalk 业务流程操作正在运行。  
  
## <a name="executing-the-operation"></a>执行该操作  
 假定 ACCOUNTACTIVITY 表已经有一些记录。 此外，请确保要执行 PROCESS_RECORDS 过程的 XML 消息位于 C:\TestLocation\MessageIn。 XML 文件应如下所示：  
  
```  
<PROCESS_RECORDS xmlns="http://schemas.microsoft.com/OracleEBS/2008/05/PackageApis/SCOTT/ACCOUNT_PKG" />  
```  
  
 BizTalk 业务流程启动后，以下一组操作将会发生，在相同的序列：  
  
-   适配器将接收通知消息，如下所示：  
  
    ```  
    \<?xml version="1.0" encoding="utf-8" ?>   
    <Notification xmlns="http://schemas.microsoft.com/OracleEBS/2008/05/Notification/">  
      <Info>ListenerStarted</Info>   
      <Source>OracleEBSBinding</Source>   
      <Type>Startup</Type>   
    </Notification>  
    ```  
  
     此消息将通知以接收通知消息的接收端口已启动。 请注意，值`<Info>`元素是"ListnerStarted"。  
  
-   适配器执行 PROCESS_RECORDS 过程。 来自 Oracle E-business Suite 的下一步响应适用于该过程。  
  
    ```  
    \<?xml version="1.0" encoding="utf-8" ?>   
    <PROCESS_RECORDSResponse xmlns="http://schemas.microsoft.com/OracleEBS/2008/05/PackageApis/SCOTT/ACCOUNT_PKG">  
      <TABLE_DATA>  
        \<xs:schema id="NewDataSet" xmlns:xs="http://www.w3.org/2001/XMLSchema" xmlns:msdata="urn:schemas-microsoft-com:xml-msdata">  
          \<xs:element msdata:IsDataSet="true" name="NewDataSet">  
            \<xs:complexType>  
              \<xs:sequence>  
                \<xs:element minOccurs="0" maxOccurs="unbounded" name="NewTable">  
                  \<xs:complexType>  
                    \<xs:sequence>  
                      \<xs:element minOccurs="0" name="TID" type="xs:decimal" />   
                      \<xs:element minOccurs="0" name="ACCOUNT" type="xs:decimal" />   
                      \<xs:element minOccurs="0" name="PROCESSED" type="xs:string" />   
                    \</xs:sequence>  
                  \</xs:complexType>  
                \</xs:element>  
              \</xs:sequence>  
            \</xs:complexType>  
          \</xs:element>  
        \</xs:schema>  
        \<diffgr:diffgram xmlns:diffgr="urn:schemas-microsoft-com:xml-diffgram-v1">  
        <NewDataSet xmlns="">  
          <NewTable>  
            <TID>1</TID>   
            <ACCOUNT>100001</ACCOUNT>   
            <PROCESSED>n</PROCESSED>   
          </NewTable>  
          <NewTable>  
            ......  
            ......  
          </NewTable>  
          ......  
          ......  
        </NewDataSet>  
        \</diffgr:diffgram>  
      </TABLE_DATA>  
    </PROCESS_RECORDSResponse>  
    ```  
  
     这是 SELECT 语句执行 PROCESS_RECORDS 过程中响应。  
  
-   PROCESS_RECORDS 过程还会更新要设置为 y 的处理的行。 因此，该适配器接收更新操作的另一个通知。  
  
    ```  
    \<?xml version="1.0" encoding="utf-8" ?>  
    <Notification xmlns="http://schemas.microsoft.com/OracleEBS/2008/05/Notification/">  
      <Details>  
        <NotificationDetails>  
          <ResourceName>SCOTT.ACCOUNTACTIVITY</ResourceName>   
          <Info>32</Info>   
          <QueryId>0</QueryId>   
        </NotificationDetails>  
      </Details>  
      <Info>Update</Info>   
      <ResourceNames>  
        <string xmlns="http://schemas.microsoft.com/2003/10/Serialization/Arrays">SCOTT.ACCOUNTACTIVITY</string>   
      </ResourceNames>  
      <Source>Data</Source>   
      <Type>Change</Type>   
    </Notification>  
    ```  
  
     请注意，`Info`元素包含"更新"。  
  
-   第二个通知之后, 该适配器再次执行 PROCESS_RECORDS 过程。 但是，现在其中处理列设置为任何记录，因为 ' n '，该过程返回与下面类似的一个空响应。  
  
    ```  
    \<?xml version="1.0" encoding="utf-8" ?>   
    <PROCESS_RECORDSResponse xmlns="http://schemas.microsoft.com/OracleEBS/2008/05/PackageApis/SCOTT/ACCOUNT_PKG">  
      <TABLE_DATA>  
        \<xs:schema id="NewDataSet" xmlns:xs="http://www.w3.org/2001/XMLSchema" xmlns:msdata="urn:schemas-microsoft-com:xml-msdata">  
          \<xs:element msdata:IsDataSet="true" name="NewDataSet">  
            \<xs:complexType>  
              \<xs:sequence>  
                \<xs:element minOccurs="0" maxOccurs="unbounded" name="NewTable">  
                  \<xs:complexType>  
                    \<xs:sequence>  
                      \<xs:element minOccurs="0" name="TID" type="xs:decimal" />   
                      \<xs:element minOccurs="0" name="ACCOUNT" type="xs:decimal" />   
                      \<xs:element minOccurs="0" name="PROCESSED" type="xs:string" />   
                    \</xs:sequence>  
                  \</xs:complexType>  
                \</xs:element>  
              \</xs:sequence>  
            \</xs:complexType>  
          \</xs:element>  
        \</xs:schema>  
        \<diffgr:diffgram xmlns:diffgr="urn:schemas-microsoft-com:xml-diffgram-v1">  
          <NewDataSet xmlns="" />   
        \</diffgr:diffgram>  
      </TABLE_DATA>  
    </PROCESS_RECORDSResponse>  
    ```  
  
## <a name="best-practices"></a>最佳实践  
 已部署并配置 BizTalk 项目之后，你可以将配置设置导出到 XML 文件称为绑定文件。 后生成绑定文件，你可以导入的配置设置文件，以便不需要创建发送端口和接收相同的业务流程的端口。 有关绑定文件的详细信息，请参阅[重用 Oracle E-business Suite 适配器绑定](../../adapters-and-accelerators/adapter-oracle-ebs/reuse-adapter-bindings-with-oracle-e-business-suite.md)。  
  
## <a name="see-also"></a>另请参阅  
 [接收使用 BizTalk Server 的 Oracle E-business Suite 数据库更改通知](../../adapters-and-accelerators/adapter-oracle-ebs/receive-oracle-ebs-database-change-notifications-using-biztalk-server.md)