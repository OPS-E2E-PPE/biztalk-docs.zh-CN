---
title: 使用 Siebel 适配器在 BizTalk 中进行的操作问题故障排除 |Microsoft Docs
description: 常见的问题和 Siebel 适配器的 BizTalk 适配器包 (BAP) 中的解决方法
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 74d152d9-9893-4f93-894a-350bae8be7bd
caps.latest.revision: 22
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 5d17e325465ce5aa575a6d499aa6b8bf73e07696
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36978934"
---
# <a name="troubleshoot-operational-issues-with-the-siebel-adapter"></a>使用 Siebel 适配器进行的操作问题故障排除
本部分提供有关操作问题的信息使用时可能遇到的一个集中的位置[!INCLUDE[adaptersiebel](../../includes/adaptersiebel-md.md)]。  
  
## <a name="enabling-tracing"></a>启用跟踪  
 有关跟踪中的支持信息[!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]，请参阅[诊断跟踪和消息日志记录 Siebel 适配器的](../../adapters-and-accelerators/adapter-siebel/diagnostic-tracing-and-message-logging-for-the-siebel-adapter.md)。  
  
## <a name="known-issues"></a>已知问题  
 以下是一些问题和建议的解决方案使用时可能遇到[!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]。  
  
  
###  <a name="BKMK_SiebelBindingError"></a> 加载适配器绑定时出错  
 **问题**  
  
 当您尝试启动[!INCLUDE[addadapterservreflong](../../includes/addadapterservreflong-md.md)]或[!INCLUDE[consumeadapterservlong](../../includes/consumeadapterservlong-md.md)]，GUI 将报告以下错误：  
  
```  
There was an error loading the binding, <binding name>, from your system configuration.  
ConfigurationErrorsException: Exception has been thrown by the target of an invocation.  
```  
  
 **原因**  
  
 当您启动[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]或[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]，WCF 将加载所有已安装的适配器的适配器绑定。 反过来，适配器绑定都依赖于特定企业应用程序客户端软件。 因此，可能会遇到此问题的一个或两个原因如下：  
  
- 在安装该适配器的计算机上未安装所需的 LOB 客户端软件。  
  
- 未将适配器安装中的所有适配器的"典型"或"完全"安装[!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)]。 但是，可能只有一个企业应用程序安装的客户端库。 因此，在 GUI 无法加载其他适配器的绑定。  
  
  **解决方法**  
  
- 请确保在您安装的计算机上安装了必需的客户端版本[!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)]。  
  
- 请确保执行要安装仅需要的适配器的适配器的自定义安装。  
  
###  <a name="BKMK_SiebelDispAdap"></a> Siebel 适配器不会显示在 BizTalk Server 管理控制台中的适配器列表中  
 **问题**  
  
 与早期版本附带的适配器的不同[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]，则[!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]附带[!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)]未显示在 BizTalk Server 管理控制台中的适配器列表中。  
  
 **原因**  
  
 最新[!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]是 WCF 自定义绑定。 因此，尽管[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理控制台中显示[!INCLUDE[wcfadapter_short](../../includes/wcfadapter-short-md.md)]，它不会显示 WCF 自定义绑定，因此，不会显示基于 WCF 的[!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]。  
  
 **解决方法**  
  
 您可以显式添加[!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]到[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理控制台中所述的步骤[将 Siebel 适配器添加到 BizTalk Server 管理控制台](../../adapters-and-accelerators/adapter-siebel/add-the-siebel-adapter-to-biztalk-server-administration-console.md)。  
  
###  <a name="BKMK_SiebelConnecting"></a> 连接到 Siebel 系统时出错  
 **问题**  
  
 [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]或[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]时尝试连接到 Siebel 系统时出现以下错误：  
  
```  
Connecting to the system LOB has failed. Retrieving the COM class factory for component with CLSID {ID} failed due to the following error: 80040154  
```  
  
 **原因**  
  
 不可能在计算机上安装 Siebel Web 客户端。  
  
 **解决方法**  
  
 请确保在计算机上安装的 Siebel Web 客户端的受支持的版本。 请参阅支持的客户端的安装指南和用于 Siebel 的服务器版本。 安装指南位于\<系统驱动器\>: \Program Files\Microsoft [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)]\Documents。  
  
###  <a name="BKMK_SiebelXMLRetrieve"></a> 具有多个 65536 节点检索 Xml 时出错  
 **问题**  
  
 检索具有超过 65536 节点的 XML 输出时，适配器将报告以下错误。  
  
```  
Maximum number of items that can be serialized or deserialized in an object graph is '65536'.  
Change the object graph or increase the MaxItemsInObjectGraph quota.  
```  
  
 **原因**  
  
 适配器不能序列化和反序列化具有多个 65536 的项的对象。  
  
 **解决方法**  
  
 可以通过设置来解决此问题`maxItemsInObjectGraph`参数。 可以在任何以下两种方式设置此：  
  
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
  
  示例 app.config 将如下所示：  
  
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
      <endpoint   behaviorConfiguration="NewBehavior" binding="siebelBinding"  
       contract="IOutboundContract" name="siebel_ICalculator" />  
    </client>  
  </system.serviceModel>  
</configuration>  
```  
  
###  <a name="BKMK_SiebelConnURI"></a> 在 BizTalk 中指定的 WCF 自定义端口的连接 URI 时出错  
 **问题**  
  
 [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] 在指定连接 URI 连接到 Siebel 系统时出现以下错误。  
  
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
  
###  <a name="BKMK_SiebelPerfOps"></a> Siebel 系统上执行操作时出错  
 **问题**  
  
 执行对 Siebel 系统使用的任何操作时，适配器将报告以下错误[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]。  
  
- **为 BizTalk Server**  
  
  ```  
  System.ArgumentNullException: Value cannot be null.  
  ```  
  
  **原因**  
  
  未指定消息的 WCF 操作。 WCF 需要用于为每个操作，向适配器通知上的 LOB 应用程序执行的操作指定的 SOAP 操作。  
  
  **解决方法**  
  
  在发送端口或为 BizTalk 业务流程的消息上下文属性指定的 SOAP 操作。 有关说明，请参阅[配置用于 Siebel 的 SOAP 操作](../../adapters-and-accelerators/adapter-siebel/configure-the-soap-action-for-siebel.md)。 请参阅[消息和消息架构](messages-and-message-schemas-for-siebel-adapter-in-biztalk.md)有关每个操作的操作的列表。  
  
###  <a name="BKMK_SiebelXmlParsing"></a> 由于指定的操作中的不正确的操作名称 XmlReaderParsingException  
 **问题**  
  
 将消息发送到 Siebel 系统时，BizTalk Server 管理控制台将报告以下错误：  
  
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
  
 在前面的格式，操作名称受生成架构时选择该操作。 例如，如果生成一个 Siebel 业务组件上的查询操作的架构，则操作中的操作名称将是"查询"。 但是中的逻辑端口的操作名称创建在 BizTalk 业务流程中[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]可能不同。  
  
 **解决方法**  
  
 请确保操作名称的两个逻辑端口 (在 BizTalk 业务流程中[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]) 和 （在 BizTalk Server 管理控制台） 的物理端口相同。  
  
###  <a name="BKMK_SiebelTerminate"></a> 使用 Siebel 适配器的应用程序不会终止  
 **问题**  
  
 使用的应用程序[!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]与 Siebel 7.5 版客户端不会终止。  
  
 **原因**  
  
 这是因为 Siebel 客户端问题的过程不会终止时从 Siebel 服务器注销。  
  
 **解决方法**  
  
 请确保你已 7.5.3.17 Siebel 服务器，以及快速修复 QF0H05 安装了修补程序。  
  
###  <a name="BKMK_SiebelHang"></a> Siebel 服务器重新启动，则可能会挂起 Siebel 适配器  
 **问题**  
  
 如果 Siebel 服务器将重启时[!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]将一条消息发送到 Siebel 服务器使用，[!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]可能会挂起。  
  
 **解决方法**  
  
 重新启动 BizTalk 应用程序主机实例。 若要执行此操作从[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理控制台中的，在控制台树中展开**BizTalk 组**，展开**平台设置**，然后单击**主机实例**。 从右窗格中，右键单击主机名称，然后选择**重新启动**。  
  
###  <a name="BKMK_SiebelAction"></a> 适配器不识别物理端口上的操作，即使由使用适配器服务加载项生成的绑定文件用于创建端口  
 **问题**  
  
 在使用后[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]若要生成上的 Siebel 系统的特定操作的架构外, 接程序还会创建端口绑定文件。 您可以导入此文件使用绑定[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理控制台，可在 BizTalk Server 中创建物理端口。 但是时将消息发送到 Siebel 系统使用此类端口时，, 适配器将无法理解的端口上指定的操作，并提供了类似于以下的错误：  
  
```  
Microsoft.ServiceModel.Channels.Common.UnsupportedOperationException: Incorrect Action   
<BtsActionMapping xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xmlns:xsd="http://www.w3.org/2001/XMLSchema">  
  <Operation Name="<op_name>" Action="<action>" />  
</BtsActionMapping>. Correct the specified Action, or refer to the documentation on the allowed formats for the Actions.  
```  
  
 **原因**  
  
 BizTalk 业务流程中创建逻辑端口时，指定这些端口上操作某些名称，或只需使用默认名称，例如 Operation_1、 Operation_2，等等。但是，在生成的绑定文件[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]，操作名称是与为其生成元数据的操作的名称相同。 例如，如果您生成帐户业务组件上的插入操作的元数据，操作将设置为以下：  
  
```  
<Operation Name="Insert" Action="http://Microsoft.LobServices.Siebel/2007/03/BusinessObjects/Account/Account/Insert" />  
```  
  
 导入绑定文件时，物理端口上设置相同的操作。 因此，逻辑端口 （Operation_1、 Operation_2 等） 上的操作名称与物理端口，从而导致错误的操作中指定的操作名称不匹配。  
  
 **解决方法**  
  
 请确保逻辑端口中的操作名称中的物理端口的操作中指定的操作名称相同。 执行以下操作之一：  
  
-   对为其生成元数据，例如 Insert 操作从 Operation_1 等更改 BizTalk 业务流程中的逻辑端口中的操作名称。  
  
-   将物理端口上的操作中的操作名称更改为中的逻辑端口的操作名称。 例如，可以更改为类似于以下的物理端口中的操作：  
  
    ```  
    <Operation Name="Operation_1" Action="http://Microsoft.LobServices.Siebel/2007/03/BusinessObjects/Account/Account/Insert" />  
    ```  
  
###  <a name="BKMK_SiebelXMLEncode"></a> Siebel 适配器不会处理与在名称中编码的 XML 字符串的 Siebel 对象  
 **问题**  
  
 [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]无法执行涉及 Siebel 对象 （业务对象、 业务组件、 业务服务、 选择列表、 方法、 字段、 参数等） 的名称中包含编码的 XML 字符串的操作。 例如，[!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]将不能调用具有名称 Time_x0020_Stamp 的业务服务方法。  
  
 **解决方法**  
  
 请确保 Siebel 对象不包含其名称中编码的 XML 字符串。  
  
###  <a name="BKMK_SiebelRootNode"></a> 使用 BizTalk 项目中的 RootNode TypeName 错误  
 **问题**  
  
 中的 BizTalk 项目中[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]，则从架构生成[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]包含无效的字符或保留的字**RootNode TypeName**属性，编译项目时将发生以下错误:  
  
```  
Node <node reference> - Specify a valid .NET type name for this root node.  
The current .NET type name of this root node is invalid (it is a reserved BizTalk Keyword or is an invalid C# identifier).  
```  
  
 **解决方法**  
  
1.  右键单击该错误，然后选择中引用的 rood 这样节点**属性**。  
  
2.  有关**RootNode TypeName**属性，删除任何非法字符或保留字，例如，点 （.）。  
  
###  <a name="BKMK_SiebelVS2008"></a> 无效的绑定时出现的警告在 Visual Studio 中使用适配器  
 **问题**  
  
 当适配器用于在 Visual Studio 中创建应用程序并打开由适配器生成的配置文件 (app.config) 时，您会看到类似于下面的警告：  
  
```  
The element 'bindings' has invalid child element 'siebelBinding'. List of possible elements expected: 'basicHttpBinding, customBinding, ...  
```  
  
 **原因**  
  
 会出现此警告[!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]绑定， `siebelBinding`，不标准绑定随附于[!INCLUDE[firstref_btsWinCommFoundation](../../includes/firstref-btswincommfoundation-md.md)]。  
  
 **解决方法**  
  
 可以安全地忽略此警告。  
  
## <a name="see-also"></a>请参阅  
[Siebel 适配器疑难解答](../../adapters-and-accelerators/adapter-siebel/troubleshoot-the-siebel-adapter.md)