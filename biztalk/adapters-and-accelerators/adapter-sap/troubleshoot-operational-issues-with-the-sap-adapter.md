---
title: 使用 BizTalk 中的 SAP 适配器进行的操作问题故障排除 |Microsoft Docs
description: 常见错误、 问题和解决方法与 mySAP 适配器在 BizTalk 适配器包 (BAP)
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: bb0f005b-7548-478b-8243-69e07c29d02c
caps.latest.revision: 32
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 1c137b60c9c9a8c354baf39b91349e0836c94b91
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36998270"
---
# <a name="troubleshoot-operational-issues-with-the-sap-adapter"></a>使用 SAP 适配器进行的操作问题故障排除
本部分讨论如何使用故障排除技术来解决操作使用时可能遇到的错误[!INCLUDE[adaptersap](../../includes/adaptersap-md.md)]。  
  
### <a name="enable-tracing"></a>启用跟踪  
 有关跟踪中的支持信息[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]，请参阅[诊断跟踪和消息日志记录 SAP 适配器的](../../adapters-and-accelerators/adapter-sap/diagnostic-tracing-and-message-logging-for-the-sap-adapter.md)。  
  
##  <a name="client_dll"></a> 加载绑定时出错  
 **问题**  
  
 当您尝试启动[!INCLUDE[addadapterservreflong](../../includes/addadapterservreflong-md.md)]或[!INCLUDE[consumeadapterservlong](../../includes/consumeadapterservlong-md.md)]，GUI 将报告以下错误：  
  
```  
There was an error loading the binding, <binding name>, from your system configuration.  
ConfigurationErrorsException: Exception has been thrown by the target of an invocation.  
```  
  
 **原因**  
  
 当您启动[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]或[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]，[!INCLUDE[firstref_btsWinCommFoundation](../../includes/firstref-btswincommfoundation-md.md)]加载所有已安装的适配器的适配器绑定。 反过来，适配器绑定都依赖于企业应用程序特定的客户端软件。 您可能会遇到此问题的一个或两个原因如下：  
  
- 在安装该适配器的计算机上未安装所需的 LOB 客户端软件。  
  
- 未将适配器安装中包含的所有适配器的典型或完全安装[!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)]。 但是，可能只有一个企业应用程序安装 LOB 客户端库。 因此，在 GUI 无法加载其他适配器的绑定。  
  
  **解决方法**  
  
- 请确保执行要安装仅需要的适配器的适配器的自定义安装。  
  
- 请确保你安装的计算机上安装了所需的 LOB 客户端版本[!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)]。 [支持 LOB 系统](https://social.technet.microsoft.com/wiki/contents/articles/17631.biztalk-server-supported-line-of-business-lob-and-enterprise-systems.aspx)列出了受支持的版本。 [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)]还要求某些 Dll，以便与 SAP 系统进行交互。 有关适配器所必需的 Dll 的详细信息，请参阅[适用于 SAP 数据提供程序安装自定义 Rfc](../../adapters-and-accelerators/adapter-sap/install-custom-rfcs-for-the-data-provider-for-sap.md)。
  
##  <a name="BKMK_SAPDisplay"></a> SAP 适配器缺少 BizTalk 管理控制台中  
 **问题**  
  
[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]附带[!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)]未显示在 BizTalk Server 管理控制台中的适配器列表中。  
  
 **原因**  
  
 [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]是 WCF 自定义绑定。 因此，尽管[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理控制台中显示[!INCLUDE[wcfadapter_short](../../includes/wcfadapter-short-md.md)]，它不会显示 WCF 自定义绑定，因此，不会显示基于 WCF 的[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]。  
  
 **解决方法**  
  
 您可以显式添加[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]到[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理控制台中所述的步骤[将 SAP 适配器添加到 BizTalk Server 管理控制台](../../adapters-and-accelerators/adapter-sap/add-the-sap-adapter-to-biztalk-server-administration-console.md)。  
  
##  <a name="BKMK_SAPConnOpen"></a> Dll 缺少打开与 SAP 的连接时出错  
 **问题**  
  
 当您尝试打开连接到 SAP 系统使用[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]，在 SAP 系统中，会出现一个对话框，在某些 Dll 丢失了通知。  
  
 **原因**  
  
 [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] Librfc32u.dll 用于建立与 SAP 系统的连接。 Librfc32u.dll，反过来，需要一的组 Dll 才能正常。 如果这些支持 Dll 不会添加到 PATH 变量的计算机上收到此错误在其中[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]安装。  
  
 **解决方法**  
  
 请参阅表来为解决此问题提供[加载适配器绑定时出错](#client_dll)问题。 此表列出了与 SAP 系统使用所需的支持 Dll [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]。  
  
##  <a name="BKMK_SAPXmlRetrieve"></a> 检索与 65536 个以上节点的 XML 时出错  
 **问题**  
  
 检索具有 65536 个以上节点的 XML 输出时，适配器将报告以下错误。  
  
```  
Maximum number of items that can be serialized or deserialized in an object graph is '65536'.  
Change the object graph or increase the MaxItemsInObjectGraph quota.  
```  
  
 **原因**  
  
 适配器不能序列化和反序列化具有多个 65,536 项的对象。  
  
 **解决方法**  
  
 可以通过设置来解决此问题`maxItemsInObjectGraph`中通过以下两种方式的参数：  
  
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
  
  示例 app.config 看起来如下所示。  
  
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
      <endpoint   behaviorConfiguration="NewBehavior" binding="sapBinding"  
       contract="IOutboundContract" name="sap_ICalculator" />  
    </client>  
  </system.serviceModel>  
</configuration>  
```  
  
##  <a name="BKMK_SAPConnURI"></a> 错误输入 BizTalk Server 中的 WCF 自定义端口的连接 URI  
 **问题**  
  
 [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] 在指定连接 URI 连接到 SAP 系统时出现以下错误。  
  
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
  
##  <a name="BKMK_SAPOperate"></a> System.ArgumentNullException 上 SAP 的操作出错  
 **问题**  
  
 对 SAP 系统使用执行任何操作时，适配器将报告以下错误[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]。  
  
```  
System.ArgumentNullException: Value cannot be null.  
```  
  
 **原因**  
  
 未指定消息的 WCF 操作。 WCF 需要用于为每个操作，向适配器通知上的 LOB 应用程序执行的操作指定的 SOAP 操作。  
  
 **解决方法**  
  
 在发送端口或为 BizTalk 业务流程的消息上下文属性指定的 SOAP 操作。 有关说明，请参阅[配置用于 SAP 系统的 SOAP 操作](../../adapters-and-accelerators/adapter-sap/configure-the-soap-action-for-the-sap-system.md)。 请参阅[消息和消息架构](messages-and-message-schemas-for-biztalk-adapter-for-mysap-business-suite.md)若要查看每个操作的操作的列表。  
  
##  <a name="BKMK_SAPXmlParsing"></a> 由于不正确的操作名称中指定的操作的 XmlReaderParsingException  
 **问题**  
  
 将消息发送到 SAP 系统时，BizTalk Server 管理控制台将报告以下错误：  
  
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
  
 在上述格式中，操作名称受生成架构时选择该操作。 例如，如果 RFC_CUSTOMER_GET 生成架构，操作名称的操作中将"RFC_CUSTOMER_GET"。 但是中的逻辑端口的操作名称创建在 BizTalk 业务流程中[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]可能不同。  
  
 **解决方法**  
  
 请确保操作名称的两个逻辑端口 (在 BizTalk 业务流程中[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]) 和 （在 BizTalk Server 管理控制台） 的物理端口相同。  
  
##  <a name="BKMK_SAPHundredCons"></a> 打开与 SAP 超过 100 个连接时出错  
 **问题**  
  
 打开到 SAP 系统的 100 多个连接时，适配器将引发以下异常。  
  
```  
Microsoft.ServiceModel.Channels.Common.ConnectionException: ErrorCode=RFC_OK. ErrorGroup=RFC_ERROR_COMMUNICATION. SapErrorMessage=Connect to SAP gateway failed  
Connect_PM  GWHOST=<gw_host>, GWSERV=<gw_serv>, SYSNR=<sys_number>  
LOCATION    CPIC (TCP/IP) on local host with Unicode  
ERROR       max no of 100 conversations exceeded  
```  
  
 **原因**  
  
 默认情况下，SAP 不会启用超过 100 个连接到系统。  
  
 **解决方法**  
  
 若要增加最大连接数，必须已安装并将其设置为数字值的 SAP 客户端库的计算机上创建一个环境变量。 为此环境变量指定的值是最大可为 SAP 系统的连接数。 使用以下详细信息创建环境变量：  
  
- **变量名称**: CPIC_MAX_CONV  
  
- **变量值**： 任何正的数字值。 例如，如果要启用 200 个连接到 SAP 系统，可以指定值设为 200。  
  
  创建一个环境变量的说明，请参阅"如何在 Windows 2000 中创建系统变量"处[ http://go.microsoft.com/fwlink/?LinkId=95020 ](http://go.microsoft.com/fwlink/?LinkId=95020)。  
  
##  <a name="BKMK_SAPIDOCMetadata"></a> 生成时出现错误或检索 Idoc 的元数据  
 **问题**  
  
 生成的元数据时**接收**SAP 系统中的 IDOC 的操作[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]时出现以下错误。  
  
```  
Error while retrieving or generating the WSDL.  
Adapter message: Details: ErrorCode=RFC_EXCEPTION.  
ErrorGroup=RFC_ERROR_APPLICATION_EXCEPTION. SapErrorMessage= OBJECT_UNKNOWN.  
AdapterErrorMessage=Error returned by RfcCallReceiveEx while calling RFC: IDOCTYPE_READ_COMPLETE.  
```  
  
 **原因**  
  
 [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] IDOCTYPE_READ_COMPLETE RFC 用于检索的元数据**接收**IDOC 的操作。 调用此 RFC 要求 SAP 系统中的特定用户的权限。 若要生成的元数据，如果已连接到 SAP 系统使用的凭据，没有权限来调用 IDOCTYPE_READ_COMPLETE RFC[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]会出错。  
  
 **解决方法**  
  
 登录到 SAP GUI 使用相同的凭据必须用于该适配器。 导航到事务 SE37，并输入 RFC IDOCTYPE_READ_COMPLETE 作为执行的名称。  
  
 PI_IDOCTYP 和 PI_CIMTYP 的输入参数，请输入对应于自定义 IDoc 的值。 对于 PI_VERSION 和 PI_RELEASE 参数，为所选适配器元数据 UI 中输入相同的值。 然后，按 F8 来执行。  
  
 应收到相同的错误什么适配器接收时，有关该问题的详细信息。  
  
 如果仍然无法解决此问题，生成的架构**ReceiveIdoc**而不是操作**接收**操作。 在这种情况下，SAP 适配器不使用 IDOCTYPE_READ_COMPLETE，并且不会引发任何错误。  
  
##  <a name="BKMK_SAPIDOCReceive"></a> 错误发送或接收具有取消释放段的 Idoc  
 **问题**  
  
 [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]发送 Idoc 时提供 XmlReaderParsingException (使用**发送**操作) 或接收 Idoc (使用**接收**操作)，已取消释放段。  
  
 **原因**  
  
 Idoc 被构成的段。 生成元数据时[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]检索 SAP 系统中存在的所有已发布的段。 但是，当适配器客户端使用的元数据执行操作接收 IDOC，例如[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]提供 XmlReaderParsingException。 这是因为 SAP 系统收到的 IDOC 后，可能发送某些未发布的段，适配器未生成其元数据。  
  
 **解决方法**  
  
 执行以下任一操作：  
  
-   将 SAP 系统升级通过应用相应的修补程序未发布段。  
  
-   使用**SendIdoc**或**ReceiveIdoc**操作来发送和接收 Idoc 分别。 有关这些操作的详细信息，请参阅[sap 的 Idoc 的操作](../../adapters-and-accelerators/adapter-sap/operations-on-idocs-in-sap.md)。  
  
##  <a name="BKMK_SAPIDOCSend"></a> 将平面文件 Idoc 发送到 SAP 使用 SAP FilePort 接收到的错误  
 **问题**  
  
 如果您尝试发送 (使用**发送**操作) 到 SAP 系统，使用 SAP FilePort 生成平面文件 IDOC，BizTalk 业务流程中的平面文件分析器无法 flatf 文件转换为 XML 格式，从而失败IDOD**发送**操作。  
  
 **原因**  
  
 当 SAP 系统生成使用 FilePort IDOC 时，修剪关闭一个段末尾的所有空白空间。 但是，平面文件分析器要求存在才可成功地将平面文件转换为 XML 的段中的最后一个字段的数据。 因为空空间不存在的段中，平面文件分析器无法分析为 XML 的平面文件。  
  
 **解决方法**  
  
 对于使用 SAP FilePort 生成此类平面文件 Idoc，使用**SendIdoc**操作相反。 有关此操作的详细信息，请参阅[sap 的 Idoc 的操作](../../adapters-and-accelerators/adapter-sap/operations-on-idocs-in-sap.md)。  
  
##  <a name="BKMK_SAPRecIDOCCompat"></a> 错误从 SAP 接收 Idoc，如果 EnableBizTalkCompatibilityMode 属性设置为 true  
 **问题**  
  
 接收与 IDOC 时遇到以下异常**EnableBizTalkCompatibilityMode**绑定属性设置为 true:  
  
```  
System.Exception: Loading property information list by namespace failed or property not found in the list. Verify that the schema is deployed properly.  
```  
  
 **原因**  
  
 如果绑定属性**EnableBizTalkCompatibilityMode**设置为**true**，你必须将 BizTalk 属性架构 DLL 添加为[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]为 BizTalk 应用程序，即中的资源在其中部署你的项目的应用程序。  
  
 **解决方法**  
  
 BizTalk 属性架构的名称[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]是*Microsoft.Adapters.SAP.BiztalkPropertySchema.dll*。 此情况下安装[!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)]设置下\<安装驱动器\>: \Program Files\Microsoft BizTalk 适配器 Pack\bin。 执行以下任务来添加此程序集作为 BizTalk 应用程序中的资源。  
  
#### <a name="add-an-assembly-as-a-resource-in-biztalk-application"></a>将程序集添加为 BizTalk 应用程序中的资源  
  
1. 启动[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理控制台。  
  
2. 在控制台树中，展开**BizTalk 组**，展开**应用程序**，，然后你想要添加 BizTalk 程序集的应用程序。  
  
3. 展开**应用程序**和你想要添加 BizTalk 程序集的应用程序。  
  
4. 右键单击**资源**，依次指向**添加**，然后单击**BizTalk 程序集**。  
  
5. 单击**外**，导航到包含 BizTalk 程序集文件的文件夹中，选择 BizTalk 程序集文件，然后单击**打开**。  
  
6. 在中**选项**，为 BizTalk 程序集安装到 GAC 中，指定选项，然后单击**确定**。  
  
##  <a name="BKMK_SAPIDOCValidate"></a> 中从 SAP 系统接收 Idoc 时的验证错误  
 **问题**  
  
 从 SAP 系统接收 IDOC 未能通过验证，类似于以下错误：  
  
```  
There was a failure executing the receive pipeline: "Microsoft.BizTalk.DefaultPipelines.XMLReceive, Microsoft.BizTalk.DefaultPipelines, Version=3.0.1.0, Culture=neutral, PublicKeyToken=<token>"  
Source: "Pipeline " Receive Port: "ReceiveIdoc" URI: "<connection uri>"  
Reason: The document failed to validate because of the following error:  
"The 'http://Microsoft.LobServices.Sap/2007/03/Types/Idoc/3/CREMAS03//620:TAXBS' element has an invalid value according to its data type."  
```  
  
 **原因**  
  
 生成用于接收 IDOC 的元数据包含接收操作的一部分接收特定列的允许值。 这些值公开为生成的元数据中的枚举。 但是，当实际收到 IDOC 时，收到的值可能不同于枚举值。 因此，接收操作失败时验证的值。 例如，在上述错误消息的验证失败 TAXBS 列。  
  
 **解决方法**  
  
 您必须手动编辑架构 （对于 BizTalk 项目） 或客户端代理中的枚举 （对于.NET 项目使用 WCF 服务模型） 包含 SAP 系统从收到的值。  
  
##  <a name="BKMK_SAPFFIDOC"></a> 平面文件 Idoc 转换为 XML，前后不完全相同  
 **问题**  
  
 如果使用平面文件分析器将平面文件 IDOC 转换为使用该架构的 XML，然后将 XML 转换回通过管道使用的架构的平面文件 IDOC，则两个平面文件 Idoc 不相同。  
  
 **原因**  
  
 当从平面文件 IDOC 生成 XML，平面文件分析器不会生成具有空白值的 XML 节点。 当此 XML 转换回平面文件时，XML 中缺少的节点不会反映在平面文件 IDOC。 因此平面文件 Idoc 不相同。  
  
 **解决方法**  
  
 用于将平面文件转换为 XML，反之亦然，在"发送"接收"节点定义中，在架构中执行以下步骤：  
  
1. 设置**suppress_empty_nodes**属性设置为**false**并设置**generate_empty_nodes**属性设置为**true**。 默认情况下**suppress_empty_nodes**属性设置为**true**并**generate_empty_nodes**属性设置为**false**，和因此所有空节点不会反映在 XML 中。  
  
2. 平面文件可能包含额外回车符结尾。 可以设置**suppress_trailing_delimiters**属性设置为**是**若要避免此额外的回车。 为该属性还公开**取消尾部分隔符**属性，如果您打开中的架构[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]。  
  
##  <a name="BKMK_SAPAction"></a> 使用绑定文件一起创建的物理端口不正确的操作错误  
 **问题**  
  
 在使用后[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]若要生成上的 SAP 系统的特定操作的架构外, 接程序还会创建端口绑定文件。 您可以导入此文件使用绑定[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理控制台，可在 BizTalk Server 中创建物理端口。 但是时将消息发送到 SAP 系统使用此类端口时，, 适配器将无法理解的端口上指定的操作，并提供了类似于以下的错误：  
  
```  
Microsoft.ServiceModel.Channels.Common.UnsupportedOperationException: Incorrect Action   
<BtsActionMapping xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xmlns:xsd="http://www.w3.org/2001/XMLSchema">  
  <Operation Name="<op_name>" Action="<action>" />  
</BtsActionMapping>. Correct the specified Action, or refer to the documentation on the allowed formats for the Actions.  
```  
  
 **原因**  
  
 BizTalk 业务流程中创建逻辑端口时，指定这些端口上操作某些名称，或只需使用默认名称，例如 Operation_1、 Operation_2，等等。但是，在生成的绑定文件[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]，操作名称是与为其生成元数据的操作的名称相同。 例如，如果您为 RFC_CUSTOMER_GET 生成元数据，操作将设置为以下：  
  
```  
<Operation Name="RFC_CUSTOMER_GET" Action="http://Microsoft.LobServices.Sap/2007/03/Rfc/RFC_CUSTOMER_GET" />  
```  
  
 导入绑定文件时，物理端口上设置相同的操作。 因此，逻辑端口 （Operation_1、 Operation_2 等） 上的操作名称与物理端口，从而导致错误的操作中指定的操作名称不匹配。  
  
 **解决方法**  
  
 请确保逻辑端口中的操作名称中的物理端口的操作中指定的操作名称相同。 执行以下操作之一：  
  
-   对为其生成元数据，例如 RFC_CUSTOMER_GET 操作从 Operation_1 等更改 BizTalk 业务流程中的逻辑端口中的操作名称。  
  
-   将物理端口上的操作中的操作名称更改为中的逻辑端口的操作名称。 例如，可以更改为类似于以下的物理端口中的操作：  
  
    ```  
    <Operation Name="Operation_1" Action="http://Microsoft.LobServices.Sap/2007/03/Rfc/RFC_CUSTOMER_GET" />  
    ```  
  
##  <a name="BKMK_SAPTableParams"></a> 响应消息的操作在 SAP 上运行不包含任何表参数  
 **原因**  
  
 如果使用[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]地执行对 SAP 系统的操作返回大量的表，每个表包含大量的记录，那将搜索到 SAP 系统从返回的响应消息的一部分的大型数据集。 因此，默认情况下，[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]不返回任何表参数作为响应消息的一部分。  
  
 **解决方法**  
  
 你可以请求所需的表[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]作为响应一部分返回。 就可以做到的请求消息发送到 SAP 系统的一部分提供一个空表参数。 例如， `<table_parameter_name />`。  
  
##  <a name="BKMK_SAPIncorrectCreds"></a> 适配器客户端不从 SAP 接收响应
 **问题**  
  
 使用与适配器时[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]，如果在 WCF 自定义的凭据将发送端口不正确，不会处理请求消息。 指定正确的凭据后，将消息发送到 SAP 系统，并收到的响应。 但是，响应消息不是输出连接到可用的。  
  
 **解决方法**  
  
 重新启动 BizTalk 主机实例。  
  
##  <a name="BKMK_SAPInboundConn"></a> 接收来自 SAP 服务器的入站的消息的连接问题  
 **问题**  
  
 获取仅在接收来自使用 WCF 自定义在 SAP 服务器的入站的消息的接收端口时出现以下错误[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]。  
  
```  
The Messaging Engine failed to add a receive location "<location_name>" with URL "<connection URI>" to the adapter "WCF-Custom".  
Reason: "Microsoft.Adapters.SAP.RFCException: Details: ErrorCode=RFC_OK. ErrorGroup=RFC_ERROR_COMMUNICATION. SapErrorMessage=Connect to SAP gateway failed  
Connect_PM  TPNAME=<name>, GWHOST=<host>, GWSERV=<server>  
```  
  
 但是，你将能够成功地将消息发送到 SAP 系统使用 Wcf-custom 发送端口。  
  
 **解决方法**  
  
 在其中运行适配器客户端，并且在尝试再次接收的入站的消息的同一计算机上安装 SAP GUI。 有关如何安装 SAP GUI 的详细信息，请参阅 SAP 文档。  
  
##  <a name="BKMK_SAPRootNode"></a> 使用 BizTalk 项目中的 RootNode TypeName 错误  
 **问题**  
  
 中的 BizTalk 项目中[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]，则从架构生成[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]包含无效的字符或保留的字**RootNode TypeName**属性，编译项目时将发生以下错误:  
  
```  
Node <node reference> - Specify a valid .NET type name for this root node.  
The current .NET type name of this root node is invalid (it is a reserved BizTalk Keyword or is an invalid C# identifier).  
```  
  
 **解决方法**  
  
1.  右键单击该错误，然后选择中引用的 rood 这样节点**属性**。  
  
2.  有关**RootNode TypeName**属性，删除任何非法字符或保留字，例如，点 （.）。  
  
##  <a name="BKMK_SAPVS2008"></a> 无效的绑定时出现的警告在 Visual Studio 中使用适配器  
 **问题**  
  
 当适配器用于在 Visual Studio 中创建应用程序并打开由适配器生成的配置文件 (app.config) 时，您会看到类似于下面的警告：  
  
```  
The element 'bindings' has invalid child element 'sapBinding'. List of possible elements expected: 'basicHttpBinding, customBinding, ...  
```  
  
 **原因**  
  
 会出现此警告[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]绑定， `sapBinding`，不标准绑定随附于[!INCLUDE[firstref_btsWinCommFoundation](../../includes/firstref-btswincommfoundation-md.md)]。  
  
 **解决方法**  
  
 可以安全地忽略此警告。  
  
##  <a name="BKMK_SAPSimilarSchema"></a> 在 BizTalk Server 中的 XLANG 异常
 **问题**  
  
 BizTalk Server 将引发异常，表明该应用程序找不到文档规范，因为多个架构匹配的消息类型或 XLANG 异常。  
  
 **原因**  
  
 由于以下任一发生这种情况：  
  
- 已生成多个架构在 BizTalk Server 项目中，一个泛型操作 （例如 SendIdoc 和 ReceiveIdoc） 部署到 BizTalk Server 应用程序，然后运行应用程序来执行 SAP 系统上的相应操作。 架构是公用的因为冲突之间没有 BizTalk Server 应用程序中部署的架构。  
  
- 如果多个项目，您为每个 BizTalk Server 项目生成泛型操作架构，部署到单独的同一个 BizTalk Server 应用程序托管，，然后运行应用程序或应用程序即可执行相应的每个项目对 SAP 系统的操作。 因为架构和程序集都是可访问 BizTalk Server 中的应用程序，则冲突之间常见的架构部署在各种 BizTalk Server 应用程序和程序集。  
  
  **解决方法**  
  
  BizTalk Server 应用程序使用单个泛型操作架构文件。 如果需要在同一主机上的多个 BizTalk Server 应用程序中使用泛型操作架构，创建包含单个泛型操作架构的应用程序，然后使用 BizTalk Server 中的所有其他应用程序中的泛型操作架构。  
  
## <a name="see-also"></a>请参阅  
[SAP 适配器疑难解答](../../adapters-and-accelerators/adapter-sap/troubleshoot-the-sap-adapter.md)