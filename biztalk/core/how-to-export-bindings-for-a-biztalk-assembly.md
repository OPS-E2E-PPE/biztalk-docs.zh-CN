---
title: "如何导出 BizTalk 程序集绑定 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- assemblies, bindings
- assemblies, exporting
- exporting, assemblies
ms.assetid: 7e37348d-5fa5-43cc-b3c0-2d8cb6a8f394
caps.latest.revision: "20"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 64086cc8e54d89180d3c95268c78bc53e5ec9f55
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-export-bindings-for-a-biztalk-assembly"></a>如何导出 BizTalk 程序集绑定
本主题介绍如何使用 BizTalk Server 管理控制台或命令行将 BizTalk 程序集的绑定导出至 .xml 文件。 然后可以将这些绑定导入到 BizTalk 应用程序中，与现有绑定同名的导入绑定将覆盖现有绑定。 在更新程序集之前可能需要导出程序集的绑定，以便在更新之后再导入绑定，以重新应用它们。 有关更新应用程序和程序集的详细信息，请参阅[更新 BizTalk 应用程序](../core/updating-biztalk-applications.md)。 有关使用绑定文件的详细信息，请参阅[绑定文件和应用程序部署](../core/binding-files-and-application-deployment.md)。  
  
## <a name="prerequisites"></a>先决条件  
 要执行本主题中介绍的过程，必须以 BizTalk Server Administrators 组或 BizTalk Server Operators 组成员帐户登录。 有关更多详细权限的信息，请参阅[用于部署和管理 BizTalk 应用程序所需权限](../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md)。  
  
## <a name="to-export-bindings-for-a-biztalk-assembly"></a>导出 BizTalk 程序集的绑定  
  
#### <a name="using-the-biztalk-server-administration-console"></a>使用 BizTalk Server 管理控制台  
  
1.  单击**启动**，单击**所有程序**，单击[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]，然后单击**BizTalk Server 管理**。  
  
2.  在控制台树中，依次展开“[!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)]”、“BizTalk 组”和“应用程序”。  
  
3.  右键单击包含该程序集的应用，指向**导出**，然后单击**绑定**。  
  
4.  在导出绑定页上，在**导出到文件**，键入要导出绑定到的.xml 文件的绝对路径。  
  
     示例： **C:\Bindings\MyAssemblyBindings_Staging1.xml**  
  
5.  在导出绑定页上，单击**导出所选的程序集绑定**，然后在**程序集**，单击该程序集。  
  
6.  如果你想要导出的所有方信息组中，选择**导出全局方信息**。  
  
     绑定被导出到指定位置上的 .xml 文件中。  
  
#### <a name="using-the-command-line"></a>使用命令行  
  
1.  如下所示打开命令提示符： 单击**启动**，单击**运行**，类型`cmd`，然后单击**确定**。  
  
2.  键入以下命令，替换为适当的值下, 表中所述：  
  
     **BTSTask ExportBindings /Destination:** *值* **/AssemblyName:** *值*[**/GlobalParties**] [**/Server:***值*] [**/数据库：***值*]  
  
     例如：  
  
     **BTSTask ExportBindings /Destination:"C:\Binding Files\MyBindings.xml"/AssemblyName:"ErrorHandling.ErrorHandler，Version = 1.0.0.0，Culture = neutral，PublicKeyToken = 11e921d58826420e"/Server:MyDatabaseServer /Database:BizTalkMgmtDb**  
  
    |参数|值|  
    |---------------|-----------|  
    |**/ 目标**|要创建的绑定文件的完整路径，包含文件名。 如果已存在具有相同路径的绑定文件，则该文件将被覆盖。 如果路径中有空格，必须将它括在双引号 （"）。|  
    |**/ 程序集名称**|要从中导出绑定程序集的本地唯一标识符 (LUID)。 你可以通过使用获取应用程序中的项目的列表的 Luid [ListApp 命令](../core/listapp-command.md)。|  
    |**/ GlobalParties**|如果指定，则导出组的全局参与方信息。|  
    |**/ 服务器**|BizTalk 管理数据库的宿主 SQL Server 实例的名称，格式为“服务器名称\实例名称,端口”。<br /><br /> 只在实例名称与服务器名称不相同时才需要指定实例名称。 只在 SQL Server 不使用默认端口号 (1433) 时才需要指定端口。<br /><br /> 示例：<br /><br /> Server=MyServer<br /><br /> Server=MyServer\MySQLServer,1533<br /><br /> 如果未提供，则使用本地计算机上运行的 SQL Server 实例的名称。|  
    |**/ 数据库**|BizTalk 管理数据库的名称。 如果未指定，则使用在本地 SQL Server 实例中运行的 BizTalk 管理数据库。|  
  
## <a name="see-also"></a>另请参阅  
 [导出绑定](../core/exporting-bindings6.md)   
 [ExportBindings 命令](../core/exportbindings-command.md)   
 [导入 BizTalk 应用程序、 绑定和策略](../core/importing-biztalk-applications-bindings-and-policies.md)