---
title: 硬件和软件要求 BizTalk Server 2016 |Microsoft 文档
description: 软件必备项和安装 BizTalk Server 2016 的受支持的版本列表
ms.custom: ''
ms.prod: biztalk-server
ms.date: 04/25/2018
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: f6120afd-310e-4155-8c23-aadb5b9a1a35
caps.latest.revision: 21
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: d473d3bf5be874edb430c80032935ddf2c7937bf
ms.sourcegitcommit: 770523695b34cc54db81f7ab7eba46f2bc19baec
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/26/2018
---
# <a name="hardware-and-software-requirements-for-biztalk-server-2016"></a>BizTalk Server 2016 的硬件和软件要求

## <a name="hardware-requirements"></a>硬件要求
下表列出了对 BizTalk Server 计算机的最低硬件要求。 在生产环境中，通信量可能会对服务器的硬件提出更高要求。 

| 资源  |最低要求 |
| --- | --- |
|计算机和处理器 | 具有与 Intel Pentium 兼容的 CPU 的计算机： <ul><li>单处理器为 1 GHz 或更高</li><li>双处理器为 900 MHz 或更高</li><li>四处理器为 700 MHz 或更高</li></ul> **注意**：支持超线程和双核处理器。<br/><br/>BizTalk Server 的 64 位版本要求运行在基于 x64 系统上的 64 位操作系统。 基于与 AMD64 (x86-64) 和扩展内存 64 位技术 (EM64T) 处理器结构兼容的 CPU 的计算机被视作基于 x64 的系统。<br/><br/>基于 Itanium 的系统上不支持 BizTalk Server。 |
|内存 | 2 GB 或更大|
|硬盘  |10 GB 的可用硬盘空间，用于包括操作系统和所有必备软件的完全安装。 硬盘必须是 NTFS 格式。|

> [!TIP] 
> 列出的是最低硬件要求。 每个环境都不同，可能你的环境具有更高要求。 请参阅 [Recommendations for Installing, Sizing, Deploying, and Maintaining a BizTalk Server Solution](http://social.technet.microsoft.com/wiki/contents/articles/666.recommendations-for-installing-sizing-deploying-and-maintaining-a-biztalk-server-solution.aspx)（BizTalk Server 解决方案的安装、大小调整、部署和维护建议）。 


## <a name="software-requirements--supported-versions"></a>软件要求和支持的版本

| 软件  |   版本 |  ...所必需 | 
| --- | --- | --- | 
| Microsoft Windows | <ul><li>Windows Server 2016</li><li>Windows Server 2012 R2</li><li>Windows 10</li><li>Windows 8.1 </li></ul> | | 
| Internet 信息服务 (IIS)   | 附带了操作系统的版本。<br/><br/> [KB 224609](https://support.microsoft.com/kb/224609) 列出了 IIS 版本。 | 提供可扩展的 Web 应用程序基础结构，这是 EDI、BAM 和 SharePoint 适配器所必需的。 |
| Windows Identity Foundation | 作为一种**功能**随操作系统一起提供。 | 可选。 <br/><br/>供 Windows SharePoint Services 客户端对象模型 (CSOM) 使用，安装 BizTalk Server 时会自动安装。 | 
| Microsoft SharePoint  | <ul><li>SharePoint Services 2016</li><li>SharePoint Services 2013 SP1</li><li>SharePoint Services Online</li></ul>  | 選擇性。 <br/><br/>如果你计划通过 SharePoint Services 接收或发送消息，则需要一台 SharePoint Services 计算机。 可将其与 BizTalk Server 安装在同一台计算机上，但最好安装在单独的计算机上。 |
| Microsoft Office  | <ul><li>Microsoft Office Excel 2016</li><li>Microsoft Office Excel 2013</li></ul>**注意**：BizTalk Server 仅支持 32 位版本的 Office。  | 選擇性。 <br/><br/>业务活动监视 (BAM) 需要它来显示业务流程的实时视图。 | 
| Microsoft .NET Framework  | <ul><li>.NET framework 4.7 (开头[CU2](https://support.microsoft.com/kb/4021095))</li><li>.NET Framework 4.6.*x* </li></ul>**请注意**： 在 Visual Studio 中创建 BizTalk 项目需要 Visual Studio 生成目标设置为.NET Framework 版本。 | 所有 BizTalk Server 托管组件都需要此软件。 | 
| Microsoft Visual Studio |Visual Studio 2015 | 選擇性。 <br/><br/>提供用于构建 BizTalk Server 应用程序的开发环境。 推荐 Ultimate Edition，但也支持 Premium 和 Professional Edition。 BizTalk Server 开发人员工具和 SDK 都需要此软件。 |
| Microsoft Visual C++ 2013 Redistributable Package | x86 和 x64 版本是必需的。 从[用于 Visual Studio 2013 的 Visual C++ 可再发行组件包](https://support.microsoft.com/help/3179560/update-for-visual-c-2013-and-visual-c-redistributable-package)处下载。    | 必需的。<br/><br/>Microsoft Visual C++ 可再发行组件包将安装所需的 Visual C++ 库的运行时组件，有了这些组件才能在未安装 Visual C++ 的计算机上运行使用 Visual C++ 开发的应用程序。<br/><br/>**注意**： <br/> 即使使用的是 Visual Studio 2015，也需要 2013 版本。|
| Microsoft SQL Server  | <ul><li>Microsoft SQL Server 2016</li><li>Microsoft SQL Server 2014 SP1</li></ul> | 这是 BizTalk Server 运行时、EDI 和 BAM 所必需的。 <br/><br/>为了获得最佳性能，Microsoft 建议使用 SQL Server Enterprise Edition。 若要从 Visual Studio 完整使用 BizTalk Server SDK 或部署 BizTalk Server 应用程序，请安装 SQL Server 开发工具。 <br/><br/>其他注意事项： <ul><li>若要使用 SQL Server AlwaysOn 可用性组 (AG)，请使用 SQL Server 2016 和更高版本。 仅 SQL Server 2016 AlwaysOn AG 支持 MSDTC；BizTalk 要求 MSDTC。 </li><li>SQL Server 标准版中不支持 BAM 实时聚合 (RTA)。 若要使用 BAM RTA，请安装 SQL Server Enterprise Edition。</li><li>不建议使用 SQL Server Express Edition。 Express Edition 不包括 BizTalk Server 需要的某些功能。</li><li>BizTalk Server 支持所有区分大小写和不区分大小写的 SQL Server 排序规则，二进制排序规则例外。 不支持二进制排序规则。</li></ul> |  |
| SQL Server Database Mail  | 随附于 SQL Server 的版本。 [配置 SQL Server 数据库邮件](https://msdn.microsoft.com/library/hh245116(v=sql.130).aspx)。| 選擇性。 <br/><br/>这是使用 BAM 警报所必需的。 | 
| SQL XML | SQL XML 4.0 Service Pack 1。 [下载 SqlXml 4.0 Service Pack 1 (SP1)](https://www.microsoft.com/en-us/download/details.aspx?id=30403)。 | 这是 BizTalk Server 运行时、管理工具和 BAM 所必需的。 <br/><br/> 通过 SQLXML，XML 能够支持 SQL Server 数据库。 开发人员使用它可以将 XML 和关系数据联系在一起。 可创建现有关系数据的 XML 视图，然后像使用 XML 文件一样来使用该视图。 <br/><br/>**注意**： <br/>可再发行的 CAB 文件将自动安装它。 SQL XML 可能有其自己的软件要求（如 `.NET Framework 3.5` 和 `.NET Framework 2.0`），这不包括在 CAB 文件中。 如果 BizTalk Server 可访问 Internet，则可能会自动安装 SQL XML 软件要求。 如果 BizTalk Server 不可访问 Internet，请手动安装 SQL XML 软件要求。| 
| WinSCP | WinSCP 版本 5.7.7。 [下载 WinSCP](http://winscp.net)。| 这是使用 SFTP 适配器所必需的。 |
| MQSeries 适配器 | <ul><li>IBM WebSphere MQ 8</li><li>IBM WebSphere MQ 9 （从 BizTalk 2016 CU4 开始）</li></ul> | 選擇性。<br/>仅在使用 IBM WebSphere MQ 时，才需要。 |
|LOB 和企业系统 | [支持的业务线 (LOB) 和企业系统](https://social.technet.microsoft.com/wiki/contents/articles/17631.biztalk-server-supported-line-of-business-lob-and-enterprise-systems.aspx)列出支持的版本。 | 在 BizTalk 适配器包中都使用适配器时需要。 <br/><br/> [BizTalk 适配器包](../adapters-and-accelerators/biztalk-adapter-pack.md)列出可用的系统的适配器。 |

## <a name="service-pack-and-cumulative-update-support"></a>Service Pack 和累积更新支持

BizTalk Server 支持所有 service pack、 累积更新、 安全更新和修补程序。 强烈建议安装 Windows、SQL Server、Visual Studio 和任何已安装程序的最新更新。 根据 Microsoft 产品的基准支持提供对该产品 Service Pack 的支持。 有关 BizTalk Server、SQL Server、Visual Studio 及其他 Microsoft 程序，请参阅[支持生命周期索引](http://go.microsoft.com/fwlink/p/?LinkID=151890)。

[BizTalk Server 的 service Pack 和累积更新列表](https://support.microsoft.com/help/2555976)

 ## <a name="next-step"></a>下一步
 
 [设置和安装必备组件](../install-and-config-guides/set-up-and-install-prerequisites-for-biztalk-server-2016.md)
