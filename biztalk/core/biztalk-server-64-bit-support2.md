---
title: BizTalk Server 的 64 位支持概述 |Microsoft Docs
description: 在适配器、 进程、 BizTalk 管理、 BAM 工具、 程序集、 业务流程、 和的详细信息在 BizTalk Server 中的 64 位支持
ms.custom: ''
ms.date: 09/27/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 52ae9037-a7af-48e4-b6a3-bff7600802de
caps.latest.revision: 42
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 3cf1c475cdd3f318fe92a3de7bc6150047f214a5
ms.sourcegitcommit: d27732e569b0897361dfaebca8352aa97bb7efe1
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/10/2019
ms.locfileid: "65530461"
---
# <a name="biztalk-server-64-bit-support"></a>BizTalk Server 64 位支持
本主题解答有关 Microsoft 的 64 位支持某些常见问题[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]。  
  
## <a name="which-versions-of-64-bit-windows-are-supported"></a>支持哪些版本的 64 位 Windows？  
 所有版本的[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]受支持的操作系统上支持 32 位执行和本机 64 位执行。 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 包括 32 位和 64 位配置选项。 
 
  [硬件和软件要求适用于 BizTalk Server 2016](../install-and-config-guides/hardware-and-software-requirements-for-biztalk-server-2016.md)  
  
 [BizTalk Server 2013 和 2013 R2 的硬件和软件要求](../install-and-config-guides/hardware-and-software-requirements-for-biztalk-server-2013-and-2013-r2.md)  
  
## <a name="is-there-an-extra-cost-for-64-bit-support"></a>是否有额外的 64 位支持费用？  
 否。 64 位支持不无需额外付费。  
  
## <a name="is-itanium-based-hardware-supported"></a>是否支持基于 Itanium 的硬件？  
 对于 BizTalk 运行时，没有。 对于 BizTalk 数据库，是。  
  
 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 需要支持 AMD64 或 EM64T 的 CPU 硬件。 因此，[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]不支持在基于 Itanium 的 64 位 Cpu 上运行的 Windows 上。 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 支持运行使用基于 Itanium 的[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]。 因此，所有[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]Itanium 64 位 cpu 支持的数据库。  
  
## <a name="which-biztalk-server-processes-run-in-64-bit-mode"></a>哪些 BizTalk Server 进程在 64 位模式下运行？  
 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 可执行文件都托管在多个不同的服务器运行时。 下表列出了哪些[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]进程在 64 位模式下运行。  
  
|Process|32 位支持|64 位支持|  
|-------------|---------------------|---------------------|  
|基于 HTTP 的适配器 (IIS)|是|Partial|  
|BizTalk 主机实例|是|是|  
|企业 SSO|是|是|  
|BAM 门户 (IIS)|是|否|  
|SQL Server|是|是|  
  
##### <a name="http-based-adapters-iis"></a>基于 HTTP 的适配器 (IIS)  
 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 组件，如 HTTP 和 SOAP 适配器是托管并执行在 Internet 信息服务 (IIS)。 在 32 位 IIS 模式下支持所有的适配器。 某些适配器支持在 64 位 IIS 模式下运行。 64 位适配器的完整列表，请参阅本主题后面的适配器列表。  
  
##### <a name="biztalk-host-instances"></a>BizTalk 主机实例  
 BizTalk 主机是服务器，每个另一个名为主机实例的逻辑组。 作为 NT 服务基于 BTSNTSvc.exe 部署每个主机实例。 加载和主机实例中执行业务流程和进程内适配器。 可以将主机实例配置为使用运行在 32 位或 64 位模式下**仅限 32 位**中的复选框选项**主机属性**中的对话框[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理控制台。  
  
##### <a name="enterprise-sso"></a>企业 SSO  
 Microsoft 企业单一登录 (SSO) 是运行在专用 NT 服务中 (ENTSSO.exe)。 它是 32 位上的本机 32 位[!INCLUDE[btsWinNoVersion](../includes/btswinnoversion-md.md)]和 64 位上的本机 64 位[!INCLUDE[btsWinNoVersion](../includes/btswinnoversion-md.md)]。  
  
##### <a name="bam-portal-iis"></a>BAM 门户 (IIS)  
 业务活动监视 (BAM) 门户组件必须运行在 IIS 中使用 32 位 ASP.NET 3.5。 BAM 门户将在 WOW 模式下的 64 位硬件上运行。 "正在运行的 64 位环境中的 BAM 门户"，请参阅[自定义 BAM 门户配置](../core/customizing-the-bam-portal-configuration.md)。  
  
##### <a name="sql-server"></a>SQL Server  
 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 与 Microsoft 通信[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]上的 32 位和 64 位版本之间进行互操作的本机传输协议[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]。 因此，32 位和 64 位[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]可执行文件可以与 32 位或 64 位版本的通信[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]。 所有[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]存储的过程是支持在 32 位或 64 位[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]。  
  
## <a name="what-about-32-bit64-bit-support-in-non-server-processes"></a>非服务器进程中的 32 位/64 位支持呢？  
 **Microsoft Visual Studio**  
  
 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 设计器可执行文件托管在 32 位[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]IDE。 [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] 支持使用 Microsoft 的 64 位项目的开发[!INCLUDE[btsDotNetFramework](../includes/btsdotnetframework-md.md)]，其中可以部署到[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]。  
  
 **Microsoft 管理控制台 (MMC)**  
  
 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]只作为 32 位 Microsoft 管理控制台 (MMC) 应用程序，即使在 64 位平台上运行管理控制台[!INCLUDE[btsWinNoVersion](../includes/btswinnoversion-md.md)]。 企业 SSO 支持 32 位和 64 位 MMC。  
  
 **Internet Explorer**  
  
 BAM 客户端要求使用 32 位 Internet Explorer 以安装和使用 64 位上[!INCLUDE[btsWinNoVersion](../includes/btswinnoversion-md.md)]。  
  
## <a name="how-do-i-enable-native-64-bit-execution-of-orchestrations"></a>如何启用业务流程的本机 64 位的执行？  
 指定业务流程具有主机实例中运行**仅限 32 位**未选择的属性。 必须在 Windows x64 计算机上运行的主机实例。  
  
## <a name="can-i-build-net-assemblies-that-run-in-64-bit-orchestrations"></a>可以生成 64 位业务流程中运行的.NET 程序集？  
 是。 使用[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]并[!INCLUDE[btsDotNetFramework](../includes/btsdotnetframework-md.md)]、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]开发人员可创建支持 64 位执行的程序集。 这些都可以部署与业务流程，并可以在配置为本机 64 位执行的主机实例中运行。  
  
## <a name="will-net-framework-20-compiled-assemblies-jit-compile-properly-in-both-32-bit-and-64-bit"></a>将.NET Framework 2.0 编译的程序集 JIT 编译在 32 位和 64 位中正常运行？  
 是。 如果该程序集编译[!INCLUDE[btsDotNetFramework](../includes/btsdotnetframework-md.md)]2.0 和**AnyCPU**标志，在 32 位或 64 位 Clr 中正确单个 DLL 将 JIT 编译。  
  
## <a name="can-i-install-both-32-bit-and-64-bit-components-in-a-single-biztalk-msi-package"></a>可以在一个 BizTalk MSI 包安装 32 位和 64 位组件？  
 是。 管理员可以创建从一个 MSI 程序包文件[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]应用程序。 MSI 文件可以包含 32 位和 64 位 Dll 和 Exe 已添加到 BizTalk 应用程序。 在 32 位 Windows 上将安装仅 32 位 Dll 和 Exe。 在[!INCLUDE[btsWinNoVersion](../includes/btswinnoversion-md.md)]x64，32 位和 64 位 Dll 和 Exe 将被安装。  
  
## <a name="how-do-32-bit-biztalk-server-executables-run-on-windows-x64"></a>如何在 Windows x64 上运行 32 位 BizTalk Server 可执行文件？  
 Windows x64 提供了同一台计算机上运行 32 位和 64 位可执行文件的能力。 32 位可执行文件使用 WOW64 服务来模拟 32 位运行时环境。  
  
## <a name="will-32-bit-biztalk-server-executables-have-4gb-of-addressable-process-memory-on-windows-x64"></a>32 位 BizTalk Server 可执行文件将在 Windows x64 上具有 4GB 可寻址进程内存？  
 是。 在[!INCLUDE[btsWinNoVersion](../includes/btswinnoversion-md.md)]x64，32 位 BTSNTSVC 和 IIS 进程在 WOW64 下运行，并可能会利用完整的 4 GB 的虚拟内存。 这是对默认的改进 2 GB 的 32 位 Windows 的可寻址虚拟内存。  
  
 您可以设置内存阻止阈值百分比 （%）用或绝对值。 例如：  
  
-   如果你使用 %可用 (0-100)，则输入的值为 2048 MB 的百分比。  
  
-   如果使用绝对值，则您输入的值可以是任何以 mb 为单位的值最大为 4096 MB （32 位限制）。 在 64 位主机，可以指定最大为 2 TB 的理论上的 64 位地址限制更高的值。  
  
## <a name="which-adapters-are-capable-of-running-in-64-bit-mode"></a>哪些适配器是否能够在 64 位模式下运行？  
 默认情况下，所有适配器可以在 32 位模式下都运行在 32 位[!INCLUDE[btsWinNoVersion](../includes/btswinnoversion-md.md)]64 位上的 wow64 [!INCLUDE[btsWinNoVersion](../includes/btswinnoversion-md.md)]。 以下适配器可以运行在本机 64 位模式下 （在 IIS 或 BTSNTSVC 作为主机进程中）：  
  
-   文件  
  
-   HTTP  
  
-   MSMQ  
  
-   MQSeries  
  
-   SFTP  
  
-   SMTP  
  
-   SOAP  
  
-   WCF  
  
> [!NOTE]
>  MQSeries 适配器支持在 32 位和 64 位进程中。 适配器已在 Windows IBM WebSphere MQ Server 运行了 MQSeries 代理。 [准备计算机以进行安装](../install-and-config-guides/prepare-your-computer-for-installation.md)列出了 MQ 要求。  
> 
> [!NOTE]
>  如果你[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]应用程序连接到 Windows Server 2003 计算机 （例如 SSO、 SQL 适配器、 MQSeries、 MQSAgent、 Oracle 等），然后安装[934016](http://support.microsoft.com/kb/934016)并[934849](http://support.microsoft.com/kb/934849)这些 Windows Server 上2003 服务器。  
> 
> [!NOTE]
>  不支持在 64 位主机实例上运行的 FTP 适配器、 POP3 适配器和 MIME 解码器。  
  
## <a name="are-persisted-biztalk-orchestrations-dependent-on-32-bit-or-64-bit-runtimes"></a>持久化的 BizTalk 业务流程是否依赖于 32 位或 64 位运行时？  
 否。 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 持久化运行时组件使用独立于 32 位或 64 位运行时的格式。 这包括业务流程、 消息和端口。 这种持久化模型使管理员能够切换而无需创建中的不兼容的 32 位和 64 位之间的主机配置[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]数据。  
  
## <a name="when-i-upgrade-to-biztalk-server-will-my-biztalk-hosts-run-as-64-bit-by-default"></a>升级到 BizTalk Server 后，将 BizTalk 主机以 64 位默认运行？  
 否。 默认情况下，升级到 BizTalk Server 将仅标记为 32 位的所有 BizTalk 主机实例。 管理员必须在 Windows x64 计算机上创建新的主机实例，并配置应用程序使用它们。  
  
## <a name="can-i-have-a-mixed-biztalk-server-group-that-includes-both-32-bit-and-64-bit-biztalk-runtimes"></a>我可以包含 32 位和 64 位 BizTalk 运行时的"混合"BizTalk Server 组？  
 是。  
  
## <a name="what-languages-are-supported-on-64-bit-runtimes"></a>在 64 位运行时上支持哪些语言？  
 所有支持的语言支持 32 位和 64 位运行时。  
  
## <a name="what-64-bit-sql-server-components-are-required-to-configure-bam-tools"></a>配置 BAM 工具需要哪些 64 位 SQL Server 组件？  
 配置向导是一个 32 位的过程;因此，它需要允许它与 64 位进行通信的某些组件[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]。 必须安装以下[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]客户端组件，以便实现 BAM 工具的配置：  
  
-   连接组件  
  
-   管理工具  
  
-   早期组件  
  
## <a name="see-also"></a>请参阅  
 [性能和容量规划](../core/performance-and-capacity-planning.md)
