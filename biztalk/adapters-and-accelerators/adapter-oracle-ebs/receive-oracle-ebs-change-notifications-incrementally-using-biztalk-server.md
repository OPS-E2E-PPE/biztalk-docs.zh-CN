---
title: Oracle E-business Suite 使用接收更改通知以增量方式 BizTalk Server |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 63dbeacc-ecde-497d-b12d-d5f9944a33f0
caps.latest.revision: 19
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e7e989b225f2c855e7b4659939f33341be652e82
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65374660"
---
# <a name="receive-oracle-e-business-suite-change-notifications-incrementally-using-biztalk-server"></a>Oracle E-business Suite 使用接收更改通知以增量方式 BizTalk Server
> [!IMPORTANT]
>  为了简洁起见，本主题仅介绍如何以增量方式接收通知。 在业务方案中，业务流程在理想情况下必须包括用于提取收到通知消息的类型，然后执行任何后续操作的逻辑。 换而言之，本主题中所述的业务流程必须基于业务流程中所述[进程通知消息到 Oracle E-business Suite 中完成特定任务](../../adapters-and-accelerators/adapter-oracle-ebs/process-notification-messages-to-complete-specific-tasks-in-oracle-ebs.md)。  
  
 本主题演示如何配置[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]以从 Oracle 接收增量查询通知消息。 为了演示增量通知，我们认为，ACCOUNTACTIVITY，包含列的表"处理"。 一条新记录插入到此表时，将"处理"列的值设置为 ' n '。 可以配置适配器后，通过执行以下接收增量通知：  
  
- 通过检索所有记录具有与"处理"列的 SELECT 语句注册通知 ' n '。 您可以通过指定的 SELECT 语句来实现**NotificationStatement**属性绑定。  
  
- 对于已通知有关的行，更新为 y 的"处理"列。  
  
  本主题演示如何创建 BizTalk 业务流程和配置 BizTalk 应用程序来实现此目的。  
  
## <a name="configuring-notifications-with-the-oracle-e-business-adapter-binding-properties"></a>使用 Oracle E-business 适配器的绑定属性中配置通知  
 下表总结了[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]绑定用于配置 Oracle E-business Suite 中接收通知的属性。 配置中的接收端口时，必须指定这些绑定属性[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理控制台。  
  
> [!NOTE]
>  您可以选择生成的架构时指定这些绑定属性**通知**操作，即使并不总是这样。 如果这样做，端口绑定文件的[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]生成元数据生成的一部分还包含为绑定属性指定的值。 稍后可以导入此绑定文件中的[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理控制台中创建的 WCF 自定义或 WCF OracleEBS 属性已设置对绑定接收端口。 有关创建接收端口使用绑定文件的详细信息，请参阅[配置物理端口绑定使用端口绑定文件到 Oracle E-business Suite](../../adapters-and-accelerators/adapter-oracle-ebs/configure-a-physical-port-binding-using-a-port-binding-file-to-oracle-ebs.md)。  
  
|绑定属性|Description|  
|----------------------|-----------------|  
|**InboundOperationType**|指定你想要执行的入站的操作。 若要接收通知消息，请将此设置为**通知**。|  
|**NotificationPort**|指定 ODP.NET 必须打开从 Oracle 数据库的数据库更改通知侦听的端口号。|  
|**NotificationStatement**|指定用于对查询通知注册的 SELECT 语句。 仅当指定的 SELECT 语句更改的结果集时，适配器将获取一条通知消息。|  
|**NotifyOnListenerStart**|指定适配器是否启动侦听器时在向适配器客户端发送了通知。|  
  
 有关这些属性的更完整说明，请参阅[了解关于 BizTalk Adapter for Oracle E-business Suite 绑定属性](../../adapters-and-accelerators/adapter-oracle-ebs/read-about-the-biztalk-adapter-for-oracle-e-business-suite-binding-properties.md)。 有关如何使用的完整说明[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]若要从 Oracle E-business Suite 中接收通知，请阅读更多。  
  
## <a name="how-this-topic-demonstrates-receiving-notification-messages"></a>如何本主题演示如何接收通知消息  
 本主题演示如何将[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]支持从 Oracle E-business Suite 中接收增量数据库更改通知消息，我们将配置的适配器接收到 ACCOUNTACTIVTY 表更改通知。 让我们假定 ACCOUNTACTIVITY 表具有列"TID"、"帐户"和"处理"。 每当添加一条新记录时，将"处理"列的值设置为 ' n '。 因此，若要获取增量通知必须作为 BizTalk 业务流程的一部分执行以下任务：  
  
- 获取作为"处理"的所有记录的通知 ' n '。 可以通过指定为 notification 语句的 SELECT 语句来执行此操作。  
  
- 某些记录收到通知后，将"处理"设置为 y。 可以通过执行存储的过程，PROCESS_RECORDS，更新"处理"列来执行此操作。  
  
  为了演示接收增量通知，我们执行以下操作：  
  
- 生成架构**通知**（入站操作），并**PROCESS_RECORDS** （出站操作） ACCOUNTACTIVITY 表。  
  
- 创建具有以下业务流程：  
  
  -   接收位置接收通知消息。 可以通过指定 SELECT 语句作为通知进行配置：  
  
      ```  
      SELECT TID,ACCOUNT,PROCESSED FROM SCOTT.ACCOUNTACTIVITY WHERE PROCESSED = ‘n’  
      ```  
  
      > [!NOTE]
      >  必须指定表名称以及架构名称。 例如，`SCOTT.ACCOUNTACTIVITY`。  
  
  -   要更新的行已为其发送通知的发送端口。 将此端口设置为 y 收到通知时的记录的"处理"列的值上执行 PROCESS_RECORDS 存储过程。  
  
       请注意接收通知消息，以便将更新已处理的行后，必须执行此操作。 若要使用正在等待获取通知响应，然后手动删除请求的消息执行 PROCESS_RECORDS 过程的开销即可执行操作，将生成为 PROCESS_RECORDS 过程本身在业务流程内的请求消息。 可以通过使用执行操作**构造消息**形状在业务流程中的。  
  
## <a name="how-to-receive-notification-messages-from-oracle-e-business-suite"></a>如何从 Oracle E-business Suite 中接收通知消息  
 对 Oracle E-business Suite 使用执行操作[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]与[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]涉及过程中所述的任务[若要创建 Oracle E-business Suite 应用程序的构建基块](../../adapters-and-accelerators/adapter-oracle-ebs/building-blocks-to-create-oracle-e-business-suite-applications.md)。 若要配置要接收通知消息的适配器，这些任务包括：  
  
1. 创建 BizTalk 项目，然后生成的架构**通知**（入站操作） 和**PROCESS_RECORDS** ACCOUNTACTIVITY 表上的过程 （出站操作）。 或者，您可以指定的值**InboundOperationType**， **NotificationPort**，并**NotificationStatement**绑定属性。  
  
2. 用于 Oracle E-business Suite 中接收通知的 BizTalk 项目中创建一条消息。  
  
3. 用于执行 PROCESS_RECORDS 存储过程和接收响应消息的 BizTalk 项目中创建消息。  
  
4. 创建业务流程中执行以下任务：  
  
   -   从 Oracle E-business Suite 中接收通知消息。  
  
   -   创建消息，以执行 PROCESS_RECORDS 过程。  
  
   -   将此消息发送到 Oracle E-business Suite 来选择和更新记录并接收响应。  
  
5. 生成并部署 BizTalk 项目。  
  
6. 配置的 BizTalk 应用程序通过创建物理发送端口和接收端口。  
  
   > [!NOTE]
   >  对于入站操作，如接收通知消息，则必须仅配置一个单向 WCF 自定义或 Wcf-oracleebs 接收端口。 双向接收端口不支持的入站操作。  
  
7. 启动 BizTalk 应用程序。  
  
   本主题介绍如何执行这些任务。  
  
## <a name="generating-schema"></a>生成架构  
 必须生成的架构**通知**操作并**PROCESS_RECORDS**过程。 请参阅[检索用于 Oracle E-business Suite 操作在 Visual Studio 中的元数据](../../adapters-and-accelerators/adapter-oracle-ebs/get-metadata-for-oracle-e-business-suite-operations-in-visual-studio.md)有关如何生成架构的详细信息。 生成架构时，请执行以下任务。 如果不想指定绑定属性在设计时，跳过的第一步。  
  
1.  为指定值**InboundOperationType**， **NotificationPort**，并**NotificationStatement**生成架构时绑定属性。 有关此绑定属性的详细信息，请参阅[了解关于 BizTalk Adapter for Oracle E-business Suite 绑定属性](../../adapters-and-accelerators/adapter-oracle-ebs/read-about-the-biztalk-adapter-for-oracle-e-business-suite-binding-properties.md)。 有关如何指定绑定属性的说明，请参阅[适用于 Oracle E-business Suite 中配置的绑定属性](../../adapters-and-accelerators/adapter-oracle-ebs/configure-the-binding-properties-for-oracle-e-business-suite.md)。  
  
2.  选择作为协定类型**服务 （入站操作）**。  
  
3.  生成架构**通知**操作。  
  
4.  选择作为协定类型**客户端 （出站操作）**。  
  
5.  生成架构**PROCESS_RECORDS**过程。 此过程位于下**ACCOUNT_PKG**包。  
  
## <a name="defining-messages-and-message-types"></a>定义消息和消息类型  
 先前生成的架构描述业务流程中的消息所需的"类型"。 一条消息通常是一个变量，要为其类型定义由相应的架构。 架构生成后，你必须将其链接到消息从 BizTalk 项目的业务流程视图。  
  
 对于本主题中，您必须创建三个消息，另一个用于从 Oracle E-business Suite 中接收通知，一个执行 PROCESS_RECORDS 过程，一个用于接收过程的响应。  
  
 执行以下步骤创建消息并将其链接到架构。  
  
#### <a name="to-create-messages-and-link-to-schema"></a>若要创建消息并将链接到架构  
  
1.  向 BizTalk 项目添加业务流程。 从解决方案资源管理器，右键单击 BizTalk 项目名称，指向**外**，然后单击**新项**。 键入 BizTalk 业务流程的名称，然后单击**添加**。  
  
2.  如果尚未打开，请打开 BizTalk 项目的业务流程视图窗口。 单击**视图**，依次指向**其他 Windows**，然后单击**业务流程视图**。  
  
3.  在中**业务流程视图**，右键单击**消息**，然后单击**新消息**。  
  
4.  右键单击新创建的消息，然后依次**属性窗口**。  
  
5.  在中**属性**窗格**Message_1**，执行以下操作：  
  
    |使用此选项|执行的操作|  
    |--------------|----------------|  
    |Identifier|键入 `NotifyReceive`。|  
    |消息类型|从下拉列表中，展开**架构**，然后选择*OracleNotifyIncremental.OracleEBSBinding.Notification*，其中*OracleNotifyIncremental*的名称您的 BizTalk 项目。 *OracleEBSBinding*是为生成的架构**通知**操作。|  
  
6.  重复步骤 3 以创建两条新消息。 在中**属性**窗格中的新消息，执行以下操作：  
  
    |将标识符设置为|将消息类型设置为|  
    |-----------------------|-------------------------|  
    |过程|*OracleNotifyIncremental.OracleEBSBinding1.PROCESS_RECORDS*，其中*OracleEBSBinding1*是为生成的架构**PROCESS_RECORDS**过程。|  
    |ProcedureResponse|*OracleNotifyIncremental.OracleEBSBinding1.PROCESS_RECORDSResponse*|  
  
## <a name="setting-up-the-orchestration"></a>设置业务流程  
 必须创建 BizTalk 业务流程使用[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]用于 Oracle E-business Suite 中接收通知消息，然后更新的行已收到通知。 在此业务流程，适配器将接收通知消息根据 SELECT 语句为指定**NotificationStatement**属性绑定。 在文件位置接收通知消息。 一旦收到响应，该业务流程将构造一条消息来调用 PROCESS_RECORDS 过程中，将更新为其接收通知的行。 在相同的文件位置还收到此消息的响应。  
  
 因此，您的业务流程必须包含以下信息：  
  
- 单向 WCF 自定义或 WCF OracleEBS 接收端口以接收通知消息。  
  
- 双向 WCF 自定义或 WCF OracleEBS 发送端口以发送消息，以执行 PROCESS_RECORDS 过程。  
  
- 一个**构造消息**形状以构造消息，来执行 PROCESS_RECORDS 过程，在业务流程内的。  
  
- 文件发送端口用于保存通知消息和 PROCESS_RECORDS 过程的响应。  
  
- 接收和发送形状。  
  
  示例业务流程如下所示。  
  
  ![从 Oracle 接收通知的业务流程](../../adapters-and-accelerators/adapter-oracle-database/media/cef49414-490a-4bd5-a32d-b3f4cde5950a.gif "cef49414-490a-4bd5-a32d-b3f4cde5950a")  
  
### <a name="adding-message-shapes"></a>添加消息形状  
 请确保为每个消息形状中指定以下属性。 形状列中列出的名称是在刚提到的业务流程中显示的消息形状的名称。  
  
|形状|形状类型|属性|  
|-----------|----------------|----------------|  
|ReceiveNotification|Receive|-设置**名称**到*ReceiveNotification*<br /><br /> -设置**激活**到 *，则返回 True*|  
|SaveNotification|Send|-设置**名称**到*SaveNotification*|  
|SendProcMessage|Send|-设置**名称**到*SendProcMessage*|  
|ReceiveProcResponse|Receive|-设置**名称**到*ReceiveProcResponse*|  
|SaveProcResponse|Send|-设置**名称**到*SaveProcResponse*|  
  
### <a name="adding-construct-message-shape"></a>添加构造消息形状  
 可以使用**构造消息**形状中，以生成请求消息在业务流程内的执行 PROCESS_RECORDS 过程。 若要执行此操作，必须添加**构造消息**形状，并在其中**消息赋值**向业务流程的形状。 对于本例，请**消息赋值**形状调用生成一条消息，发送到 Oracle E-business Suite 执行该过程的代码。 **消息赋值**形状还设置用于消息发送到 Oracle E-business Suite 的操作。  
  
 对于构造消息形状，请设置**构造的消息**属性设置为**过程**。  
  
 若要生成响应的代码可能与您的 BizTalk 项目相同的 Visual Studio 解决方案的一部分。 用于生成响应消息的示例代码如下所示。  
  
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
  
 对于上述代码摘录中以便能够生成请求消息，您必须 （针对 PROCESS_RECORDS 过程中） 的 XML 请求消息中为指定的位置`XmlFileLocation`变量。  
  
> [!NOTE]
>  生成项目后，将在项目目录中创建 MessageCreator.dll。 必须将此 DLL 添加到全局程序集缓存 (GAC) 中。 此外，必须将 MessageCreator.dll 添加为 BizTalk 项目中的引用。  
  
 添加以下表达式来调用此代码从**消息赋值**形状，以及设置用于消息的操作。 若要添加一个表达式，请双击**消息赋值**形状以打开表达式编辑器。  
  
```  
Procedure = MessageCreator.MessageCreator.XMLMessageCreator();  
Procedure(WCF.Action) = "PackageApis/SCOTT/ACCOUNT_PKG/PROCESS_RECORDS";  
```  
  
### <a name="adding-ports"></a>添加端口  
 请确保为每个逻辑端口中指定以下属性。 端口列中列出的名称是在业务流程中显示的端口的名称。  
  
|Port|属性|  
|----------|----------------|  
|OracleNotifyPort|-设置**标识符**到*OracleNotifyPort*<br /><br /> -设置**类型**到*OracleNotifyPortType*<br /><br /> -设置**通信模式**到*单向*<br /><br /> -设置**通信方向**到*接收*|  
|SaveMessagePort|-设置**标识符**到*SaveMessagePort*<br /><br /> -设置**类型**到*SaveMessagePortType*<br /><br /> -设置**通信模式**到*单向*<br /><br /> -设置**通信方向**到*发送*<br /><br /> -创建一个操作*通知*。 此操作用于通知消息。<br /><br /> -创建一个操作*过程*。 此操作用于选择响应消息。|  
|OracleOutboundPort|-设置**标识符**到*OracleOutboundPort*<br /><br /> -设置**类型**到*OracleOutboundPortType*<br /><br /> -设置**通信模式**到*请求-响应*<br /><br /> -设置**通信方向**到*发送接收*|  
  
### <a name="specify-messages-for-action-shapes-and-connect-to-ports"></a>为操作形状指定消息并将连接到端口  
 下表指定属性应设置为指定操作形状的消息并链接到的端口的消息及其值。 形状列中列出的名称是消息形状的名称，前面所述的业务流程中所示。  
  
|形状|属性|  
|-----------|----------------|  
|ReceiveNotification|-设置**消息**到*NotifyReceive*<br /><br /> -设置**操作**到*OracleNotifyPort.Notify.Request*|  
|SaveNotification|-设置**消息**到*NotifyReceive*<br /><br /> -设置**操作**到*SaveMessagePort.Notify.Request*|  
|SendProcMessage|-设置**消息**到*过程*<br /><br /> -设置**操作**到*OracleOutboundPort.Procedure.Request*|  
|ReceiveProcResponse|-设置**消息**到*ProcedureResponse*<br /><br /> -设置**操作**到*OracleOutboundPort.Procedure.Response*|  
|SaveProcResponse|-设置**消息**到*ProedureResponse*<br /><br /> -设置**操作**到*SaveMessagePort.Procedure.Request*|  
  
 指定这些属性后，消息形状和端口进行连接，您的业务流程已完成。  
  
 现在必须生成 BizTalk 解决方案，并将其部署到[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]。 详细信息，请参阅"构建和运行业务流程"网址[ http://go.microsoft.com/fwlink/?LinkId=102359 ](http://go.microsoft.com/fwlink/?LinkId=102359)。  
  
## <a name="configuring-the-biztalk-application"></a>配置 BizTalk 应用程序  
 部署 BizTalk 项目后，将前面创建的业务流程下列出**业务流程**窗格中的[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理控制台。 必须使用[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理控制台来配置应用程序。 有关配置应用程序的详细信息，请参阅"如何配置应用程序的"网址[ http://go.microsoft.com/fwlink/?LinkID=196961 ](http://go.microsoft.com/fwlink/?LinkID=196961)。  
  
 配置应用程序包括：  
  
- 选择应用程序的主机。  
  
- 映射到物理端口在业务流程中创建的端口[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理控制台。 对于此业务流程，您必须：  
  
  - 定义一个物理 WCF 自定义或 WCF OracleEBS 单向接收端口。 此端口侦听来自 Oracle E-business Suite 的通知。 有关如何创建接收端口，请参阅[手动配置物理端口绑定到 Oracle E-business 适配器](../../adapters-and-accelerators/adapter-oracle-ebs/manually-configure-a-physical-port-binding-to-the-oracle-e-business-adapter.md)。 请确保指定的接收端口的以下绑定属性。  
  
    > [!IMPORTANT]
    >  不需要执行此步骤中，如果指定在设计时的绑定属性。 在这种情况下，您可以创建接收端口，使用所需的绑定属性集，通过导入绑定文件创建的[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]。 有关详细信息请参阅[物理端口绑定使用端口绑定文件配置到 Oracle E-business Suite](../../adapters-and-accelerators/adapter-oracle-ebs/configure-a-physical-port-binding-using-a-port-binding-file-to-oracle-ebs.md)。  
  
    |绑定属性|ReplTest1|  
    |----------------------|-----------|  
    |**InboundOperationType**|将此设置为**通知**。|  
    |**NotificationPort**|指定 ODP.NET 必须打开从 Oracle 数据库的数据库更改通知侦听的端口号。 将此设置为相同的端口号必须已添加到 Windows 防火墙例外列表。 有关如何将端口添加到 Windows 防火墙例外列表的说明，请参阅[ http://go.microsoft.com/fwlink/?LinkID=196959 ](http://go.microsoft.com/fwlink/?LinkID=196959)。<br /><br /> **重要提示：** 如果将其设置为默认值-1，必须将完全禁用 Windows 防火墙，以接收通知消息。|  
    |**NotificationStatement**|将此设置为：<br /><br /> `SELECT TID,ACCOUNT,PROCESSED FROM SCOTT.ACCOUNTACTIVITY WHERE PROCESSED = ‘n’`<br /><br /> **注意：** 必须指定表名称以及架构名称。 例如，`SCOTT.ACCOUNTACTIVITY`。|  
    |**NotifyOnListenerStart**|将此设置为 **，则返回 True**。|  
  
     有关不同的绑定属性的详细信息，请参阅[了解关于 BizTalk Adapter for Oracle E-business Suite 绑定属性](../../adapters-and-accelerators/adapter-oracle-ebs/read-about-the-biztalk-adapter-for-oracle-e-business-suite-binding-properties.md)。  
  
    > [!IMPORTANT]
    >  如果要配置通知的接口表，则必须通过指定必要的绑定属性来设置应用程序上下文。 有关设置应用程序上下文的详细信息请参阅[设置应用程序上下文](../../adapters-and-accelerators/adapter-oracle-ebs/set-application-context.md)。  
    > 
    > [!NOTE]
    >  我们建议执行使用的入站的操作时配置的事务隔离级别和事务超时[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]。 您为此，可添加服务行为配置 WCF 自定义时或 WCF OracleEBS 接收端口。 有关如何添加服务行为的说明，请参阅[配置事务隔离级别和事务超时与 Oracle E-business Suite](../../adapters-and-accelerators/adapter-oracle-ebs/configure-transaction-isolation-level-and-transaction-timeout-with-oracle-ebs.md)。  
  
  - 定义一个物理 WCF 自定义或 WCF OracleEBS 发送端口将消息发送到 Oracle E-business Suite 执行 PROCESS_REOCRDS 过程。 您必须在发送端口中指定的操作。  
  
  - 硬盘和相应的 BizTalk 业务流程将从 Oracle E-business Suite 中删除消息的文件端口上定义的位置。 这些将是从 Oracle E-business Suite 收到的通知消息和发送端口通过 WCF 自定义或 WCF OracleEBS 执行 PROCESS_RECORDS 过程的消息。  
  
## <a name="starting-the-application"></a>启动应用程序  
 必须启动 BizTalk 应用程序用于接收来自 Oracle E-business Suite 的通知消息和执行 PROCESS_RECORDS 过程。 有关说明在启动 BizTalk 应用程序，请参阅"如何向启动业务流程"，网址[ http://go.microsoft.com/fwlink/?LinkId=102387 ](http://go.microsoft.com/fwlink/?LinkId=102387)。  
  
 在此阶段，请确保：  
  
-   WCF 自定义或 WCF OracleEBS 单向接收端口，它可以接收通知消息来自 Oracle E-business Suite 正在运行。  
  
-   WCF 自定义或 WCF OracleEBS 发送端口执行 PROCESS_RECORDS 过程正在运行。  
  
-   FILE 发送端口，从 Oracle E-business Suite 中接收消息，正在运行。  
  
-   该操作的 BizTalk 业务流程正在运行。  
  
## <a name="executing-the-operation"></a>执行该操作  
 假定 ACCOUNTACTIVITY 表已经有一些记录。 此外，请确保要执行 PROCESS_RECORDS 过程的 XML 消息位于 C:\TestLocation\MessageIn。 XML 文件应如下所示：  
  
```  
<PROCESS_RECORDS xmlns="http://schemas.microsoft.com/OracleEBS/2008/05/PackageApis/SCOTT/ACCOUNT_PKG" />  
```  
  
 BizTalk 业务流程启动后，以下组操作发生，相同的顺序：  
  
-   适配器接收一条通知消息，如下所示：  
  
    ```  
    <?xml version="1.0" encoding="utf-8" ?>   
    <Notification xmlns="http://schemas.microsoft.com/OracleEBS/2008/05/Notification/">  
      <Info>ListenerStarted</Info>   
      <Source>OracleEBSBinding</Source>   
      <Type>Startup</Type>   
    </Notification>  
    ```  
  
     此消息会通知已启动用于接收通知消息的接收端口。 请注意，对于值`<Info>`元素是"ListnerStarted"。  
  
-   适配器执行 PROCESS_RECORDS 过程。 Oracle E-business Suite 的下一步响应是过程。  
  
    ```  
    <?xml version="1.0" encoding="utf-8" ?>   
    <PROCESS_RECORDSResponse xmlns="http://schemas.microsoft.com/OracleEBS/2008/05/PackageApis/SCOTT/ACCOUNT_PKG">  
      <TABLE_DATA>  
        <xs:schema id="NewDataSet" xmlns:xs="http://www.w3.org/2001/XMLSchema" xmlns:msdata="urn:schemas-microsoft-com:xml-msdata">  
          <xs:element msdata:IsDataSet="true" name="NewDataSet">  
            <xs:complexType>  
              <xs:sequence>  
                <xs:element minOccurs="0" maxOccurs="unbounded" name="NewTable">  
                  <xs:complexType>  
                    <xs:sequence>  
                      <xs:element minOccurs="0" name="TID" type="xs:decimal" />   
                      <xs:element minOccurs="0" name="ACCOUNT" type="xs:decimal" />   
                      <xs:element minOccurs="0" name="PROCESSED" type="xs:string" />   
                    </xs:sequence>  
                  </xs:complexType>  
                </xs:element>  
              </xs:sequence>  
            </xs:complexType>  
          </xs:element>  
        </xs:schema>  
        <diffgr:diffgram xmlns:diffgr="urn:schemas-microsoft-com:xml-diffgram-v1">  
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
        </diffgr:diffgram>  
      </TABLE_DATA>  
    </PROCESS_RECORDSResponse>  
    ```  
  
     这是 SELECT 语句作为 PROCESS_RECORDS 过程的一部分执行响应。  
  
-   PROCESS_RECORDS 过程还会更新行处理设置为 y。 因此，适配器将接收的更新操作的另一条通知。  
  
    ```  
    <?xml version="1.0" encoding="utf-8" ?>  
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
  
-   第二个通知之后, 该适配器再次执行 PROCESS_RECORDS 过程。 但是，现在其中处理列设置为任何记录，因为 ' n '，该过程将返回空响应与下面类似的。  
  
    ```  
    <?xml version="1.0" encoding="utf-8" ?>   
    <PROCESS_RECORDSResponse xmlns="http://schemas.microsoft.com/OracleEBS/2008/05/PackageApis/SCOTT/ACCOUNT_PKG">  
      <TABLE_DATA>  
        <xs:schema id="NewDataSet" xmlns:xs="http://www.w3.org/2001/XMLSchema" xmlns:msdata="urn:schemas-microsoft-com:xml-msdata">  
          <xs:element msdata:IsDataSet="true" name="NewDataSet">  
            <xs:complexType>  
              <xs:sequence>  
                <xs:element minOccurs="0" maxOccurs="unbounded" name="NewTable">  
                  <xs:complexType>  
                    <xs:sequence>  
                      <xs:element minOccurs="0" name="TID" type="xs:decimal" />   
                      <xs:element minOccurs="0" name="ACCOUNT" type="xs:decimal" />   
                      <xs:element minOccurs="0" name="PROCESSED" type="xs:string" />   
                    </xs:sequence>  
                  </xs:complexType>  
                </xs:element>  
              </xs:sequence>  
            </xs:complexType>  
          </xs:element>  
        </xs:schema>  
        <diffgr:diffgram xmlns:diffgr="urn:schemas-microsoft-com:xml-diffgram-v1">  
          <NewDataSet xmlns="" />   
        </diffgr:diffgram>  
      </TABLE_DATA>  
    </PROCESS_RECORDSResponse>  
    ```  
  
## <a name="best-practices"></a>最佳实践  
 部署和配置 BizTalk 项目后，你可以配置设置导出到名为绑定文件的 XML 文件。 后生成的绑定文件，可以以便不需要创建发送端口和接收端口的同一业务流程，从文件导的配置设置。 有关绑定文件的详细信息，请参阅[Oracle E-business Suite 的重用适配器绑定](../../adapters-and-accelerators/adapter-oracle-ebs/reuse-adapter-bindings-with-oracle-e-business-suite.md)。  
  
## <a name="see-also"></a>请参阅  
 [Oracle E-business Suite 数据库使用接收更改通知 BizTalk Server](../../adapters-and-accelerators/adapter-oracle-ebs/receive-oracle-ebs-database-change-notifications-using-biztalk-server.md)