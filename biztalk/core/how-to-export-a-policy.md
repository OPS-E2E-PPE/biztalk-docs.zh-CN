---
title: 如何导出策略 |Microsoft 文档
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
ms.openlocfilehash: 752336e0642c42418f6c68ddefb719d02051d937
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22254909"
---
# <a name="how-to-export-a-policy"></a>如何导出策略
本主题介绍如何使用 BizTalk Server 管理控制台或命令行导出一个或多个策略以及关联词汇。  
  
 导出策略时，请切记以下几点：  
  
-   使用 BizTalk Server 管理控制台，您可以从 BizTalk 组或 BizTalk 应用程序导出策略以及要导出的词汇。 使用 BTSTask，您可以从某一应用程序导出策略，并且还将导出所有关联的词汇。 您不能选择要导出的词汇。  
  
    > [!IMPORTANT]
    >  在使用管理控制台时，您可以选择要导出哪些词汇。 我们建议您选择导出与某一策略关联的所有词汇。 这样，就可以确保在目标环境中存在所需的词汇。 即使所需的词汇以前已部署到该目标环境中，但如果其关联的策略被删除，则这些词汇也会被删除。 这是因为，在删除某一策略时，该策略的未由其他策略使用的所有词汇都将被删除。  
  
-   你可以然后导入的策略到不同的 BizTalk 组或在不同的 BizTalk 组中，应用程序中所述[如何导入策略](../core/how-to-import-a-policy.md)。  
  
-   在您可以导出某一策略前，该策略必须存在于 BizTalk 组的规则引擎数据库中。 有几种方法来插入规则引擎数据库中，导入策略中所述[如何导入策略](../core/how-to-import-a-policy.md)。  
  
    > [!NOTE]
    >  在使用规则引擎部署向导从规则引擎数据库中删除某个策略时，该策略仍将会在管理控制台中显示，但您将无法导出该策略。 有关规则引擎部署向导的详细信息，请参阅[如何部署和取消部署策略和词汇](../core/how-to-deploy-and-undeploy-policies-and-vocabularies.md)。  
  
-   在使用管理控制台进行导出时，策略和词汇将导出到某一 .xml 文件中。 在使用 BTSTask 命令行工具进行导出时，策略和词汇将导出到某一应用程序 .msi 文件中。  
  
-   BTSTask 并不为导出策略提供特定的命令；但是，可以使用 BTSTask 的 ExportApp 命令有选择地只导出所需策略，而不导出其他项目。 这将生成一个包含这些策略的应用程序 .msi 文件。 您可以使用 ImportApp 命令将该 .msi 文件导入不同的 BizTalk 组。  
  
## <a name="prerequisites"></a>先决条件  
 以下为执行本主题中步骤的前提条件：  
  
-   您必须以 BizTalk Server Administrators 组成员的帐户身份登录。 有关更多详细有关权限的信息，请参阅[用于部署和管理 BizTalk 应用程序所需权限](../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md)。  
  
-   必须安装业务规则引擎。 有关详细信息，请参阅[BizTalk Server 2013 和 2013 R2 的安装概述](http://msdn.microsoft.com/library/8041926c-cfc9-4eaf-9c28-a2c6e8015bc5)。  
  
-   您要导出的策略必须存在于 BizTalk 组的规则引擎数据库中。 如果您要从某一应用程序导出策略，则该策略必须也已经添加到该应用程序中。  
  
## <a name="to-export-a-policy"></a>导出策略  
  
#### <a name="using-the-biztalk-server-administration-console"></a>使用 BizTalk Server 管理控制台  
  
1.  单击**启动**，单击**所有程序**，单击[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]，然后单击**BizTalk Server 管理**。  
  
2.  在控制台树中，展开**BizTalk Server 管理**展开的 BizTalk 组。  
  
3.  如果你想要选择要从所有 BizTalk 组右键单击中的策略都导出的策略**应用程序**文件夹中，单击**都导出**，然后单击**策略**。  
  
     或  
  
     如果你想要导出的策略在特定的应用程序中，展开应用程序文件夹，右键单击应用程序，单击**导出**，然后单击**策略**。  
  
     或  
  
     如果你想要导出特定策略，单击包含的策略的策略文件夹，右键单击的策略，然后单击**导出**。  
  
4.  在导出策略页上，在**要导出的策略**，选择要导出的策略。  
  
5.  在**要导出的词汇**，选择复选框的词汇后，若要导出，然后清除不想导出任何词汇的复选框。 该策略所使用的词汇将会自动选择。  
  
6.  在**要导出文件**到中，键入要导出的策略或策略，到 XML 文件的路径，然后单击**确定**。  
  
#### <a name="using-the-command-line"></a>使用命令行  
  
1.  使用带有 /ResourceSpec 选项 BTSTask ListApp 命令生成一个 XML 文件，其中列出了要从中导出策略中, 所述 BizTalk 应用程序中的项目[ListApp 命令](../core/listapp-command.md)。  
  
2.  编辑在前一步骤中生成的 XML 文件，删除除您要导出的策略外的所有项目。  
  
3.  使用 BTSTask ExportApp 命令，并且为 /ResourceSpec 参数指定已修改的 XML 文件。 有关详细信息，请参阅[ExportApp 命令](../core/exportapp-command.md)。  
  
     BTSTask 将指定的策略及其所有关联的词汇都导出到应用程序 .msi 文件中。  
  
## <a name="see-also"></a>另请参阅  
 [导出 BizTalk 应用程序、 绑定和策略](../core/exporting-biztalk-applications-bindings-and-policies.md)   
 [管理策略](../core/managing-policies.md)