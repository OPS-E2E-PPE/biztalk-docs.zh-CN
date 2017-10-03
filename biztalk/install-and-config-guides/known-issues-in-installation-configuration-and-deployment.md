---
title: "安装、 配置和部署中的已知问题 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: ed1c08eb-d647-4a4a-b9a3-c4d84e8d4b82
caps.latest.revision: "18"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: cda1bd5c8167bbf9f6049b3620c0c949950b1e89
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="known-issues-in-installation-configuration-and-deployment"></a>安装、配置和部署过程中的已知问题
## <a name="some-biztalk-edias2-artifacts-are-still-active-after-unconfiguring"></a>某些 BizTalk EDI/AS2 项目在取消配置后仍处于活动状态  
  
##### <a name="problem"></a>Problem  
 取消对 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 的 BizTalk EDI/AS2 功能的配置后，与 EDI 和 AS2 处理相关的某些 BizTalk Server 项目在 BizTalk 组配置的上下文中将仍处于活动状态。 这些项目将包括 EDI 和 AS2 管道以及批处理业务流程。 因此，即使在取消对 BizTalk EDI/AS2 功能的配置后，您仍然能够执行基本的 EDI 和 AS2 处理。  
  
##### <a name="cause"></a>原因  
 存在与 EDI 和 AS2 处理关联的活动端口。 某些项目在这些端口保持活动时会继续工作。  
  
##### <a name="resolution"></a>解决方法  
 若要禁用所有 EDI/AS2 项目，应禁用、停止或删除与 EDI 和 AS2 处理关联的端口。  
  
## <a name="if-the-biztalk-server-computer-or-sql-server-computer-is-renamed-after-biztalk-server-configuration-the-configuration-wizard-will-fail"></a>如果在对 BizTalk Server 进行配置之后重命名了 BizTalk Server 计算机或 SQL Server 计算机，则配置向导将失败  
  
##### <a name="problem"></a>Problem  
 此问题的表现方式有多种：  
  
-   BizTalk Server 配置可以正确加载“概述”页，但在尝试配置功能时，屏幕上不显示功能选项。  
  
-   配置向导无法连接到 SQL Server。  
  
-   尝试使用“取消对所有功能的配置”时仅取消了对部分功能而不是所有功能的配置。  
  
##### <a name="cause"></a>原因  
 BizTalk Server 配置存储了计算机的网络名称。 如果重命名了计算机，“BizTalk Server 配置”和配置向导将无法找到 BizTalk Server。 如果在对 BizTalk Server 进行配置之后重命名了 SQL Server 计算机，将会出现类似的问题。  
  
##### <a name="resolution"></a>解决方法  
 请不要重命名 BizTalk Server 计算机或 SQL Server 计算机。 如果必须对服务器进行重命名，请取消对所有 BizTalk 功能的配置，然后再重命名计算机。 在重命名计算机后，请重新配置 BizTalk Server 功能。  
  
## <a name="the-biztalk-server-business-rules-configuration-wizard-fails"></a>BizTalk Server 业务规则配置向导失败  
  
### <a name="problem"></a>Problem  
  
-   业务规则配置向导失败，并显示错误“某些组件配置失败，没有为这些组件应用任何设置”。  
  
-   在已为其成功配置业务规则引擎的 BizTalk Server 计算机上，规则引擎更新服务启动失败并且不能手动启动。  
  
 出现此问题时，可能会在 BizTalk Server 计算机的应用程序日志中生成与下面类似的错误：  
  
```  
Service could not be started. : System.Net.Sockets.SocketException (10061): No connection could be made because the target machine actively refused it ::1:3132  
  
```  
  
### <a name="cause"></a>原因  
 Microsoft 恶意软件防护中心发布了一个更新的签名文件，用于解决可能来自 SettingsModifier:Win32/PossibleHostsFileHijack 的威胁。 此更新的签名文件可能导致 Microsoft 恶意软件检测软件（例如 Windows Defender）更新本地 HOSTS 文件，以缓解来自 SettingsModifier:Win32/PossibleHostsFileHijack 的威胁。 由于这些更改，BizTalk Server 规则引擎更新服务可能启动失败。  
  
### <a name="resolution"></a>解决方法  
 更新本地 HOSTS 文件以包括以下行：  
  
```  
127.0.0.1         localhost  
```  
  
 HOSTS 文件位于 %systemroot%\drivers\etc\ 目录中。  
  
> [!NOTE]
>  有关解决可能来自 SettingsModifier:Win32/PossibleHostsFileHijack 的威胁的 Microsoft 恶意软件防护中心签名更新的详细信息，请参阅 [http://go.microsoft.com/fwlink/?LinkId=146221](http://go.microsoft.com/fwlink/?LinkId=146221)。  
  
## <a name="enlistment-of-an-orchestration-fails-if-referenced-assemblies-are-missing-from-the-gacmgmt-db"></a>如果 GAC/Mgmt 数据库中缺少引用的程序集，则业务流程登记将失败  
  
##### <a name="problem"></a>Problem  
 如果 GAC/Mgmt 数据库中缺少引用（业务流程中引用的 C# 程序集），则业务流程登记将失败。 在重新部署过程中，可能会需要基于业务流程的现有状态登记业务流程。 如果缺少引用，则部署也会失败。  
  
##### <a name="cause"></a>原因  
 GAC/Mgmt 数据库中缺少引用的程序集。  
  
##### <a name="resolution"></a>解决方法  
 在 GAC 中添加引用的程序集，或者将它们作为资源添加，以便可以将它们存储在 Mgmt 数据库中，并且可以在业务流程登记过程中访问它们。  

## <a name="community-blog-biztalk-2013-r2-bugs-issues--quirks"></a>社区博客：BizTalk 2013 R2 bug、问题和 quirks

[BizTalk Server 2013 R2 known bugs, issues, quirks](https://cdijkgraaf.wordpress.com/2016/08/12/biztalk-2013-r2-known-bugs-issues-quirks/)（BizTalk Server 2013 R2 已知 bug、问题和 quirks）
  
## <a name="additional-configuration-topics"></a>其他配置主题  
  
 [配置 BizTalk Server](../install-and-config-guides/configure-biztalk-server.md)  
  
 [在 Azure VM 上配置 BizTalk Server](http://msdn.microsoft.com/library/azure/jj248689.aspx)  
  
  [在群集中配置 BizTalk Server](../install-and-config-guides/configure-biztalk-server-in-a-cluster.md)
  
 [确保 BizTalk Server 部署的安全](../install-and-config-guides/securing-your-biztalk-server-deployment.md)  
  