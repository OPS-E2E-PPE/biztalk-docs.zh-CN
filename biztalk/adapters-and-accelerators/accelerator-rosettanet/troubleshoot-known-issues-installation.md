---
title: 进行故障排除和 BizTalk Server 上安装 BizTalk RosettaNet 加速器 (BTARN) 的已知的问题 |Microsoft Docs"
description: 用于安装 BizTalk Server 中的 BTARN 安装 SQL、 主机实例和已知的错误的服务帐户建议
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: ''
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c169a0871826aaaae9341f3ccafcb3e888ffbdbb
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36974622"
---
# <a name="troubleshoot-the-installation-and-see-the-known-install-issues"></a>安装进行故障排除，请参阅已知的安装问题


## <a name="do-not-install-sql-server-on-the-domain-controller-computer"></a>不要在域控制器计算机上安装 SQL Server  
 如果在域控制器计算机在同一计算机上安装 SQL Server，则尝试创建 SQL 发送端口时返回以下错误消息：  

```
Error: Failed updating binding information.  
BindingException: Could not validate TransportTypeData or Address properties for Primary Transport of Send Port 'SendPort1'. Exception from HRESULT: 0x80131500.  
Error: Failed updating binding information.  
BindingException: Could not validate TransportTypeData or Address properties for Primary Transport of Send Port 'SendPort1'. Exception from HRESULT: 0x80131500  
```

> [!IMPORTANT]
>  不要在域控制器计算机上安装 SQL 服务器。  

## <a name="service-account-for-the-application-pools-must-be-the-same-as-the-service-account-for-the-isolated-host-and-host-instances"></a>应用程序池的服务帐户必须与独立主机和主机实例的服务帐户相同  
 如果为 BTARN 应用程序池设置的服务帐户与独立主机帐户不同，BTARN 不正确处理传入的消息。 当接收.aspx 页调用管道时，管道无法访问相应的证书。 因此，它不解密传入消息或验证签名。 此外，它将无法访问 MessageBox 数据库。  


## <a name="known-install-issues"></a>已知的安装问题


### <a name="btarn-http-front-end-feature-configuration-fails"></a>BTARN HTTP 前端功能配置失败  
 **问题**  

 如果通过执行自定义安装来仅安装 BTARN HTTP 前端功能，安装完成后，BTARN 配置可能会因以下错误而失败： 

`Failed to create object for feature: WebApp`  

 **解决方法**  

手动复制文件并重新配置： 

1. 将以下两个文件从 BizTalk Server 的计算机复制到安装了 BTARN HTTP 前端功能的计算机：

   - Microsoft.VC80.ATL.manifest  

   - atl80.dll  

     如果在 BizTalk Server 所在的计算机上安装 Visual Studio，两个文件的源文件夹是 <*驱动器*>: \Program Files\Microsoft Visual Studio < 版本\>\VC\redist\x86\Microsoft.VC100.ATL.  

     如果在同一 BizTalk Server 计算机上未安装 Visual Studio，两个文件的源文件夹是在 <*驱动器*>: \WINDOWS\WinSxS。  

2. 将复制的文件添加到安装了 BTARN HTTP 前端功能的计算机。 默认情况下，将文件复制到 <*驱动器*>: \Program Files\Microsoft BizTalk Accelerator for RosettaNet。  

3. 文件复制到 HTTP 前端计算机后，运行**Configuration.exe**试。  

### <a name="some-btarn-assemblies-stay-in-gac-after-uninstalling"></a>某些 BTARN 程序集后仍保持在 GAC 中卸载  
 **问题**  

 当你卸载 BTARN 后时，某些程序集保留在全局程序集缓存 (GAC) 中。  

 **解决方法**  

 重新安装 BTARN 前，从 GAC 中删除程序集。  

 使用**BtarnClean**实用程序删除程序集的 SDK。 该实用程序执行下列操作：  

- 停止和取消登记所有 BTARN 业务流程。  

- 停止和删除所有关联的端口。  

- 取消部署所有 Microsoft.Solutions.BTARN.* 程序集。  

  运行该实用程序后，如果仍有程序集保留在 GAC 中，请打开 Windows 资源管理器，转到“C:\Windows\Assembly”文件夹，然后手动删除所有以 Microsoft.Solutions.BTARN 开头的程序集。  

### <a name="service-unavailable-error-on-64-bit-os"></a>64 位操作系统上的服务不可用错误
 **问题**  

 你可能会收到`Service Unavailable`错误时尝试访问 BTARN HTTP 接收位置在 64 位 Windows 操作系统上的。  

 **原因**  

 此问题可能是由“RPCProxy.dll”ISAPI 筛选器造成的。  

 **解决方法**  

删除对 RPC 代理 ISAPI 筛选器的引用并重新启动 IIS:

1.  在 Internet 信息服务 (IIS) 管理器中，右键单击**网站**，然后单击**属性**。  

2.  在中**的 Web 站点属性**对话框中，单击**ISAPI 筛选器**选项卡上，删除**RPC 代理**筛选，然后依次**确定**。  

3.  重新启动 IIS。  

4.  在重新启动 IIS 后，请尝试访问 http://localhost 。 你会收到从 Internet 浏览器返回的 400 消息。  

### <a name="sql-server-mixed-mode-not-supported"></a>不支持 SQL Server 混合模式  
在混合模式下，BTARN 不支持 SQL Server。  

### <a name="run-setupx64bat-to-set-up-the-double-action-pipautomation-orchestration-sample"></a>运行 setupx64.bat 设置双操作 PIPAutomation 业务流程示例 

运行 \Program Files\Microsoft BizTalk Accelerator for RosettaNet\SDK\PIPAutomation\DoubleAction 文件夹来安装双操作 PIPAutomation Orchestration 示例中的 setupx64.bat。

### <a name="download-the-btarn-setup-file-from-the-web-to-a-temp-folder"></a>将 BTARN 安装文件从 Web 下载到临时文件夹  
 **问题**  

 如果您下载 BTARN 自解压可执行文件从 Web，并将其保存到 BizTalk Server 根文件夹中，当您尝试运行可执行文件，BizTalk**安装向导**运行，而不是 BTARN 安装向导。  

 **解决方法**  

 下载 BTARN 自解压可执行文件，并将文件保存到临时文件夹。
