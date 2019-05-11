---
title: 注册适配器 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: bc85b96e-7b7b-4131-88ec-87b419a61bc2
caps.latest.revision: 18
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 14a758ff842531c6b4851e94b7fd06d5174cd550
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65398007"
---
# <a name="registering-an-adapter"></a>注册适配器
如果你正在开发的自定义适配器，您可以通过修改和运行在软件开发工具包 (SDK) 中的示例文件适配器附带的注册表文件之一与 BizTalk Server 注册它。 或者，可以使用适配器注册向导来创建注册表文件。 此向导位于[!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]Utilities\AdapterRegistryWizard 文件夹。  
  
> [!IMPORTANT]
> - 在 32 位计算机上，必须从命令提示符运行适配器注册向导生成的注册表 (.reg) 文件。  
>   -   在 64 位计算机上，通过适配器注册向导生成的注册表 (.reg) 文件必须运行同时从 32 位和 64 位命令提示符。  
  
 创建注册表项后，可以添加适配器，BizTalk Server 管理控制台中或以编程方式使用 Windows Management Instrumentation (WMI) 方法。 本主题讨论各个注册表条目，然后向您显示在何处以及如何为自定义适配器修改现有注册表文件。  
  
 有关使用适配器注册向导的说明，请参阅[适配器注册向导](../core/adapter-registry-wizard.md)。 有关修改 SDK 中包含的示例注册表文件的说明，请参阅[适配器注册文件](../core/adapter-registration-file.md)。  
  
## <a name="registry-keys"></a>注册表项  
 您需要创建以下注册表项来部署适配器：  
  
 **注册表项位置**  
  
```  
[HKEY_CLASSES_ROOT\CLSID\{%uuid of custom transport%}\BizTalk]  
@="BizTalk"  
  
```  
  
 **类型名称**  
  
 适配器类型名称标识 BizTalk Server 计算机中适配器的类型。 此项是必需的任何适配器。  
  
```  
"TransportType"="MyTransportAdapter"  
  
```  
  
 **约束**  
  
 适配器约束定义适配器的功能。  
  
 为每个适配器需要此密钥。 根据所创建的适配器的类型，您可能想要修改的约束的位掩码值。  
  
```  
"Constraints"=dword:00003C0b  
```  
  
 描述适配器功能的值可以是下表中所示的值的组合。  
  
|ReplTest1|十六进制值|标志|Description|  
|-----------|---------------|----------|-----------------|  
|1|0x0001|eProtocolSupportsReceive|适配器支持接收操作。|  
|2|0x0002|eProtocolSupportsTransmit|适配器支持发送操作。|  
|8|0x0008|eProtocolReceiveIsCreatable|接收适配器的处理程序承载进程内。|  
|128|0x0080|eProtocolSupportsRequestResponse|适配器支持请求-响应操作。|  
|256|0x0100|eProtocolSupportsSolicitResponse|适配器支持要求-响应操作。|  
|1024|0x4000|eOutboundProtocolRequiresContextInitialization|指示适配器发送处理程序配置为使用适配器框架用户界面。|  
|2048|0x0800|eInboundProtocolRequiresContextInitialization|指示适配器将使用适配器框架用户界面进行接收处理程序配置。|  
|4096|0x1000|eReceiveLocationRequiresContextInitialization|指示适配器使用适配器框架用户界面进行接收位置配置。|  
|8192|0x2000|eTransmitLocationRequiresContextInitialization|指示适配器使用适配器框架用户界面进行发送端口配置。|  
|16384|0x4000|eSupportsOrderedDelivery|指示适配器支持按序的送达消息。|  
|32768|0x8000|eInitTransmitterOnServiceStart|发送适配器启动时将发送第一条消息，而不是启动服务时。|  
|65536|0x10000|eSupport32BitOnly|指示适配器支持仅在 32 位主机中运行。|  
  
### <a name="namespace"></a>命名空间  
 每个适配器必须定义其属性的命名空间。 BizTalk Server 此命名空间下的消息上下文上存储特定于适配器的属性。 此属性是必需的所有适配器。  
  
```  
"PropertyNameSpace"="namespace"  
```  
  
### <a name="aliases"></a>Aliases  
 每个适配器都可以具有一组的唯一地标识 BizTalk Server 中的适配器类型的前缀。 通过动态发送端口发送消息时，这允许正确的传输类型的解决方法。 适配器需要在注册时指定其前缀列表。  
  
```  
"AliasesXML"="<AdapterAliasList><AdapterAlias>sample://</AdapterAlias></AdapterAliasList>"  
```  
  
### <a name="configuration-property-pages"></a>配置属性页  
 适配器必须具有配置属性页来配置其接收位置和发送端口。 每个适配器通过指定其相应类 Id 注册其属性页。  
  
```  
"InboundProtocol_PageProv"="{%CLSID for inbound protocol prop page%}"  
"OutboundProtocol_PageProv"="{%CLSID for outbound protocol prop page%}"  
"ReceiveLocation_PageProv"="{%CLSID for receive location prop page%}"  
"TransmitLocation_PageProv"="{%CLSID for transmit location prop page%}"  
```  
  
 如果适配器使用适配器框架用户界面生成属性页，它必须指定以下值的注册表项：  
  
```  
"InboundProtocol_PageProv"="{2DE93EE6-CB01-4007-93E9-C3D71689A281}"  
"OutboundProtocol_PageProv"="{2DE93EE6-CB01-4007-93E9-C3D71689A283}"  
"ReceiveLocation_PageProv"="{2DE93EE6-CB01-4007-93E9-C3D71689A280}"  
"TransmitLocation_PageProv"="{2DE93EE6-CB01-4007-93E9-C3D71689A282}"  
```  
  
 请注意，如果不需要的终结点之一 （该适配器是发送或仅接收），可以从注册表中删除未使用的注册表项。  
  
### <a name="runtime-component-registration"></a>运行时组件注册  
 适配器注册通过指定其类 Id （对于 COM 和.NET） 及其运行时组件类型名称和程序集路径 （适用于.NET) 接收和发送运行时组件。  
  
> [!NOTE]
>  所有**OutboundEngineCLSID**并**InboundEngineCLSID**必须是唯一的密钥。 在数据库中，单个行的**OutboundEngineCLSID**并**InboundEngineCLSID**可能相同。  
  
```  
"OutboundEngineCLSID"="{%CLSID of outbound transport%}"  
"InboundEngineCLSID"="{%CLSID of inbound transport%}"  
"InboundTypeName"="BizTalk.Samples.Adapters.MyReceiver"  
"OutboundTypeName"="BizTalk.Samples.Adapters.MyTransmitter"  
"InboundAssemblyPath"="C:\Program Files\MyTransport.dll"  
"OutboundAssemblyPath"="C:\Program Files\MyTransport.dll"  
```  
  
> [!NOTE]
>  可以将适配器的程序集安装到全局程序集缓存，并在注册表文件中引用它。  
  
### <a name="registration-of-adapter-properties-for-sso-configuration-store"></a>用于 SSO 配置存储的适配器属性的注册  
 适配器需要向 BizTalk Server SSO 数据库可以存储和检索的属性在设计时和运行时注册其属性。  
  
```  
ReceiveHandlerPropertiesXML  
ReceiveLocationPropertiesXML  
SendHandlerPropertiesXML  
SendLocationPropertiesXML  
```  
  
 这些值包含相应的适配器，可以存储在配置存储区中与相关的实体的允许属性定义 （架构）。 作为 XML 字符串反序列化的属性包，其中包含属性类型，但不包含值保持这些定义。 属性元素的非空值意味着该属性被屏蔽。 （被屏蔽的意味着该是只写的不是由安全存储区 API 在管理模式下调用时返回; 安全存储区 API 为此类属性返回 VT_NULL。）  
  
### <a name="example"></a>示例  
 HTTP 适配器通过定义来注册其属性进行 HTTP 发送端口**SendLocationPropertiesXML**具有以下值的注册表项：  
  
```  
<CustomProps><Username vt="8"/><Password vt="8">Encrypted</Password><Certificate vt="8"/><RequestTimeout vt="3"/><MaxRedirects vt="3"/><ContentType vt="8"/><UseProxy vt="11"/><ProxyName vt="8"/><ProxyPort vt="3"/><ProxyUsername vt="8"/><ProxyPassword vt="8">Encrypted</ProxyPassword><UseHandlerSetting vt="11"/><AuthenticationScheme vt="8"/><UseSSO vt="11"/><AffiliateApplicationName vt="8"/></CustomProps>  
```  
  
### <a name="registration-of-the-component-as-a-transport-provider"></a>为传输提供程序组件的注册  
 必须在注册表中的其 Implemented Categories 属性下注册适配器，为传输提供程序。 此属性标识其向适配器的使用者的特征。  
  
```  
[HKEY_CLASSES_ROOT\CLSID\{%uuid of custom transport%}\Implemented Categories]  
[HKEY_CLASSES_ROOT\CLSID\{%uuid of custom transport%}\Implemented Categories\{7F46FC3E-3C2C-405B-A47F-8D17942BA8F9}]  
```  
  
## <a name="see-also"></a>请参阅  
 [适配器设计问题](../core/adapter-design-issues.md)