---
title: 适配器注册文件 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 6750f0ed-4411-4a63-a7fe-f66132cd1e22
caps.latest.revision: 35
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 5aeda24a40da78cfef5fb66f9069b0a8b80b986c
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "37012574"
---
# <a name="adapter-registration-file"></a>适配器注册文件
已成功生成自定义适配器代码后必须将它注册使用[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]。 可通过使用适当的适配器设置更新注册表来完成此步骤。 你可以手动编写注册表文件，但由于需要输入的信息要求精确且比较复杂，这样做容易出错。 一个更好的办法是运行适配器注册向导。 适配器注册向导提供的所有选项与从头创建注册表文件时提供的完全一样，能降低文件中出错的可能性。 有关适配器注册向导的详细信息，请参阅[适配器注册向导](../core/adapter-registry-wizard.md)。  
  
 StaticAdapterManagement.reg 文件和 DynamicAdapterManagement.reg 文件位于*\<驱动器\>*: \Program Files\Microsoft Server\SDK\Samples\AdaptersDevelopment\File 的 BizTalk 适配器。 当你运行这些文件之一 (可以双击它，也可以右键单击该和，然后选择**合并**)，它向注册表注册示例文件适配器并将该程序集安装到全局程序集缓存。 若要注册自定义适配器，最好的方法是使用适配器注册向导创建一个新的注册表文件。 如果自定义静态适配器类似于示例适配器，并且你决定修改现有的注册表文件，请在 StaticAdapterManagement.reg 文件中打开并修改以下属性：  
  
-   **约束**  
  
-   **InboundTypeName**  
  
-   **InboundAssemblyPath**  
  
-   **OutboundTypeName**  
  
-   **OutboundAssemblyPath**  
  
-   **AdapterMgmtTypeName**  
  
-   **AdapterMgmtAssemblyPath**  
  
-   **PropertyNameSpace**  
  
> [!NOTE]
>  有关**OutboundAssemblyPath**并**AdapterMgmtAssemblyPath**我们建议，你的本地路径中包含属性值，因为配置可能会中断时安装在不同服务器位置。 一个更好的选择是，使用强名称，并在全局程序集缓存中安装它。  
  
 你可以通过两种方式指定实现适配器接收器、适配器发送器和适配器管理的 .NET 类型：  
  
1. 将适配器安装到一个文件夹，并指定 * TypeName 和\*AssemblyPath 其中\*TypeName 是类型。类的 FullName 和\*AssemblyPath 是程序集的路径和文件。  
  
2. 在全局程序集缓存中安装适配器，且仅指定 * TypeName 其中\*TypeName 是类型。类的 AssemblyQualifiedName。 这是建议的选项。  
  
   所有适配器必须包括具有指定 GUID 的注册表项：  
  
- **实现类别\\{7F46FC3E-3C2C-405B-A47F-8D17942BA8F9}**  
  
- **"InboundProtocol_PageProv"="{2DE93EE6-CB01-4007-93E9-C3D71689A281}"**  
  
- **"OutboundProtocol_PageProv"="{2DE93EE6-CB01-4007-93E9-C3D71689A283}"**  
  
- **"ReceiveLocation_PageProv"="{2DE93EE6-CB01-4007-93E9-C3D71689A280}"**  
  
- **"TransmitLocation_PageProv"="{2DE93EE6-CB01-4007-93E9-C3D71689A282}"**  
  
  基于适配器框架的适配器必须将这些特定的 GUID 用于发送和接收处理程序以及位置属性页。 请注意，是否适配器是仅限发送的适配器只需要**OutboundProtocol_PageProv**并**TransmitLocation_PageProv**Guid。 仅接收适配器只要求同样**InboundProtocol_PageProv**并**ReceiveLocation_PageProv** Guid。  
  
  以下代码来自 StaticAdapterManagement.reg 文件，DynamicAdapterManagement.reg 文件的代码几乎完全一样。 有关每个注册表属性的详细信息，请参阅[注册适配器](../core/registering-an-adapter.md)。 对注册表文件进行更改后，保存该文件，然后运行它。  
  
```  
Windows Registry Editor Version 5.00  
[HKEY_CLASSES_ROOT\CLSID\{62018D08-281A-415b-A6D3-6172E3762867}]  
@="Static DotNetFile Adapter"  
"AppID"="{12A6EBAA-CF68-4B58-B36E-A5A19B22C04E}"  
  
[HKEY_CLASSES_ROOT\CLSID\{62018D08-281A-415b-A6D3-6172E3762867}\BizTalk]  
@="BizTalk"  
"TransportType"="Static DotNetFile"  
"Constraints"=dword:00003C0b  
  
"InboundProtocol_PageProv"="{2DE93EE6-CB01-4007-93E9-C3D71689A281}"  
"OutboundProtocol_PageProv"="{2DE93EE6-CB01-4007-93E9-C3D71689A283}"  
"ReceiveLocation_PageProv"="{2DE93EE6-CB01-4007-93E9-C3D71689A280}"  
"TransmitLocation_PageProv"="{2DE93EE6-CB01-4007-93E9-C3D71689A282}"  
  
"InboundEngineCLSID"="{3D4B599E-2202-4bbb-9FC6-7ACA3906E5DE}"  
"InboundTypeName"="Microsoft.BizTalk.SDKSamples.Adapters.DotNetFileReceiver""InboundAssemblyPath"="C:\\Program Files\\Microsoft BizTalk Server <version>\\SDK\\Samples\\AdaptersDevelopment\\File Adapter\\Runtime\\bin\\Debug\\Microsoft.BizTalk.SDKSamples.Adapters.DotNetFile.Runtime.dll"  
"OutboundEngineCLSID"="{024DB758-AAF9-415e-A121-4AC245DD49EC}"  
"OutboundTypeName"="Microsoft.BizTalk.SDKSamples.Adapters.DotNetFileTransmitter""OutboundAssemblyPath"="C:\\Program Files\\Microsoft BizTalk Server <version>\SDK\\Samples\\AdaptersDevelopment\\File Adapter\\Runtime\\bin\\Debug\\Microsoft.BizTalk.SDKSamples.Adapters.DotNetFile.Runtime.dll""AdapterMgmtTypeName"="Microsoft.BizTalk.SDKSamples.Adapters.Designtime.StaticAdapterManagement""AdapterMgmtAssemblyPath"="C:\\Program Files\\Microsoft BizTalk Server <version>\SDK\\Samples\\AdaptersDevelopment\\File Adapter\\Design Time\\Adapter Management\\bin\\Debug\\Microsoft.BizTalk.SDKSamples.Adapters.DotNetFile.Designtime.dll""PropertyNameSpace"="http://schemas.microsoft.com/BizTalk/2003/SDK_Samples/Messaging/Transports/dotnetfile-properties"  
"AliasesXML"="<AdapterAliasList><AdapterAlias>DotNetFILE://</AdapterAlias></AdapterAliasList>"  
"ReceiveHandlerPropertiesXML"="<CustomProps><AdapterConfig vt=\"8\"/></CustomProps>"  
"SendHandlerPropertiesXML"="<CustomProps><AdapterConfig vt=\"8\"/></CustomProps>"  
"ReceiveLocationPropertiesXML"="<CustomProps><AdapterConfig vt=\"8\"/></CustomProps>"  
"SendLocationPropertiesXML"="<CustomProps><AdapterConfig vt=\"8\"/></CustomProps>"  
[HKEY_CLASSES_ROOT\CLSID\{62018D08-281A-415b-A6D3-6172E3762867}\Implemented Categories]  
[HKEY_CLASSES_ROOT\CLSID\{62018D08-281A-415b-A6D3-6172E3762867}\Implemented Categories\{7F46FC3E-3C2C-405B-A47F-8D17942BA8F9}]  
```  
  
### <a name="to-register-the-static-sample-adapter"></a>注册静态示例适配器  
  
1. 使用以下过程运行 SDK 中的文件适配器。 有关详细信息，请参阅[文件适配器 （BizTalk Server 示例）](../core/file-adapter-biztalk-server-sample.md)。  
  
2. 单击**启动**，依次指向**所有程序**，指向**附件**，然后单击**Windows 资源管理器**。  
  
3. 有关 BizTalk Server 中，导航到安装驱动器，然后导航到**<** `drive` **>: \Program Files\Microsoft** [!INCLUDE[btsBizTalkServer2006r3ui](../includes/btsbiztalkserver2006r3ui-md.md)] **\SDK\Samples\AdaptersUsage\File 适配器**。  
  
4. 若要将示例适配器添加到注册表中，双击**StaticAdapterManagement.reg**。(如果你想要向运行注册表添加动态文件适配器**DynamicAdapterManagement.reg**改为使用该文件无处不在否则根据需要。)  
  
   > [!NOTE]
   >  如果 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 没有安装在计算机的 C 驱动器上，你必须用适当的安装路径修改 StaticAdapterManagement.reg 文件。 搜索该文件查找 c： 和其替换为正确的安装路径。  
  
5. 在中**注册表编辑器**对话框中，单击**是**以将示例适配器添加到注册表，然后单击**确定**以关闭对话框，验证了信息添加到注册表。  
  
6. 若要关闭 Windows 资源管理器，在**文件**菜单上，单击**关闭**。  
  
    现在注册示例静态适配器[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]。