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
ms.openlocfilehash: 0af1ab10400b51515b3041e12935e571eb76be69
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65397961"
---
# <a name="how-to-remove-a-net-assembly-certificate-or-other-resource-artifact-from-an-application"></a>如何从应用程序中删除.NET 程序集、 证书或其他资源项目
本主题介绍如何使用 BizTalk Server 管理控制台或命令行从 BizTalk 应用程序中删除以下资源项目。 使用本主题中的过程从 BizTalk 管理数据库中删除该项目。 如果它存在于这些位置中，它不会从文件系统、 证书存储区、 Internet 信息服务 (IIS) 或 Windows 注册表中，删除该项目。 此外，如果删除绑定文件，则绑定保持不变，删除只绑定文件。  
  
- .NET 程序集  
  
- COM 组件  
  
- 证书  
  
- 特别文件  
  
- BAM 定义  
  
- 绑定文件  
  
- 虚拟目录  
  
  如果虚拟目录显式添加到应用程序，同时从导入或添加，通过它可以通过使用本主题中的过程中删除。 如果它未显式添加，但而不是已通过引用来添加配置接收位置时，无法通过使用本主题中的过程中将其删除。 这是因为 BizTalk 管理数据库中不存储的虚拟目录。 导出应用程序.msi 文件时将从 IIS 获取虚拟目录，并将其添加到.msi 文件中。 导入.msi 文件时，虚拟目录将添加到该组的 BizTalk 管理数据库。  
  
## <a name="prerequisites"></a>先决条件  
 若要执行本主题中的过程，必须是 BizTalk Server Administrators 组的成员的帐户登录。 有关详细的权限的信息，请参阅[用于部署和管理 BizTalk 应用程序所需权限](../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md)。  
  
## <a name="to-remove-a-resource-artifact-from-an-application"></a>若要从应用程序中删除资源项目  
  
#### <a name="using-the-biztalk-server-administration-console"></a>使用 BizTalk Server 管理控制台  
  
1. 单击**启动**，单击**程序**，单击[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]，然后单击**BizTalk Server 管理**。  
  
2. 在控制台树中，依次展开 BizTalk Server 管理、 包含的资源项目的 BizTalk 组删除，和包含该项目的应用程序。  
  
3. 单击**资源**文件夹，右键单击该项目，然后单击**删除**。  
  
#### <a name="using-the-command-line"></a>使用命令行  
  
1. 打开命令提示符，如下所示：单击**启动**，单击**运行**，类型`cmd`，然后单击**确定**。  
  
2. 键入以下命令，替换适当的值下, 表中所述：  
  
    **BTSTask RemoveResource** [**/ApplicationName:**<em>value</em>] **/Luid:**<em>value</em> [**/Server:**<em>value</em>] [**/Database:**<em>value</em>]  
  
    例如：  
  
    **BTSTask RemoveResource /ApplicationName:MyApplication /Luid:"MyAssembly, Version=1.0.0.0, Culture=neutral, PublicKeyToken=0123456789ABCDEF"**  
  
   |参数|Description|  
   |---------------|-----------------|  
   |**/ApplicationName**|包含项目的 BizTalk 应用程序若要删除的名称。 如果未指定，则使用默认应用程序。 如果名称包含空格，则必须将其括在双引号 （"）。|  
   |**/Luid**|项目的本地唯一标识符 (LUID)。 可通过获得 LUID **ListApp**命令，如中所述[ListApp 命令](../core/listapp-command.md)。|  
   |**/Server**|承载 BizTalk 管理数据库，在窗体 ServerName\InstanceName，端口中的 SQL Server 实例的名称。<br /><br /> 实例名称仅是所需的实例名称不同于服务器名称时。 端口是仅在 SQL Server 使用的端口号而不是默认 (1433) 时所需。<br /><br /> 示例：<br /><br /> Server=MyServer<br /><br /> Server=MyServer\MySQLServer,1533<br /><br /> 如果未提供，则使用本地计算机上运行的 SQL Server 实例的名称。|  
   |**/Database**|BizTalk 管理数据库的名称。 如果未指定，使用 SQL Server 的本地实例中运行的 BizTalk 管理数据库。|  
  
## <a name="see-also"></a>请参阅  
 [管理.NET 程序集、 证书和其他资源](../core/managing-net-assemblies-certificates-and-other-resources.md)   
 [RemoveResource 命令](../core/removeresource-command.md)