---
title: "如何导入策略 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- policies, requirements
- importing, policies
- policies, importing
- managing [policies], importing
ms.assetid: 92f6ef18-279f-416d-b13e-8b9642539d27
caps.latest.revision: "29"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: bae0b72eb323e75a8ecf9563b4fa0e0bc1b725d8
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-import-a-policy"></a>如何导入策略
本主题介绍如何使用 BizTalk Server 管理控制台将策略导入到 BizTalk 组或使用 BTSTask 命令行工具将策略导入到 BizTalk 应用程序。  
  
 中所述，可以通过使用业务规则编辑器，创建一个策略[创建业务规则使用业务规则编辑器](../core/creating-business-rules-using-the-business-rule-composer.md)，并直接，然后导入或中所述，你可以从另一个 BizTalk 组中，导出策略[如何导出策略](../core/how-to-export-a-policy.md)然后导入它。  
  
 导入某个策略时，将在 BizTalk 组的规则引擎数据库中注册此策略。 导入策略后，可以在 BizTalk Server 管理控制台中查看此策略。 如果使用 BizTalk Server 管理控制台来导入策略，它将显示在\<所有项目 > BizTalk 组的节点。 然后可以将其以使其可将其添加到 BizTalk 应用程序，如中所述发布[如何发布策略](../core/how-to-publish-a-policy.md)。 如果使用 BTSTask 命令行工具来导入策略，将自动发布此策略，并且它将显示在您导入此策略的应用程序的“策略”文件夹中。  
  
 导入策略时，请切记以下几点：  
  
-   即使您指定使用导入的策略覆盖现有策略的选项，也无法导入该组的规则引擎数据库中现有的且已部署的策略。 导入操作将失败。  
  
-   即使当从其他 BizTalk 组中导出时策略已处于部署状态，在导入时它也将处于未部署状态。  
  
-   BTSTask 并不为导入策略提供特定的命令；但是，可以使用 BTSTask 的 ExportApp 命令在应用程序中有选择地只导出所需的策略（不包括其他应用程序项目）。 然后，可以使用 ImportApp 命令将该 .msi 文件导入到不同 BizTalk 组中的应用程序。 本主题中说明了此方法。 当您完成此操作后，此策略将自动导入到 BizTalk 组中并在此组中发布，同时添加到指定的应用程序中。  
  
 有关使用策略的详细信息，请参阅[管理策略](../core/managing-policies.md)。 将策略添加到应用程序的最佳做法，请参阅[部署 BizTalk 应用程序的最佳做法](../core/best-practices-for-deploying-a-biztalk-application.md)。  
  
> [!NOTE]
>  解决方案开发人员可以创建策略并将其导入组的规则引擎数据库通过使用规则引擎部署向导中中, 所述[如何部署和取消部署策略和词汇](../core/how-to-deploy-and-undeploy-policies-and-vocabularies.md)。  
  
## <a name="prerequisites"></a>先决条件  
 以下为执行本主题中步骤的前提条件：  
  
-   您必须以 BizTalk Server Administrators 组成员的帐户身份登录。 有关更多详细权限的信息，请参阅[用于部署和管理 BizTalk 应用程序所需权限](../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md)。  
  
-   必须安装业务规则引擎。 有关详细信息，请参阅[BizTalk Server 2013 和 2013 R2 的安装概述](http://msdn.microsoft.com/library/8041926c-cfc9-4eaf-9c28-a2c6e8015bc5)。  
  
-   如果要使用 BizTalk Server 管理控制台来导入策略，则必须具有包含要导入的策略的可用 .xml 文件。 中所述，你可以通过从另一个 BizTalk 组或应用程序中，导出策略生成此类的.xml 文件[如何导出策略](../core/how-to-export-a-policy.md)，或通过使用业务规则编辑器中, 所述[如何导入和导出策略和词汇](../core/how-to-import-and-export-policies-and-vocabularies.md)。  
  
-   如果要使用 BTSTask 来导入策略，必须具有包含要导入的策略的 .xml 文件。 有关说明，请参阅[如何导出策略](../core/how-to-export-a-policy.md)。  
  
## <a name="to-import-a-policy"></a>导入策略  
  
#### <a name="using-the-biztalk-server-administration-console"></a>使用 BizTalk Server 管理控制台  
  
1.  单击**启动**，单击**所有程序**，单击[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]，然后单击**BizTalk Server 管理**。  
  
2.  在控制台树中，展开[!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)]，展开你想要将策略导入，展开在其中的 BizTalk 组**应用程序**，然后展开**\<所有项目 >**。  
  
3.  右键单击**策略**，然后单击**导入**。  
  
4.  浏览到包含该策略，然后单击的.xml 文件**打开**。  
  
     策略导入组并显示在**策略**文件夹**\<所有项目 >**。  
  
#### <a name="using-the-command-line"></a>使用命令行  
  
1.  如下所示打开命令提示符： 单击**启动**，单击**运行**，类型`cmd`，然后单击**确定**。  
  
2.  键入以下命令，替换为适当的值下, 表中所述：  
  
     **BTSTask ImportApp /Package:** *值*[**/ApplicationName:***值*] [**/覆盖**] [**/ 服务器：***值*] [**/数据库：***值*]  
  
     例如：  
  
     **BTSTask ImportApp /Package:"C:\MSI Files\MyApplication.msi"/Environment:Test /ApplicationName:MyApplication / 覆盖**  
  
    |参数|值|  
    |---------------|-----------|  
    |**/ 包**|.msi 文件（包含要导入的策略）的完整路径。 如果该路径包含空格，则必须将其括在引号 (") 中。|  
    |**/ 应用程序名称**|向其导入策略的 BizTalk 应用程序的名称。 如果没有指定 BizTalk 应用程序的名称，则将使用导出 .msi 文件时指定的应用程序的名称。 如果指定的应用程序不存在，则将创建该应用程序。 包含空格的应用程序名必须括在双引号 (") 中。|  
    |**/ 覆盖**|该选项的功能是，如果应用程序中的策略的名称和版本号与 .msi 文件中项目的名称和版本号相同，则使用后者覆盖前者。 如果未指定此选项，并且应用程序中存在一个或多个策略与 .msi 文件中的策略具有相同的名称和版本号，则导入过程失败。 你也可以通过使用应用程序中查看策略的名称和版本数目[ListApp 命令](../core/listapp-command.md)。|  
    |**/ 服务器**|BizTalk 管理数据库的宿主 SQL Server 实例的名称，格式为“服务器名称\实例名称,端口”。<br /><br /> 只在实例名称与服务器名称不相同时才需要指定实例名称。 只在 SQL Server 不使用默认端口号 (1433) 时才需要指定端口。<br /><br /> 示例：<br /><br /> Server=MyServer<br /><br /> Server=MyServer\MySQLServer,1533<br /><br /> 如果未提供，则使用本地计算机上运行的 SQL Server 实例的名称。|  
    |**/ 数据库**|BizTalk 管理数据库的名称。 如果未指定，则使用在本地 SQL Server 实例中运行的 BizTalk 管理数据库。|  
  
    > [!NOTE]
    >  在支持用户帐户控制 (UAC) 的系统上，可能需要具有管理权限才能运行该工具。 要执行此操作，右键单击该应用程序，，然后选择**以管理员身份运行**。  
  
## <a name="see-also"></a>另请参阅  
 [导入 BizTalk 应用程序、 绑定和策略](../core/importing-biztalk-applications-bindings-and-policies.md)   
 [导出 BizTalk 应用程序、 绑定和策略](../core/exporting-biztalk-applications-bindings-and-policies.md)   
 [管理策略](../core/managing-policies.md)