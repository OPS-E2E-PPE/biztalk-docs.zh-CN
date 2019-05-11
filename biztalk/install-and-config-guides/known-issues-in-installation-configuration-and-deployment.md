---
title: 安装、 配置和部署中的已知问题 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: ed1c08eb-d647-4a4a-b9a3-c4d84e8d4b82
caps.latest.revision: 18
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 040b1921228608deddb3e950613f447d984121c9
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65266202"
---
# <a name="known-issues-in-installation-configuration-and-deployment"></a>安装、 配置和部署中的已知的问题
## <a name="some-biztalk-edias2-artifacts-are-still-active-after-unconfiguring"></a>某些 BizTalk edi/as2 项目在取消后仍处于活动  
  
##### <a name="problem"></a>问题  
 取消对 BizTalk EDI/AS2 功能后[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]，与 EDI 和 AS2 处理相关的某些 BizTalk Server 项目仍将在 BizTalk 组配置的上下文中处于活动状态。 这些项目将包括 EDI 和 AS2 管道以及批处理业务流程。 因此，您将仍然能够执行基本的 EDI 和 AS2 处理后取消 BizTalk EDI/AS2 功能的配置。  
  
##### <a name="cause"></a>原因  
 有活动与 EDI 和 AS2 处理关联的端口。 某些项目将继续工作时这些端口保持活动状态。  
  
##### <a name="resolution"></a>解决方法  
 若要禁用所有 edi/as2 项目，应都禁用、 停止或删除与 EDI 和 AS2 处理关联的端口。  
  
## <a name="if-the-biztalk-server-computer-or-sql-server-computer-is-renamed-after-biztalk-server-configuration-the-configuration-wizard-will-fail"></a>如果 BizTalk Server 计算机或 SQL Server 计算机已重命名 BizTalk Server 配置后，配置向导将失败  
  
##### <a name="problem"></a>问题  
 此问题可能表现几种方式：  
  
-   BizTalk Server 配置正确，将加载概述页，但在尝试配置功能时不在屏幕上显示功能选项。  
  
-   配置向导无法连接到 SQL Server。  
  
-   尝试取消对所有 0}run 某些功能，但不是全部。  
  
##### <a name="cause"></a>原因  
 BizTalk Server 配置存储的计算机网络名称。 如果重命名计算机的 BizTalk Server 配置和配置向导找不到 BizTalk Server。 如果 SQL Server 计算机已重命名 BizTalk Server 配置后，将发生类似的问题。  
  
##### <a name="resolution"></a>解决方法  
 不要重命名 BizTalk Server 计算机或 SQL Server 计算机。 如果必须重命名服务器，然后再重命名计算机取消所有 BizTalk 功能。 重命名计算机之后, 重新配置 BizTalk Server 功能。  
  
## <a name="the-biztalk-server-business-rules-configuration-wizard-fails"></a>BizTalk Server 业务规则配置向导失败  
  
### <a name="problem"></a>问题  
  
- 业务规则配置向导失败并出现错误"某些组件的配置失败，这些组件未应用任何设置"。  
  
- 在 BizTalk Server 计算机上为其业务规则引擎已成功配置，规则引擎更新服务无法启动，并不能手动启动。  
  
  发生此问题时，可能会在 BizTalk Server 计算机应用程序日志中生成如下错误：  
  
```  
Service could not be started. : System.Net.Sockets.SocketException (10061): No connection could be made because the target machine actively refused it ::1:3132  
  
```  
  
### <a name="cause"></a>原因  
 Microsoft 恶意软件防护中心发布更新的签名文件，用于解决可能来自 SettingsModifier:Win32 威胁 / PossibleHostsFileHijack。 此更新的签名文件可能会导致 Microsoft 恶意软件检测软件，如 Windows Defender 更新本地 HOSTS 文件，以消除威胁 SettingsModifier:Win32 / PossibleHostsFileHijack。 这些更改会导致 BizTalk Server 规则引擎更新服务可能无法启动。  
  
### <a name="resolution"></a>解决方法  
 更新本地 HOSTS 文件，以包含以下行：  
  
```  
127.0.0.1         localhost  
```  
  
 主机文件位于 %systemroot%\drivers\etc\ 目录中。  
  
> [!NOTE]
>  有关解决可能来自 SettingsModifier:Win32 威胁的 Microsoft 恶意软件防护中心签名更新的详细信息 / PossibleHostsFileHijack，请转到[ http://go.microsoft.com/fwlink/?LinkId=146221 ](http://go.microsoft.com/fwlink/?LinkId=146221)。  
  
## <a name="enlistment-of-an-orchestration-fails-if-referenced-assemblies-are-missing-from-the-gacmgmt-db"></a>Enlistment 的业务流程失败，如果引用程序集缺少 GAC/Mgmt 数据库中  
  
##### <a name="problem"></a>问题  
 如果业务流程登记将失败的引用 (C#中引用的业务流程的程序集) 缺少 GAC/Mgmt 数据库中。 在重新部署过程都可能有需要登记业务流程基于其现有状态。 如果缺少引用然后部署也会失败。  
  
##### <a name="cause"></a>原因  
 GAC/Mgmt 数据库中缺少引用的程序集。  
  
##### <a name="resolution"></a>解决方法  
 在 GAC 中添加引用的程序集或将其添加为资源，以便存储在 Mgmt 数据库中并在业务流程登记过程进行访问。  

## <a name="community-blog-biztalk-2013-r2-bugs-issues-quirks"></a>社区博客：BizTalk 2013 R2 bug、 问题和 quirks

[BizTalk Server 2013 R2 已知 bug、 问题、 quirks](https://cdijkgraaf.wordpress.com/2016/08/12/biztalk-2013-r2-known-bugs-issues-quirks/)
  
## <a name="additional-configuration-topics"></a>其他配置主题  
  
 [配置 BizTalk Server](../install-and-config-guides/configure-biztalk-server.md)  
  
 [在 Azure VM 上配置 BizTalk Server](http://msdn.microsoft.com/library/azure/jj248689.aspx)  
  
  [在群集中配置 BizTalk Server](../install-and-config-guides/configure-biztalk-server-in-a-cluster.md)
  
 [保护 BizTalk Server 部署](../install-and-config-guides/securing-your-biztalk-server-deployment.md)  
  