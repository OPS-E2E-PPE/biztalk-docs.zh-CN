---
title: 如何创建应用程序 |Microsoft 文档
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
ms.openlocfilehash: e6078e292673a1d9dbe3634ea9c0c4e79ab9c2cc
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22250133"
---
# <a name="how-to-create-an-application"></a>如何创建应用程序
有三种方法可以创建新的 BizTalk 应用程序：  
  
-   使用 BizTalk Server 管理控制台的 New Application 命令或 BTSTask 命令行工具的 AddApp 命令来创建 BizTalk 应用程序。 您可以在本主题后面部分找到具体步骤。  
  
-   导入从另一个应用程序导出的 .msi 文件。 如果该应用程序在当前 BizTalk 组中不存在，则在当前 BizTalk 组中自动创建该应用程序，包括其项目。 有关详细信息，请参阅[如何导入 BizTalk 应用程序](../core/how-to-import-a-biztalk-application.md)。  
  
-   将 BizTalk 程序集从 Visual Studio 部署到 BizTalk 应用程序。 如果 Visual Studio 中指定的应用程序在当前 BizTalk 组中不存在，则自动创建该应用程序。 有关详细信息，请参阅[部署 BizTalk 中的程序集到 BizTalk 应用程序的 Visual Studio](../core/deploying-biztalk-assemblies-from-visual-studio-into-a-biztalk-application.md)。  
  
 在创建新的应用程序之前，可能需要确定如何配置以下选项：  
  
-   **要将新的应用程序的内容。** BizTalk 组中的每个应用程序必须具有唯一名称。  
  
-   **是否需要添加对其他应用程序的任何引用。** 必须从此应用程序添加对任何包含您要在此应用程序中重用的项目的应用程序的引用。 这样会在应用程序之间建立依赖关系，这会影响您部署这些应用程序的方式。 有关背景信息，请参阅[依赖关系和应用程序部署](../core/dependencies-and-application-deployment.md)和[如何添加对另一个应用程序的引用](../core/how-to-add-a-reference-to-another-application.md)。  
  
-   **是否需要创建多个应用程序。** 您可能需要将某些项目部署到单独的应用程序中。 例如，共享项目应部署到自己的单独的应用程序中。 有关详细信息，请参阅[部署 BizTalk 应用程序的最佳做法](../core/best-practices-for-deploying-a-biztalk-application.md)。  
  
 一旦你已创建应用程序，可以向其添加项目和此部分中的其他主题中所述进行其他修改，([创建和修改 BizTalk 应用程序](../core/creating-and-modifying-biztalk-applications.md))。  
  
## <a name="prerequisites"></a>先决条件  
 若要执行本主题中的过程，必须使用 BizTalk Server Administrators 组的成员帐户登录。 有关更多详细权限的信息，请参阅[用于部署和管理 BizTalk 应用程序所需权限](../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md)。  
  
## <a name="to-create-a-biztalk-application"></a>创建 BizTalk 应用程序  
  
#### <a name="using-the-biztalk-server-administration-console"></a>使用 BizTalk Server 管理控制台  
  
1.  单击**启动**，指向**所有程序**，指向[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]，然后单击**BizTalk Server 管理**。  
  
2.  在控制台树中，展开[!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)]，右键单击你要在其中创建新的应用程序，指向的 BizTalk 组**新建**，然后单击**应用程序**。  
  
3.  在**名称**，键入应用程序的名称。 该名称在 BizTalk 组中必须是唯一的。  
  
4.  如果你想要使此 BizTalk 组的默认应用程序，选择**使这成为默认应用**复选框。  
  
5.  在**说明**，键入应用程序的说明。  
  
6.  如果此应用程序将重复使用从另一个应用程序的项目，请单击**引用**和执行的其余步骤。 否则，请单击**确定**并采取任何进一步的步骤。  
  
7.  单击**添加**，选择包含你想要在此应用程序中重复使用，然后单击的项目的应用程序**确定**。 对任何其他要添加引用的应用程序重复此步骤。  
  
8.  如果你想要从列表中删除应用程序，选择应用程序，然后单击**删除**。  
  
9. 完成后，单击 **“确定”**。  
  
#### <a name="using-the-command-line"></a>使用命令行  
  
1.  如下所示打开命令提示符： 单击**启动**，单击**运行**，类型`cmd`，然后单击**确定**。  
  
2.  键入以下命令，替换为适当的值下, 表中所述：  
  
     **BTSTask AddApp /ApplicationName:** *值*[**/默认**] [**/Description:***值*] [**/服务器：***值*] [**/数据库：***值*]  
  
     例如：  
  
     **BTSTask AddApp /ApplicationName:MyApplication /Description:"我最喜欢的应用程序"/Server:MySQLServer /Database:BizTalkMgmtDb**  
  
    |参数|值|  
    |---------------|-----------|  
    |**/ 应用程序名称**|要创建的应用程序的名称。 包含空格的名称必须括在双引号 （"）。|  
    |**/ 默认**|如果指定，使新的应用程序的默认应用程序的 BizTalk 组。|  
    |**/ 说明**|应用程序的说明。 包含空格的说明必须括在双引号 (") 中。|  
    |**/ 服务器**|BizTalk 管理数据库的宿主 SQL Server 实例的名称，格式为“服务器名称\实例名称,端口”。<br /><br /> 只在实例名称与服务器名称不相同时才需要指定实例名称。 只在 SQL Server 不使用默认端口号 (1433) 时才需要指定端口。<br /><br /> 示例：<br /><br /> Server=MyServer<br /><br /> Server=MyServer\MySQLServer,1533<br /><br /> 如果未提供，则使用本地计算机上运行的 SQL Server 实例的名称。|  
    |**/ 数据库**|BizTalk 管理数据库的名称。 如果未指定，则使用在本地 SQL Server 实例中运行的 BizTalk 管理数据库。|  
  
## <a name="see-also"></a>另请参阅  
 [创建和修改 BizTalk 应用程序](../core/creating-and-modifying-biztalk-applications.md)   
 [AddApp 命令](../core/addapp-command.md)