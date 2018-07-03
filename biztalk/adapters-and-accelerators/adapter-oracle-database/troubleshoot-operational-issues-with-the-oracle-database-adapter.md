---
title: 使用 Oracle 数据库适配器的操作问题疑难解答 |Microsoft Docs
description: 常见的问题和 Oracle 数据库适配器在 BizTalk 适配器包 (BAP) 的解决方法
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 2fb83245-2b6a-48cc-8601-b923bb009a58
caps.latest.revision: 25
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 13dfe903e897ebc3d26e6dc380233f80253ddfc5
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36968414"
---
# <a name="troubleshoot-operational-issues-with-the-oracle-database-adapter"></a>使用 Oracle 数据库适配器的操作问题疑难解答
故障排除技术来解决你可能会遇到使用的操作错误[!INCLUDE[adapteroracle](../../includes/adapteroracle-md.md)]。  
  
## <a name="enable-tracing"></a>启用跟踪  
 有关跟踪中的支持信息[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]，请参阅[诊断跟踪和消息日志记录的 Oracle 数据库适配器](../../adapters-and-accelerators/adapter-oracle-database/diagnostic-tracing-and-message-logging-for-the-oracle-database-adapter.md)。  
  
## <a name="known-issues"></a>已知问题  
 以下是在使用时可能遇到的最常见错误[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]，以及其可能的原因和解决方法。   
  
### <a name="BKMK_OraDBLoading"></a> 加载适配器绑定时出错  
 **问题**  
  
 当您尝试启动[!INCLUDE[addadapterservreflong](../../includes/addadapterservreflong-md.md)]或[!INCLUDE[consumeadapterservlong](../../includes/consumeadapterservlong-md.md)]，收到以下错误：  
  
```  
There was an error loading the binding, <binding name>, from your system configuration.  
ConfigurationErrorsException: Exception has been thrown by the target of an invocation.  
```  
  
 **原因**  
  
 当您尝试启动[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]或[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]，WCF 将加载所有已安装的适配器的适配器绑定。 反过来，适配器绑定都依赖于企业应用程序特定的客户端软件。 您可能会遇到此问题的一个或两个原因如下：  
  
- 在安装该适配器的计算机上未安装所需的 LOB 客户端软件。  
  
- 未将适配器安装中包含的所有适配器的典型或完全安装[!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)]。 但是，可能只有一个企业应用程序安装 LOB 客户端库。 因此，在 GUI 无法加载其他适配器的绑定。  
  
  **解决方法**  
  
- 请确保在您安装的计算机上安装了所需的 LOB 客户端版本[!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)]。 [支持的业务线 (LOB) 和企业系统](https://social.technet.microsoft.com/wiki/contents/articles/17631.biztalk-server-supported-line-of-business-lob-and-enterprise-systems.aspx)列出了支持的客户端版本。  
  
- 请确保执行要安装仅需要的适配器的适配器的自定义安装。  
  
  > [!NOTE]
  >  若要确保你的应用程序处理 ODP.NET 的最新版本，必须具有策略的"Dll"的计算机上安装和在 GAC 中注册。 有关详细信息，请参阅[适用于.NET 的 Oracle 数据提供程序](http://go.microsoft.com/fwlink/p/?LinkId=92834)Oracle 的网站上。  
  
###  <a name="BKMK_OraDBAdapDisplay"></a> Oracle 数据库适配器不会显示在 BizTalk Server 管理控制台中的适配器列表中  
 **问题**  
  
[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]包含[!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)]不在 BizTalk Server 管理控制台中的适配器列表中列出。  
  
 **原因**  
  
 [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]是 WCF 自定义绑定。 因此，尽管[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理控制台中显示[!INCLUDE[wcfadapter_short](../../includes/wcfadapter-short-md.md)]，它不会显示 WCF 自定义绑定，因此，不会显示基于 WCF 的[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]。  
  
 **解决方法**  
  
 您可以显式添加[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]到[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理控制台中所述的步骤[将 Oracle 数据库适配器添加到 BizTalk Server 管理控制台](../../adapters-and-accelerators/adapter-oracle-database/adding-the-oracle-database-adapter-to-biztalk-server-administration-console.md)。  
  
###  <a name="BKMK_OraDBXMLRetrieve"></a> 检索与 65536 个以上节点的 XML 输出时出错  
 **问题**  
  
 在检索 XML 输出的具有多个 65,536 节点时，适配器将报告以下错误。  
  
```  
Maximum number of items that can be serialized or deserialized in an object graph is '65536'.  
Change the object graph or increase the MaxItemsInObjectGraph quota.  
```  
  
 **原因**  
  
 适配器不能序列化和反序列化具有多个 65,536 项的对象。  
  
 **解决方法**  
  
 可以通过设置来解决此问题`maxItemsInObjectGraph`参数。 您可以设置这在以下两种方法之一：  
  
- 将此参数设置通过更改`maxItemsInObjectGraph`中的参数`ServiceBehavior`服务类中的属性。  
  
- 以下代码添加到应用程序的 app.config 文件。  
  
  ```  
  <behaviors>  
    <endpointBehaviors>  
      <behavior name="NewBehavior">  
        <dataContractSerializer maxItemsInObjectGraph="65536000" />  
      </behavior>  
    </endpointBehaviors>  
  </behaviors>  
  ```  
  
  示例 app.config 外观如下所示。  
  
```  
<?xml version="1.0" encoding="utf-8"?>  
<configuration>  
  <system.serviceModel>  
    <behaviors>  
      <endpointBehaviors>  
        <behavior name="NewBehavior">  
         <dataContractSerializer maxItemsInObjectGraph="65536000" />  
        </behavior>  
      </endpointBehaviors>  
    </behaviors>  
    <client>  
      <endpoint   behaviorConfiguration="NewBehavior" binding="oracleDBBinding"  
       contract="IOutboundContract" name="oracle_ICalculator" />  
    </client>  
  </system.serviceModel>  
</configuration>  
```  
  
###  <a name="BKMK_OraDBPerfOps"></a> 在 Oracle 数据库上执行操作时出错  
 **问题**  
  
 执行对 Oracle 数据库使用的任何操作时，适配器将报告以下错误[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]。  
  
- **为 BizTalk Server**  
  
  ```  
  System.ArgumentNullException: Value cannot be null.  
  ```  
  
  **原因**  
  
  未指定消息的 WCF 操作。 WCF 需要用于为每个操作，向适配器通知上的 LOB 应用程序执行的操作指定的 SOAP 操作。  
  
  **解决方法**  
  
  在发送端口或为 BizTalk 业务流程的消息上下文属性指定的 SOAP 操作。 有关说明，请参阅[配置 Oracle 数据库的 SOAP 操作](../../adapters-and-accelerators/adapter-oracle-database/configure-the-soap-action-for-oracle-database.md)。 请参阅[消息和消息架构](messages-and-message-schemas-for-biztalk-adapter-for-oracle-database.md)若要查看每个操作的操作的列表。  
  
###  <a name="BKMK_OraDBXmlParsing"></a> 由于指定的操作中的不正确的操作名称 XmlReaderParsingException  
 **问题**  
  
 将消息发送到 Oracle 数据库时，BizTalk Server 管理控制台提供了以下错误：  
  
```  
Microsoft.ServiceModel.Channels.Common.XmlReaderParsingException: Invalid argument:  
<BtsActionMapping xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xmlns:xsd="http://www.w3.org/2001/XMLSchema">  
  <Operation Name="<operation_name>" Action="<action>" />  
</BtsActionMapping>  
```  
  
 **原因**  
  
 如果通过导入创建的端口绑定文件配置 WCF 自定义端口[!INCLUDE[consumeadapterservlong](../../includes/consumeadapterservlong-md.md)]，采用以下格式指定端口中的操作：  
  
```  
<BtsActionMapping>  
  <Operation Name="Op1" Action="http://MyService/Svc/Op1" />  
</BtsActionMapping>  
```  
  
 在上述格式中，操作名称受生成架构时选择该操作。 例如，如果生成的上一个表的插入操作的架构，操作中的操作名称将"Insert"。 但是中的逻辑端口的操作名称创建在 BizTalk 业务流程中[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]可能不同。  
  
 **解决方法**  
  
 请确保操作名称的两个逻辑端口 (在 BizTalk 业务流程中[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]) 和 （在 BizTalk Server 管理控制台） 的物理端口相同。  
  
###  <a name="BKMK_OraDBConnURI"></a> 在 BizTalk 中指定的 WCF 自定义端口的连接 URI 时出错  
 **问题**  
  
 [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] 在指定连接 URI 连接到 Oracle 数据库时出现以下错误。  
  
```  
Error saving properties.  
(System.ArgumentException) The specified address is invalid.  
(System.ArgumentException) Invalid address;  
"<connection URI>" is not a well-formed absolute uri.  
```  
  
 **原因**  
  
 连接 URI 不符合标准的编码格式。 例如，某个参数的值可能包含一个空格。  
  
 **解决方法**  
  
 请确保你指定的 URI 遵循标准编码格式的连接。 例如，必须通过"%20"替换为空格。  
  
###  <a name="BKMK_OraDBInvalCursor"></a> 调用采用 REF CURSOR 参数的存储的过程时无效的游标异常  
 **问题**  
  
 当您调用使用 REF CURSOR 输入 Oracle 数据库中的过程时，可能会收到以下异常：  
  
```  
Microsoft.ServiceModel.Channels.Common.TargetSystemException: ORA-01001: invalid cursor ---> Oracle.DataAccess.Client.OracleException  
```  
  
 **原因**  
  
 所调用的过程的 PL/SQL 块可能会通过管道将 REF Cursor，也就是说，在 REF CURSOR 无法获取分配给出 REF CURSOR。  
  
 **解决方法**  
  
 PL/SQL 块必须不通过管道传递到而无需正确处理 OUT REF Cursor。  
  
###  <a name="BKMK_OraDBValidateResp"></a> 验证使用 BizTalk Server ReadLOB 操作的响应时出错  
 **问题**  
  
 执行 ReadLOB 操作使用时[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]与[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]，从 Oracle 数据库的响应未通过验证对 Web 服务描述语言 (WSDL)。  
  
 **原因**  
  
 WSDL 包含 StreamBody 节点名为基于服务的请求的执行定义但不需要为 BizTalk 方案。 因此，输出 XML，不包含 StreamBody 节点，相比使用 WSDL 中，验证将失败。  
  
 **解决方法**  
  
 使用 BizTalk Server 生成的输出进行验证时，则从 WSDL 中删除 StreamBody 节点。 执行以下步骤来执行此操作：  
  
1. WSDL 包含 StreamBody 节点如下所示。  
  
   ```  
   <xs:element name="ReadLOBResponse">  
       <xs:annotation>  
         <xs:documentation>  
           <doc:action xmlns:doc="http://schemas.microsoft.com/servicemodel/adapters/metadata/documentation">http://Microsoft.LobServices.OracleDB/2007/03/SCOTT/Table/TBL_ALL_DATATYPES/ReadLOB/response\</doc:action>  
         </xs:documentation>  
       </xs:annotation>  
       <xs:complexType>  
         <xs:sequence>  
           <xs:element minOccurs="1" maxOccurs="1" name="ReadLOBResult" nillable="true" type="ns3:StreamBody" />  
         </xs:sequence>  
       </xs:complexType>  
     </xs:element>  
   ```  
  
    替换以下前面。  
  
   ```  
   <xs:element name="ReadLOBResponse">  
    <xs:annotation>  
    <xs:documentation>  
     <doc:action xmlns:doc="http://schemas.microsoft.com/servicemodel/adapters/metadata/documentation">http://Microsoft.LobServices.OracleDB/2007/03/SCOTT/Table/TBL_ALL_DATATYPES/ReadLOB/response\</doc:action>   
     </xs:documentation>  
     </xs:annotation>  
    <xs:complexType>  
    <xs:sequence>  
     <xs:element minOccurs="1" maxOccurs="1" name="ReadLOBResult" type="xs:base64Binary" />   
     </xs:sequence>  
     </xs:complexType>  
     </xs:element>  
   ```  
  
    在此步骤中，删除对类型的引用 ="ns3:StreamBody"原始 XSD 中的，并将其替换类型为 ="xs:base64Binary"。 此外，您可以从原始 XSD 删除 nillable ="true"值。  
  
2. 从 WSDL 中删除以下。  
  
   ```  
   <xs:complexType name="StreamBody">  
       <xs:sequence>  
         <xs:element minOccurs="1" maxOccurs="1" name="Stream">  
           <xs:simpleType>  
             <xs:restriction base="xs:base64Binary">  
               <xs:minLength value="0" />  
             </xs:restriction>  
           </xs:simpleType>  
         </xs:element>  
       </xs:sequence>  
     </xs:complexType>  
     <xs:element name="StreamBody" nillable="true" type="ns3:StreamBody" />  
   ```  
  
   > [!NOTE]
   >  不支持的操作 ReadLOB [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]。 应使用的表选择操作来读取从 LOB 数据[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]解决方案。  
  
###  <a name="BKMK_OraDBSchemaValidateFail"></a> 架构验证在轮询方案中可能会失败  
 **问题**  
  
 在方案中的架构验证失败，[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]轮询数据库包含 ROWID 或 UNROWID 类型的字段的表。  
  
 **原因**  
  
 在设计时适配器生成包含 ROWID 或 UNROWID，类型的字段的表的元数据时的架构包括"nillable = false"，这意味着 ROWID 或 UNROWID 类型的字段不能为 null。 但是，在运行时在适配器检索元数据，当 ROWID 或 UNROWID 类型的字段包含 null 值。 因此架构验证失败。  
  
 **解决方法**  
  
 如果使用的[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]与[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]，您可以选择禁用架构验证。 或者，可以手动编辑要更改的架构"nillbale = true"ROWID 和 UNROWID 数据类型。  
  
###  <a name="BKMK_OraDBUnreasonConv"></a> 请求不合理 conversion 错误时执行存储过程以及记录类型作为参数  
 **原因**  
  
 考虑 Oracle 存储过程采用的方案记录类型作为参数。 假定记录类型声明为\<表名称\>%行类型，在表有长整型数据类型的列。 当[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]遇到长整型数据类型，它设置数据类型的大小为指定的值等于**LongDatatypeColumnSize**属性绑定。 但是，Oracle 数据库不定义为 LONG 数据类型的大小。 因此，当适配器调用存储的过程，它会导致不合理 conversion 请求错误。  
  
 **解决方法**  
  
 如果记录类型的长整型数据类型，您必须显式定义它作为包的一部分。  
  
###  <a name="BKMK_OraDBAdapRecognize"></a> 适配器不识别物理端口上的操作，即使由使用适配器服务加载项生成的绑定文件用于创建端口  
 **问题**  
  
 在使用后[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]若要生成的 Oracle 数据库上的特定操作的架构外, 接程序还会创建端口绑定文件。 您可以导入此文件使用绑定[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理控制台，可在 BizTalk Server 中创建物理端口。 但是时将消息发送到 Oracle 数据库使用此类端口时，, 适配器将无法理解的端口上指定的操作，并提供了类似于以下的错误：  
  
```  
Microsoft.ServiceModel.Channels.Common.UnsupportedOperationException: Incorrect Action   
<BtsActionMapping xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xmlns:xsd="http://www.w3.org/2001/XMLSchema">  
  <Operation Name="<op_name>" Action="<action>" />  
</BtsActionMapping>. Correct the specified Action, or refer to the documentation on the allowed formats for the Actions.  
```  
  
 **原因**  
  
 BizTalk 业务流程中创建逻辑端口时，指定这些端口上操作某些名称，或只需使用默认名称，例如 Operation_1、 Operation_2，等等。但是，在生成的绑定文件[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]，操作名称是与为其生成元数据的 Oracle 数据库操作的名称相同。 例如，如果在 Oracle 数据库中生成针对 ACCOUNTACTIVITY 表选择操作的元数据，操作将设置为以下：  
  
```  
<Operation Name="Select" Action="http://Microsoft.LobServices.OracleDB/2007/03/SCOTT/Table/ACCOUNTACTIVITY/Select" />  
```  
  
 导入绑定文件时，物理端口上设置相同的操作。 因此，逻辑端口 （Operation_1、 Operation_2 等） 上的操作名称与物理端口，从而导致错误的操作中指定的操作名称不匹配。  
  
 **解决方法**  
  
 请确保逻辑端口中的操作名称中的物理端口的操作中指定的操作名称相同。 执行以下操作之一：  
  
-   将 BizTalk 业务流程中的逻辑端口中的操作名称从 Operation_1 等更改为其生成元数据，例如选择该操作。  
  
-   将物理端口上的操作中的操作名称更改为中的逻辑端口的操作名称。 例如，可以更改为类似于以下的物理端口中的操作：  
  
    ```  
    <Operation Name="Operation_1" Action="http://Microsoft.LobServices.OracleDB/2007/03/SCOTT/Table/ACCOUNTACTIVITY/Select" />  
    ```  
  
###  <a name="BKMK_OraDBOverflowExcep"></a> 适配器引发溢出异常 ("System.OverflowException") 上执行某项操作  
 **问题**  
  
 如果尝试执行包含内部数据集或弱类型化 REF CURSOR 的 Oracle 数值数据类型的操作，请使用适配器，适配器可能引发溢出异常。  
  
 **原因**  
  
 如果提供的数据集或不适合放在相应的.NET 类型的弱类型化 REF CURSOR 的 Oracle 数值数据类型较大的值，将发生这种情况。  
  
 **解决方法**  
  
 如果你想要传递的数据集或弱类型化 REF CURSOR 的 Oracle 数值数据类型的较大值，则必须启用安全设置的值键入**EnableSafeTyping**属性绑定到**true**. 启用安全键入以字符串形式公开的数据集或弱类型化 REF CURSOR 的 Oracle 数值数据类型。  
  
###  <a name="BKMK_OraDBRootNode"></a> 使用 BizTalk 项目中的 RootNode TypeName 错误  
 **问题**  
  
 中的 BizTalk 项目中[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]，则从架构生成[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]包含无效的字符或保留的字**RootNode TypeName**属性，编译项目时将发生以下错误:  
  
```  
Node <node reference> - Specify a valid .NET type name for this root node.  
The current .NET type name of this root node is invalid (it is a reserved BizTalk Keyword or is an invalid C# identifier).  
```  
  
 **解决方法**  
  
1.  右键单击该错误，然后选择中引用的 rood 这样节点**属性**。  
  
2.  有关**RootNode TypeName**属性，删除任何非法字符或保留字，例如，点 （.）。  
  
###  <a name="BKMK_OraDBInvalBinding"></a> 无效的绑定时出现的警告在 Visual Studio 中使用适配器  
 **问题**  
  
 当您使用适配器中创建应用程序[!INCLUDE[btsVStudio2008](../../includes/btsvstudio2008-md.md)]和打开由适配器生成的配置文件 (app.config)，会看到类似于以下警告：  
  
```  
The element 'bindings' has invalid child element 'oracleDBBinding'. List of possible elements expected: 'basicHttpBinding, customBinding, ...  
```  
  
 **原因**  
  
 会出现此警告[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]绑定， `oracleDBBinding`，不标准绑定随附于[!INCLUDE[firstref_btsWinCommFoundation](../../includes/firstref-btswincommfoundation-md.md)]。  
  
 **解决方法**  
  
 可以安全地忽略此警告。  
  
###  <a name="BKMK_OraDBNotification"></a> BizTalk Server 将引发异常，如果在同一个应用程序中使用多个通知架构或在同一主机上的多个应用程序中使用通知架构  
 **问题**  
  
 BizTalk Server 将引发异常，表明该应用程序找不到文档规范，因为多个架构匹配的消息类型或 XLANG 异常。  
  
 **原因**  
  
 由于以下任一发生这种情况：  
  
- 已生成多个通知架构在 BizTalk Server 项目中，将其部署到 BizTalk Server 应用程序，然后运行应用程序从 Oracle 数据库接收通知。 由于通知架构都是公用的冲突之间没有 BizTalk Server 应用程序中部署的架构。  
  
- 发生多个项目时您已为每个 BizTalk Server 部署的项目，每个项目到同一主机上单独的 BizTalk Server 应用程序生成的通知架构，然后运行应用程序或应用程序以接收来自通知Oracle 数据库中。 因为架构和程序集都是可访问 BizTalk Server 中的应用程序，则冲突之间常见的架构部署在各种 BizTalk Server 应用程序和程序集。  
  
  **解决方法**  
  
  为 BizTalk Server 应用程序使用单个通知架构文件。 如果需要在同一主机上的多个 BizTalk Server 应用程序中使用通知架构，创建包含单个通知架构的应用程序，然后使用 BizTalk Server 中的从所有其他应用程序的通知架构。  
  
###  <a name="BKMK_MemUsage"></a> 内存使用情况和线程数将增加时在事务处理的入站操作中使用适配器  
 **问题**  
  
 在事务处理的入站操作中，如轮询，**如果没有数据轮询表中可用**并且该适配器将继续轮询，一段时间内遇到内存使用情况和线程计数的增加。  
  
 **原因**  
  
 **如果没有数据轮询表中可用**后，每个接收超时周期[!INCLUDE[firstref_btsWinCommFoundation](../../includes/firstref-btswincommfoundation-md.md)]产生了一个新的线程无法继续轮询操作。 因此，一段时间内会增加线程计数和内存使用情况。 但是，如果正在轮询一次的表具有一些数据，同一个线程继续执行所有后续轮询。  
  
 **解决方法**  
  
 我们建议设置**ReceiveTimeout**的最大可能值，这是 24.20:31:23.6470000 （24 天），以便生成新线程，仅每隔 24 天。 这将确保，内存使用情况和线程计数不会不会变得太多时间太短。  
  
> [!NOTE]
>  如果尚未设置 SqlAdapterInboundTransactionBehavior，请确保 TransactionTimeout 也被配置为最大可能值，即 24.20:31:23.6470000 （24 天）。 在使用此解决方法，我们可以添加 SqlAdapterInboundTransactionBehavior，仅当事务隔离级别必须进行配置。 否则，它是删除该行为的最佳做法。  
  
 有关详细信息**ReceiveTimeout**绑定属性，请参阅[阅读有关 Oracle 数据库适配器绑定属性](../../adapters-and-accelerators/adapter-oracle-database/read-about-the-oracle-database-adapter-binding-properties.md)。 指定绑定属性的说明，请参阅[用于 Oracle 数据库配置的绑定属性](../../adapters-and-accelerators/adapter-oracle-database/configure-the-binding-properties-for-oracle-database.md)。  
  
> [!NOTE]
>  使用的适配器时[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]，超时值设置为较大的值不会影响适配器的功能。  
  
## <a name="see-also"></a>请参阅  
[Oracle 数据库适配器疑难解答](../../adapters-and-accelerators/adapter-oracle-database/troubleshoot-the-oracle-database-adapter.md)  
[对 Oracle 数据库适配器的安装问题进行故障排除](../../adapters-and-accelerators/adapter-oracle-database/troubleshoot-installation-issues-with-the-oracle-database-adapter.md)