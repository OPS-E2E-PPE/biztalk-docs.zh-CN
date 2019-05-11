---
title: 如何导出 BizTalk 应用程序的绑定 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- bindings, exportings
- applications, exporting
- applications, bindings
ms.assetid: 700d2781-480b-42ed-a313-1a67a7406369
caps.latest.revision: 22
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 6750ff2f6684942c20eb4fdaa286dcbc181bb5b2
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65385052"
---
# <a name="how-to-export-bindings-for-a-biztalk-application"></a>如何导出 BizTalk 应用程序的绑定
本主题介绍如何使用 BizTalk Server 管理控制台或命令行导出到.xml 文件的 BizTalk 应用程序的绑定。 您然后可以导入另一个应用程序，使用相同名称的导入绑定将覆盖在应用程序中的当前绑定的绑定文件。 有关详细信息，请参阅[导入绑定到 BizTalk 应用程序如何](../core/how-to-import-bindings-into-a-biztalk-application.md)。 有关使用绑定文件的详细信息，请参阅[绑定文件和应用程序部署](../core/binding-files-and-application-deployment.md)。  
  
## <a name="prerequisites"></a>先决条件  
 若要执行本主题中的过程，必须是 BizTalk Server Administrators 或 BizTalk Server Operators 组的成员的帐户登录。 有关详细的权限的信息，请参阅[用于部署和管理 BizTalk 应用程序所需权限](../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md)。  
  
## <a name="to-export-bindings-for-a-biztalk-application"></a>导出 BizTalk 应用程序的绑定  
  
#### <a name="using-the-biztalk-server-administration-console"></a>使用 BizTalk Server 管理控制台  
  
1. 单击**启动**，单击**所有程序**，单击[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]，然后单击**BizTalk Server 管理**。  
  
2. 在控制台树中，展开[!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)]，展开 BizTalk 组，然后展开**应用程序**。  
  
3. 右键单击你想要导出，其的绑定指向应用程序**导出**，然后单击**绑定**。  
  
4. 在导出绑定页上，在**导出到文件**，键入要导出绑定到的.xml 文件的绝对路径。  
  
    例如：**C:\Bindings\Application1Bindings_Staging1.xml**  
  
5. 絋粄**导出当前应用程序中的所有绑定**已选中，然后单击**确定**。  
  
6. 若要导出组的所有参与方信息，请选择**导出全局参与方信息**复选框。  
  
    绑定被导出到.xml 文件中指定的位置。  
  
#### <a name="using-the-command-line"></a>使用命令行  
  
1. 打开命令提示符，如下所示：单击**启动**，单击**运行**，类型`cmd`，然后单击**确定**。  
  
2. 键入以下命令，替换适当的值下, 表中所述：  
  
    **BTSTask ExportBindings /Destination:** *值*[**/ApplicationName:**<em>值</em>] [**/GlobalParties**] [**/Server:**<em>值</em>] [**/database:**<em>值</em>]  
  
    例如：  
  
    **BTSTask ExportBindings /Destination:"C:\Binding Files\MyBindings.xml" /ApplicationName:MyApplication /Server:MyDatabaseServer /Database:BizTalkMgmtDb**  
  
   |参数|ReplTest1|  
   |---------------|-----------|  
   |**/ 目标**|若要创建，其中包括文件名的绑定文件的完整路径。 如果绑定文件具有相同的路径已存在，则将覆盖。 如果路径中有空格，则必须将其括在双引号 （"）。|  
   |**/ApplicationName**|从中导出绑定的应用程序名称。 该应用程序必须存在。 若要验证的应用程序名称，可以使用**ListApps**命令，如中所述[ListApps 命令](../core/listapps-command.md)。 如果未指定此参数，则使用默认 BizTalk 应用程序。 如果名称中有空格，则必须将其括在双引号 （"）。|  
   |**/GlobalParties**|如果指定，将导出组的全局参与方信息。|  
   |**/Server**|承载 BizTalk 管理数据库，在窗体 ServerName\InstanceName，端口中的 SQL Server 实例的名称。<br /><br /> 实例名称仅是所需的实例名称不同于服务器名称时。 端口是仅在 SQL Server 使用的端口号而不是默认 (1433) 时所需。<br /><br /> 示例：<br /><br /> Server=MyServer<br /><br /> Server=MyServer\MySQLServer,1533<br /><br /> 如果未提供，则使用本地计算机上运行的 SQL Server 实例的名称。|  
   |**/Database**|BizTalk 管理数据库的名称。 如果未指定，使用 SQL Server 的本地实例中运行的 BizTalk 管理数据库。|  
  
## <a name="see-also"></a>请参阅  
 [导出绑定](../core/exporting-bindings6.md)   
 [ExportBindings 命令](../core/exportbindings-command.md)   
 [导入 BizTalk 应用程序、绑定和策略](../core/importing-biztalk-applications-bindings-and-policies.md)