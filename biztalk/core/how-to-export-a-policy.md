---
title: 如何导出策略 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- managing [policies], exporting
- policies, exporting
- exporting, policies
ms.assetid: 2e46d96a-7762-479b-be20-bd590b2a4f0a
caps.latest.revision: 30
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 80a6f199ebda349192e8b950af7023c45b4e4c97
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65337807"
---
# <a name="how-to-export-a-policy"></a>如何导出策略
本主题介绍如何使用 BizTalk Server 管理控制台或命令行导出一个或多个策略和相关联的词汇。  
  
 导出时策略，请切记以下几点：  
  
-   使用 BizTalk Server 管理控制台，您可以从 BizTalk 组或 BizTalk 应用程序，以及词汇将导出导出策略。 使用 BTSTask，您可以从应用程序导出策略和所有关联的词汇也将被导出。 不能选择要导出的词汇。  
  
    > [!IMPORTANT]
    >  使用管理控制台时，可以选择要导出哪些词汇。 我们建议您选择导出的所有词汇与策略相关联。 这样一来，您可以确保所需的词汇已存在于目标环境。 即使如果其关联的策略已被删除时，所需的词汇以前已部署到目标环境，它们将被删除也。 这是因为会删除时删除策略时，所有未由其他策略使用词汇。  
  
-   您然后可以导入或多个策略到不同的 BizTalk 组或不同的 BizTalk 组中的应用程序中所述[如何导入策略](../core/how-to-import-a-policy.md)。  
  
-   导出策略之前，它必须存在于 BizTalk 组的规则引擎数据库中。 有几种方法将策略导入到规则引擎数据库中，如中所述[如何导入策略](../core/how-to-import-a-policy.md)。  
  
    > [!NOTE]
    >  当使用规则引擎部署向导从规则引擎数据库中删除策略时，它仍将显示在管理控制台中，但您将无法再将其导出。 有关规则引擎部署向导的详细信息，请参阅[如何部署和取消部署策略及词汇](../core/how-to-deploy-and-undeploy-policies-and-vocabularies.md)。  
  
-   在使用管理控制台进行导出时，策略和词汇都导出到.xml 文件。 在使用 BTSTask 命令行工具进行导出时，策略和词汇都导出到应用程序.msi 文件。  
  
-   BTSTask 不为导出策略; 提供特定的命令但是，您可以使用 BTSTask 有选择地导出所需策略和任何其他项目的 ExportApp 命令。 这将生成包含这些策略应用程序.msi 文件。 ImportApp 命令可用于将.msi 文件导入其他 BizTalk 组。  
  
## <a name="prerequisites"></a>先决条件  
 以下是执行本主题中的过程的先决条件：  
  
-   您必须是 BizTalk Server Administrators 组的成员的帐户登录。 详细了解权限的详细信息，请参阅[用于部署和管理 BizTalk 应用程序所需权限](../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md)。  
  
-   必须安装业务规则引擎。 有关详细信息，请参阅[BizTalk Server 2013 和 2013 R2 安装概述](http://msdn.microsoft.com/library/8041926c-cfc9-4eaf-9c28-a2c6e8015bc5)。  
  
-   你想要导出的策略必须存在于 BizTalk 组的规则引擎数据库中。 如果你想要从应用程序导出策略，它必须具有也已添加到也在应用程序。  
  
## <a name="to-export-a-policy"></a>导出策略  
  
#### <a name="using-the-biztalk-server-administration-console"></a>使用 BizTalk Server 管理控制台  
  
1. 单击**启动**，单击**所有程序**，单击[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]，然后单击**BizTalk Server 管理**。  
  
2. 在控制台树中，展开**BizTalk Server 管理**和相应的 BizTalk 组。  
  
3. 如果你想要选择要从 BizTalk 组右键单击中的策略的所有导出的策略**应用程序**文件夹中，单击**导出**，然后单击**策略**。  
  
    或  
  
    如果你想要导出的策略为特定应用程序，展开应用程序文件夹，右键单击该应用程序，单击**导出**，然后单击**策略**。  
  
    或  
  
    如果你想要导出特定策略，单击包含该策略的策略文件夹，右键单击该策略，然后单击**导出**。  
  
4. 在导出策略页上，在**要导出的策略**，选择要导出的策略。  
  
5. 在中**要导出的词汇**，选中要导出的词汇的复选框并清除不希望导出所有词汇的复选框。 自动选择此策略使用的词汇。  
  
6. 在中**要导出的文件**，键入要导出策略或策略的 XML 文件的路径，然后单击**确定**。  
  
#### <a name="using-the-command-line"></a>使用命令行  
  
1.  使用 BTSTask ListApp 命令与 /ResourceSpec 选项来生成一个 XML 文件，其中列出了要从中导出策略，如中所述的 BizTalk 应用程序中的项目[ListApp 命令](../core/listapp-command.md)。  
  
2.  编辑生成上一步，删除所有的项目除外或多个你想要导出的策略中的 XML 文件。  
  
3.  使用 BTSTask ExportApp 命令，并指定为 /ResourceSpec 参数修改后的 XML 文件。 有关详细信息，请参阅[ExportApp 命令](../core/exportapp-command.md)。  
  
     BTSTask 将指定的策略和所有关联的词汇导出到应用程序.msi 文件中。  
  
## <a name="see-also"></a>请参阅  
 [导出 BizTalk 应用程序、 绑定和策略](../core/exporting-biztalk-applications-bindings-and-policies.md)   
 [管理策略](../core/managing-policies.md)