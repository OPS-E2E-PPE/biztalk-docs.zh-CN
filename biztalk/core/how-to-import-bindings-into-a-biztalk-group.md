---
title: 如何将绑定导入到 BizTalk 组 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- groups, importing
- importing, bindings
- groups, bindings
- bindings, groups
ms.assetid: 38da14fb-3522-4274-a633-2ff24e4bd574
caps.latest.revision: 17
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a64bac6c64a9aadc772bfe8445b23f87b469471d
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/28/2017
ms.locfileid: "25970131"
---
# <a name="how-to-import-bindings-into-a-biztalk-group"></a>如何将绑定导入到 BizTalk 组
本主题介绍如何使用 BizTalk Server 管理控制台或命令行通过 .xml 文件向 BizTalk 组导入绑定。 有关将绑定从 BizTalk 组导出到.xml 文件，你可以导入的说明，请参阅[如何导出绑定 BizTalk 组](../core/how-to-export-bindings-for-a-biztalk-group.md)。  
  
 你还可以导入绑定到 BizTalk 应用程序，如中所述[如何导入到 BizTalk 应用程序的绑定](../core/how-to-import-bindings-into-a-biztalk-application.md)。  
  
## <a name="prerequisites"></a>先决条件  
 若要执行本主题中的过程，必须使用 BizTalk Server Administrators 组的成员帐户登录。 有关更多详细权限的信息，请参阅[用于部署和管理 BizTalk 应用程序所需权限](../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md)。  
  
## <a name="to-import-bindings-into-a-biztalk-group"></a>将绑定导入到 BizTalk 组  
  
#### <a name="using-the-biztalk-server-administration-console"></a>使用 BizTalk Server 管理控制台  
  
1.  单击**启动**，单击**所有程序**，单击[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]，然后单击**BizTalk Server 管理**。  
  
2.  在控制台树中，展开**BizTalk Server 管理**，展开 BizTalk 组，然后右键单击**应用程序**。  
  
3.  指向**导入**，然后单击**绑定**。  
  
4.  单击绑定文件，然后单击**打开**。  
  
     绑定文件中的项目将写入该组。 它们的相应文件夹中显示\<所有项目\>节点。  
  
#### <a name="using-the-command-line"></a>使用命令行  
  
1.  如下所示打开命令提示符： 单击**启动**，单击**运行**，类型`cmd`，然后单击**确定**。  
  
2.  键入以下命令，替换为适当的值下, 表中所述：  
  
     **BTSTask ImportBindings /Source:** *值* **/GroupLevel** [**/Server:***值*] [**/数据库：***值*]  
  
     例如，以下命令将绑定导入到 BizTalk 管理数据库中所定义的组，该 BizTalk 管理数据库运行在名为 MyServer 的 SQL Server 实例上。  
  
     **BTSTask ImportBindings GroupLevel /Server:MyServer /Database:BiztalkMgmtDb /Source:C:\Bindings\Binding1.xml**  
  
    |参数|值|  
    |---------------|-----------|  
    |**/ 源**|要导入的绑定文件的完整路径，包含文件名。 包含空格的路径必须放在引号 (") 中。|  
    |**/ GroupLevel**|将绑定文件导入到当前组的选项。|  
    |**/ 服务器**|BizTalk 管理数据库的宿主 SQL Server 实例的名称，格式为“服务器名称\实例名称,端口”。<br /><br /> 只在实例名称与服务器名称不相同时才需要指定实例名称。 只在 SQL Server 不使用默认端口号 (1433) 时才需要指定端口。<br /><br /> 示例：<br /><br /> Server=MyServer<br /><br /> Server=MyServer\MySQLServer,1533<br /><br /> 如果未提供，则使用本地计算机上运行的 SQL Server 实例的名称。|  
    |**/ 数据库**|BizTalk 管理数据库的名称。 如果未指定，则使用在本地 SQL Server 实例中运行的 BizTalk 管理数据库。|  
  
## <a name="see-also"></a>另请参阅  
 [导入 BizTalk 应用程序、 绑定和策略](../core/importing-biztalk-applications-bindings-and-policies.md)   
 [ImportBindings 命令](../core/importbindings-command.md)