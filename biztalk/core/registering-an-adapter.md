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
ms.openlocfilehash: 6ff8395a6ea80494e5fe21c7b05ebc25e6ed8c44
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36985782"
---
# <a name="registering-an-adapter"></a>注册适配器
如果您在开发自定义适配器，则可以通过修改和运行在软件开发包 (SDK) 的示例文件适配器中附带的某一注册表文件，向 BizTalk Server 注册您开发的适配器。 或者，您可以使用适配器注册向导来创建注册表文件。 该向导位于 [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]Utilities\AdapterRegistryWizard 文件夹中。  
  
> [!IMPORTANT]
> - 在 32 位计算机上，必须从命令提示符运行适配器注册向导生成的注册表 (.reg) 文件。  
>   -   在 64 位计算机上，必须从 32 位和 64 位命令提示符运行适配器注册向导生成的注册表 (.reg) 文件。  
  
 在您创建注册表条目后，可以在 BizTalk Server 管理控制台中添加该适配器，也可以使用 Windows 管理规范 (WMI) 方法以编程方式添加该适配器。 本主题首先介绍各个注册表条目，然后显示为您的自定义适配器修改现有注册表文件的地方和方法。  
  
 有关使用适配器注册向导的说明，请参阅[适配器注册向导](../core/adapter-registry-wizard.md)。 有关修改 SDK 中包含的示例注册表文件的说明，请参阅[适配器注册文件](../core/adapter-registration-file.md)。  
  
## <a name="registry-keys"></a>注册表项  
 您需要创建以下注册表条目以便部署某一适配器：  
  
 **注册表项位置**  
  
```  
[HKEY_CLASSES_ROOT\CLSID\{%uuid of custom transport%}\BizTalk]  
@="BizTalk"  
  
```  
  
 **类型名称**  
  
 适配器类型名称标识 BizTalk Server 计算机中适配器的类型。 此注册表项是所有适配器都必需的。  
  
```  
"TransportType"="MyTransportAdapter"  
  
```  
  
 **约束**  
  
 适配器约束定义适配器的功能。  
  
 此注册表项是每个适配器所必需的。 根据您所创建的适配器的类型，您可能要修改约束的位掩码值。  
  
```  
"Constraints"=dword:00003C0b  
```  
  
 描述适配器功能的值可以是下表中所示的值的组合。  
  
|ReplTest1|十六进制值|标志|Description|  
|-----------|---------------|----------|-----------------|  
|@shouldalert|0x0001|eProtocolSupportsReceive|适配器支持接收操作。|  
|2|0x0002|eProtocolSupportsTransmit|适配器支持发送操作。|  
|8|0x0008|eProtocolReceiveIsCreatable|适配器的接收处理程序是在进程内承载的。|  
|128|0x0080|eProtocolSupportsRequestResponse|适配器支持请求-响应操作。|  
|256|0x0100|eProtocolSupportsSolicitResponse|适配器支持要求-响应操作。|  
|1024|0x4000|eOutboundProtocolRequiresContextInitialization|指示适配器使用适配器框架用户界面进行发送处理程序配置。|  
|2048|0x0800|eInboundProtocolRequiresContextInitialization|指示适配器使用适配器框架用户界面进行接收处理程序配置。|  
|4096|0x1000|eReceiveLocationRequiresContextInitialization|指示适配器使用适配器框架用户界面进行接收位置配置。|  
|8192|0x2000|eTransmitLocationRequiresContextInitialization|指示适配器使用适配器框架用户界面进行发送端口配置。|  
|16384|0x4000|eSupportsOrderedDelivery|指示适配器支持消息的按序送达。|  
|32768|0x8000|eInitTransmitterOnServiceStart|在服务启动时（而非发送第一个消息时）发送适配器启动。|  
|65536|0x10000|eSupport32BitOnly|指示适配器只支持在 32 位主机中运行。|  
  
### <a name="namespace"></a>命名空间  
 每个适配器都必须为其属性定义命名空间。 BizTalk Server 在此命名空间下的消息上下文上存储特定于适配器的属性。 此属性是所有适配器所必需的。  
  
```  
"PropertyNameSpace"="namespace"  
```  
  
### <a name="aliases"></a>Aliases  
 每个适配器都可以具有一组前缀，这些前缀唯一标识 BizTalk Server 中的适配器类型。 这允许在通过动态发送端口发送消息时解析正确的传输类型。 适配器需要在注册时指定其前缀列表。  
  
```  
"AliasesXML"="<AdapterAliasList><AdapterAlias>sample://</AdapterAlias></AdapterAliasList>"  
```  
  
### <a name="configuration-property-pages"></a>配置属性页  
 适配器必须具有配置属性页，以便配置其接收位置和发送端口。 每个适配器都通过指定其相应类 ID，注册其属性页。  
  
```  
"InboundProtocol_PageProv"="{%CLSID for inbound protocol prop page%}"  
"OutboundProtocol_PageProv"="{%CLSID for outbound protocol prop page%}"  
"ReceiveLocation_PageProv"="{%CLSID for receive location prop page%}"  
"TransmitLocation_PageProv"="{%CLSID for transmit location prop page%}"  
```  
  
 如果适配器使用适配器框架的用户界面生成属性页，则它必须为注册表项指定以下值：  
  
```  
"InboundProtocol_PageProv"="{2DE93EE6-CB01-4007-93E9-C3D71689A281}"  
"OutboundProtocol_PageProv"="{2DE93EE6-CB01-4007-93E9-C3D71689A283}"  
"ReceiveLocation_PageProv"="{2DE93EE6-CB01-4007-93E9-C3D71689A280}"  
"TransmitLocation_PageProv"="{2DE93EE6-CB01-4007-93E9-C3D71689A282}"  
```  
  
 请注意，如果某一终结点不是必需的（适配器仅是发送或接收适配器），则可以从注册表中删除不需要的注册表项。  
  
### <a name="runtime-component-registration"></a>运行时组件注册  
 适配器通过为接收和发送运行时组件指定其类 ID（对于 COM 和 .NET）、类型名称和程序集路径（对于 .NET），注册其运行时组件。  
  
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
>  您可以将适配器的程序集安装到全局程序集缓存中并在注册表文件中引用它。  
  
### <a name="registration-of-adapter-properties-for-sso-configuration-store"></a>用于 SSO 配置存储的适配器属性的注册  
 适配器需要向 BizTalk Server SSO 数据库注册其属性，以便能够在设计时和运行时存储和检索属性。  
  
```  
ReceiveHandlerPropertiesXML  
ReceiveLocationPropertiesXML  
SendHandlerPropertiesXML  
SendLocationPropertiesXML  
```  
  
 这些值包含与适配器相关的相应实体的允许属性的定义（架构），这些值可以存储在配置存储中。 这些定义以 XML 字符串的形式保存，由包含属性类型（但没有值）的属性包反序列化。 属性元素的非空值意味着该属性被屏蔽。 （被屏蔽意味着该属性是只写的，在管理模式下调用时不由安全存储区 API 返回；安全存储区 API 为此类属性返回 VT_NULL。）  
  
### <a name="example"></a>示例  
 HTTP 适配器通过定义来注册其属性进行 HTTP 发送端口**SendLocationPropertiesXML**具有以下值的注册表项：  
  
```  
<CustomProps><Username vt="8"/><Password vt="8">Encrypted</Password><Certificate vt="8"/><RequestTimeout vt="3"/><MaxRedirects vt="3"/><ContentType vt="8"/><UseProxy vt="11"/><ProxyName vt="8"/><ProxyPort vt="3"/><ProxyUsername vt="8"/><ProxyPassword vt="8">Encrypted</ProxyPassword><UseHandlerSetting vt="11"/><AuthenticationScheme vt="8"/><UseSSO vt="11"/><AffiliateApplicationName vt="8"/></CustomProps>  
```  
  
### <a name="registration-of-the-component-as-a-transport-provider"></a>将组件注册为传输提供程序  
 适配器必须在注册表中的其 Implemented Categories 属性下作为传输提供程序注册。 此属性向适配器的使用者标识其特性。  
  
```  
[HKEY_CLASSES_ROOT\CLSID\{%uuid of custom transport%}\Implemented Categories]  
[HKEY_CLASSES_ROOT\CLSID\{%uuid of custom transport%}\Implemented Categories\{7F46FC3E-3C2C-405B-A47F-8D17942BA8F9}]  
```  
  
## <a name="see-also"></a>请参阅  
 [适配器设计问题](../core/adapter-design-issues.md)