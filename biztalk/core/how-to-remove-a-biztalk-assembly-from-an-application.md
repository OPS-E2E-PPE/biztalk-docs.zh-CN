---
title: 如何从应用程序删除 BizTalk 程序集 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- managing [applications], assemblies
- assemblies, deleting
- deleting, assemblies
- applications, assemblies
- managing [assemblies], deleting
ms.assetid: 0691c3b6-476d-4e01-b50b-47d7c0b299bf
caps.latest.revision: 13
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b0865c55480710e52c4d4d87d444d35ac48f0dd0
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36987830"
---
# <a name="how-to-remove-a-biztalk-assembly-from-an-application"></a>如何从应用程序中删除 BizTalk 程序集
本主题介绍如何使用 BizTalk Server 管理控制台或命令行从 BizTalk 应用程序删除 BizTalk 程序集。 执行此操作时，程序集和其中包含的项目（如业务流程、架构和管道）都将从应用程序和 BizTalk 管理数据库中删除。  
  
 在删除 BizTalk 程序集之前，请切记以下几点重要事项：  
  
-   删除 BizTalk 程序集时，程序集文件不会自动从全局程序集缓存 (GAC) 或本地文件系统中删除（如果存在）。 您必须手动删除它。 有关说明，请参阅[如何从 GAC 卸载程序集](http://msdn.microsoft.com/library/464706a8-f902-4d05-a724-19169facd2b4)并[如何删除其他文件和 BizTalk 应用程序设置](../core/how-to-remove-other-files-and-settings-for-a-biztalk-application.md)。  
  
-   如果删除包含管道的 BizTalk 程序集，则同一应用程序中使用该管道的所有发送端口都将重置为使用默认的 PassThruTransmit 管道。  
  
-   不能删除其他项目所依赖的 BizTalk 程序集。 必须首先删除依存项目。 然后才能删除 BizTalk 程序集。  
  
## <a name="prerequisites"></a>必要條件  
 若要执行本主题中的过程，必须是 BizTalk Server Administrators 组的成员的帐户登录。 有关详细的权限的信息，请参阅[用于部署和管理 BizTalk 应用程序所需权限](../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md)。  
  
## <a name="to-remove-a-biztalk-assembly-from-an-application"></a>从应用程序中删除 BizTalk 程序集  
  
#### <a name="using-the-biztalk-server-administration-console"></a>使用 BizTalk Server 管理控制台  
  
1. 单击**启动**，单击**所有程序**，单击[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]，然后单击**BizTalk Server 管理**。  
  
2. 在控制台树中，依次展开 BizTalk Server 管理、 BizTalk 组包含 BizTalk 程序集，若要删除，和包含 BizTalk 程序集的应用程序。  
  
3. 单击**资源**文件夹中，右键单击 BizTalk 程序集，然后依次**删除**。  
  
#### <a name="using-the-command-line"></a>使用命令行  
  
1. 按如下所示打开命令提示符： 单击**启动**，单击**运行**，类型`cmd`，然后单击**确定**。  
  
2. 键入以下命令，替换适当的值下, 表中所述：  
  
    **BTSTask RemoveResource** [**/ApplicationName:**<em>值</em>] **/Luid:**<em>值</em>[**/Server:** <em>值</em>] [**/database:**<em>值</em>]  
  
    例如：  
  
    **BTSTask RemoveResource /ApplicationName:MyApplication /Luid:"MyApp.Orchestrations，版本 = 1.0.0.0，区域性 = 中性，PublicKeyToken = 0123456789ABCDEF"**  
  
   |参数|Description|  
   |---------------|-----------------|  
   |**/ 应用程序名称**|包含要删除的 BizTalk 程序集的 BizTalk 应用程序的名称。 如果未指定此参数，则使用默认的应用程序。 如果名称包含空格，则必须将其括在双引号 （"）。|  
   |**/ Luid**|BizTalk 程序集的本地唯一标识符 (LUID)。 可通过获得 LUID **ListApp**命令，如中所述[ListApp 命令](../core/listapp-command.md)。|  
   |**/ 服务器**|BizTalk 管理数据库的宿主 SQL Server 实例的名称，格式为“服务器名称\实例名称,端口”。<br /><br /> 只在实例名称与服务器名称不相同时才需要指定实例名称。 只在 SQL Server 不使用默认端口号 (1433) 时才需要指定端口。<br /><br /> 示例：<br /><br /> Server=MyServer<br /><br /> Server=MyServer\MySQLServer,1533<br /><br /> 如果未提供，则使用本地计算机上运行的 SQL Server 实例的名称。|  
   |**/ 数据库**|BizTalk 管理数据库的名称。 如果未指定，则使用在本地 SQL Server 实例中运行的 BizTalk 管理数据库。|  
  
## <a name="see-also"></a>请参阅  
 [管理 BizTalk 程序集](../core/managing-biztalk-assemblies.md)   
 [RemoveResource 命令](../core/removeresource-command.md)