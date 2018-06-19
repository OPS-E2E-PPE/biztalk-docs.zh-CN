---
title: 排除故障并在 BizTalk Server 上安装的已知的问题与 BizTalk RosettaNet 快捷键 (BTARN) |Microsoft 文档"
description: 安装与 BTARN 安装 BizTalk Server 中的 SQL，主机实例和已知的错误的服务帐户的建议
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: ''
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: cdca89c1a7a4ed3834103776f9f28c8631c5de0a
ms.sourcegitcommit: 8418b1a8f38b7f56979cd6e203f0b591e2f40fe1
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/28/2018
ms.locfileid: "22210837"
---
# <a name="troubleshoot-the-installation-and-see-the-known-install-issues"></a>解决安装问题和发现的已知的安装问题

  
## <a name="do-not-install-sql-server-on-the-domain-controller-computer"></a>不要在域控制器计算机上安装 SQL Server  
 如果在同一台计算机作为域控制器计算机上安装 SQL Server，它在尝试创建 SQL 发送端口时将返回以下错误消息：  
  
```
Error: Failed updating binding information.  
BindingException: Could not validate TransportTypeData or Address properties for Primary Transport of Send Port 'SendPort1'. Exception from HRESULT: 0x80131500.  
Error: Failed updating binding information.  
BindingException: Could not validate TransportTypeData or Address properties for Primary Transport of Send Port 'SendPort1'. Exception from HRESULT: 0x80131500  

```
  
> [!IMPORTANT]
>  不要在域控制器计算机上安装 SQL 服务器。  
  
## <a name="service-account-for-the-application-pools-must-be-the-same-as-the-service-account-for-the-isolated-host-and-host-instances"></a>应用程序池的服务帐户必须与独立主机和主机实例的服务帐户相同  
 如果为 BTARN 应用程序池设置的服务帐户从独立主机帐户不同，BTARN 不正确处理传入消息。 当接收.aspx 页调用管道时，管道没有合适的证书的访问。 因此，它不会对传入消息进行解密或验证的签名。 此外，它将无法访问 MessageBox 数据库。  
  

## <a name="known-install-issues"></a>已知的安装问题

  
### <a name="btarn-http-front-end-feature-configuration-fails"></a>BTARN HTTP 前结束功能配置失败  
 **问题**  
  
 如果通过执行自定义安装来仅安装 BTARN HTTP 前端功能，安装完成后，BTARN 配置可能会因以下错误而失败： 

`Failed to create object for feature: WebApp`  
  
 **解决方法**  
  
手动将文件复制和重新配置： 
  
1.  从 BizTalk Server 计算机的以下两个文件复制到计算机在其安装了 BTARN HTTP 前端功能：
  
    -   Microsoft.VC80.ATL.manifest  
  
    -   atl80.dll  
  
     如果在 BizTalk Server 所在的计算机上安装 Visual Studio，两个文件的源文件夹是 <*驱动器*>: files\microsoft Visual Studio < 版本\>\VC\redist\x86\Microsoft.VC100.ATL.  
  
     如果相同的 BizTalk Server 计算机上未安装 Visual Studio，两个文件的源文件夹是在 <*驱动器*>: \WINDOWS\WinSxS。  
  
2.  将复制的文件添加到安装了 BTARN HTTP 前端功能的计算机。 默认情况下，将文件复制到 <*驱动器*>: files\microsoft BizTalk Accelerator for RosettaNet。  
  
3.  将文件复制到 HTTP 前端计算机后，运行**Configuration.exe**试。  
  
### <a name="some-btarn-assemblies-stay-in-gac-after-uninstalling"></a>某些 BTARN 程序集在 GAC 中保持卸载后  
 **问题**  
  
 当你卸载 BTARN 时，某些程序集将保留在全局程序集缓存 (GAC) 中。  
  
 **解决方法**  
  
 重新安装 BTARN 前，从 GAC 中删除程序集。  
  
 使用**BtarnClean**实用工具从 SDK 以移除程序集。 该实用程序执行下列操作：  
  
-   停止和取消登记所有 BTARN 业务流程。  
  
-   停止和删除所有关联的端口。  
  
-   取消部署所有 Microsoft.Solutions.BTARN.* 程序集。  
  
 运行该实用程序后，如果仍有程序集保留在 GAC 中，请打开 Windows 资源管理器，转到“C:\Windows\Assembly”文件夹，然后手动删除所有以 Microsoft.Solutions.BTARN 开头的程序集。  
  
### <a name="service-unavailable-error-on-64-bit-os"></a>64 位操作系统上的服务不可用错误
 **问题**  
  
 你可能会收到`Service Unavailable`错误尝试访问 BTARN HTTP 时接收在 64 位 Windows 操作系统上的位置。  
  
 **可能的原因**  
  
 此问题可能是由“RPCProxy.dll”ISAPI 筛选器造成的。  
  
 **解决方法**  
  
删除对 RPC 代理 ISAPI 筛选器的引用并重新启动 IIS:
  
1.  在 Internet 信息服务 (IIS) 管理器中，右键单击**网站**，然后单击**属性**。  
  
2.  在**Web 站点属性**对话框中，单击**ISAPI 筛选器**选项卡上，删除**RPC 代理**筛选，并依次**确定**。  
  
3.  重新启动 IIS。  
  
4.  在重新启动 IIS 后，请尝试访问http://localhost。 你会收到从 Internet 浏览器返回的 400 消息。  
  
### <a name="sql-server-mixed-mode-not-supported"></a>SQL Server 混合模式不支持  
在混合模式下，BTARN 不支持 SQL Server。  
  
### <a name="run-setupx64bat-to-set-up-the-double-action-pipautomation-orchestration-sample"></a>运行 setupx64.bat 设置双操作 PIPAutomation 业务流程示例 

运行 setupx64.bat files\microsoft BizTalk Accelerator for RosettaNet\SDK\PIPAutomation\DoubleAction 文件夹设置双操作 PIPAutomation 业务流程示例中。
  
### <a name="download-the-btarn-setup-file-from-the-web-to-a-temp-folder"></a>将 BTARN 安装文件从 Web 下载到临时文件夹  
 **问题**  
  
 如果您下载 BTARN 自解压可执行文件从 Web 中，并将其保存到 BizTalk Server 根文件夹中，当你尝试运行可执行文件，BizTalk**安装向导**运行，而不是 BTARN 安装向导。  
  
 **解决方法**  
  
 下载 BTARN 自解压可执行文件，并将文件保存到临时文件夹。
