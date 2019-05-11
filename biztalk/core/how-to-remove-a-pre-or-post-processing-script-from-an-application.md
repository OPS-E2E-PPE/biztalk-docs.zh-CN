---
title: 如何从应用程序删除预处理或后处理脚本 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- managing [scripts], deleting
- deleting, scripts
- managing [applications], scripts
- scripts, deleting
- applications, scripts
ms.assetid: 7911f098-97f2-4a5d-87fe-20b55231113e
caps.latest.revision: 14
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 4af32e7aa3edae39fb43c1bf884c97ec376c7acf
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65384382"
---
# <a name="how-to-remove-a-pre--or-post-processing-script-from-an-application"></a>如何从应用程序删除预处理或后处理脚本
本主题介绍如何使用 BizTalk Server 管理控制台或命令行从应用程序删除预处理或后处理脚本。 这样，以便在应用程序.msi 文件中将不导出从 BizTalk 管理数据库中删除的脚本。 如果存在，这不会不删除从本地文件系统中，脚本。  
  
 如果已在本地文件系统上，安装包含该脚本的应用程序和脚本设计为在卸载期间运行，则必须从文件系统，以防止其运行时卸载应用程序中删除该脚本。  
  
## <a name="prerequisites"></a>先决条件  
 若要执行本主题中的过程，必须是 BizTalk Server Administrators 组的成员的帐户登录。 有关详细的权限的信息，请参阅[用于部署和管理 BizTalk 应用程序所需权限](../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md)。  
  
## <a name="to-remove-a-script-from-an-application"></a>若要从应用程序中删除脚本  
  
#### <a name="using-the-biztalk-server-administration-console"></a>使用 BizTalk Server 管理控制台  
  
1. 单击**启动**，单击**所有程序**，单击[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]，然后单击**BizTalk Server 管理**。  
  
2. 在控制台树中，展开[!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)]，展开包含该脚本的 BizTalk 组删除，，然后展开包含该脚本的应用程序。  
  
3. 单击**资源**文件夹中，右键单击脚本，然后依次**删除**。  
  
#### <a name="using-the-command-line"></a>使用命令行  
  
1. 打开命令提示符，如下所示：单击**启动**，单击**运行**，类型`cmd`，然后单击**确定**。  
  
2. 键入以下命令，替换适当的值下, 表中所述：  
  
    **BTSTask RemoveResource** [**/ApplicationName:**<em>value</em>] **/Luid:**<em>value</em> [**/Server:**<em>value</em>] [**/Database:**<em>value</em>]  
  
    例如：  
  
    **BTSTask RemoveResource /ApplicationName:MyApplication /Luid:"MyApplication:MyScript.vbs"**  
  
   |参数|Description|  
   |---------------|-----------------|  
   |**/ApplicationName**|包含 BizTalk 脚本的 BizTalk 应用程序若要删除的名称。 如果名称包含空格，则必须放在双引号 （"） 中。 如果未指定此参数，则使用默认应用程序。|  
   |**/Luid**|该脚本的本地唯一标识符 (LUID)。 可通过获得 LUID [ListApp 命令](../core/listapp-command.md)。|  
   |**/Server**|承载 BizTalk 管理数据库，在窗体 ServerName\InstanceName，端口中的 SQL Server 实例的名称。<br /><br /> 实例名称仅是所需的实例名称不同于服务器名称时。 端口是仅在 SQL Server 使用的端口号而不是默认 (1433) 时所需。<br /><br /> 示例：<br /><br /> Server=MyServer<br /><br /> Server=MyServer\MySQLServer,1533<br /><br /> 如果未提供，则使用本地计算机上运行的 SQL Server 实例的名称。|  
   |**/Database**|BizTalk 管理数据库的名称。 如果未指定，使用 SQL Server 的本地实例中运行的 BizTalk 管理数据库。|  
  
## <a name="see-also"></a>请参阅  
 [管理预处理和后处理脚本](../core/managing-pre-and-post-processing-scripts.md)   
 [RemoveResource 命令](../core/removeresource-command.md)