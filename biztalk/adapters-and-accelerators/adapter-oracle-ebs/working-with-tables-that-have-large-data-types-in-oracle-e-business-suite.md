---
title: 使用 Oracle E-business Suite 中具有较大的数据类型的表 |Microsoft Docs
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
ms.openlocfilehash: 51b22afd469b472b4d960daf19b50bc4994d24e8
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65374231"
---
# <a name="working-with-tables-that-have-large-data-types-in-oracle-e-business-suite"></a>使用 Oracle E-business Suite 中具有较大的数据类型的表
[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]使适配器客户端能够执行对界面表和视图的较大的数据类型，如 BLOB、 CLOB、 NCLOB、 和 BFILE 操作。  
  
- 类型的列的 BLOB、 CLOB、 和 NCLOB 适配器允许客户端读取以及更新的数据。 该适配器公开 Read_\<LOBColName\>和 Update_\<LOBColName\>操作来读取和更新数据，其中\<LOBColName\>是较大的列的名称数据类型。 如果有多个大型数据类型列的单个接口表中，适配器将公开，因为许多读取和更新该表的接口的操作。  
  
- 对于类型 BFILE 列，适配器客户端只能读取的数据。 该适配器公开 Read_\<LOBColName\>操作从 BFILE 类型的列读取数据。 如果有多个大型数据类型列的单个接口表中，适配器将公开任意数量的读取操作的接口表。  
  
  有关这些操作的详细信息，请参阅[对界面表、 界面视图、 表和包含 LOB 数据的视图的操作](../../adapters-and-accelerators/adapter-oracle-ebs/read-and-update-on-interface-tables-and-views-with-large-object-data-types.md)。 有关执行这些操作的消息架构的信息，请参阅[特殊 LOB 操作的消息架构](../../adapters-and-accelerators/adapter-oracle-ebs/message-schemas-for-special-lob-operations1.md)。  
  
## <a name="how-to-perform-operations-on-columns-with-large-data-types"></a>如何在具有较大的数据类型的列上执行操作  
 通过执行对 Oracle E-business Suite 的操作[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]与[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]涉及过程中所述的任务[来创建 Oracle E-business Suite 应用程序的构建基块](../../adapters-and-accelerators/adapter-oracle-ebs/building-blocks-to-create-oracle-e-business-suite-applications.md)。 若要在包含大型数据类型的 Oracle E-business Suite 中执行对界面表和界面视图的操作，这些任务包括：  
  
1. 创建 BizTalk 项目，并为操作生成架构 (Read_\<LOBColName\>或 Update_\<LOBColName\>) 你想要调用表或视图。  
  
2. 在发送和接收消息从 Oracle E-business Suite 的 BizTalk 项目中创建的消息。  
  
3. 创建一个业务流程调用的接口表或视图上的操作。  
  
4. 生成并部署 BizTalk 项目。  
  
5. 配置的 BizTalk 应用程序通过创建物理发送端口和接收端口。  
  
6. 启动 BizTalk 应用程序。  
  
   本主题介绍如何执行这些任务。  
  
## <a name="how-this-topic-demonstrates-reading-and-writing-data-into-columns-of-large-data-types"></a>本主题读取和写入大型数据类型的列的数据的演示  
 为了演示读取和写入大型数据类型的列的数据，本主题介绍如何创建将执行以下业务流程：  
  
- 更新计算 CUSTOMER 表的照片列 （的 BLOB 数据类型）。  
  
- 读取已更新记录的 PHOTO 列的值。  
  
  此业务流程设计仅用于更新操作在运行时提供的请求消息的方式。 将在操作中构造的消息的读取操作。  
  
> [!NOTE]
>  本主题中的业务流程中读取和更新数据的 CUSTOMER 表，这是一个基本的数据库表中创建的运行这些示例提供的脚本。 本主题，以执行读取或更新任何接口表或界面视图上的操作中所述，必须执行类似的过程。  
  
## <a name="generating-schema"></a>生成架构  
 本主题演示如何执行基本读取和更新 CUSTOMER 表中的照片列 （的 BLOB 数据类型） 的操作。 通过运行这些示例提供的脚本创建此表。  
  
 若要演示如何读取和写入大型数据类型的列的数据，架构为生成**Update_PHOTO**并**Read_PHOTO** CUSTOMER 表的操作。 必须创建一个 BizTalk 项目，并使用[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]生成的架构。 请参阅[检索用于 Oracle E-business Suite 操作在 Visual Studio 中的元数据](../../adapters-and-accelerators/adapter-oracle-ebs/get-metadata-for-oracle-e-business-suite-operations-in-visual-studio.md)有关如何生成架构的详细信息。  
  
## <a name="defining-messages-and-message-types"></a>定义消息和消息类型  
 先前生成的架构描述业务流程中的消息所需的"类型"。 一条消息通常是一个变量，要为其类型定义由相应的架构。 现在必须为该业务流程创建消息并将其链接到你在上一步中生成的架构。  
  
 在此业务流程中，你必须创建四个消息 — 设置一个接收响应**Update_PHOTO**为设置操作和其他接收-响应**Read_PHOTO**操作。  
  
#### <a name="to-create-messages-and-link-to-schema"></a>若要创建消息并将链接到架构  
  
1.  向 BizTalk 项目添加业务流程。 从解决方案资源管理器，右键单击 BizTalk 项目名称，指向**外**，然后单击**新项**。 键入 BizTalk 业务流程的名称，然后单击**添加**。  
  
2.  如果尚未打开，请打开 BizTalk 项目的业务流程视图窗口。 若要执行此操作，请单击**视图**，依次指向**其他 Windows**，然后单击**业务流程视图**。  
  
3.  在业务流程视图中，右键单击**消息**，然后单击**新消息**。  
  
4.  右键单击新创建的消息，然后依次**属性窗口**。  
  
5.  在中**属性**窗格**Message_1**，执行以下操作：  
  
    |使用此选项|执行的操作|  
    |--------------|----------------|  
    |Identifier|类型 `UpdateMessage`|  
    |消息类型|从下拉列表中，展开**架构**，然后选择*LOBOperations.OracleEBSBinding.Update_PHOTO*，其中 LOBOperations 是 BizTalk 项目的名称。 OracleEBSBindingSchema 是用于调用生成的架构**Update_PHOTO**客户表上的操作。|  
  
6.  重复步骤 3 以创建三个新消息。 在中**属性**窗格中的新消息，执行以下操作：  
  
    |将标识符设置为|将消息类型设置为|  
    |-----------------------|-------------------------|  
    |UpdateResponse|*LOBOperations.OracleEBSBinding.Update_PHOTOResponse*|  
    |ReadMessage|*LOBOperations.OracleEBSBinding1.Read_PHOTO*|  
    |ReadResponse|*LOBOperations.OracleEBSBinding1.Read_PHOTOResponse*|  
  
## <a name="setting-up-the-orchestration"></a>设置业务流程  
 在此业务流程，该适配器收到的请求消息执行 Update_PHOTO 操作对 CUSTOMER 表。 在文件位置接收通知消息。 适配器使用此消息，并将其传递到 Oracle 数据库。 从 Oracle 数据库的响应保存在另一个位置中。 一旦收到响应，该业务流程将构造一条消息，调用 Read_PHOTO 操作，读取 Update_PHOTO 操作更新照片列的值。 在相同的文件位置还收到此消息的响应。  
  
 因此，您的业务流程必须包含以下信息：  
  
- 一个 FILE 接收端口用于将请求消息放**Update_PHOTO**操作。  
  
- 双向 WCF 自定义或 WCF OracleEBS 发送端口以发送消息，以执行**Update_PHOTO**操作。  
  
- 双向 WCF 自定义或 WCF OracleEBS 发送端口以发送消息，以执行**Read_PHOTO**操作。 您还可以执行这两**Read_PHOTO**并**Update_PHOTO**使用相同的 WCF 自定义或 WCF OracleEBS 发送端口。 在本主题中，您将这两个操作使用单个发送端口。  
  
- 一个**构造消息**形状可以构造在业务流程内的消息。  
  
- 文件发送端口，用于保存的响应消息**Update_PHOTO**并**Read_PHOTO**操作。  
  
- 接收和发送形状。  
  
  示例业务流程如下所示。  
  
  ![在较大的数据类型列上操作的业务流程](../../adapters-and-accelerators/adapter-oracle-ebs/media/1976ab27-94c3-4039-a1ca-8790e8897ad5.gif "1976ab27-94c3-4039-a1ca-8790e8897ad5")  
  
### <a name="adding-message-shapes"></a>添加消息形状  
 请确保为每个消息形状中指定以下属性。 形状列中列出的名称是在刚提到的业务流程中显示的消息形状的名称。  
  
|形状|形状类型|属性|  
|-----------|----------------|----------------|  
|ReceiveUpdateMessage|Receive|-设置**名称**到*ReceiveUpdateMessage*<br />-设置**激活**到 *，则返回 True*|  
|SendUpdateMessage|Send|-设置**名称**到*SendUpdateMessage*|  
|ReceiveUpdateResponse|Receive|-设置**名称**到*ReceiveUpdateResponse*|  
|SendUpdateResponse|Receive|-设置**名称**到*SendUpdateResponse*|  
|SendReadMessage|Send|-设置**名称**到*SendReadMessage*|  
|ReceiveReadResponse|Receive|-设置**名称**到*ReceiveReadResponse*|  
|SaveReadResponse|Send|-设置**名称**到*SaveReadResponse*|  
  
### <a name="adding-construct-message-shape"></a>添加构造消息形状  
 可以使用**构造消息**形状中，以生成请求消息在业务流程内的执行**Read_PHOTO**操作。 若要执行此操作，必须添加**构造消息**形状，并在其中**消息赋值**向业务流程的形状。 对于本例，请**消息赋值**形状调用生成一条消息，发送到 Oracle E-business Suite 要执行的代码**Read_PHOTO**操作。 **消息赋值**形状还设置用于消息发送到 Oracle E-business Suite 的操作。  
  
 对于构造消息形状，请设置**构造的消息**属性设置为**ReadMessage**。  
  
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
  
 对于上述代码摘录中以便能够生成请求消息，你必须具有 XML 请求消息 (对于**Read_PHOTO**操作) 中为指定的位置`XmlFileLocation`变量。  
  
> [!NOTE]
>  生成项目后，将在项目目录中创建 MessageCreator.dll。 必须将此 DLL 添加到全局程序集缓存 (GAC) 中。 此外，必须将 MessageCreator.dll 添加为 BizTalk 项目中的引用。  
  
 添加以下表达式来调用此代码从**消息赋值**形状，以及设置用于消息的操作。 若要添加一个表达式，请双击**消息赋值**形状以打开表达式编辑器。  
  
```  
ReadMessage = MessageCreator.MessageCreator.XMLMessageCreator();  
ReadMessage(WCF.Action) = "Tables/ReadLOB/SCOTT/CUSTOMER/PHOTO ";  
```  
  
### <a name="adding-ports"></a>添加端口  
 请确保为每个逻辑端口中指定以下属性。 端口列中列出的名称是在业务流程中显示的端口的名称。  
  
|Port|属性|  
|----------|----------------|  
|MessageIn|-设置**标识符**到*MessageIn*<br />-设置**类型**到*MessageInType*<br />-设置**通信模式**到*单向*<br />-设置**通信方向**到*接收*|  
|LOBPort|-设置**标识符**到*LOBPort*<br />-设置**类型**到*LOBPortType*<br />-设置**通信模式**到*请求-响应*<br />-设置**通信方向**到*发送接收*<br />-创建一个操作*Read_LOB*。 此操作的消息用于从大型数据类型列中读取值。<br />-创建一个操作*Update_LOB*。 此操作的消息用于更新较大的数据类型列中的值。|  
|ResponseOut|-设置**标识符**到*ResponseOut*<br />-设置**类型**到*ResponseOutType*<br />-设置**通信模式**到*单向*<br />-设置**通信方向**到*发送*<br />-创建一个操作*Read_LOB*。 此操作的消息用于从大型数据类型列中读取值。<br />-创建一个操作*Update_LOB*。 此操作的消息用于更新较大的数据类型列中的值。|  
  
### <a name="specify-messages-for-action-shapes-and-connect-to-ports"></a>为操作形状指定消息并将连接到端口  
 下表指定属性应设置为指定操作形状的消息并链接到的端口的消息及其值。 形状列中列出的名称是消息形状的名称，前面所述的业务流程中所示。  
  
|形状|属性|  
|-----------|----------------|  
|ReceiveUpdateMessage|-设置**消息**到*UpdateMessage*<br />-设置**操作**到*MessageIn.Update_LOB。请求*|  
|SendUpdateMessage|-设置**消息**到*UpdateMessage*<br />-设置**操作**到*LOBPort.Update_LOB。请求*|  
|ReceiveUpdateResponse|-设置**消息**到*UpdateResponse*<br />-设置**操作**到*LOBPort.Update_LOB。响应*|  
|SendUpdateResponse|-设置**消息**到*UpdateResponse*<br />-设置**操作**到*ResponseOut.Update_LOB。请求*|  
|SendReadMessage|-设置**消息**到*ReadMessage*<br />-设置**操作**到*LOBPort.Read_LOB。请求*|  
|ReceiveReadResponse|-设置**消息**到*ReadResponse*<br />-设置**操作**到*LOBPort.Read_LOB。响应*|  
|SendReadResponse|-设置**消息**到*ReadResponse*<br />-设置**操作**到*ResponseOut.Read_LOB。请求*|  
  
 指定这些属性后，消息形状和端口进行连接，您的业务流程已完成。  
  
 现在必须生成 BizTalk 解决方案，并将其部署到[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]。 有关详细信息，请参阅[构建和运行业务流程](../../core/building-and-running-orchestrations.md)。  
  
## <a name="configuring-the-biztalk-application"></a>配置 BizTalk 应用程序  
 部署 BizTalk 项目后，在业务流程窗格中列出前面创建的业务流程[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理控制台。 必须使用[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理控制台来配置应用程序。 有关演练，请参阅[演练：部署基本 BizTalk 应用程序](Walkthrough:%20Deploying%20a%20Basic%20BizTalk%20Application.md)。
  
 配置应用程序包括：  
  
- 选择应用程序的主机。  
  
- 映射到物理端口在业务流程中创建的端口[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理控制台。 对于此业务流程，您必须：  
  
  - 硬盘和相应 FILE 端口将放置请求消息的位置上定义的位置。 BizTalk 业务流程将使用请求消息并将其发送到 Oracle 数据库。  
  
  - 硬盘和相应的 BizTalk 业务流程放置包含从 Oracle 数据库响应的响应消息的位置的文件端口上定义的位置。  
  
  - 定义一个物理 WCF 自定义或 WCF OracleEBS 发送端口将消息发送到 Oracle 数据库。 您必须在发送端口中指定的操作。 有关如何创建端口的信息，请参阅[手动配置物理端口绑定到 Oracle E-business 适配器](../../adapters-and-accelerators/adapter-oracle-ebs/manually-configure-a-physical-port-binding-to-the-oracle-e-business-adapter.md)。 配置 WCF 自定义时，必须考虑以下注意事项或 WCF OracleEBS 发送端口。  
  
    -   `Update_<LOBColName>`作为事务的一部分，必须在执行操作。 若要确保此操作，请**UseAmbientTransaction**绑定属性必须设置为**True**。  
  
    -   由于 WCF 自定义或 WCF OracleEBS 发送端口发送和接收符合多个架构的消息并执行两个操作，必须设置为这两种操作的动态操作。 有关操作的详细信息，请参阅[适用于 Oracle E-business Suite 中配置 SOAP 操作](../../adapters-and-accelerators/adapter-oracle-ebs/configure-the-soap-action-for-oracle-e-business-suite.md)。 对于此业务流程，应将操作设置，如下所示：  
  
        ```  
        <BtsActionMapping xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xmlns:xsd="http://www.w3.org/2001/XMLSchema">  
          <Operation Name="Update_LOB" Action="Tables/UpdateBlob/SCOTT/CUSTOMER/PHOTO" />  
          <Operation Name="Read_LOB" Action="Tables/ReadLOB/SCOTT/CUSTOMER/PHOTO" />  
        </BtsActionMapping>  
        ```  
  
        > [!IMPORTANT]
        >  请注意，中的动态操作的操作名称必须与创建 BizTalk 业务流程时指定的逻辑端口的操作名称相同。  
  
    > [!NOTE]
    >  若要执行的接口表或界面视图上的操作还必须设置应用程序上下文。 适配器如何支持设置应用程序上下文的详细信息，请参阅[设置应用程序上下文](../../adapters-and-accelerators/adapter-oracle-ebs/set-application-context.md)。 您可以通过指定的绑定属性或设置消息上下文属性公开的设置应用程序上下文[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]。 有关如何设置绑定属性的说明，请参阅[适用于 Oracle E-business Suite 中配置的绑定属性](../../adapters-and-accelerators/adapter-oracle-ebs/configure-the-binding-properties-for-oracle-e-business-suite.md)。 有关如何设置应用程序上下文中使用消息上下文属性的说明，请参阅[Oracle E-business Suite 中配置应用程序上下文使用消息上下文属性](../../adapters-and-accelerators/adapter-oracle-ebs/configure-application-context-using-message-context-properties-in-oracle-ebs.md)。  
    > 
    > [!NOTE]
    >  生成架构使用[!INCLUDE[consumeadapterservlong](../../includes/consumeadapterservlong-md.md)]还会创建一个绑定文件，包含有关端口和要为这些端口设置的操作的信息。 可以将此绑定文件导入[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理控制台来创建 （对于出站调用） 的发送端口或接收端口 （对于入站调用）。 有关详细信息，请参阅[物理端口绑定使用端口绑定文件配置到 Oracle E-business Suite](../../adapters-and-accelerators/adapter-oracle-ebs/configure-a-physical-port-binding-using-a-port-binding-file-to-oracle-ebs.md)。  
  
## <a name="starting-the-application"></a>启动应用程序  
 开始之前 BizTalk 业务流程，请确保要调用的请求 XML **Read_PHOTO**操作位于 C:\TestLocation\MessageIn。 请求 XML 必须如下所示：  
  
```  
<Read_PHOTO xmlns="http://schemas.microsoft.com/OracleEBS/2008/05/Tables/SCOTT/CUSTOMER">  
  <FILTER>WHERE NAME='Mindy Martin'</FILTER>  
</Read_PHOTO>  
```  
  
> [!NOTE]
>  请求消息的特定名称具有筛选器，因为在请求消息，消息**Update_PHOTO**操作，PHOTO 列的值更新为相同的名称。 因此，读取的操作将读取相同使用更新操作插入的值。  
  
 现在，你必须启动用于读取和写入大型数据类型的值从 Oracle 数据库的 BizTalk 应用程序。 在启动 BizTalk 应用程序的说明，请参阅[如何启动业务流程](../../core/how-to-start-an-orchestration.md)。  
  
 在此阶段，请确保：  
  
-   文件接收端口接收请求消息的业务流程正在运行。  
  
-   运行文件发送端口以接收来自业务流程的响应消息。  
  
-   WCF 自定义或 WCF OracleEBS 发送端口将消息发送到 Oracle 数据库正在运行。  
  
-   该操作的 BizTalk 业务流程正在运行。  
  
## <a name="executing-the-operation"></a>执行该操作  
 启动应用程序必须删除后的文件的请求消息的接收位置。 请求消息的架构的架构必须符合**Update_PHOTO**先前生成的操作。 例如，更新照片的 CUSTOMER 表的列的请求消息如下所示：  
  
```  
<Update_PHOTO xmlns="http://schemas.microsoft.com/OracleEBS/2008/05/Tables/SCOTT/CUSTOMER">  
  <FILTER>WHERE Name='Mindy Martin'</FILTER>  
  <DATA>U2FtcGxlIERhdGE=</DATA>  
</Update_PHOTO>  
```  
  
> [!NOTE]
>  更新 BLOB 列，时的数据元素必须始终包含一个 base64 编码值。 有关 CLOB 和 NCLOB，数据元素可以具有字符串值。  
  
 前面的请求消息更新的记录匹配的 WHERE 子句照片列中的值。 请参阅有关在使用大型数据类型上执行操作的请求消息架构详细信息，对大型数据类型的操作的消息架构[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]。  
  
 业务流程使用该消息并将其发送到 Oracle 数据库。 从 Oracle 数据库的响应保存在定义为业务流程的一部分的其他文件位置。 例如，从 Oracle 数据库中前面的请求消息的响应如下所示：  
  
```  
<?xml version="1.0" encoding="utf-8"?>  
<Update_PHOTOResponse xmlns="http://schemas.microsoft.com/OracleEBS/2008/05/Tables/SCOTT/CUSTOMER" />  
```  
  
 现在，业务流程将构造的请求消息**Read_PHOTO** C:\TestLocation\MessageIn 在使用提供的请求消息的操作。 请求消息发送到 Oracle 数据库和响应保存在相同的文件位置。 PHOTO 列上的读取操作的响应类似于以下内容：  
  
```  
<?xml version="1.0" encoding="utf-8"?>  
<Read_PHOTOResponse xmlns="http://schemas.microsoft.com/OracleEBS/2008/05/Tables/SCOTT/CUSTOMER">  
  <Read_PHOTOResult>U2FtcGxlIERhdGE=</Read_PHOTOResult>  
</Read_PHOTOResponse>  
```  
  
> [!NOTE]
>  请注意，响应包含相同的值为 PHOTO 列中传递**Update_PHOTO**操作。  
  
## <a name="best-practices"></a>最佳实践  
 部署和配置 BizTalk 项目后，你可以配置设置导出到名为绑定文件的 XML 文件。 后生成的绑定文件，可以以便不需要创建诸如发送端口和接收端口的同一业务流程，从文件导的配置设置。 有关绑定文件的详细信息，请参阅[Oracle E-business Suite 的重用适配器绑定](../../adapters-and-accelerators/adapter-oracle-ebs/reuse-adapter-bindings-with-oracle-e-business-suite.md)。  
  
## <a name="see-also"></a>请参阅  
[开发 BizTalk 应用程序使用 Oracle E-business Suite 适配器](../../adapters-and-accelerators/adapter-oracle-ebs/develop-biztalk-applications-using-the-oracle-e-business-suite-adapter.md)