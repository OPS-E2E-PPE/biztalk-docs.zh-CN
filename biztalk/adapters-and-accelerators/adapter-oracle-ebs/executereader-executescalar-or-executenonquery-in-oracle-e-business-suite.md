---
title: 在 Oracle E-business Suite ExecuteReader、 ExecuteScalar 或 ExecuteNonQuery 操作 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 1e2d377d-60a2-45fe-8458-433e6f4f6619
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 227e6ce16e7cf555a1f600feac215e433a9e7574
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/28/2017
ms.locfileid: "25965475"
---
# <a name="executereader-executescalar-or-executenonquery-operations-in-oracle-e-business-suite"></a>在 Oracle E-business Suite ExecuteReader、 ExecuteScalar 或 ExecuteNonQuery 操作
[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]如公开泛型操作**ExecuteNonQuery**， **ExecuteReader**，和**ExecuteScalar**。 这些操作可用于 Oracle 数据库执行任何 SQL 语句。 这些操作因响应为 SQL 语句所获取的类型而异。 有关如何适配器支持这些操作的详细信息，请参阅[支持 ExecuteNonQuery、 ExecuteReader 和 ExecuteScalar 操作](../../adapters-and-accelerators/adapter-oracle-ebs/support-for-executenonquery-executereader-and-executescalar-operations.md)。  
  
 本主题演示如何执行**ExecuteReader**操作使用[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]与[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]。 你可以按照同一套执行本主题中所述的过程**ExecuteNonQuery**和**ExecuteScalar**操作。  
  
## <a name="how-to-invoke-executereader-operation-on-oracle-database"></a>如何在 Oracle 数据库上的调用 ExecuteReader 操作  
 通过执行对 Oracle 数据库的操作[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]与[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]涉及过程中所述的任务[创建 Oracle E-business Suite 应用程序的构建基块](../../adapters-and-accelerators/adapter-oracle-ebs/building-blocks-to-create-oracle-e-business-suite-applications.md)。 若要调用**ExecuteReader** Oracle 数据库的操作，这些任务都是：  
  
1.  创建 BizTalk 项目，并生成架构**ExecuteReader**操作。  
  
2.  在发送和接收消息从 Oracle 数据库的 BizTalk 项目中创建消息。  
  
3.  创建业务流程以调用在 Oracle 数据库上的操作。  
  
4.  生成和部署 BizTalk 项目。  
  
5.  配置的 BizTalk 应用程序创建的物理发送和接收端口。  
  
6.  启动 BizTalk 应用程序。  
  
 本主题提供执行这些任务的说明。  
  
## <a name="generating-schema"></a>生成架构  
 本主题演示如何调用**ExecuteReader** Oracle 数据库使用的操作[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]与[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]。 **ExecuteReader**操作采用任何 SQL 语句作为参数并返回的数据集作为数组的操作的结果集。 本主题中，为我们执行的 SELECT 语句 ACCOUNTACTIVITY 表使用**ExecuteReader**操作。 ACCOUNTACTIVITY 表是通过运行这些示例提供的脚本创建的。 有关的脚本的详细信息，请参阅[示例](../../adapters-and-accelerators/adapter-oracle-ebs/samples-for-the-oracle-ebs-adapter.md)。  
  
 为了演示如何调用**ExecuteReader**操作，为生成架构**ExecuteReader**操作。 您必须创建 BizTalk 项目，并使用[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]生成架构。 有关如何生成架构的详细信息，请参阅[检索用于 Oracle E-business Suite 操作 Visual Studio 中的元数据](../../adapters-and-accelerators/adapter-oracle-ebs/get-metadata-for-oracle-e-business-suite-operations-in-visual-studio.md)。  
  
## <a name="defining-messages-and-message-types"></a>定义消息和消息类型  
 你之前生成的架构描述了业务流程中的消息所需的“类型”。 消息通常是一个变量，其类型由相应的架构定义。 现在，你必须创建业务流程的消息，并将它们链接到你在上一步中生成的架构。  
  
#### <a name="to-create-messages-and-link-to-schema"></a>创建消息并将链接到架构  
  
1.  BizTalk 项目中添加业务流程。 从解决方案资源管理器，右键单击 BizTalk 项目名称，指向**添加**，然后单击**新项**。 键入 BizTalk 业务流程的名称，然后单击**添加**。  
  
2.  如果尚未打开，请打开 BizTalk 项目的业务流程视图窗口。 若要执行此操作，请单击**视图**，指向**其他窗口**，然后单击**业务流程视图**。  
  
3.  在业务流程视图中，右键单击**消息**，然后单击**新消息**。  
  
4.  右键单击新创建的消息中，，然后选择**属性窗口**。  
  
5.  在**属性**窗格**Message_1**，执行以下操作：  
  
    |使用此选项|执行的操作|  
    |--------------|----------------|  
    |Identifier|类型`Request`|  
    |消息类型|从下拉列表中，展开**架构**，然后选择*Execute_Reader.GenericOperation.ExecuteReader*，其中 Execute_Reader 是 BizTalk 项目的名称。 *GenericOperation*是为生成的架构**ExecuteReader**操作。|  
  
6.  重复步骤 2 创建一条新消息。 在**属性**窗格中，为新的消息中，执行以下操作：  
  
    |使用此选项|执行的操作|  
    |--------------|----------------|  
    |Identifier|类型`Response`|  
    |消息类型|从下拉列表中，展开**架构**，然后选择*Execute_Reader.GenericOperation.ExecuteReaderResponse*。|  
  
## <a name="setting-up-the-orchestration"></a>设置业务流程  
 你必须创建要使用 BizTalk 业务流程[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]为 Oracle 数据库上执行操作。 此业务流程，在你删除时的请求消息的定义接收位置。 [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]使用此消息并将其传递到 Oracle 数据库。 从 Oracle 数据库的响应保存到另一个位置。 调用泛型操作如典型业务流程**ExecuteReader**将包含：  
  
-   发送和接收形状来发送和接收消息从 Oracle 数据库。  
  
-   双向接收端口来发送和接收消息从 Oracle 数据库。  
  
-   单向发送端口将响应从 Oracle 数据库发送到的文件夹。  
  
 调用示例业务流程**ExecuteReader**操作如下所示：  
  
 ![业务流程，以调用 ExecuteReader 操作](../../adapters-and-accelerators/adapter-oracle-ebs/media/37b63331-76b7-47a2-b9d3-0c60e165d993.gif "37b63331-76b7-47a2-b9d3-0c60e165d993")  
  
### <a name="adding-message-shapes"></a>添加消息形状  
 你需要为每个消息形状配置以下属性。 形状列中列出的名称的名称相对应的消息形状刚提到业务流程中所示。  
  
|形状|形状类型|属性|  
|-----------|----------------|----------------|  
|ReceiveMessage|Receive|-将设置**名称**到*ReceiveMessage*<br />-将设置**激活**到*True*|  
|发送消息|Send|-将设置**名称**到*SendMessage*|  
|ReceiveResponse|Receive|-将设置**名称**到*ReceiveResponse*<br />-将设置**激活**到*False*|  
|SendResponse|Send|-将设置**名称**到*SendResponse*|  
  
### <a name="adding-ports"></a>添加端口  
 对于每个逻辑端口，配置下表中的属性。 端口列中列出的名称的名称相对应的端口业务流程中所示。  
  
|端口|属性|  
|----------|----------------|  
|MessageIn|-将设置**标识符**到*MessageIn*<br />-将设置**类型**到*MessageInType*<br />-将设置**通信模式**到*单向*<br />-将设置**通信方向**到*接收*|  
|LOBPort|-将设置**标识符**到*LOBPort*<br />-将设置**类型**到*LOBPortType*<br />-将设置**通信模式**到*请求-响应*<br />-将设置**通信方向**到*发送接收*|  
|ResponseOut|-将设置**标识符**到*ResponseOut*<br />-将设置**类型**到*ResponseOutType*<br />-将设置**通信模式**到*单向*<br />-将设置**通信方向**到*发送*|  
  
### <a name="specify-messages-for-action-shapes-and-connect-them-to-ports"></a>指定消息的操作形状并将其连接到端口  
 下表指定属性值，用于指定操作形状的消息并将邮件链接到的端口。 中列出的名称**形状**列的名称相对应的消息形状更早版本的业务流程关系图所示。  
  
 已配置这些属性后，连接的消息形状和端口，，您的业务流程已完成。  
  
 然后，你现在必须生成 BizTalk 解决方案并将其部署到 BizTalk Server。 有关详细信息，请参阅[生成和运行业务流程](../../core/building-and-running-orchestrations.md)。  
  
|形状|属性|  
|-----------|----------------|  
|ReceiveMessage|-将设置**消息**到*请求*<br />-将设置**操作**到*MessageIn.Exec_Reader.Request*|  
|发送消息|-将设置**消息**到*请求*<br />-将设置**操作**到*LOBPort.Exec_Reader.Request*|  
|ReceiveResponse|-将设置**消息**到*响应*<br />-将设置**操作**到*LOBPort.Exec_Reader.Response*|  
|SendResponse|-将设置**消息**到*响应*<br />-将设置**操作**到*ResponseOut.Exec_Reader.Request*|  
  
 指定这些属性后，消息形状和端口将连接，并且您的业务流程已完成。  
  
 现在，你必须生成 BizTalk 解决方案，并将其部署到 BizTalk Server。 有关详细信息，请参阅[生成和运行业务流程](../../core/building-and-running-orchestrations.md)。  
  
## <a name="configuring-the-biztalk-application"></a>配置 BizTalk 应用程序  
 部署 BizTalk 项目后，业务流程之前创建下列出**业务流程**窗格中的[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理控制台。 必须使用[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理控制台配置该应用程序。 有关演练，请参阅[演练： 将基本的 BizTalk 应用程序部署](Walkthrough:%20Deploying%20a%20Basic%20BizTalk%20Application.md)。  
  
 配置应用程序涉及：  
  
-   选择应用程序的主机。  
  
-   映射到中的物理端口业务流程中创建的端口[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理控制台。 对于此业务流程，您必须：  
  
    -   硬盘和放置请求消息的位置的相应文件端口上定义的位置。 BizTalk 业务流程将使用请求消息并将其发送到 Oracle 数据库。  
  
    -   硬盘和 BizTalk 业务流程放置包含从 Oracle 数据库响应的响应消息的位置的相应文件端口上定义的位置。  
  
    -   定义一个物理 WCF 自定义或 WCF OracleEBS 发送端口将消息发送到 Oracle 数据库。 你必须在发送端口中指定的操作。 有关如何创建发送端口的信息，请参阅[手动配置到 Oracle E-business 适配器的物理端口绑定](../../adapters-and-accelerators/adapter-oracle-ebs/manually-configure-a-physical-port-binding-to-the-oracle-e-business-adapter.md)。  
  
        > [!IMPORTANT]
        >  泛型操作的一部分如果执行操作的对象，例如存储过程、 函数、 接口表或界面视图，属于 Oracle E-business Suite 应用程序，您必须通过指定设置的应用程序上下文必备项绑定的属性。 有关设置应用程序上下文的详细信息，请参阅[设置应用程序上下文](../../adapters-and-accelerators/adapter-oracle-ebs/set-application-context.md)。  
        >   
        >  你可以通过指定的绑定属性或设置消息上下文属性公开的设置应用程序上下文[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]。 有关如何设置绑定属性的说明，请参阅[配置的 Oracle E-business Suite 绑定属性](../../adapters-and-accelerators/adapter-oracle-ebs/configure-the-binding-properties-for-oracle-e-business-suite.md)。 有关如何设置应用程序上下文使用消息上下文属性的说明，请参阅[在 Oracle E-business Suite 中配置应用程序上下文使用消息上下文属性](../../adapters-and-accelerators/adapter-oracle-ebs/configure-application-context-using-message-context-properties-in-oracle-ebs.md)。  
  
        > [!NOTE]
        >  生成架构使用[!INCLUDE[consumeadapterservlong](../../includes/consumeadapterservlong-md.md)]还会创建包含有关端口以及要为这些端口设置的操作信息绑定文件。 你可以导入此绑定文件与[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理控制台来创建发送端口 （对于出站调用），或接收 （对于入站调用） 的端口。 有关详细信息，请参阅[物理端口绑定使用端口绑定文件配置到 Oracle E-business Suite](../../adapters-and-accelerators/adapter-oracle-ebs/configure-a-physical-port-binding-using-a-port-binding-file-to-oracle-ebs.md)。  
  
## <a name="starting-the-application"></a>启动应用程序  
 你必须启动 BizTalk 应用程序，然后调用**ExecuteReader** Oracle 数据库的操作。 有关启动 BizTalk 应用程序的说明，请参阅[如何启动 Orchestration](../../core/how-to-start-an-orchestration.md)。  
  
 在此阶段，请确保：  
  
-   FILE 接收端口，以便运行业务流程的是接收请求消息。  
  
-   要从业务流程接收响应消息的文件发送端口正在运行。  
  
-   WCF 自定义或 WCF OracleEBS 发送端口将消息发送到 Oracle 数据库正在运行。  
  
-   BizTalk 业务流程操作正在运行。  
  
## <a name="executing-the-operation"></a>执行该操作  
 运行应用程序后，必须放到该文件的请求消息接收位置。 请求消息的架构必须符合的架构**ExecuteReader**先前生成的操作。 例如，请求消息执行 SELECT 语句使用**ExecuteReader**操作：  
  
```  
<ExecuteReader xmlns="http://schemas.microsoft.com/OracleEBS/2008/05/GenericOperation/">  
  <Query>SELECT * FROM ACCOUNTACTIVITY</Query>  
</ExecuteReader>  
```  
  
 有关 ExecuteReader、 ExecuteScalar 和 ExecuteNonQuery 操作调用的请求消息架构有关的详细信息，请参阅消息架构**ExecuteReader**操作使用[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]。  
  
 业务流程使用该消息，并将其发送到 Oracle 数据库。 从 Oracle 数据库的响应保存在定义为业务流程的一部分的其他文件位置中。 有关响应**ExecuteReader**操作中包含的结果集作为数据集。 例如，来自前面的请求消息的 Oracle 数据库的响应是：  
  
```  
<?xml version="1.0" encoding="utf-8" ?>   
<ExecuteReaderResponse xmlns="http://schemas.microsoft.com/OracleEBS/2008/05/GenericOperation/">  
  <ExecuteReaderResult>  
    <xs:schema id="NewDataSet" xmlns:xs="http://www.w3.org/2001/XMLSchema" xmlns:msdata="urn:schemas-microsoft-com:xml-msdata">  
      <xs:element msdata:IsDataSet="true" name="NewDataSet">  
        <xs:complexType>  
          <xs:sequence>  
            <xs:element minOccurs="0" maxOccurs="unbounded" name="NewTable">  
              <xs:complexType>  
                <xs:sequence>  
                  <xs:element minOccurs="0" name="TID" type="xs:decimal" />   
                  <xs:element minOccurs="0" name="ACCOUNT" type="xs:decimal" />   
                  <xs:element minOccurs="0" name="AMOUNT" type="xs:decimal" />   
                  <xs:element minOccurs="0" name="DESCRIPTION" type="xs:string" />   
                  <xs:element minOccurs="0" name="TRANSDATE" type="xs:dateTime" />   
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
          <AMOUNT>500</AMOUNT>   
          <DESCRIPTION />   
          <TRANSDATE>2008-08-04T13:04:20</TRANSDATE>   
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
  </ExecuteReaderResult>  
</ExecuteReaderResponse>  
```  
  
## <a name="best-practices"></a>最佳实践  
 已部署并配置 BizTalk 项目之后，你可以将配置设置导出到 XML 文件称为绑定文件。 生成绑定文件后，你可以导入的配置设置文件，以便不需要创建诸如发送端口和接收相同的业务流程的端口。 有关绑定文件的详细信息，请参阅[重用 Oracle E-business Suite 适配器绑定](../../adapters-and-accelerators/adapter-oracle-ebs/reuse-adapter-bindings-with-oracle-e-business-suite.md)。  
  
## <a name="see-also"></a>另请参阅  
[开发使用 Oracle E-business Suite 适配器的 BizTalk 应用程序](../../adapters-and-accelerators/adapter-oracle-ebs/develop-biztalk-applications-using-the-oracle-e-business-suite-adapter.md)