---
title: 如何将绑定导入 BizTalk 组 |Microsoft Docs
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
ms.openlocfilehash: 1e2e29b96f36bea9a645da802da4dd10c2a67614
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65337082"
---
# <a name="how-to-import-bindings-into-a-biztalk-group"></a>如何将绑定导入 BizTalk 组
本主题介绍如何使用 BizTalk Server 管理控制台或命令行来绑定导入到 BizTalk 组中的.xml 文件。 有关 BizTalk 组中的绑定导出到.xml 文件，可以导入的说明，请参阅[如何为 BizTalk 组导出绑定](../core/how-to-export-bindings-for-a-biztalk-group.md)。  
  
 您还可以导入绑定到 BizTalk 应用程序，如中所述[如何将绑定导入到 BizTalk 应用程序](../core/how-to-import-bindings-into-a-biztalk-application.md)。  
  
## <a name="prerequisites"></a>先决条件  
 若要执行本主题中的过程，必须是 BizTalk Server Administrators 组的成员的帐户登录。 有关详细的权限的信息，请参阅[用于部署和管理 BizTalk 应用程序所需权限](../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md)。  
  
## <a name="to-import-bindings-into-a-biztalk-group"></a>若要将绑定导入 BizTalk 组  
  
#### <a name="using-the-biztalk-server-administration-console"></a>使用 BizTalk Server 管理控制台  
  
1. 单击**启动**，单击**所有程序**，单击[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]，然后单击**BizTalk Server 管理**。  
  
2. 在控制台树中，展开**BizTalk Server 管理**、 BizTalk 组，，然后右键单击**应用程序**。  
  
3. 指向**导入**，然后单击**绑定**。  
  
4. 单击绑定文件，然后单击**打开**。  
  
    绑定文件中的项目将写入到组。 它们的相应文件夹中显示\<的所有项目\>节点。  
  
#### <a name="using-the-command-line"></a>使用命令行  
  
1. 打开命令提示符，如下所示：单击**启动**，单击**运行**，类型`cmd`，然后单击**确定**。  
  
2. 键入以下命令，替换适当的值下, 表中所述：  
  
    **BTSTask ImportBindings /Source:** *value* **/GroupLevel** [**/Server:**<em>value</em>] [**/Database:**<em>value</em>]  
  
    例如，以下命令将导入绑定到名为 MyServer 的 SQL Server 实例上运行的 BizTalk 管理数据库中定义的组。  
  
    **BTSTask ImportBindings /GroupLevel /Server:MyServer /Database:BiztalkMgmtDb /Source:C:\Bindings\Binding1.xml**  
  
   |参数|ReplTest1|  
   |---------------|-----------|  
   |**/Source**|要导入，其中包括文件名的绑定文件的完整路径。 包含空格的路径必须括在引号 （"）。|  
   |**/GroupLevel**|绑定文件导入到当前组的选项。|  
   |**/Server**|承载 BizTalk 管理数据库，在窗体 ServerName\InstanceName，端口中的 SQL Server 实例的名称。<br /><br /> 实例名称仅是所需的实例名称不同于服务器名称时。 端口是仅在 SQL Server 使用的端口号而不是默认 (1433) 时所需。<br /><br /> 示例：<br /><br /> Server=MyServer<br /><br /> Server=MyServer\MySQLServer,1533<br /><br /> 如果未提供，则使用本地计算机上运行的 SQL Server 实例的名称。|  
   |**/Database**|BizTalk 管理数据库的名称。 如果未指定，使用 SQL Server 的本地实例中运行的 BizTalk 管理数据库。|  
  
## <a name="see-also"></a>请参阅  
 [导入 BizTalk 应用程序、 绑定和策略](../core/importing-biztalk-applications-bindings-and-policies.md)   
 [ImportBindings 命令](../core/importbindings-command.md)