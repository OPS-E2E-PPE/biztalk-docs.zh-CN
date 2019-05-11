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
ms.openlocfilehash: 6beaec0f6363765706d0eb248fa348e0aa5fe254
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65335094"
---
# <a name="how-to-remove-a-biztalk-assembly-from-an-application"></a>如何从应用程序删除 BizTalk 程序集
本主题介绍如何使用 BizTalk Server 管理控制台或命令行从 BizTalk 应用程序中删除 BizTalk 程序集。 执行此操作时，程序集和项目的包括，例如业务流程、 架构和管道，将从应用程序和 BizTalk 管理数据库中删除。  
  
 然后再删除 BizTalk 程序集，请记住以下重要事项：  
  
-   删除 BizTalk 程序集，程序集文件是不会自动删除从全局程序集缓存 (GAC) 或本地文件系统中，如果它不存在。 您必须手动删除它。 有关说明，请参阅[如何从 GAC 卸载程序集](http://msdn.microsoft.com/library/464706a8-f902-4d05-a724-19169facd2b4)并[如何删除其他文件和 BizTalk 应用程序设置](../core/how-to-remove-other-files-and-settings-for-a-biztalk-application.md)。  
  
-   如果删除包含管道的 BizTalk 程序集时，所有发送都端口都在同一个应用程序中使用该管道将重置为使用默认的 PassThruTransmit 管道。  
  
-   不能删除其他项目所依赖的 BizTalk 程序集。 必须先删除依赖项目。 然后可以删除 BizTalk 程序集。  
  
## <a name="prerequisites"></a>先决条件  
 若要执行本主题中的过程，必须是 BizTalk Server Administrators 组的成员的帐户登录。 有关详细的权限的信息，请参阅[用于部署和管理 BizTalk 应用程序所需权限](../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md)。  
  
## <a name="to-remove-a-biztalk-assembly-from-an-application"></a>若要从应用程序中删除 BizTalk 程序集  
  
#### <a name="using-the-biztalk-server-administration-console"></a>使用 BizTalk Server 管理控制台  
  
1. 单击**启动**，单击**所有程序**，单击[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]，然后单击**BizTalk Server 管理**。  
  
2. 在控制台树中，依次展开 BizTalk Server 管理、 BizTalk 组包含 BizTalk 程序集，若要删除，和包含 BizTalk 程序集的应用程序。  
  
3. 单击**资源**文件夹中，右键单击 BizTalk 程序集，然后依次**删除**。  
  
#### <a name="using-the-command-line"></a>使用命令行  
  
1. 打开命令提示符，如下所示：单击**启动**，单击**运行**，类型`cmd`，然后单击**确定**。  
  
2. 键入以下命令，替换适当的值下, 表中所述：  
  
    **BTSTask RemoveResource** [**/ApplicationName:**<em>value</em>] **/Luid:**<em>value</em> [**/Server:**<em>value</em>] [**/Database:**<em>value</em>]  
  
    例如：  
  
    **BTSTask RemoveResource /ApplicationName:MyApplication /Luid:"MyApp.Orchestrations, Version=1.0.0.0, Culture=neutral, PublicKeyToken=0123456789ABCDEF"**  
  
   |参数|Description|  
   |---------------|-----------------|  
   |**/ApplicationName**|包含 BizTalk 程序集的 BizTalk 应用程序若要删除的名称。 如果未指定此参数，则使用默认应用程序。 如果名称包含空格，则必须将其括在双引号 （"）。|  
   |**/Luid**|BizTalk 程序集的本地唯一标识符 (LUID)。 可通过获得 LUID **ListApp**命令，如中所述[ListApp 命令](../core/listapp-command.md)。|  
   |**/Server**|承载 BizTalk 管理数据库，在窗体 ServerName\InstanceName，端口中的 SQL Server 实例的名称。<br /><br /> 实例名称仅是所需的实例名称不同于服务器名称时。 端口是仅在 SQL Server 使用的端口号而不是默认 (1433) 时所需。<br /><br /> 示例：<br /><br /> Server=MyServer<br /><br /> Server=MyServer\MySQLServer,1533<br /><br /> 如果未提供，则使用本地计算机上运行的 SQL Server 实例的名称。|  
   |**/Database**|BizTalk 管理数据库的名称。 如果未指定，使用 SQL Server 的本地实例中运行的 BizTalk 管理数据库。|  
  
## <a name="see-also"></a>请参阅  
 [管理 BizTalk 程序集](../core/managing-biztalk-assemblies.md)   
 [RemoveResource 命令](../core/removeresource-command.md)