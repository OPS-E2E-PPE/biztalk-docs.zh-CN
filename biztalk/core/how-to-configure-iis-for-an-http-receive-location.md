---
title: 为 HTTP 接收位置配置 IIS |Microsoft Docs
description: 在 IIS 中，创建 BTS HTTP 接收应用程序和 BizTalk Server 中测试应用程序池设置
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
ms.openlocfilehash: cfc616fa9834071c2ee8d2b4d63f486ff0abbeab
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "37004817"
---
# <a name="configure-iis-for-an-http-receive-location"></a>为 HTTP 接收位置配置 IIS
HTTP 接收位置使用的应用程序在 Internet 信息服务 (IIS)。 本主题列出了步骤后，若要启用 HTTP 接收位置在 IIS 中。 

具体取决于你的操作系统配置 IIS 应用程序的步骤可能会有所不同。 使用与用户界面可能会不同操作系统上作为指南，这些步骤。
  
## <a name="32-bit-vs-64-bit"></a>32 位与 64 位

HTTP 接收位置使用 BTSHTTPReceive.dll。 没有 32 位和 64 位版本的 dll。 选择你想要使用哪个的版本。 64 位进程有更多可用内存，因此如果处理更大的消息，则可能是最佳选择 64 位版本。 

**32 位安装位置**: *Program Files (x86) \Microsoft BizTalk Server\HttpReceive*。
**64 位安装位置**: *Program Files (x86) \Microsoft BizTalk Server\HttpReceive64*

若要运行 64 位版本的 HTTP 接收适配器在 64 位本机模式下，打开命令提示符，并执行以下脚本：  

1. 类型： `cscript %SystemDrive%\inetpub\AdminScripts\adsutil.vbs set w3svc/AppPools/Enable32bitAppOnWin64 0`  

2. 类型： `C:\WINDOWS\Microsoft.NET\Framework64\vX.X.XXXXX>aspnet_regiis.exe -i`  
  
> [!NOTE]
>  任何会导致 SOAP 与 HTTP 共享同一进程的 IIS 配置都是无效的。 对于每个进程，只能有一个独立的接收器。  
  
##  <a name="configure-the-iis-application"></a>配置 IIS 应用程序
  
1. 打开**Internet 信息服务**(打开**服务器管理器**，选择**工具**，然后选择**Internet Information Services Manager**). 
  
2. 在 IIS 中，选择你的服务器名称。 在中**功能视图**，双击**处理程序映射**。 在操作窗格中选择**添加脚本映射**。  
  
   > [!NOTE]
   >  当在 web 服务器级别配置的脚本映射时，映射应用到所有网站。 如果你想要将映射限制到特定网站或虚拟文件夹，选择该 web 站点或文件夹，以及如何将脚本映射。  
  
3. 在中**添加脚本映射**，选择**请求路径**，然后键入`BtsHttpReceive.dll`。  
  
4. 在中**可执行文件**，选择省略号 (**...**)，并浏览到[!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]\HttpReceive。 选择**BtsHttpReceive.dll**，然后选择**打开**。  
  
5. 在中**名称**，输入`BizTalk HTTP Receive`，然后选择**请求限制**。 在此窗口中：
  
   1. 在中**谓词**，选择**以下谓词之一**，然后输入`POST`。  
  
   2. 在中**访问**，选择**脚本**，然后选择**确定**。  
  
   3. 在提示是否允许 ISAPI 扩展，选择**是**。  
  
6. 创建新的应用程序池 (右键单击**应用程序池**，选择**添加应用程序池**)。 **名称**应用程序池 (如`BTSHTTPReceive`)，选择**NET Framework v4.0.30319**，然后选择**确定**。  
  
    > [!NOTE]
    >  .NET 版本号可能会有所不同，具体取决于在计算机上安装.NET Framework 的版本。  
  
     将列出新的应用程序池。  
  
7. 选择新的应用程序池，并打开**高级设置**(**操作**窗格)。 在此窗口中：

    - **启用 32 位应用程序**： 设置为**True**如果选择了 32 位**BtsHttpReceive.dll**
    - **处理模型**部分中，**标识**： 选择省略号 (**...**)，选择**自定义帐户**，然后**设置**到该帐户是属于**BizTalk Isolated Host Users**和**IIS_WPG**组。 选择“确定”。 
  
8. 添加新的应用程序的 web 站点 (右键单击**Default Web Site**，选择**添加应用程序**)。 在此窗口中：
  
   1. **别名**： 输入与应用程序关联的别名 (如`BTS HTTP Receive`，然后**选择**。  
   2. 选择您刚的新应用程序池创建，并选择**确定**。  
   3. **物理路径**： 选择省略号 (**...**)，并浏览到[!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]\HttpReceive。  
   4. **测试设置**以验证是否在没有错误**测试连接**对话框。 **关闭**，然后选择**确定**。  
  
      > [!TIP]
      > 如果测试设置返回一条警告，可能缺少应用程序池标识的对文件夹的权限或访问组。 作为故障排除步骤，选择**连接身份**，输入**用户名**并**密码**是 Administrators 组的成员的用户帐户。 

9. 新应用程序将显示已列入**默认网站**。  
  
## <a name="see-also"></a>请参阅  
 [如何配置 HTTP 接收位置](../core/how-to-configure-an-http-receive-location.md)
