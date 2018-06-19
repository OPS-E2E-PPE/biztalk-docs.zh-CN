---
title: 将 IIS 配置为 HTTP 接收位置 |Microsoft 文档
description: 在 IIS 中，创建 BTS HTTP 接收应用程序和测试 BizTalk Server 中的应用程序池设置
ms.custom: ''
ms.date: 10/10/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 1c420f46-01f1-4c9c-9144-d8d2acc8b0c4
caps.latest.revision: 26
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e09768d6616a33a4900995f3dd3225fa34318b3c
ms.sourcegitcommit: 75d35f6f230f0846c29a4b146c6d5b074e60b13c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/11/2017
ms.locfileid: "22645169"
---
# <a name="configure-iis-for-an-http-receive-location"></a>将 IIS 配置为 HTTP 接收位置
HTTP 接收位置使用的应用程序在 Internet 信息服务 (IIS)。 本主题列出的步骤，若要启用 HTTP 接收在 IIS 中的位置。 

根据你的操作系统，配置 IIS 应用程序的步骤可能会有所不同。 作为指南，使用以下步骤，因为用户界面可能会在您的操作系统上不同。
  
## <a name="32-bit-vs-64-bit"></a>32 位与 64 位

HTTP 接收位置使用 BTSHTTPReceive.dll。 没有 32 位和 64 位版本的 DLL。 选择你想要使用哪个的版本。 64 位进程具有更多可用内存，因此如果处理更大的消息，则可能是最佳的 64 位版本。 

**32 位安装位置**: *Program Files (x86) \Microsoft BizTalk Server\HttpReceive*。
**64 位安装位置**: *Program Files (x86) \Microsoft BizTalk Server\HttpReceive64*

若要运行 64 位版本的 HTTP 接收适配器在 64 位本机模式下，打开命令提示符，执行以下脚本：  

1. 类型：`cscript %SystemDrive%\inetpub\AdminScripts\adsutil.vbs set w3svc/AppPools/Enable32bitAppOnWin64 0`  

2. 类型：`C:\WINDOWS\Microsoft.NET\Framework64\vX.X.XXXXX>aspnet_regiis.exe -i`  
  
> [!NOTE]
>  任何会导致 SOAP 与 HTTP 共享同一进程的 IIS 配置都是无效的。 对于每个进程，只能有一个独立的接收器。  
  
##  <a name="configure-the-iis-application"></a>配置 IIS 应用程序
  
1.  打开**Internet Information Services** (打开**服务器管理器**，选择**工具**，然后选择**Internet Information Services Manager**). 
  
2.  在 IIS 中，选择你的服务器名称。 在**功能视图**，双击**处理程序映射**。 在操作窗格中，选择**添加脚本映射**。  
  
    > [!NOTE]
    >  当在 web 服务器级别配置的脚本映射，则映射应用到所有 web 站点。 如果你想要限制映射到特定的网站或虚拟文件夹，选择该网站或文件夹，，，然后添加脚本映射。  
  
3.  在**添加脚本映射**，选择**请求路径**，和类型`BtsHttpReceive.dll`。  
  
4.  在**可执行文件**，选择省略号 (**...**)，并浏览到[!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]\HttpReceive。 选择**BtsHttpReceive.dll**，然后选择**打开**。  
  
5.  在**名称**，输入`BizTalk HTTP Receive`，然后选择**请求限制**。 在此窗口中：
  
    1. 在**谓词**，选择**的以下谓词之一**，并输入`POST`。  
  
    2. 在**访问**，选择**脚本**，然后选择**确定**。  
  
    3. 当系统提示允许 ISAPI 扩展，选择**是**。  
  
6. 创建新的应用程序池 (右键单击**应用程序池**，选择**添加应用程序池**)。 **名称**应用程序池 (如`BTSHTTPReceive`)，选择**NET Framework v4.0.30319**，然后选择**确定**。  
  
    > [!NOTE]
    >  .NET 版本号可能会有所不同，具体取决于计算机上安装的.NET Framework 的版本。  
  
     列出了新的应用程序池。  
  
7. 选择你新的应用程序池，并打开**高级设置**(**操作**窗格中)。 在此窗口中：

    - **启用 32 位应用程序**： 设置为**True**如果你选择 32 位**BtsHttpReceive.dll**
    - **处理模型**部分中，**标识**： 选择省略号 (**...**)，选择**自定义帐户**，，然后**设置**到成员的帐户**BizTalk 独立主机用户**和**IIS_WPG**组。 选择“确定”。 
  
8. 添加新的应用程序到 web 站点 (右键单击**Default Web Site**，选择**添加应用程序**)。 在此窗口中：
  
    1. **别名**： 输入与应用程序关联的别名 (如`BTS HTTP Receive`，，然后**选择**。  
    2. 选择新的应用程序池刚刚创建，，然后选择**确定**。  
    3. **物理路径**： 选择省略号 (**...**)，并浏览到[!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]\HttpReceive。  
    4. **测试设置**以验证是否在没有错误**测试连接**对话框。 **关闭**，然后选择**确定**。  
  
    > [!TIP]
    > 如果测试设置返回一条警告，可能缺少应用程序池标识的为的文件夹的权限或对一组访问。 故障排除步骤中，选择**连接身份**，输入**用户名**和**密码**是 Administrators 组的成员的用户帐户。 

9. 新的应用程序将显示为下列出**默认网站**。  
  
## <a name="see-also"></a>另请参阅  
 [如何配置 HTTP 接收位置](../core/how-to-configure-an-http-receive-location.md)
