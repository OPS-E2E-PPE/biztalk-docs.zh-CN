---
title: "HTTP 适配器 （BizTalk Server 示例） |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- HTTP adapters, examples
- examples, HTTP adapters
ms.assetid: f3bd8172-15c4-42fa-aa17-e4bed9d4aba4
caps.latest.revision: "32"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a4f443bf0b60f0bb90a914824b3922110ee1b300
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="http-adapter-biztalk-server-sample"></a>HTTP 适配器 （BizTalk Server 示例）
HTTP 适配器示例演示如何实现中使用的请求/响应和请求/响应通信范例[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]。  
  
## <a name="where-to-find-this-sample"></a>本示例所在的位置  
 *\<示例路径 >*\AdaptersDevelopment\HttpAdapter\  
  
 下表显示了本示例中的文件及其用途说明：  
  
|文件|Description|  
|---------------|-----------------|  
|\Design-Time\Adapter Management|包含实现此适配器的设计时部分的项目。|  
|\Run-Time\HttpReceive|包含实现请求/响应适配器通信模式的项目。 这是一个独立的接收器。|  
|\Run-Time\HttpSend|包含实现要求/响应适配器通信模式的项目。|  
  
## <a name="how-to-use-this-sample"></a>如何使用本示例  
 此示例旨在作为一个框架，用于你在开发自定义适配器使用。 在某些情况下 BizTalk Server 可能需要传输特定的自定义应用程序的消息或为其使用协议的本机适配器不存在。 第三方公司编写了支持其他协议的适配器。 您可能要在决定编写某一自定义适配器前确定是否存在可用于您的协议的适配器。 如果您无法找到支持您的通信要求的适配器，则可以开发自定义适配器。  
  
 编写自定义适配器可能颇具挑战性。 为了简化此过程，Microsoft 开发了称作适配器框架的基础框架。 您可以将此框架以及 BizTalk Server SDK 中的示例适配器源代码为基础进行开发。  有关自定义适配器和适配器框架的详细信息，请参阅**另请参阅**本文档末尾的部分。  
  
## <a name="building-and-initializing-the-sample-adapter"></a>生成并初始化示例适配器  
  
> [!IMPORTANT]
>  如果是在 64 位计算机上安装 BizTalk 或安装位置已修改，则需要相应修改 OutboundAssemblyPath、InboundAssemblyPath、AdapterMgmtAssemblyPath。  
  
#### <a name="to-build-and-initialize-the-http-adapter-sample"></a>生成和初始化 HTTP 适配器示例  
  
1.  在命令窗口中，导航到下面的文件夹：  
  
     \<*示例路径*> \AdaptersDevelopment\HttpAdapter  
  
2.  运行 Setup.bat 文件，该文件将执行以下操作：  
  
    -   编译 HTTPAdapter 及其所有依存关系。  
  
    -   创建由适配器的接收方使用的 Internet 信息服务 (IIS) 应用程序。  
  
 在 IIS 7.0 上必须确保运行此 IIS 应用程序的应用程序池的标识是以下组的成员：  
  
-   BizTalk Isolated Host Users 组。  
  
-   IIS_WPG 组。  
  
-   在 IIS 7.0 上，你必须迁移应用程序以使用.NET 集成模式。 你可以迁移应用程序配置，包括文件夹的内容\<httpHandlers > 配置节，通过从命令行窗口 （窗口中必须以管理员身份运行） 使用以下：  
  
    ```  
    %systemroot%\system32\inetsrv\APPCMD.EXE migrate config "Default Web Site/HttpReceive"  
    ```  
  
-   在迁移应用程序后，它既可以在经典模式下也可以在集成 .NET 模式下运行，还可以在下级平台上运行。  
  
> [!NOTE]
>  在尝试运行本示例前，你应确认在生成和初始化过程中未报告任何错误。  
  
> [!NOTE]
>  如果选择在不运行 Setup.bat 文件的情况下打开并生成本示例中的项目，则必须先使用 .NET Framework 强名称实用工具 (sn.exe) 创建一个强名称密钥对。 使用该密钥对可以对生成的程序集签名。  
  
> [!NOTE]
>  若要撤销 Setup.bat 所做的更改，请运行 Cleanup.bat。 在第二个运行 Setup.bat 之前，必须运行 Cleanup.bat，时间。  
  
## <a name="registering-the-sample-adapter"></a>注册示例适配器  
  
#### <a name="to-register-the-http-adapter-sample"></a>注册 HTTP 适配器示例  
  
1.  在 Windows 资源管理器，导航到安装驱动器以[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]，然后导航到\<示例路径 > \AdaptersDevelopment\HTTPAdapter。  
  
2.  若要将示例适配器添加到注册表中，双击**HTTP.NET.reg**。  
  
    > [!NOTE]
    >  HTTP.NET.reg 包含指向 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 安装目录的硬编码路径。 如果您未在默认位置安装 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 或者如果您从以前版本的 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 升级了 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 安装，则必须使用相应的路径修改文件 HTTP.NET.reg。 更新与“OutboundAssemblyPath”和“AdapterMgmtAssemblyPath”值相关联的路径，使其指向指定文件的正确位置。  
  
    > [!IMPORTANT]
    >  如果在 64 位计算机上安装 BizTalk，将 HKEY_CLASSES_ROOT\CLSID\ 注册表项的所有实例都更改为在 HKEY_CLASSES_ROOT\Wow6432Node\CLSID\ **HTTP.NET.reg**注册表文件。  
  
3.  在**注册表编辑器**对话框中，单击**是**以将示例适配器添加到注册表中，然后单击**确定**。  
  
4.  若要关闭 Windows 资源管理器，在**文件**菜单上，单击**关闭**。  
  
## <a name="installing-the-sample-adapter"></a>安装示例适配器  
  
#### <a name="to-install-the-http-adapter-sample"></a>安装 HTTP 适配器示例  
  
1.  单击**启动**菜单上，选择**所有程序**，选择[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]，然后选择**BizTalk Server 管理**。  
  
2.  在[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理控制台中，展开[!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)]树，然后展开**BizTalk 组**树，然后展开**平台设置**树。  
  
3.  右键单击**适配器**，单击**新建**，然后单击**适配器**。  
  
4.  在**适配器属性**对话框框中，执行以下操作。  
  
    |使用此选项|执行的操作|  
    |--------------|----------------|  
    |Name|类型**HTTP.NET**。|  
    |适配器|选择**HTTP.NET**从下拉列表。|  
    |Description|类型**示例 HTTP.NET 适配器**。|  
  
5.  单击 **“确定”**。  
  
6.  现在该适配器显示在 BizTalk 管理控制台右侧窗口中的适配器列表中。  
  
## <a name="stopping-and-restarting-the-host-instance"></a>停止并重新启动主机实例  
  
#### <a name="to-stop-and-restart-the-host-instance-for-the-http-adapter-sample"></a>停止并重新启动 HTTP 适配器示例的主机实例  
  
1.  单击**启动**菜单上，选择**所有程序**，选择[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]，然后选择[!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)]。  
  
2.  在[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理控制台中，展开[!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)]树，然后展开**平台设置**，然后单击**主机实例**。  
  
3.  在结果窗格中，右键单击主机实例 （通常情况下，计算机名称），并依次**停止**。  
  
     主机实例的状态更改为**已停止**。  
  
4.  在结果窗格中，右键单击主机实例，然后单击**启动**。  
  
 现在，HTTP.NET 适配器已经准备就绪，可供您的应用程序使用了。 配置的适配器的格式时**虚拟目录**传输属性的形式： /httpreceive/httpreceive.aspx?optionalQueryString。  
  
## <a name="comments"></a>注释  
 中提供的 BaseAdapter 类使用 HTTP.NET 适配器使*\<示例路径 >*\AdaptersDevelopment\BaseAdapter\v1.0...2\\。 BaseAdapter 项目中提供的类可以加快适配器的开发速度。 请参考 BaseAdapter 代码注释了解所提供的类的详细信息。  
  
## <a name="see-also"></a>另请参阅  
 [注册的适配器](../core/registering-an-adapter.md)   
 [适配器示例-使用情况](../core/adapter-samples-usage.md)   
 [开发自定义适配器](../core/developing-custom-adapters.md)   
 [什么是适配器 Framework？](../core/what-is-the-adapter-framework.md)   
 [使用适配器 Framework 工具](../core/using-the-adapter-framework-tools.md)   
 [开发接收适配器](../core/developing-a-receive-adapter.md)   
 [开发发送适配器](../core/developing-a-send-adapter.md)   
 [如何部署自定义适配器](../core/how-to-deploy-a-custom-adapter.md)   
 [设计你的适配器的提示](../core/tips-for-designing-your-adapter.md)   
 [适配器设计时配置](../core/adapter-design-time-configuration.md)