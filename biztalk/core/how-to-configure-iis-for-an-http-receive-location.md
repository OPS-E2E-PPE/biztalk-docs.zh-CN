---
title: "如何配置 IIS，用于 HTTP 接收位置 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- 64-bit support, HTTP adapters
- HTTP adapters, IIS
- configuring [HTTP adapters], IIS
- receive locations, IIS
- IIS, receive locations
- HTTP adapters, 64-bit support
- IIS, HTTP adapters
ms.assetid: 1c420f46-01f1-4c9c-9144-d8d2acc8b0c4
caps.latest.revision: "26"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a1daa535c546bef0b390f0f7f84c45d546ac0005
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-configure-iis-for-an-http-receive-location"></a>如何配置 IIS，用于 HTTP 接收位置
你必须根据所用的 Microsoft Windows 版本来以相应的方式配置 Microsoft Internet 信息服务 (IIS)，以便使用 HTTP 适配器接收位置。  
  
 如果操作系统为 [!INCLUDE[btsWinSvr2k8](../includes/btswinsvr2k8-md.md)] 或 [!INCLUDE[btsWinSvr2k8R2](../includes/btswinsvr2k8r2-md.md)]，则 IIS 7.0 提供两种不同的应用程序隔离模式来保护 Web 应用程序。 工作进程隔离模式为默认模式。 你可以将 HTTP 适配器接收位置配置为使用上述两种模式之一，但由于工作进程隔离模式的安全性已提高，因此建议使用该模式。  
  
> [!NOTE]
>  如果你的操作系统是 x64 版本的[!INCLUDE[btsWinSvr2k8](../includes/btswinsvr2k8-md.md)]或[!INCLUDE[btsWinSvr2k8R2](../includes/btswinsvr2k8r2-md.md)]，64 位版本的 HTTP 接收适配器安装到*\<驱动器 >***\Program Files (x86) \Microsoft**[!INCLUDE[btsBizTalkServer2006r3ui](../includes/btsbiztalkserver2006r3ui-md.md)] **\HttpReceive64**目录你[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]默认情况下。 若要以 64 位本机模式运行 64 位版本的 HTTP 接收适配器，则必须从命令行执行以下脚本：  
>   
>  `cscript %SystemDrive%\inetpub\AdminScripts\adsutil.vbs set w3svc/AppPools/Enable32bitAppOnWin64 0`  
>   
>  `C:\WINDOWS\Microsoft.NET\Framework64\vX.X.XXXXX>aspnet_regiis.exe -i`  
  
> [!NOTE]
>  任何会导致 SOAP 与 HTTP 共享同一进程的 IIS 配置都是无效的。 对于每个进程，只能有一个独立的接收器。  
  
### <a name="to-configure-the-iis-70-worker-process-isolation-mode-to-work-with-the-http-adapter-receive-location"></a>若要配置 IIS 7.0 工作进程隔离模式使用 HTTP 适配器接收位置  
  
1.  单击**启动**，指向**设置**，然后单击**控制面板**。  
  
2.  在 Control Panel 中，双击**管理工具**。  
  
3.  在管理工具中，双击**Internet Information Services**。  
  
4.  在 Internet 信息服务中，选择根 Web 服务器条目。 在**功能视图**，双击**处理程序映射**，然后在操作窗格中，单击**添加脚本映射**。  
  
    > [!NOTE]
    >  在 Web 服务器级别配置脚本映射会导致此映射应用于所有子网站。 如果要将映射限制为特定网站或虚拟文件夹，请选择目标站点或文件夹（而不是 Web 服务器）。  
  
5.  在**添加脚本映射**对话框中，在**请求路径**字段中，键入`BtsHttpReceive.dll`。  
  
6.  在**可执行文件**字段中，单击省略号 (**...**) 按钮，然后浏览到[!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]HttpReceive。 选择**BtsHttpReceive.dll** ，然后单击**确定**。  
  
7.  在**名称**字段中，键入`BizTalk HTTP Receive`，然后单击**请求限制**。  
  
8.  在**请求限制**对话框中，单击**谓词**选项卡上，然后选择**的以下谓词之一**。 输入`POST`作为谓词。  
  
9. 上**访问**选项卡上，选择**脚本**，然后单击**确定**。  
  
10. 在提示是否允许 ISAPI 扩展插件时，单击 **“是”**。  
  
11. 右键单击**应用程序池**，指向**新建**，然后单击**应用程序池**。  
  
12. 在**添加应用程序池**对话框中，在**名称**框中，键入应用程序池的名称。 选择**NET Framework v4.0.30319** ，然后单击**确定**。  
  
    > [!NOTE]
    >  版本号可能会因计算机上安装的 .NET Framework 版本而异。  
  
     新的应用程序池出现在列表中**应用程序池**。  
  
13. 在**应用程序池**中**功能视图**，选择新的应用程序池，，然后单击**高级设置**在操作窗格中。  
  
14. 在**高级设置**对话框中，在**进程模型**部分中，在**标识**字段中，单击省略号 (**...**) 按钮。  
  
15. 在**应用程序池标识**对话框中，选择**自定义帐户**，然后单击**设置**。 单击“确定”  关闭“高级设置”  对话框。  
  
16. 在 IIS 管理器中，打开**站点**文件夹。 右键单击**Default Web Site** ，然后单击**添加应用程序**。  
  
17. 在**添加应用程序**对话框中，在**别名**，输入别名以将应用程序后，相关联，然后单击**选择**。  
  
18. 在**选择应用程序池**对话框中，选择更早版本，创建新应用程序池，然后单击**确定**。  
  
19. 单击省略号 (**...**) 按钮，然后浏览到[!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]为 HttpReceive**物理路径**。  
  
20. 单击**连接身份**并输入**用户名**和**密码**的用户帐户的是管理员组的成员，然后单击**确定**.  
  
21. 单击**测试设置**并验证没有错误都显示在**测试连接**对话框。 单击 **“关闭”**，然后单击 **“确定”**。  
  
22. 新的应用程序将出现在列表**默认网站**Internet 信息服务 (IIS) 管理器。  
  
## <a name="see-also"></a>另请参阅  
 [如何配置 HTTP 接收位置](../core/how-to-configure-an-http-receive-location.md)