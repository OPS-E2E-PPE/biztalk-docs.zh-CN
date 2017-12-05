---
title: "使用 BizTalk 中的 Siebel 适配器进行的操作问题故障排除 |Microsoft 文档"
description: "常见的问题和解决方法为 Siebel 适配器 BizTalk 适配器包 (BAP) 中"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 74d152d9-9893-4f93-894a-350bae8be7bd
caps.latest.revision: "22"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 1ff6e36afd7cecc967069fd3ecf5414c6afdb014
ms.sourcegitcommit: 3fc338e52d5dbca2c3ea1685a2faafc7582fe23a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/01/2017
---
# <a name="troubleshoot-operational-issues-with-the-siebel-adapter"></a>与 Siebel 适配器排除操作问题
本部分提供有关操作问题的信息使用时可能遇到的一个集中的位置[!INCLUDE[adaptersiebel](../../includes/adaptersiebel-md.md)]。  
  
## <a name="enabling-tracing"></a>启用跟踪  
 有关跟踪中的支持信息[!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]，请参阅[诊断跟踪和消息日志记录为 Siebel 适配器](../../adapters-and-accelerators/adapter-siebel/diagnostic-tracing-and-message-logging-for-the-siebel-adapter.md)。  
  
## <a name="known-issues"></a>已知问题  
 以下是一些问题和建议的解决方案使用时，你可能会遇到[!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]。  
  
  
###  <a name="BKMK_SiebelBindingError"></a>在加载适配器绑定错误  
 **问题**  
  
 当你尝试启动[!INCLUDE[addadapterservreflong](../../includes/addadapterservreflong-md.md)]或[!INCLUDE[consumeadapterservlong](../../includes/consumeadapterservlong-md.md)]，GUI 将报告以下错误：  
  
```  
There was an error loading the binding, <binding name>, from your system configuration.  
ConfigurationErrorsException: Exception has been thrown by the target of an invocation.  
```  
  
 **可能的原因**  
  
 当你启动[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]或[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]，WCF 加载所有已安装适配器的适配器绑定。 反过来，适配器绑定都依赖于特定的企业应用程序客户端软件。 因此，您会受到此问题的一个或两个原因如下：  
  
-   在安装适配器的计算机上未安装所需的 LOB 客户端软件。  
  
-   未将适配器安装中的所有适配器的"典型"或"完成"安装[!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)]。 但是，可能只有一个企业应用程序安装的客户端库。 因此，GUI 无法加载其他适配器的绑定。  
  
 **解决方法**  
  
-   请确保在你安装的计算机上安装了必需的客户端版本[!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)]。  
  
-   请确保执行适配器安装需要适配器的自定义安装。  
  
###  <a name="BKMK_SiebelDispAdap"></a>Siebel 适配器不会显示在列表中在 BizTalk Server 管理控制台中的适配器  
 **问题**  
  
 与不同的是较早版本附带的适配器[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]、[!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]所附带[!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)]未显示在列表中的 BizTalk Server 管理控制台中的适配器。  
  
 **可能的原因**  
  
 最新[!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]是 WCF 自定义绑定。 因此，尽管[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理控制台显示[!INCLUDE[wcfadapter_short](../../includes/wcfadapter-short-md.md)]，它不会显示 WCF 自定义绑定，并因此，不会显示基于 WCF 的[!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]。  
  
 **解决方法**  
  
 你可以显式添加[!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]到[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理控制台中所述的步骤[将 Siebel 适配器添加到 BizTalk Server 管理控制台](../../adapters-and-accelerators/adapter-siebel/add-the-siebel-adapter-to-biztalk-server-administration-console.md)。  
  
###  <a name="BKMK_SiebelConnecting"></a>连接到 Siebel 系统时出错  
 **问题**  
  
 [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]或[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]当你尝试连接到 Siebel 系统时将报告以下错误：  
  
```  
Connecting to the system LOB has failed. Retrieving the COM class factory for component with CLSID {ID} failed due to the following error: 80040154  
```  
  
 **可能的原因**  
  
 计算机上可能未安装 Siebel Web 客户端。  
  
 **解决方法**  
  
 请确保在计算机上安装 Siebel Web 客户端的受支持的版本。 请参阅安装指南以支持的客户端和的 Siebel server 版本。 安装指南位于\<系统驱动器\>: files\microsoft [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)]\Documents。  
  
###  <a name="BKMK_SiebelXMLRetrieve"></a>具有多个 65536 节点检索 Xml 时的错误  
 **问题**  
  
 适配器将检索具有多个 65536 节点的 XML 输出时报告以下错误。  
  
```  
Maximum number of items that can be serialized or deserialized in an object graph is '65536'.  
Change the object graph or increase the MaxItemsInObjectGraph quota.  
```  
  
 **可能的原因**  
  
 适配器不能序列化和反序列化具有多个 65536 的项的对象。  
  
 **解决方法**  
  
 可以通过设置来解决此问题`maxItemsInObjectGraph`参数。 可在任何以下两种方式将其设置：  
  
-   将此参数设置通过更改`maxItemsInObjectGraph`中的参数`ServiceBehavior`服务类中的属性。  
  
-   将以下代码添加到你的应用程序的 app.config 文件。  
  
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
  
###  <a name="BKMK_SiebelConnURI"></a>在 BizTalk 中指定的 WCF 自定义端口的连接 URI 时出错  
 **问题**  
  
 [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]指定连接 URI 以连接到 Siebel 系统时，则报告以下错误。  
  
```  
Error saving properties.  
(System.ArgumentException) The specified address is invalid.  
(System.ArgumentException) Invalid address;  
"<connection URI>" is not a well-formed absolute uri.  
```  
  
 **可能的原因**  
  
 连接 URI 不符合标准的编码格式。 例如，参数的值可能包含一个空格。  
  
 **解决方法**  
  
 请确保你指定的 URI 符合标准的编码格式的连接。 例如，必须通过"%20"替换为空格。  
  
###  <a name="BKMK_SiebelPerfOps"></a>执行 Siebel 系统上的操作时出错  
 **问题**  
  
 适配器执行针对 Siebel 系统使用的任何操作时将报告以下错误[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]。  
  
-   **BizTalk server**  
  
    ```  
    System.ArgumentNullException: Value cannot be null.  
    ```  
  
 **可能的原因**  
  
 未指定消息的 WCF 操作。 WCF 需要为每个操作，在 LOB 应用程序上执行的操作会告知适配器指定的 SOAP 操作。  
  
 **解决方法**  
  
 指定的 SOAP 操作中发送端口或 BizTalk 业务流程中的消息上下文属性。 有关说明，请参阅[配置用于 Siebel 的 SOAP 操作](../../adapters-and-accelerators/adapter-siebel/configure-the-soap-action-for-siebel.md)。 请参阅[消息和消息架构](messages-and-message-schemas-for-siebel-adapter-in-biztalk.md)有关每个操作的操作的列表。  
  
###  <a name="BKMK_SiebelXmlParsing"></a>由于指定的操作中的不正确的操作名称 XmlReaderParsingException  
 **问题**  
  
 将消息发送到 Siebel 系统时，BizTalk Server 管理控制台提供了以下错误：  
  
```  
Microsoft.ServiceModel.Channels.Common.XmlReaderParsingException: Invalid argument:  
<BtsActionMapping xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xmlns:xsd="http://www.w3.org/2001/XMLSchema">  
  <Operation Name="<operation_name>" Action="<action>" />  
</BtsActionMapping>  
```  
  
 **可能的原因**  
  
 如果通过导入创建的端口绑定文件中配置 WCF 自定义端口[!INCLUDE[consumeadapterservlong](../../includes/consumeadapterservlong-md.md)]，采用以下格式指定端口中的操作：  
  
```  
<BtsActionMapping>  
  <Operation Name="Op1" Action="http://MyService/Svc/Op1" />  
</BtsActionMapping>  
```  
  
 在前面的格式中，操作名称受生成架构时选择该操作。 例如，如果你生成 Siebel 在业务组件上的查询操作的架构，则操作中的操作名称将"查询"。 但是中的逻辑端口的操作名称创建在 BizTalk 业务流程中[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]可能不同。  
  
 **解决方法**  
  
 请确保操作名称在这两个逻辑端口 (在 BizTalk 业务流程中[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]) 和 （在 BizTalk Server 管理控制台） 的物理端口相同。  
  
###  <a name="BKMK_SiebelTerminate"></a>使用在 Siebel 适配器的应用程序不会终止  
 **问题**  
  
 使用的应用程序[!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]与 Siebel 7.5 版客户端不会终止。  
  
 **可能的原因**  
  
 这是因为 Siebel 客户端问题其中过程不会终止时从 Siebel 服务器注销。  
  
 **解决方法**  
  
 请确保你具有 7.5.3.17 为 Siebel 服务器，以及快速修复 QF0H05 安装的修补程序。  
  
###  <a name="BKMK_SiebelHang"></a>Siebel 服务器重新启动，则可能会挂起 Siebel 适配器  
 **问题**  
  
 如果 Siebel 服务器重新启动时[!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]将消息发送到使用 Siebel 服务器，[!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]可能会挂起。  
  
 **解决方法**  
  
 重新启动 BizTalk 应用程序主机实例。 若要这样做从[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理控制台中的，在控制台树中展开**BizTalk 组**，展开**平台设置**，然后单击**主机实例**。 从右窗格中，右键单击主机名称，然后选择**重新启动**。  
  
###  <a name="BKMK_SiebelAction"></a>适配器无法识别的物理端口上的操作，即使使用适配器服务外接程序生成的绑定文件用于创建端口  
 **问题**  
  
 在使用后[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]若要生成 Siebel 系统上的特定操作的架构外, 接程序还会创建端口绑定文件。 可以导入此文件使用绑定的[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]BizTalk Server 中创建的物理端口的管理控制台。 但是，当消息发送到 Siebel 系统使用此类端口时，该适配器将无法了解在端口上指定的操作，并提供了类似于以下错误：  
  
```  
Microsoft.ServiceModel.Channels.Common.UnsupportedOperationException: Incorrect Action   
<BtsActionMapping xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xmlns:xsd="http://www.w3.org/2001/XMLSchema">  
  <Operation Name="<op_name>" Action="<action>" />  
</BtsActionMapping>. Correct the specified Action, or refer to the documentation on the allowed formats for the Actions.  
```  
  
 **可能的原因**  
  
 在创建逻辑端口 BizTalk 业务流程中时，指定这些端口上的操作的某些名称，或只需使用如 Operation_1、 Operation_2 等的默认名称。但是，在生成的绑定文件[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]，操作名称是为其生成元数据操作的名称相同。 例如，如果你生成帐户在业务组件上的插入操作的元数据，操作将设置为以下：  
  
```  
<Operation Name="Insert" Action="http://Microsoft.LobServices.Siebel/2007/03/BusinessObjects/Account/Account/Insert" />  
```  
  
 当你导入的绑定文件时，物理端口设置相同的操作。 因此，逻辑端口 （Operation_1、 Operation_2 等） 上的操作名称与上的物理端口，从而导致错误的操作中指定的操作名称不匹配。  
  
 **解决方法**  
  
 请确保逻辑端口中的操作名称指定为中的物理端口的操作的一部分的操作名称相同。 执行以下操作之一：  
  
-   对为其生成元数据，例如插入操作从 Operation_1 等更改 BizTalk 业务流程中的逻辑端口中的操作名称。  
  
-   将中的物理端口上的操作的操作名称更改为中的逻辑端口的操作名称。 例如，你无法更改中类似于下面的物理端口的操作：  
  
    ```  
    <Operation Name="Operation_1" Action="http://Microsoft.LobServices.Siebel/2007/03/BusinessObjects/Account/Account/Insert" />  
    ```  
  
###  <a name="BKMK_SiebelXMLEncode"></a>Siebel 适配器不处理使用名称中的 XML 编码字符串的 Siebel 对象  
 **问题**  
  
 [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]无法执行涉及其名称中包含编码的 XML 字符串的 Siebel 对象 （业务对象、 业务组件、 业务服务、 选择列表、 方法、 字段、 自变量、 等） 的操作。 例如，[!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]将不能调用具有名称 Time_x0020_Stamp 的业务服务方法。  
  
 **解决方法**  
  
 请确保 Siebel 对象不包含其名称中编码的 XML 字符串。  
  
###  <a name="BKMK_SiebelRootNode"></a>与 RootNode TypeName BizTalk 项目中的错误  
 **问题**  
  
 在 BizTalk 项目中[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]，如果从架构生成[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]包含无效字符或保留的字**RootNode TypeName**属性，编译项目时将出现以下错误:  
  
```  
Node <node reference> - Specify a valid .NET type name for this root node.  
The current .NET type name of this root node is invalid (it is a reserved BizTalk Keyword or is an invalid C# identifier).  
```  
  
 **解决方法**  
  
1.  右键单击该错误并选择中引用的 rood 节点**属性**。  
  
2.  有关**RootNode TypeName**属性，删除任何非法字符或保留字，例如，圆点 （.）。  
  
###  <a name="BKMK_SiebelVS2008"></a>使用 Visual Studio 中的适配器时出现的无效的绑定警告  
 **问题**  
  
 当你使用该适配器在 Visual Studio 中创建应用程序并打开生成的适配器的配置文件 (app.config) 时，你将看到类似于以下警告：  
  
```  
The element 'bindings' has invalid child element 'siebelBinding'. List of possible elements expected: 'basicHttpBinding, customBinding, ...  
```  
  
 **可能的原因**  
  
 由于会出现此警告[!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]绑定， `siebelBinding`，不标准绑定随[!INCLUDE[firstref_btsWinCommFoundation](../../includes/firstref-btswincommfoundation-md.md)]。  
  
 **解决方法**  
  
 可以安全地忽略此警告。  
  
## <a name="see-also"></a>另请参阅  
[解决在 Siebel 适配器](../../adapters-and-accelerators/adapter-siebel/troubleshoot-the-siebel-adapter.md)