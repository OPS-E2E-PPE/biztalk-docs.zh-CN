---
title: 使用在 Oracle E-business Suite 中具有较大的数据类型的表 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 501aa302-0f82-4221-b99f-423bc8621a6a
caps.latest.revision: 15
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: d65bd37e6ad9c8b8b196df6092a0573d2774a756
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/28/2017
ms.locfileid: "25968107"
---
# <a name="working-with-tables-that-have-large-data-types-in-oracle-e-business-suite"></a>使用在 Oracle E-business Suite 中具有较大的数据类型的表
[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]使适配器客户端可以执行对接口表和视图的较大的数据类型，如 BLOB、 CLOB、 NCLOB、 和 BFILE 操作。  
  
-   列类型的 BLOB、 CLOB、 和 NCLOB 适配器允许客户端读取，以及更新数据。 适配器公开 Read_\<LOBColName\>和 Update_\<LOBColName\>操作来读取和更新数据分别，其中\<LOBColName\>是较大的列名称数据类型。 如果没有具有单个接口表中的较大的数据类型的多个列，适配器将公开为许多读取和更新接口该表的操作。  
  
-   对于类型 BFILE 列，适配器客户端只能读取的数据。 适配器公开 Read_\<LOBColName\>操作从 BFILE 类型的列读取数据。 如果没有具有单个接口表中的较大的数据类型的多个列，该适配器将公开许多读取接口表的操作。  
  
 有关这些操作的详细信息，请参阅[接口表、 界面视图、 表和包含 LOB 数据的视图上的操作](../../adapters-and-accelerators/adapter-oracle-ebs/read-and-update-on-interface-tables-and-views-with-large-object-data-types.md)。 有关执行这些操作的消息架构的信息，请参阅[特殊 LOB 操作的消息架构](../../adapters-and-accelerators/adapter-oracle-ebs/message-schemas-for-special-lob-operations1.md)。  
  
## <a name="how-to-perform-operations-on-columns-with-large-data-types"></a>如何在具有较大的数据类型的列上执行操作  
 通过执行上 Oracle E-business Suite 操作[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]与[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]涉及过程中所述的任务[创建 Oracle E-business Suite 应用程序的构建基块](../../adapters-and-accelerators/adapter-oracle-ebs/building-blocks-to-create-oracle-e-business-suite-applications.md)。 若要在包含较大的数据类型的 Oracle E-business Suite 执行接口表和接口视图上的操作，这些任务包括：  
  
1.  创建 BizTalk 项目，并生成操作的架构 (Read_\<LOBColName\>或 Update_\<LOBColName\>) 你想要在表或视图上调用。  
  
2.  在发送和接收消息从 Oracle E-business Suite 的 BizTalk 项目中创建消息。  
  
3.  创建业务流程以调用在接口表或视图上的操作。  
  
4.  生成和部署 BizTalk 项目。  
  
5.  配置的 BizTalk 应用程序创建的物理发送和接收端口。  
  
6.  启动 BizTalk 应用程序。  
  
 本主题提供执行这些任务的说明。  
  
## <a name="how-this-topic-demonstrates-reading-and-writing-data-into-columns-of-large-data-types"></a>本主题读取和写入到较大的数据类型的列的数据的演示  
 为了演示读取和写入到较大的数据类型的列的数据，本主题提供创建将执行以下业务流程的说明：  
  
-   更新在 CUSTOMER 表的照片列 （的 BLOB 数据类型）。  
  
-   读取的值对于此照片列的更新的记录。  
  
 此业务流程旨在仅提供请求消息，以在运行时执行更新操作的方式。 将在操作内构造读取操作的消息。  
  
> [!NOTE]
>  本主题中的业务流程读取并更新数据来自 CUSTOMER 表，这是一个基本的数据库表创建通过运行这些示例提供的脚本。 本主题，以执行读取或更新任何接口表或接口视图上的操作中所述，你必须执行类似的过程。  
  
## <a name="generating-schema"></a>生成架构  
 本主题演示如何执行基本的读取和更新在 CUSTOMER 表中的照片列 （的 BLOB 数据类型） 上的操作。 此表是通过运行这些示例提供的脚本创建的。  
  
 为了演示如何读取和写入到的较大的数据类型列的数据，架构为生成**Update_PHOTO**和**Read_PHOTO** CUSTOMER 表的操作。 您必须创建 BizTalk 项目，并使用[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]生成架构。 请参阅[检索用于 Oracle E-business Suite 操作 Visual Studio 中的元数据](../../adapters-and-accelerators/adapter-oracle-ebs/get-metadata-for-oracle-e-business-suite-operations-in-visual-studio.md)有关如何生成架构的详细信息。  
  
## <a name="defining-messages-and-message-types"></a>定义消息和消息类型  
 你之前生成的架构描述了业务流程中的消息所需的“类型”。 一条消息通常是一个变量，为其类型由相应的架构定义。 你现在必须创建消息业务流程，并将它们链接到你在上一步中生成的架构。  
  
 在此业务流程中，你必须创建四条消息 — 为一个接收响应设置**Update_PHOTO**为设置操作和其他接收的响应**Read_PHOTO**操作。  
  
#### <a name="to-create-messages-and-link-to-schema"></a>创建消息并将链接到架构  
  
1.  BizTalk 项目中添加业务流程。 从解决方案资源管理器，右键单击 BizTalk 项目名称，指向**添加**，然后单击**新项**。 键入 BizTalk 业务流程的名称，然后单击**添加**。  
  
2.  如果尚未打开，请打开 BizTalk 项目的业务流程视图窗口。 若要执行此操作，请单击**视图**，指向**其他窗口**，然后单击**业务流程视图**。  
  
3.  在业务流程视图中，右键单击**消息**，然后单击**新消息**。  
  
4.  右键单击新创建的消息中，，然后选择**属性窗口**。  
  
5.  在**属性**窗格**Message_1**，执行以下操作：  
  
    |使用此选项|执行的操作|  
    |--------------|----------------|  
    |Identifier|类型`UpdateMessage`|  
    |消息类型|从下拉列表中，展开**架构**，然后选择*LOBOperations.OracleEBSBinding.Update_PHOTO*，其中 LOBOperations 是 BizTalk 项目的名称。 OracleEBSBindingSchema 是为调用生成的架构**Update_PHOTO**客户表上的操作。|  
  
6.  重复步骤 3 以创建三个新消息。 在**属性**窗格中，为新的消息中，执行以下操作：  
  
    |设置为标识符|将消息类型设置为|  
    |-----------------------|-------------------------|  
    |UpdateResponse|*LOBOperations.OracleEBSBinding.Update_PHOTOResponse*|  
    |ReadMessage|*LOBOperations.OracleEBSBinding1.Read_PHOTO*|  
    |ReadResponse|*LOBOperations.OracleEBSBinding1.Read_PHOTOResponse*|  
  
## <a name="setting-up-the-orchestration"></a>设置业务流程  
 在此业务流程，适配器接收请求消息执行对 CUSTOMER 表的 Update_PHOTO 操作。 在文件位置接收通知消息。 适配器使用此消息，并将其传递到 Oracle 数据库。 从 Oracle 数据库的响应保存在另一个位置中。 一旦收到响应，业务流程将构造一条消息，以调用 Read_PHOTO 操作，它读取 Update_PHOTO 操作更新照片列的值。 在相同的文件位置还收到此消息的响应。  
  
 因此，您的业务流程必须包含以下信息：  
  
-   文件接收端口若要删除的请求消息**Update_PHOTO**操作。  
  
-   双向的 WCF 自定义或 WCF OracleEBS 发送端口来发送消息，以执行**Update_PHOTO**操作。  
  
-   双向的 WCF 自定义或 WCF OracleEBS 发送端口来发送消息，以执行**Read_PHOTO**操作。 你还可以同时执行**Read_PHOTO**和**Update_PHOTO**使用相同的 WCF 自定义或 WCF OracleEBS 发送端口。 在本主题中，会将一个发送端口，用于这两种操作。  
  
-   A**构造消息**形状构造业务流程中的消息。  
  
-   文件发送端口保存为响应消息**Update_PHOTO**和**Read_PHOTO**操作。  
  
-   接收和发送形状。  
  
 示例业务流程如下所示。  
  
 ![要对较大的数据类型列进行操作的业务流程](../../adapters-and-accelerators/adapter-oracle-ebs/media/1976ab27-94c3-4039-a1ca-8790e8897ad5.gif "1976ab27-94c3-4039-a1ca-8790e8897ad5")  
  
### <a name="adding-message-shapes"></a>添加消息形状  
 请确保为每个消息形状指定以下属性。 刚提到业务流程中所示，形状列中列出的名称将是消息形状的名称。  
  
|形状|形状类型|属性|  
|-----------|----------------|----------------|  
|ReceiveUpdateMessage|Receive|-将设置**名称**到*ReceiveUpdateMessage*<br />-将设置**激活**到*True*|  
|SendUpdateMessage|Send|-将设置**名称**到*SendUpdateMessage*|  
|ReceiveUpdateResponse|Receive|-将设置**名称**到*ReceiveUpdateResponse*|  
|SendUpdateResponse|Receive|-将设置**名称**到*SendUpdateResponse*|  
|SendReadMessage|Send|-将设置**名称**到*SendReadMessage*|  
|ReceiveReadResponse|Receive|-将设置**名称**到*ReceiveReadResponse*|  
|SaveReadResponse|Send|-将设置**名称**到*SaveReadResponse*|  
  
### <a name="adding-construct-message-shape"></a>添加构造消息形状  
 你可以使用**构造消息**要生成请求消息中业务流程执行形状**Read_PHOTO**操作。 若要执行此操作，你必须添加**构造消息**形状和在其中**消息分配**形状上与您的业务流程。 对于此示例，**消息分配**形状时，生成一条消息，发送到 Oracle E-business Suite 要执行的代码将调用**Read_PHOTO**操作。 **消息分配**形状还设置用于消息发送到 Oracle E-business Suite 的操作。  
  
 构造消息形状，请设置**构造消息**属性**ReadMessage**。  
  
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
  
 对于上述代码摘录中能够生成请求消息，你必须具有一个 XML 请求消息 (有关**Read_PHOTO**操作) 中为指定的位置`XmlFileLocation`变量。  
  
> [!NOTE]
>  生成项目后，将在项目目录中创建 MessageCreator.dll。 必须将此 DLL 添加到全局程序集缓存 (GAC) 中。 此外，你必须添加 MessageCreator.dll 作为 BizTalk 项目中的引用。  
  
 添加以下表达式来调用此代码从**消息分配**形状以及设置用于消息的操作。 若要添加一个表达式，请双击**消息分配**形状以打开表达式编辑器中。  
  
```  
ReadMessage = MessageCreator.MessageCreator.XMLMessageCreator();  
ReadMessage(WCF.Action) = "Tables/ReadLOB/SCOTT/CUSTOMER/PHOTO ";  
```  
  
### <a name="adding-ports"></a>添加端口  
 请确保为每个逻辑端口指定以下属性。 端口列中列出的名称是在业务流程中显示的端口的名称。  
  
|端口|属性|  
|----------|----------------|  
|MessageIn|-将设置**标识符**到*MessageIn*<br />-将设置**类型**到*MessageInType*<br />-将设置**通信模式**到*单向*<br />-将设置**通信方向**到*接收*|  
|LOBPort|-将设置**标识符**到*LOBPort*<br />-将设置**类型**到*LOBPortType*<br />-将设置**通信模式**到*请求-响应*<br />-将设置**通信方向**到*发送接收*<br />-创建一个操作*Read_LOB*。 此操作的消息用于从较大的数据类型列中读取值。<br />-创建一个操作*Update_LOB*。 此操作的消息用于更新较大的数据类型列中的值。|  
|ResponseOut|-将设置**标识符**到*ResponseOut*<br />-将设置**类型**到*ResponseOutType*<br />-将设置**通信模式**到*单向*<br />-将设置**通信方向**到*发送*<br />-创建一个操作*Read_LOB*。 此操作的消息用于从较大的数据类型列中读取值。<br />-创建一个操作*Update_LOB*。 此操作的消息用于更新较大的数据类型列中的值。|  
  
### <a name="specify-messages-for-action-shapes-and-connect-to-ports"></a>指定消息的操作形状并将连接到端口  
 下表指定的属性和用于指定操作形状的消息，并链接到的端口的消息应设置其值。 前面提到的业务流程中所示，形状列中列出的名称将是消息形状的名称。  
  
|形状|属性|  
|-----------|----------------|  
|ReceiveUpdateMessage|-将设置**消息**到*UpdateMessage*<br />-将设置**操作**到*MessageIn.Update_LOB。请求*|  
|SendUpdateMessage|-将设置**消息**到*UpdateMessage*<br />-将设置**操作**到*LOBPort.Update_LOB。请求*|  
|ReceiveUpdateResponse|-将设置**消息**到*UpdateResponse*<br />-将设置**操作**到*LOBPort.Update_LOB。响应*|  
|SendUpdateResponse|-将设置**消息**到*UpdateResponse*<br />-将设置**操作**到*ResponseOut.Update_LOB。请求*|  
|SendReadMessage|-将设置**消息**到*ReadMessage*<br />-将设置**操作**到*LOBPort.Read_LOB。请求*|  
|ReceiveReadResponse|-将设置**消息**到*ReadResponse*<br />-将设置**操作**到*LOBPort.Read_LOB。响应*|  
|SendReadResponse|-将设置**消息**到*ReadResponse*<br />-将设置**操作**到*ResponseOut.Read_LOB。请求*|  
  
 指定这些属性后，连接的消息形状和端口，您的业务流程已完成。  
  
 现在必须生成 BizTalk 解决方案，并将其部署到[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]。 有关详细信息，请参阅[生成和运行业务流程](../../core/building-and-running-orchestrations.md)。  
  
## <a name="configuring-the-biztalk-application"></a>配置 BizTalk 应用程序  
 部署 BizTalk 项目后，将先前创建的业务流程下列出的业务流程窗格中[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理控制台。 必须使用[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理控制台配置该应用程序。 有关演练，请参阅[演练： 将基本的 BizTalk 应用程序部署](Walkthrough:%20Deploying%20a%20Basic%20BizTalk%20Application.md)。
  
 配置应用程序涉及：  
  
-   选择应用程序的主机。  
  
-   映射到中的物理端口业务流程中创建的端口[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理控制台。 对于此业务流程，您必须：  
  
    -   硬盘和放置请求消息的位置的相应文件端口上定义的位置。 BizTalk 业务流程将使用请求消息并将其发送到 Oracle 数据库。  
  
    -   硬盘和 BizTalk 业务流程放置包含从 Oracle 数据库响应的响应消息的位置的相应文件端口上定义的位置。  
  
    -   定义一个物理 WCF 自定义或 WCF OracleEBS 发送端口将消息发送到 Oracle 数据库。 你必须在发送端口中指定的操作。 有关如何创建端口的信息，请参阅[手动配置到 Oracle E-business 适配器的物理端口绑定](../../adapters-and-accelerators/adapter-oracle-ebs/manually-configure-a-physical-port-binding-to-the-oracle-e-business-adapter.md)。 你必须考虑以下配置 WCF 自定义时或 WCF OracleEBS 发送端口。  
  
        -   `Update_<LOBColName>`必须作为事务的一部分执行操作。 若要确保此操作，请**UseAmbientTransaction**绑定属性必须设置为**True**。  
  
        -   由于 WCF 自定义或 WCF OracleEBS 发送端口将发送和接收符合到多个架构的消息并执行两个操作，必须设置为这两种操作的动态操作。 有关操作的详细信息，请参阅[为 Oracle E-business Suite 配置 SOAP 操作](../../adapters-and-accelerators/adapter-oracle-ebs/configure-the-soap-action-for-oracle-e-business-suite.md)。 适用于此业务流程，应将操作设置，如下所示：  
  
            ```  
            <BtsActionMapping xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xmlns:xsd="http://www.w3.org/2001/XMLSchema">  
              <Operation Name="Update_LOB" Action="Tables/UpdateBlob/SCOTT/CUSTOMER/PHOTO" />  
              <Operation Name="Read_LOB" Action="Tables/ReadLOB/SCOTT/CUSTOMER/PHOTO" />  
            </BtsActionMapping>  
            ```  
  
            > [!IMPORTANT]
            >  请注意，中的动态操作的操作名称必须与创建 BizTalk 业务流程时指定的逻辑端口的操作名称相同。  
  
        > [!NOTE]
        >  若要对接口表或接口视图执行操作还必须设置应用程序上下文。 有关如何的适配器支持设置应用程序上下文的详细信息，请参阅[设置应用程序上下文](../../adapters-and-accelerators/adapter-oracle-ebs/set-application-context.md)。 你可以通过指定的绑定属性或设置消息上下文属性公开的设置应用程序上下文[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]。 有关如何设置绑定属性的说明，请参阅[配置的 Oracle E-business Suite 绑定属性](../../adapters-and-accelerators/adapter-oracle-ebs/configure-the-binding-properties-for-oracle-e-business-suite.md)。 有关如何设置应用程序上下文使用消息上下文属性的说明，请参阅[在 Oracle E-business Suite 中配置应用程序上下文使用消息上下文属性](../../adapters-and-accelerators/adapter-oracle-ebs/configure-application-context-using-message-context-properties-in-oracle-ebs.md)。  
  
        > [!NOTE]
        >  生成架构使用[!INCLUDE[consumeadapterservlong](../../includes/consumeadapterservlong-md.md)]还会创建包含有关端口以及要为这些端口设置的操作信息绑定文件。 你可以导入此绑定文件与[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理控制台来创建发送端口 （对于出站调用），或接收 （对于入站调用） 的端口。 有关详细信息，请参阅[物理端口绑定使用端口绑定文件配置到 Oracle E-business Suite](../../adapters-and-accelerators/adapter-oracle-ebs/configure-a-physical-port-binding-using-a-port-binding-file-to-oracle-ebs.md)。  
  
## <a name="starting-the-application"></a>启动应用程序  
 在开始之前 BizTalk 业务流程，请确保请求 XML 以调用**Read_PHOTO**操作都在 C:\TestLocation\MessageIn 可用。 请求 XML 必须如下所示：  
  
```  
<Read_PHOTO xmlns="http://schemas.microsoft.com/OracleEBS/2008/05/Tables/SCOTT/CUSTOMER">  
  <FILTER>WHERE NAME='Mindy Martin'</FILTER>  
</Read_PHOTO>  
```  
  
> [!NOTE]
>  请求消息具有特定名称的筛选器因为在请求消息的**Update_PHOTO**具有相同名称的更新操作，照片列的值。 因此，读取的操作将读取使用更新操作插入的相同值。  
  
 你现在必须启动 BizTalk 应用程序用于读取和写入的较大的数据类型的值从 Oracle 数据库。 有关启动 BizTalk 应用程序的说明，请参阅[如何启动 Orchestration](../../core/how-to-start-an-orchestration.md)。  
  
 在此阶段，请确保：  
  
-   FILE 接收端口，以便运行业务流程的是接收请求消息。  
  
-   要从业务流程接收响应消息的文件发送端口正在运行。  
  
-   WCF 自定义或 WCF OracleEBS 发送端口将消息发送到 Oracle 数据库正在运行。  
  
-   BizTalk 业务流程操作正在运行。  
  
## <a name="executing-the-operation"></a>执行该操作  
 启动应用程序必须删除后该文件的请求消息接收位置。 请求消息的架构必须符合的架构**Update_PHOTO**先前生成的操作。 例如，更新 CUSTOMER 表的照片列的请求消息如下所示：  
  
```  
<Update_PHOTO xmlns="http://schemas.microsoft.com/OracleEBS/2008/05/Tables/SCOTT/CUSTOMER">  
  <FILTER>WHERE Name='Mindy Martin'</FILTER>  
  <DATA>U2FtcGxlIERhdGE=</DATA>  
</Update_PHOTO>  
```  
  
> [!NOTE]
>  更新 BLOB 列，时的数据元素必须始终包含一个 base64 编码值。 对于 CLOB NCLOB，可将此数据元素字符串值。  
  
 前面的请求消息更新记录匹配 WHERE 子句照片列中的值。 请参阅有关在使用较大的数据类型上执行操作的请求消息架构的详细信息对大型数据类型的操作的消息架构[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]。  
  
 业务流程使用该消息，并将其发送到 Oracle 数据库。 从 Oracle 数据库的响应保存在定义为业务流程的一部分的其他文件位置中。 例如，从前面的请求消息的 Oracle 数据库响应如下所示：  
  
```  
<?xml version="1.0" encoding="utf-8"?>  
<Update_PHOTOResponse xmlns="http://schemas.microsoft.com/OracleEBS/2008/05/Tables/SCOTT/CUSTOMER" />  
```  
  
 业务流程现在构造的请求消息**Read_PHOTO** C:\TestLocation\MessageIn 在使用提供的请求消息的操作。 请求消息发送到 Oracle 数据库和响应保存在同一文件位置。 在照片列上执行读取操作的响应如下所示：  
  
```  
<?xml version="1.0" encoding="utf-8"?>  
<Read_PHOTOResponse xmlns="http://schemas.microsoft.com/OracleEBS/2008/05/Tables/SCOTT/CUSTOMER">  
  <Read_PHOTOResult>U2FtcGxlIERhdGE=</Read_PHOTOResult>  
</Read_PHOTOResponse>  
```  
  
> [!NOTE]
>  请注意，响应将包含相同的值中传递的照片列**Update_PHOTO**操作。  
  
## <a name="best-practices"></a>最佳实践  
 已部署并配置 BizTalk 项目之后，你可以将配置设置导出到 XML 文件称为绑定文件。 后生成绑定文件，你可以导入的配置设置文件，以便不需要创建诸如发送端口和接收相同的业务流程的端口。 有关绑定文件的详细信息，请参阅[重用 Oracle E-business Suite 适配器绑定](../../adapters-and-accelerators/adapter-oracle-ebs/reuse-adapter-bindings-with-oracle-e-business-suite.md)。  
  
## <a name="see-also"></a>另请参阅  
[开发使用 Oracle E-business Suite 适配器的 BizTalk 应用程序](../../adapters-and-accelerators/adapter-oracle-ebs/develop-biztalk-applications-using-the-oracle-e-business-suite-adapter.md)