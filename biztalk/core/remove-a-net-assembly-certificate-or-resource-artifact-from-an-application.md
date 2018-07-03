---
title: 如何从应用程序中删除.NET 程序集、 证书或其他资源项目 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- virtual directories, deleting
- managing [.NET assemblies], deleting
- managing [applications], COM components
- managing [applications], deleting artifcats
- managing [certificates], deleting
- deleting, binding files
- binding files, deleting
- managing, COM components
- COM components, deleting
- managing [artifacts], deleting
- .NET assemblies, deleting
- deleting, virtual directories
- deleting, definitions [BAM]
- applications, .NET assemblies
- certificates, deleting
- deleting, .NET assemblies
- deleting, artifacts
- deleting, certificates
ms.assetid: b84eebac-261d-495f-80cd-ddda5bb08bef
caps.latest.revision: 14
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 1dce140e7adeaf6115ad2f8b2199a3a77292a953
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "37002918"
---
# <a name="how-to-remove-a-net-assembly-certificate-or-other-resource-artifact-from-an-application"></a>如何从应用程序中删除 .NET 程序集、证书或其他资源项目
本主题描述如何使用 BizTalk Server 管理控制台或命令行从 BizTalk 应用程序删除以下资源项目。 使用本主题中的过程可以从 BizTalk 管理数据库中删除项目。 这一删除不会从文件系统、证书存储、Internet 信息服务 (IIS) 或 Windows 注册表中删除项目（如果项目存在于这些位置中）。 此外，如果您删除某一绑定文件，则绑定保持不变，仅删除该绑定文件。  
  
- .NET 程序集  
  
- COM 组件  
  
- 证书  
  
- 特别文件  
  
- BAM 定义  
  
- 绑定文件  
  
- 虚拟目录  
  
  如果通过导入或添加将某一虚拟目录显式添加到某一应用程序，则可以通过使用本主题中的过程删除该虚拟目录。 如果虚拟目录不是显式添加的，而是在配置接收位置时由引用添加的，则不能通过使用本主题中的过程删除该虚拟目录。 这是因为，虚拟目录不存储于 BizTalk 管理数据库中。 在导出应用程序的 .msi 文件时，将从 IIS 获取虚拟目录并将虚拟目录添加到 .msi 文件中。 在导入 .msi 文件时，虚拟目录将添加到该组的 BizTalk 管理数据库中。  
  
## <a name="prerequisites"></a>必要條件  
 若要执行本主题中的过程，必须是 BizTalk Server Administrators 组的成员的帐户登录。 有关详细的权限的信息，请参阅[用于部署和管理 BizTalk 应用程序所需权限](../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md)。  
  
## <a name="to-remove-a-resource-artifact-from-an-application"></a>从应用程序中删除资源项目  
  
#### <a name="using-the-biztalk-server-administration-console"></a>使用 BizTalk Server 管理控制台  
  
1. 单击**启动**，单击**程序**，单击[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]，然后单击**BizTalk Server 管理**。  
  
2. 在控制台树中，依次展开 BizTalk Server 管理、 包含的资源项目的 BizTalk 组删除，和包含该项目的应用程序。  
  
3. 单击**资源**文件夹，右键单击该项目，然后单击**删除**。  
  
#### <a name="using-the-command-line"></a>使用命令行  
  
1. 按如下所示打开命令提示符： 单击**启动**，单击**运行**，类型`cmd`，然后单击**确定**。  
  
2. 键入以下命令，替换适当的值下, 表中所述：  
  
    **BTSTask RemoveResource** [**/ApplicationName:**<em>值</em>] **/Luid:**<em>值</em>[**/Server:** <em>值</em>] [**/database:**<em>值</em>]  
  
    例如：  
  
    **BTSTask RemoveResource /ApplicationName:MyApplication /Luid:"MyAssembly，版本 = 1.0.0.0，区域性 = 中性，PublicKeyToken = 0123456789ABCDEF"**  
  
   |参数|Description|  
   |---------------|-----------------|  
   |**/ 应用程序名称**|包含要删除的项目的 BizTalk 应用程序的名称。 如果未指定，则使用默认应用程序。 如果名称包含空格，则必须将其括在双引号 （"）。|  
   |**/ Luid**|项目的本地唯一标识符 (LUID)。 可通过获得 LUID **ListApp**命令，如中所述[ListApp 命令](../core/listapp-command.md)。|  
   |**/ 服务器**|BizTalk 管理数据库的宿主 SQL Server 实例的名称，格式为“服务器名称\实例名称,端口”。<br /><br /> 只在实例名称与服务器名称不相同时才需要指定实例名称。 只在 SQL Server 不使用默认端口号 (1433) 时才需要指定端口。<br /><br /> 示例：<br /><br /> Server=MyServer<br /><br /> Server=MyServer\MySQLServer,1533<br /><br /> 如果未提供，则使用本地计算机上运行的 SQL Server 实例的名称。|  
   |**/ 数据库**|BizTalk 管理数据库的名称。 如果未指定，则使用在本地 SQL Server 实例中运行的 BizTalk 管理数据库。|  
  
## <a name="see-also"></a>请参阅  
 [管理.NET 程序集、 证书和其他资源](../core/managing-net-assemblies-certificates-and-other-resources.md)   
 [RemoveResource 命令](../core/removeresource-command.md)