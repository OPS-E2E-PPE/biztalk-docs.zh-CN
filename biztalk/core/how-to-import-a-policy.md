---
title: 如何导入策略 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- policies, requirements
- importing, policies
- policies, importing
- managing [policies], importing
ms.assetid: 92f6ef18-279f-416d-b13e-8b9642539d27
caps.latest.revision: 29
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a994cfdf8ab98f13b86ff586d0d6517ea38e13df
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65337059"
---
# <a name="how-to-import-a-policy"></a>如何导入策略
本主题介绍如何使用 BizTalk Server 管理控制台将策略导入 BizTalk 组或 BTSTask 命令行工具将策略导入到 BizTalk 应用程序。  
  
 可以通过使用业务规则编辑器中，创建策略，如中所述[使用业务规则编辑器创建业务规则](../core/creating-business-rules-using-the-business-rule-composer.md)，并直接，然后导入或如中所述，可以从其他 BizTalk 组，导出策略[如何导出策略](../core/how-to-export-a-policy.md)然后导入它。  
  
 导入策略可将其注册为 BizTalk 组的规则引擎数据库中。 将策略导入后，您可以在 BizTalk Server 管理控制台中查看它。 如果使用 BizTalk Server 管理控制台来导入策略，它将以显示\<的所有项目\>BizTalk 组节点。 然后可以发布它，使其能够将其添加到 BizTalk 应用程序，如中所述[如何发布策略](../core/how-to-publish-a-policy.md)。 如果使用 BTSTask 命令行工具来导入策略，策略将自动发布，并且将显示在导入的应用程序的策略文件夹中。  
  
 在导入策略，请记住以下重要事项：  
  
- 即使你指定要使用导入的策略覆盖现有策略选项，无法导入已在组的规则引擎数据库中存在并已部署的策略。 导入操作将失败。  
  
- 即使策略已处于已部署的状态从其他 BizTalk 组导出时，它将处于取消状态时导入。  
  
- BTSTask 不为导入策略; 提供特定的命令但是可以使用 BTSTask 的 ExportApp 命令有选择地导出仅在想，包括任何其他应用程序项目的应用程序中的策略。 然后可以使用 ImportApp 命令.msi 文件导入到不同的 BizTalk 组中的应用程序。 这是本主题中介绍的方法。 当执行此操作时，该策略是自动导入和 BizTalk 组中发布并添加到指定的应用程序。  
  
  有关使用策略的详细信息，请参阅[管理策略](../core/managing-policies.md)。 将策略添加到应用程序的最佳实践，请参阅[部署 BizTalk 应用程序的最佳做法](../core/best-practices-for-deploying-a-biztalk-application.md)。  
  
> [!NOTE]
>  解决方案开发人员可以创建策略并将其导入规则引擎数据库组的使用规则引擎部署向导，如中所述[如何部署和取消部署策略及词汇](../core/how-to-deploy-and-undeploy-policies-and-vocabularies.md)。  
  
## <a name="prerequisites"></a>先决条件  
 以下是执行本主题中的过程的先决条件：  
  
-   您必须是 BizTalk Server Administrators 组的成员的帐户登录。 有关详细的权限的信息，请参阅[用于部署和管理 BizTalk 应用程序所需权限](../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md)。  
  
-   必须安装业务规则引擎。 有关详细信息，请参阅[BizTalk Server 2013 和 2013 R2 安装概述](http://msdn.microsoft.com/library/8041926c-cfc9-4eaf-9c28-a2c6e8015bc5)。  
  
-   如果你想要使用 BizTalk Server 管理控制台来导入策略，则必须提供包含要导入的策略的.xml 文件。 可以通过将策略导出从另一个 BizTalk 组或应用程序，生成一个.xml 文件，此类，如中所述[如何导出策略](../core/how-to-export-a-policy.md)，或通过使用业务规则编辑器，如中所述[如何导入和导出策略和词汇](../core/how-to-import-and-export-policies-and-vocabularies.md)。  
  
-   如果你想要使用 BTSTask 来导入策略，必须具有某一.msi 文件包含要导入的策略。 有关说明，请参阅[如何导出策略](../core/how-to-export-a-policy.md)。  
  
## <a name="to-import-a-policy"></a>若要导入策略  
  
#### <a name="using-the-biztalk-server-administration-console"></a>使用 BizTalk Server 管理控制台  
  
1. 单击**启动**，单击**所有程序**，单击[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]，然后单击**BizTalk Server 管理**。  
  
2. 在控制台树中，展开[!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)]，展开您要向其中导入策略中，展开 BizTalk 组**应用程序**，然后展开**\<的所有项目\>**.  
  
3. 右键单击**策略**，然后单击**导入**。  
  
4. 浏览到包含该策略并单击的.xml 文件**打开**。  
  
    策略导入到组，并显示在**策略**的文件夹**\<的所有项目\>**。  
  
#### <a name="using-the-command-line"></a>使用命令行  
  
1. 打开命令提示符，如下所示：单击**启动**，单击**运行**，类型`cmd`，然后单击**确定**。  
  
2. 键入以下命令，替换适当的值下, 表中所述：  
  
    **BTSTask ImportApp /Package:** *value* [**/ApplicationName:**<em>value</em>] [**/Overwrite**] [**/Server:**<em>value</em>] [**/Database:**<em>value</em>]  
  
    例如：  
  
    **BTSTask ImportApp /Package:"C:\MSI Files\MyApplication.msi"  /Environment:Test /ApplicationName:MyApplication /Overwrite**  
  
   |参数|ReplTest1|  
   |---------------|-----------|  
   |**/Package**|包含要导入的策略的.msi 文件的完整路径。 如果路径包含空格，则必须将其括在引号 （"）。|  
   |**/ApplicationName**|要将策略导入到其中的 BizTalk 应用程序的名称。 如果未指定，是应用程序名称指定使用导出.msi 文件时。 如果指定的应用程序不存在，将创建它。 包含空格的应用程序名必须括在双引号 （"）。|  
   |**/Overwrite**|若要覆盖应用程序中的策略与.msi 文件中具有相同名称和版本数量的项目的选项。 如果未指定此选项，并且有一个或多个策略中应用程序的.msi 文件中的策略具有相同的名称和版本号，导入失败。 可以通过应用程序中查看策略的名称和版本数目[ListApp 命令](../core/listapp-command.md)。|  
   |**/Server**|承载 BizTalk 管理数据库，在窗体 ServerName\InstanceName，端口中的 SQL Server 实例的名称。<br /><br /> 实例名称仅是所需的实例名称不同于服务器名称时。 端口是仅在 SQL Server 使用的端口号而不是默认 (1433) 时所需。<br /><br /> 示例：<br /><br /> Server=MyServer<br /><br /> Server=MyServer\MySQLServer,1533<br /><br /> 如果未提供，则使用本地计算机上运行的 SQL Server 实例的名称。|  
   |**/Database**|BizTalk 管理数据库的名称。 如果未指定，使用 SQL Server 的本地实例中运行的 BizTalk 管理数据库。|  
  
   > [!NOTE]
   >  在支持用户帐户控制 (UAC) 的系统上，可能需要具有管理权限才能运行该工具。 要执行此操作，右键单击该应用程序，并选择**以管理员身份运行**。  
  
## <a name="see-also"></a>请参阅  
 [导入 BizTalk 应用程序、 绑定和策略](../core/importing-biztalk-applications-bindings-and-policies.md)   
 [导出 BizTalk 应用程序、 绑定和策略](../core/exporting-biztalk-applications-bindings-and-policies.md)   
 [管理策略](../core/managing-policies.md)