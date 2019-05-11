---
title: 如何创建应用程序 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- applications, creating
- creating, applications
ms.assetid: 6a8682a7-3bef-4978-996f-5a9c5154ce62
caps.latest.revision: 28
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 1e7734be0d965e57df627b1f5fda4bb18955cd34
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65385524"
---
# <a name="how-to-create-an-application"></a>如何创建应用程序
有三种方法来创建新的 BizTalk 应用程序：  
  
- 使用 BizTalk Server 管理控制台的新的应用程序命令或 BTSTask 命令行工具的 AddApp 命令创建的 BizTalk 应用程序。 您可以执行此操作在本主题后面找到过程。  
  
- 导入从另一个应用程序导出的.msi 文件。 如果当前的 BizTalk 组中不存在该应用程序，包括其项目的应用程序是自动创建当前 BizTalk 组中。 有关详细信息，请参阅[导入 BizTalk 应用程序的方式](../core/how-to-import-a-biztalk-application.md)。  
  
- 部署 BizTalk 程序集从 Visual Studio 到 BizTalk 应用程序。 如果当前的 BizTalk 组中不存在指定 Visual Studio 中的应用程序，它是自动创建。 有关详细信息，请参阅[从到 BizTalk 应用程序的 Visual Studio 部署 BizTalk 程序集](../core/deploying-biztalk-assemblies-from-visual-studio-into-a-biztalk-application.md)。  
  
  然后再创建新的应用程序，你可能想要决定如何配置以下选项：  
  
- **如何命名新的应用程序。** 在 BizTalk 组中的每个应用程序必须具有唯一名称。  
  
- **您是否需要添加对其他应用程序的任何引用。** 来自此应用程序到包含你想要在此应用程序中重复使用的项目的任何应用程序，必须添加的引用。 这将创建应用程序，这会影响您部署这些方法之间的依赖项。 有关背景信息，请参阅[依赖项和应用程序部署](../core/dependencies-and-application-deployment.md)并[如何添加对另一个应用程序的引用](../core/how-to-add-a-reference-to-another-application.md)。  
  
- **您是否需要创建多个应用程序。** 您可能需要将某些项目部署到单独的应用程序。 例如，共享的项目应部署到其自身的、 单独的应用程序。 有关详细信息，请参阅[部署 BizTalk 应用程序的最佳做法](../core/best-practices-for-deploying-a-biztalk-application.md)。  
  
  创建应用程序后，可以向其添加项目和进行其他修改，如本部分中的其他主题中所述 ([创建和修改 BizTalk 应用程序](../core/creating-and-modifying-biztalk-applications.md))。  
  
## <a name="prerequisites"></a>先决条件  
 若要执行本主题中的过程，必须是 BizTalk Server Administrators 组的成员的帐户登录。 有关详细的权限的信息，请参阅[用于部署和管理 BizTalk 应用程序所需权限](../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md)。  
  
## <a name="to-create-a-biztalk-application"></a>若要创建 BizTalk 应用程序  
  
#### <a name="using-the-biztalk-server-administration-console"></a>使用 BizTalk Server 管理控制台  
  
1. 单击**启动**，依次指向**所有程序**，指向[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]，然后单击**BizTalk Server 管理**。  
  
2. 在控制台树中，展开[!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)]，右键单击您要在其中创建新的应用程序，指向该 BizTalk 组**新建**，然后单击**应用程序**。  
  
3. 在中**名称**，键入应用程序的名称。 名称必须是 BizTalk 组中唯一的。  
  
4. 如果你想要将此 BizTalk 组的默认应用程序，请选择**将此默认应用程序**复选框。  
  
5. 在中**说明**，键入应用程序的说明。  
  
6. 如果此应用程序将重用来自另一个应用程序的项目，请单击**引用**和执行的其余步骤。 否则，请单击**确定**和不再执行任何步骤。  
  
7. 单击**外**，选择包含你想要在此应用程序中重复使用，然后单击的项目的应用程序**确定**。 你想要添加的引用任何其他应用程序重复此步骤。  
  
8. 如果你想要从列表中删除应用程序，选择应用程序并单击**删除**。  
  
9. 完成后，单击 **“确定”**。  
  
#### <a name="using-the-command-line"></a>使用命令行  
  
1. 打开命令提示符，如下所示：单击**启动**，单击**运行**，类型`cmd`，然后单击**确定**。  
  
2. 键入以下命令，替换适当的值下, 表中所述：  
  
    **BTSTask AddApp /ApplicationName:** *value* [**/Default**] [**/Description:**<em>value</em>] [**/Server:**<em>value</em>] [**/Database:**<em>value</em>]  
  
    例如：  
  
    **BTSTask AddApp /ApplicationName:MyApplication /Description:"My favorite application" /Server:MySQLServer /Database:BizTalkMgmtDb**  
  
   |参数|ReplTest1|  
   |---------------|-----------|  
   |**/ApplicationName**|要创建的应用程序的名称。 包含空格的名称必须括在双引号 （"）。|  
   |**/ 默认**|如果指定，使新的应用程序的 BizTalk 组的默认应用程序。|  
   |**/ 说明**|应用程序的说明。 包含空格的说明必须括在双引号 （"）。|  
   |**/Server**|承载 BizTalk 管理数据库，在窗体 ServerName\InstanceName，端口中的 SQL Server 实例的名称。<br /><br /> 实例名称仅是所需的实例名称不同于服务器名称时。 端口是仅在 SQL Server 使用的端口号而不是默认 (1433) 时所需。<br /><br /> 示例：<br /><br /> Server=MyServer<br /><br /> Server=MyServer\MySQLServer,1533<br /><br /> 如果未提供，则使用本地计算机上运行的 SQL Server 实例的名称。|  
   |**/Database**|BizTalk 管理数据库的名称。 如果未指定，使用 SQL Server 的本地实例中运行的 BizTalk 管理数据库。|  
  
## <a name="see-also"></a>请参阅  
 [创建和修改 BizTalk 应用程序](../core/creating-and-modifying-biztalk-applications.md)   
 [AddApp 命令](../core/addapp-command.md)