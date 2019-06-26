---
title: HTTP 适配器 （BizTalk Server 示例） |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- HTTP adapters, examples
- examples, HTTP adapters
ms.assetid: f3bd8172-15c4-42fa-aa17-e4bed9d4aba4
caps.latest.revision: 32
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 2e204d1e15ec7483bf2ae2f10db30ffd019651bf
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65332836"
---
# <a name="http-adapter-biztalk-server-sample"></a>HTTP 适配器 （BizTalk Server 示例）
HTTP 适配器示例演示如何实现中使用的请求/响应和要求/响应范例[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]。  

## <a name="where-to-find-this-sample"></a>本示例所在的位置  
 *\<Samples Path\>* \AdaptersDevelopment\HttpAdapter\  

 下表显示了本示例中的文件及其用途说明：  

|文件|Description|  
|---------------|-----------------|  
|\Design-Time\Adapter 管理|包含实现此适配器的设计时部分的项目。|  
|\Run-Time\HttpReceive|包含实现请求/响应适配器通信模式的项目。 这是一个独立的接收器。|  
|\Run-Time\HttpSend|包含实现要求/响应适配器通信模式的项目。|  

## <a name="how-to-use-this-sample"></a>如何使用此示例  
 此示例旨在为您要在开发自定义适配器中使用的框架。 在某些情况下 BizTalk Server 可能需要消息传输到特定的自定义应用程序或为其使用的协议不存在的本机适配器。 第三方公司编写了适配器，以支持其他协议。 您可能想要确定是否有您的协议的适配器在决定编写自定义适配器之前。 如果您找不到适配器以支持您的通信要求，可以开发自定义适配器。  

 编写自定义适配器很有挑战性的工作。 若要简化此过程，Microsoft 已开发了称作适配器框架的基础。 可以将此框架为基础进行开发以及 BizTalk Server SDK 中的示例适配器源代码。  有关自定义适配器和适配器框架的详细信息，请参阅**另请参阅**本文档末尾部分。  

## <a name="building-and-initializing-the-sample-adapter"></a>生成并初始化示例适配器  

> [!IMPORTANT]
>  如果 BizTalk 安装的是 64 位或修改安装位置，OutboundAssemblyPath、 InboundAssemblyPath、 AdapterMgmtAssemblyPath 需要相应地更改。  

#### <a name="to-build-and-initialize-the-http-adapter-sample"></a>若要生成并初始化 HTTP 适配器示例  

1. 在命令窗口中，导航到以下文件夹：  

    \<*Samples Path*\>\AdaptersDevelopment\HttpAdapter  

2. 运行文件 Setup.bat，以执行以下操作：  

   -   编译 HTTPAdapter 及其所有依赖项。  

   -   创建适配器的接收方端使用的 Internet 信息服务 (IIS) 应用程序。  

   在 IIS 7.0 中，必须确保运行此 IIS 应用程序的应用程序池标识是以下组的成员：  

-   BizTalk Isolated Host Users 组。  

-   IIS_WPG 组。  

-   在 IIS 7.0 上必须迁移应用程序集成.NET 模式下工作。 您可以将迁移应用程序配置，包括的内容\<httpHandlers\>配置部分中的，通过使用以下从命令行窗口 （窗口中必须以管理员身份运行）：  

    ```  
    %systemroot%\system32\inetsrv\APPCMD.EXE migrate config "Default Web Site/HttpReceive"  
    ```  

-   迁移你的应用程序后，它将运行在经典和集成.NET 模式下，以及在下级平台上。  

> [!NOTE]
>  在尝试运行本示例前，你应确认在生成和初始化过程中未报告任何错误。  

> [!NOTE]
>  如果你选择打开并生成此示例中的项目，而无需运行 Setup.bat 文件，必须首先创建强名称密钥对使用.NET Framework 强名称实用工具 (sn.exe)。 使用此密钥对生成程序集进行签名。  

> [!NOTE]
>  若要撤消 Setup.bat 所做的更改，请运行 Cleanup.bat。 必须运行 Setup.bat 前运行 Cleanup.bat 时间。  

## <a name="registering-the-sample-adapter"></a>注册示例适配器  

#### <a name="to-register-the-http-adapter-sample"></a>若要注册 HTTP 适配器示例  

1. 在 Windows 资源管理器，导航到安装驱动器[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]，然后导航到\<示例路径\>\AdaptersDevelopment\HTTPAdapter。  

2. 若要将示例适配器添加到注册表中，双击**HTTP.NET.reg**。  

   > [!NOTE]
   >  HTTP.NET.reg 包含硬编码路径[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]安装目录。 如果未安装[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]中的默认位置或者升级你[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]从以前版本的安装[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]，则必须修改文件 HTTP.NET.reg 使用相应的路径。 更新相关联的"揙 OutboundAssemblyPath"和"AdapterMgmtAssemblyPath"值，使其指向正确的位置的指定文件的路径。  
   > 
   > [!IMPORTANT]
   >  如果在 64 位计算机上安装 BizTalk，将 HKEY_CLASSES_ROOT\CLSID\ 注册表项的所有实例都更改为 hkey_classes_root\wow6432node\clsid \ 中**HTTP.NET.reg**注册表文件。  

3. 在中**注册表编辑器**对话框中，单击**是**以将示例适配器添加到注册表，然后单击**确定**。  

4. 若要关闭 Windows 资源管理器，在**文件**菜单上，单击**关闭**。  

## <a name="installing-the-sample-adapter"></a>安装示例适配器  

#### <a name="to-install-the-http-adapter-sample"></a>若要安装 HTTP 适配器示例  

1. 单击**启动**菜单中，选择**所有程序**，选择[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]，然后选择**BizTalk Server 管理**。  

2. 在中[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理控制台中，展开[!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)]树，然后展开**BizTalk 组**树，然后展开**平台设置**树。  

3. 右键单击**适配器**，单击**新建**，然后单击**适配器**。  

4. 在中**适配器属性**对话框框中，执行以下操作。  


   |  使用此选项   |                  执行的操作                  |
   |-------------|----------------------------------------------|
   |    “属性”     |              类型**HTTP.NET**。              |
   |   适配器   | 选择**HTTP.NET**从下拉列表。 |
   | Description |      类型**示例 HTTP.NET 适配器**。       |


5. 单击“确定”  。  

6. 此时，适配器将显示在 BizTalk 管理控制台右侧窗口中的适配器列表中。  

## <a name="stopping-and-restarting-the-host-instance"></a>停止并重新启动主机实例  

#### <a name="to-stop-and-restart-the-host-instance-for-the-http-adapter-sample"></a>若要停止并重新启动 HTTP 适配器示例的主机实例  

1. 单击**启动**菜单中，选择**所有程序**，选择[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]，然后选择[!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)]。  

2. 在中[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理控制台中，展开[!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)]树，然后展开**平台设置**，然后单击**主机实例**。  

3. 在结果窗格中，右键单击主机实例 （通常情况下，计算机名称），然后依次**停止**。  

    主机实例的状态将变为**已停止**。  

4. 在结果窗格中，右键单击该主机实例，然后依次**启动**。  

   现在，HTTP.NET 适配器已准备好应用程序使用。 配置适配器的格式时**虚拟目录**传输属性的形式： /httpreceive/httpreceive.aspx?optionalQueryString。  

## <a name="comments"></a>注释  
 建立的 HTTP.NET 适配器中提供的 BaseAdapter 类用法 *\<示例路径\>* \AdaptersDevelopment\BaseAdapter\v1.0...2\\。 BaseAdapter 项目中提供的类旨在加快适配器的开发速度。 请参考有关提供的类的详细信息的 BaseAdapter 代码注释。  

## <a name="see-also"></a>请参阅  
 [注册适配器](../core/registering-an-adapter.md)   
 [适配器示例-用法](../core/adapter-samples-usage.md)   
 [开发自定义适配器](../core/developing-custom-adapters.md)   
 [适配器框架是什么？](../core/what-is-the-adapter-framework.md)   
 [使用适配器框架工具](../core/using-the-adapter-framework-tools.md)   
 [开发接收适配器](../core/developing-a-receive-adapter.md)   
 [开发发送适配器](../core/developing-a-send-adapter.md)   
 [如何部署自定义适配器](../core/how-to-deploy-a-custom-adapter.md)   
 [设计您的适配器的提示](../core/tips-for-designing-your-adapter.md)   
 [适配器设计时配置](../core/adapter-design-time-configuration.md)