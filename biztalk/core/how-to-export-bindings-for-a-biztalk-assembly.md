---
title: 如何导出 BizTalk 程序集的绑定 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- assemblies, bindings
- assemblies, exporting
- exporting, assemblies
ms.assetid: 7e37348d-5fa5-43cc-b3c0-2d8cb6a8f394
caps.latest.revision: 20
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 2807e0832dae1722e2b0b15e7b098246784bca88
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65337775"
---
# <a name="how-to-export-bindings-for-a-biztalk-assembly"></a>如何导出 BizTalk 程序集的绑定
本主题介绍如何使用 BizTalk Server 管理控制台或命令行来将 BizTalk 程序集的绑定导出到.xml 文件。 然后可以这些绑定导入到 BizTalk 应用程序，将使用相同名称的导入绑定覆盖现有绑定。 您可能想要导出的程序集绑定之后更新，以便更新以重新应用它们之后，您可以导入绑定。 有关更新应用程序和程序集的详细信息，请参阅[更新 BizTalk 应用程序](../core/updating-biztalk-applications.md)。 有关使用绑定文件的详细信息，请参阅[绑定文件和应用程序部署](../core/binding-files-and-application-deployment.md)。  
  
## <a name="prerequisites"></a>先决条件  
 若要执行本主题中的过程，必须是 BizTalk Server Administrators 或 BizTalk Server Operators 组的成员的帐户登录。 有关详细的权限的信息，请参阅[用于部署和管理 BizTalk 应用程序所需权限](../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md)。  
  
## <a name="to-export-bindings-for-a-biztalk-assembly"></a>若要导出的 BizTalk 程序集绑定  
  
#### <a name="using-the-biztalk-server-administration-console"></a>使用 BizTalk Server 管理控制台  
  
1. 单击**启动**，单击**所有程序**，单击[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]，然后单击**BizTalk Server 管理**。  
  
2. 在控制台树中，展开[!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)]，展开 BizTalk 组，然后展开应用程序。  
  
3. 右键单击包含该程序集的应用程序，指向**导出**，然后单击**绑定**。  
  
4. 在导出绑定页上，在**导出到文件**，键入要导出绑定到的.xml 文件的绝对路径。  
  
    例如：**C:\Bindings\MyAssemblyBindings_Staging1.xml**  
  
5. 在导出绑定页上，单击**导出的所选程序集绑定**，然后在**程序集**，单击该程序集。  
  
6. 如果你想要导出所有组中的参与方信息，请选择**导出全局参与方信息**。  
  
    绑定被导出到.xml 文件中指定的位置。  
  
#### <a name="using-the-command-line"></a>使用命令行  
  
1. 打开命令提示符，如下所示：单击**启动**，单击**运行**，类型`cmd`，然后单击**确定**。  
  
2. 键入以下命令，替换适当的值下, 表中所述：  
  
    **BTSTask ExportBindings /Destination:** *值* **/AssemblyName:** *值*[**/GlobalParties**] [**/Server:**<em>值</em>] [**/database:**<em>值</em>]  
  
    例如：  
  
    **BTSTask ExportBindings /Destination:"C:\Binding Files\MyBindings.xml"/AssemblyName:"ErrorHandling.ErrorHandler，版本 = 1.0.0.0，区域性 = 中性，PublicKeyToken = 11e921d58826420e"/Server:MyDatabaseServer /Database:BizTalkMgmtDb**  
  
   |参数|ReplTest1|  
   |---------------|-----------|  
   |**/ 目标**|若要创建，其中包括文件名的绑定文件的完整路径。 如果绑定文件具有相同的路径已存在，则将覆盖。 如果路径中有空格，则必须将其括在双引号 （"）。|  
   |**/AssemblyName**|从中导出绑定程序集的本地唯一标识符 (LUID)。 你可以通过使用获取应用程序中的项目的 Luid 的列表[ListApp 命令](../core/listapp-command.md)。|  
   |**/GlobalParties**|如果指定，将导出组的全局参与方信息。|  
   |**/Server**|承载 BizTalk 管理数据库，在窗体 ServerName\InstanceName，端口中的 SQL Server 实例的名称。<br /><br /> 实例名称仅是所需的实例名称不同于服务器名称时。 端口是仅在 SQL Server 使用的端口号而不是默认 (1433) 时所需。<br /><br /> 示例：<br /><br /> Server=MyServer<br /><br /> Server=MyServer\MySQLServer,1533<br /><br /> 如果未提供，则使用本地计算机上运行的 SQL Server 实例的名称。|  
   |**/Database**|BizTalk 管理数据库的名称。 如果未指定，使用 SQL Server 的本地实例中运行的 BizTalk 管理数据库。|  
  
## <a name="see-also"></a>请参阅  
 [导出绑定](../core/exporting-bindings6.md)   
 [ExportBindings 命令](../core/exportbindings-command.md)   
 [导入 BizTalk 应用程序、绑定和策略](../core/importing-biztalk-applications-bindings-and-policies.md)