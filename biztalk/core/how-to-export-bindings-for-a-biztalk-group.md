---
title: 如何导出绑定 BizTalk 组 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- bindings, exporting
- groups, bindings
- groups, exporting
ms.assetid: 51955266-f87f-41c9-992c-93036b40f663
caps.latest.revision: 23
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: df08f99a9e37bf1a4d4a794c17d483fdc381f463
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22253981"
---
# <a name="how-to-export-bindings-for-a-biztalk-group"></a>如何导出绑定 BizTalk 组
本主题介绍如何使用 BizTalk Server 管理控制台或命令行将 BizTalk 组的绑定导出至 .xml 文件。 你可以然后导入这些绑定到 BizTalk 组或应用程序中所述[如何导入绑定到 BizTalk 组](../core/how-to-import-bindings-into-a-biztalk-group.md)和[如何导入到 BizTalk 应用程序的绑定](../core/how-to-import-bindings-into-a-biztalk-application.md)。 有关使用绑定文件的详细信息，请参阅[绑定文件和应用程序部署](../core/binding-files-and-application-deployment.md)。  
  
> [!NOTE]
>  导出某个组的绑定时将始终导出全局参与方信息，无论是否指定此选项。  
  
## <a name="prerequisites"></a>先决条件  
 要执行本主题中介绍的过程，必须以 BizTalk Server Administrators 组或 BizTalk Operators 组成员帐户登录。 有关更多详细权限的信息，请参阅[用于部署和管理 BizTalk 应用程序所需权限](../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md)。  
  
## <a name="to-export-bindings-for-a-biztalk-group"></a>导出 BizTalk 组的绑定  
  
#### <a name="using-the-biztalk-server-administration-console"></a>使用 BizTalk Server 管理控制台  
  
1.  单击**启动**，单击**所有程序**，单击[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]，然后单击**BizTalk Server 管理**。  
  
2.  在控制台树中，展开[!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)]，展开 BizTalk 组，右键单击**应用程序**，指向**导出**，然后单击**绑定**。  
  
3.  在导出绑定页上，在**导出到文件**，键入要导出绑定到的.xml 文件的绝对路径。  
  
     示例： C:\Bindings\Group1Bindings_Staging1.xml  
  
4.  确保**导出当前组中的所有绑定**已选择，然后单击**确定**。  
  
     绑定被导出到指定位置上的 .xml 文件中。  
  
#### <a name="using-the-command-line"></a>使用命令行  
  
1.  如下所示打开命令提示符： 单击**启动**，单击**运行**，类型`cmd`，然后单击**确定**。  
  
2.  键入以下命令，替换为适当的值下, 表中所述：  
  
     **BTSTask ExportBindings /Destination:** *值* **/GroupLevel** [**/GlobalParties**] [**/Server:** *值*] [**/数据库：***值*]  
  
     例如：  
  
     **BTSTask ExportBindings /Destination:"C:\Binding Files\MyBindings.xml"GroupLevel /Server:MyDatabaseServer /Database:BizTalkMgmtDb**  
  
    |参数|值|  
    |---------------|-----------|  
    |**/ 目标**|要创建的绑定文件的完整路径，包含文件名。 如果已存在具有相同路径的绑定文件，则该文件将被覆盖。 如果路径中有空格，必须将它括在双引号 （"）。|  
    |**/ GroupLevel**|如果指定，则当前 BizTalk 组中的所有绑定均被导出。|  
    |**/ GlobalParties**|如果指定，将为组的全局参与方信息导出。|  
    |**/ 服务器**|BizTalk 管理数据库的宿主 SQL Server 实例的名称，格式为“服务器名称\实例名称,端口”。<br /><br /> 只在实例名称与服务器名称不相同时才需要指定实例名称。 只在 SQL Server 不使用默认端口号 (1433) 时才需要指定端口。<br /><br /> 示例：<br /><br /> Server=MyServer<br /><br /> Server=MyServer\MySQLServer,1533<br /><br /> 如果未提供，则使用本地计算机上运行的 SQL Server 实例的名称。|  
    |**/ 数据库**|BizTalk 管理数据库的名称。 如果未指定，则使用在本地 SQL Server 实例中运行的 BizTalk 管理数据库。|  
  
## <a name="see-also"></a>另请参阅  
 [导出绑定](../core/exporting-bindings6.md)   
 [ExportBindings 命令](../core/exportbindings-command.md)   
 [导入 BizTalk 应用程序、 绑定和策略](../core/importing-biztalk-applications-bindings-and-policies.md)