---
title: "演练： 部署策略 |Microsoft 文档"
ms.custom: 
ms.date: 2016-04-05
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 205760e2-9cd4-496f-93cd-0f93bc5d3231
caps.latest.revision: "25"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 00c603a3a0c52d735441858af6a2f602c30d1f51
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="walkthrough-deploying-the-policy"></a>演练： 部署策略
本演练提供了部署的分步说明**ProcessPurchaseOrder**以下三种方式的策略：  
  
-   导出和导入策略，通过使用业务规则引擎部署向导。  
  
-   通过使用 BizTalk Server 管理控制台将策略导出到某一 XML 文件或者从某一 XML 文件导入策略。  
  
-   通过使用 BizTalk Server 管理控制台将策略作为 XML 文件的一部分导出并导入该 XML 文件。  
  
## <a name="prerequisites"></a>先决条件  
 必须完成[演练： 跟踪策略执行](../core/walkthrough-tracking-policy-execution.md)执行本演练之前的演练。  
  
## <a name="overview-of-this-walkthrough"></a>本演练的概述  
 本主题包含下列三个演练：  
  
1.  第一个演练包含用于部署的过程**ProcessPurchaseOrder**通过业务规则引擎部署向导的策略。 下表描述此演练中的各个过程。  
  
    |过程标题|过程说明|  
    |---------------------|---------------------------|  
    |若要使用业务规则引擎部署向导导出 POVocabulary 1.0 和 1.1 版|提供用于导出的 1.0 和 1.1 版的分步说明**POVocabulary**词汇到 XML 文件使用业务规则引擎部署向导。|  
    |使用业务规则引擎部署向导来导出 ProcessPurchaseOrder 1.3|提供用于导出 1.3 版的分步说明**ProcessPurchaseOrder**策略应用到 XML 文件使用业务规则引擎部署向导。|  
    |删除 ProcessPurchaseOrder 和 POVocabulary|提供有关删除的分步说明**ProcessPurchaseOrder**策略和**POVocabulary**词汇，以便可以测试导入 XML 文件来重新创建它们。|  
    |从 XML 导入以重新创建 POVocabulary 1.0 和 1.1|提供你在重新创建的第一个过程中创建的导入词汇 XML 文件的分步说明**POVocabulary**词汇。|  
    |确认 POVocabulary 1.0 和 1.1 已重新创建|提供有关使用业务规则编辑器来验证分步说明的该版本 1.0 和 1.1 **POVocabulary**重新创建。|  
    |从 XML 导入以重新创建 ProcessPurchaseOrder 1.3|提供你在重新创建 1.3 版的第二个过程中创建的导入策略 XML 文件的分步说明**ProcessPurchaseOrder**策略。|  
    |验证 ProcessPurchaseOrder 1.3 已重新创建|提供有关使用业务规则编辑器来验证该版本 1.3 的分步说明**ProcessPurchaseOrder**策略是重新创建。|  
  
2.  第二个演练中包含的部署过程**ProcessPurchaseOrder**使用 XML 文件的策略导出从 BizTalk Server 管理控制台下表介绍了在此过程演练。  
  
    |过程标题|过程说明|  
    |---------------------|---------------------------|  
    |将 ProcessPurchaseOrder 1.3 策略和 POVocabulary 词汇导出到某一 XML 文件|提供有关使用 BizTalk Server 管理控制台导出的分步说明**ProcessPurchaseOrder**策略和**POVocabulary** XML 文件的词汇。|  
    |删除 ProcessPurchaseOrder 策略|提供有关删除的分步说明**ProcessPurchaseOrder**策略从**RuleTestApp**和规则引擎数据库。|  
    |导入 XML 文件以便重新创建 ProcessPurchaseOrder 策略|提供有关导入 XML 文件的分步说明重新创建的第一个步骤中导出**ProcessPurchaseOrder**策略。|  
    |将 ProcessPurchaseOrder 策略添加到 RuleTestApp 应用程序|提供有关将添加的分步说明**ProcessPurchaseOrder**策略应用到**RuleTestApp**应用程序。|  
  
3.  第三个演练中包含的部署过程**ProcessPurchaseOrder**从 BizTalk Server 管理控制台导出策略通过使用 MSI 文件。 下表描述此演练中的各个过程。  
  
    |过程标题|过程具有针对以下操作的分步说明|  
    |---------------------|---------------------------------------------------|  
    |将 RuleTestApp 应用程序导出到某一 MSI 文件|提供用于导出的分步说明**RuleTestApp**到 MSI 文件，用于更高版本进行重新创建应用程序的应用程序。|  
    |删除 RuleTestApp 应用程序|提供有关删除的分步说明**RuleTestApp**应用程序，以便你可以测试重新创建应用程序使用的 MSI 文件。|  
    |验证 ProcessPurchaseOrder 策略和 POVocabulary 词汇已删除|提供有关使用业务规则编辑器来验证的分步说明**ProcessPurchaseOrder**删除策略和 POVocabulary 词汇。|  
    |导入 MSI 文件以便重新创建 RuleTestApp 应用程序|提供使用 BizTalk Server 管理控制台将导入的 MSI 文件以重新创建的指导**RuleTestApp**应用程序。|  
    |验证 ProcessPurchaseOrder 策略已添加到 RuleTestApp|提供有关使用 BizTalk Server 管理控制台以验证的分步说明**ProcessPurchaseOrder**策略添加到**RuleTestApp**应用程序。|  
    |确认 ProcessPurchaseOrder 策略和 POVocabulary 词汇已重新创建|提供有关使用业务规则编辑器来验证的分步说明**ProcessPurchaseOrder**策略和**POVocabulary**词汇将重新创建。|  
    |若要测试解决方案|提供用于测试解决方案的分步说明。|  
  
## <a name="procedures-for-deploying-the-processpurchaseorder-policy-by-using-the-business-rules-engine-deployment-wizard"></a>使用业务规则引擎部署向导部署 ProcessPurchaseOrder 策略的过程  
  
#### <a name="to-export-povocabulary-10-and-11-by-using-the-business-rules-engine-deployment-wizard"></a>若要使用业务规则引擎部署向导导出 POVocabulary 1.0 和 1.1 版  
  
1.  上**启动**菜单上，打开**业务规则引擎部署向导**。  
  
    > [!NOTE]
    >  在支持用户帐户控制 (UAC) 的系统上，可能需要具有管理权限才能运行该工具。 要执行此操作，右键单击该应用程序，，然后选择**以管理员身份运行**。  
  
2.  单击 **“下一步”**。  
  
3.  上**部署任务**页上，选择**导出策略/词汇文件从数据库**，然后单击**下一步**。  
  
4.  上**策略存储区**页上，单击**下一步**。  
  
5.  上**导出策略/词汇**页上，单击**词汇**。  
  
6.  选择**POVocabulary.1.0**从下拉列表中为**策略/词汇**，键入或浏览以将 XML 输出文件名称指定为**C:\BRE-walkthroughs\POVocabulary10.xml**，然后单击**下一步**。  
  
7.  上**准备**页上，单击**下一步**。  
  
8.  上**导出策略/词汇**页上，单击**下一步。**  
  
9. 选择**再次运行此向导**，然后单击**完成**。  
  
     由于你选择了**再次运行此向导**，向导的第一个屏幕会再次出现。  
  
10. 重复步骤 2 到 6。  
  
11. 选择**POVocabulary.1.1**从下拉列表中为**策略/词汇**，键入或浏览以将 XML 输出文件名称指定为**C:\BRE-walkthroughs\POVocabulary11.xml**，然后单击**下一步**。  
  
12. 重复步骤 8 和 9。  
  
13. 单击 **“完成”**。  
  
    > [!NOTE]
    >  你需要导出版本 1.0 和 1.1 版**POVocabulary**因为**ProcessPurchaseOrder** 1.3 取决于这两个版本**POVocabulary**。 **项允许的最大数目**定义使用从版本 1.1 的词汇。 **请求数量**和**请求状态**定义使用从版本 1.0。  
  
#### <a name="to-export-processpurchaseorder-13-by-using-the-business-rule-engine-deployment-wizard"></a>若要使用业务规则引擎部署向导导出 ProcessPurchaseOrder 1.3  
  
1.  上**启动**菜单上，打开**业务规则引擎部署向导**。  
  
    > [!NOTE]
    >  在支持用户帐户控制 (UAC) 的系统上，可能需要具有管理权限才能运行该工具。 要执行此操作，右键单击该应用程序，，然后选择**以管理员身份运行**。  
  
2.  上**欢迎规则引擎部署向导**页上，单击**下一步**。  
  
3.  选择**导出策略/词汇文件从数据库**，然后单击**下一步**。  
  
4.  上**策略存储区**页上，单击**下一步**。  
  
5.  验证**策略**选项。  
  
6.  选择**ProcessPurchaseOrder.1.3**从下拉列表中为**策略/词汇**。  
  
7.  键入或浏览以指定要**C:\BRE-walkthroughs\ProcessPOPolicy13.xml**作为 XML 输出文件的名称。  
  
8.  单击**下一步**三次，然后单击**完成**。  
  
#### <a name="to-delete-processpurchaseorder-and-povocabulary"></a>删除 ProcessPurchaseOrder 和 POVocabulary  
  
1.  上**启动**菜单上，打开**业务规则编辑器**。 如果必须业务规则编辑器已打开，按 F5 或单击**重新加载**上**文件**菜单可对其进行刷新。  
  
    > [!NOTE]
    >  在支持用户帐户控制 (UAC) 的系统上，可能需要具有管理权限才能运行该工具。 要执行此操作，右键单击该应用程序，，然后选择**以管理员身份运行**。  
  
2.  在策略资源管理器窗口中，展开**策略**，展开**ProcessPurchaseOrder**，右键单击**版本 1.0**，然后单击**删除**. 如果**删除**是禁用，右键单击**版本 1.0**，然后单击**取消部署后再次**。  
  
    > [!NOTE]
    >  已部署的策略版本不能删除。 您必须首先取消部署策略，然后才能删除策略版本。  
  
3.  单击**是**确认消息框中。  
  
4.  重复步骤 2 和 3 以删除**版本 1.1**。  
  
5.  重复步骤 2 和 3 以删除**版本 1.2**。  
  
6.  右键单击**版本 1.3-部署**，然后单击**取消部署后再次**。 如果**取消部署后再次**选项处于禁用状态，忽略此步骤。  
  
7.  在事实浏览器窗口中，展开**词汇**，右键单击**POVocabulary**，然后单击**删除**。  
  
#### <a name="to-import-from-xml-to-re-create-povocabulary-10-and-11"></a>从 XML 导入以重新创建 POVocabulary 1.0 和 1.1  
  
1.  上**启动**菜单上，打开**业务规则引擎部署向导**。  
  
    > [!NOTE]
    >  在支持用户帐户控制 (UAC) 的系统上，可能需要具有管理权限才能运行该工具。 要执行此操作，右键单击该应用程序，，然后选择**以管理员身份运行**。  
  
2.  上**欢迎规则引擎部署向导**，单击**下一步**。  
  
3.  上**部署任务**页上，选择**导入并将其从文件发布到数据库的策略/词汇**，然后单击**下一步**。  
  
4.  上**策略存储区**页上，单击**下一步**。  
  
5.  浏览并选择**POVocabulary10.xml**第一个过程中创建的文件。  
  
6.  单击**打开**或双击**POVocabulary10.xml**。  
  
7.  单击**下一步**在业务规则引擎部署向导。  
  
8.  单击 **“下一步”**。  
  
9. 单击 **“下一步”**。  
  
10. 选择**再次运行此向导**，然后单击**完成**。  
  
11. 重复步骤 2-9 可以导入**POVocabulary11.xml**。  
  
12. 单击 **“完成”**。  
  
#### <a name="to-verify-that-povocabulary-10-and-11-are-re-created"></a>确认 POVocabulary 1.0 和 1.1 已重新创建  
  
1.  上**启动**菜单上，打开**业务规则编辑器**。 如果你有已打开它，按 F5 或单击**重新加载**上**文件**菜单可对其进行刷新。  
  
    > [!NOTE]
    >  在支持用户帐户控制 (UAC) 的系统上，可能需要具有管理权限才能运行该工具。 要执行此操作，右键单击该应用程序，，然后选择**以管理员身份运行**。  
  
2.  在事实浏览器窗口中，单击**词汇**选项卡。  
  
3.  展开**词汇**，并且你应看到**POVocabulary**。  
  
4.  展开**POVocabulary**，并且你应看到**版本 1.0**和**版本 1.1**。  
  
#### <a name="to-import-from-xml-to-re-create-processpurchaseorder-13"></a>从 XML 导入以重新创建 ProcessPurchaseOrder 1.3  
  
1.  上**启动**菜单上，打开**业务规则引擎部署向导**。  
  
    > [!NOTE]
    >  在支持用户帐户控制 (UAC) 的系统上，可能需要具有管理权限才能运行该工具。 要执行此操作，右键单击该应用程序，，然后选择**以管理员身份运行**。  
  
2.  上**欢迎规则引擎部署向导**，单击**下一步**。  
  
3.  上**部署任务**页上，选择**导入和从文件中的文件要数据库发布到数据库的策略/词汇**，然后单击**下一步**。  
  
4.  上**策略存储区**页上，单击**下一步**。  
  
5.  浏览并选择**ProcessPOPolicy13.xml**在本演练前面创建的文件。  
  
6.  单击**打开**或双击**ProcessPOPolicy13.xml**。  
  
7.  单击**下一步**在业务规则引擎部署向导。  
  
8.  单击 **“下一步”**。  
  
9. 单击“下一步” ，然后单击“完成” 。  
  
#### <a name="to-verify-that-processpurchaseorder-13-is-re-created"></a>验证 ProcessPurchaseOrder 1.3 已重新创建  
  
1.  上**启动**菜单上，打开**业务规则编辑器**。 如果你有已打开它，按 F5 或单击**重新加载**上**文件**菜单可对其进行刷新。  
  
    > [!NOTE]
    >  在支持用户帐户控制 (UAC) 的系统上，可能需要具有管理权限才能运行该工具。 要执行此操作，右键单击该应用程序，，然后选择**以管理员身份运行**。  
  
2.  在策略资源管理器窗口中，展开**策略**，你应看到**ProcessPurchaseOrder**。  
  
3.  展开**ProcessPurchaseOrder** ，你应看到**版本 1.3-发布**。  
  
## <a name="procedures-for-deploying-the-policy-by-using-an-xml-file-exported-from-the-biztalk-server-administration-console"></a>通过使用从 BizTalk Server 管理控制台导出的 XML 文件部署策略的过程  
  
#### <a name="to-export-the-processpurchaseorder-13-policy-and-the-povocabulary-vocabulary-to-an-xml-file"></a>将 ProcessPurchaseOrder 1.3 策略和 POVocabulary 词汇导出到某一 XML 文件  
  
1.  上**启动**菜单上，打开[!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)]。 如果已打开该工具，请按 F5 键刷新。  
  
2.  展开**控制台根节点**，展开[!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)]，展开**BizTalk 组**，展开**应用程序**，然后展开**RuleTestApp**.  
  
3.  单击**策略**并确保你看到 ProcessPurchaseOrder 1.3 策略列表中的。  
  
4.  右键单击**ProcessPurchaseOrder**，然后单击**导出**。  
  
5.  在**导出策略**对话框框中，请确保**ProcessPurchaseOrder**策略和**POVocabulary**选择。  
  
    > [!NOTE]
    >  你可以通过右键单击导出为 XML 文件的应用程序中的所有策略**RuleTest** ，然后单击**都导出**上**策略**菜单。 这样，您就可以将此应用程序使用的所有策略和词汇都导出到单个 XML 文件中。  
  
    > [!NOTE]
    >  你可以通过右键单击导出到 XML 文件的所有应用程序中的所有策略**应用程序**节点，然后单击**都导出**上**策略**菜单。 这样，您就可以将所有应用程序使用的所有策略和词汇都导出到单个 XML 文件中。  
  
6.  指定输出 XML 文件的名称 (**C:\BRE-Walkthroughs\ProcessPOFromAdmin.xml**)，然后单击**确定**。  
  
#### <a name="to-delete-the-processpurchaseorder-policy"></a>删除 ProcessPurchaseOrder 策略  
  
1.  在 BizTalk Server 管理中，右键单击**ProcessPurchaseOrder**在列表中，然后单击**删除**。  
  
2.  单击**是**中**删除策略**消息框。  
  
    > [!NOTE]
    >  如果该策略为已部署状态，则无法删除它。 右键单击**ProcessPurchaseOrder**，然后单击**取消部署后再次**取消部署策略。 **删除**未部署此策略时，菜单项是否可用。  
  
    > [!NOTE]
    >  在其上的词汇**ProcessPurchaseOrder**策略依赖，在这种情况下**POVocabulary**，也将被删除。  
  
    > [!NOTE]
    >  在您从某一应用程序删除策略时，该策略以及它所依赖的词汇也将从规则引擎数据库中删除，而不只是从应用程序中删除。  
  
#### <a name="to-import-the-xml-file-to-re-create-the-processpurchaseorder-policy"></a>导入 XML 文件以便重新创建 ProcessPurchaseOrder 策略  
  
1.  在 BizTalk Server 管理中，展开**控制台根节点**，展开[!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)]，然后展开**BizTalk 组**。  
  
2.  右键单击**应用程序**，指向**导入**，然后单击**策略**。  
  
3.  浏览，然后双击该 XML 文件 (**C:\BRE-Walkthroughs\ProcessPOFromAdmin.xml**) 在第一个过程中创建。  
  
4.  展开**\<所有项目 >**下**应用程序**。  
  
5.  单击**策略**，并且你应看到 1.3 版**ProcessPurchaseOrder**列表中的策略。  
  
6.  按下 F5 键来刷新视图。 **ProcessPurchaseOrder**策略应为**未发布**状态。  
  
#### <a name="to-add-the-processpurchaseorder-policy-to-the-ruletestapp-application"></a>将 ProcessPurchaseOrder 策略添加到 RuleTestApp 应用程序  
  
1.  在 BizTalk Server 管理中，右键单击**ProcessPurchaseOrder**策略，，然后单击**发布**。  
  
    > [!NOTE]
    >  只有已发布的策略才能添加到 BizTalk 应用程序中。  
  
2.  在**应用程序**节点，展开**RuleTestApp**。  
  
3.  单击**策略**中**RuleTestApp**。  
  
4.  在右侧的列表中右击，指向**添加**，然后单击**策略**。  
  
5.  展开**ProcessPurchaseOrder**节点中，选择的复选框**版本 1.3 （已发布）**，然后单击**确定**。 实例时都提供 SQL Server 登录名。  
  
6.  右键单击**ProcessPurchaseOrder**，然后单击**部署**。 如果看不到**ProcessPurchaseOrder**在列表中，按 F5 刷新视图。  
  
7.  单击**是**确认消息框中。  
  
## <a name="procedures-for-deploying-the-policy-by-using-an-msi-file"></a>通过使用 MSI 文件部署策略的过程  
  
#### <a name="to-export-the-ruletestapp-application-to-an-msi-file"></a>将 RuleTestApp 应用程序导出到某一 MSI 文件  
  
1.  上**启动**菜单上，打开**BizTalk Server 管理**。 如果已打开该工具，请按 F5 键刷新。  
  
2.  展开**控制台根节点**，展开[!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)]，展开**BizTalk 组**，然后展开**应用程序**。  
  
3.  右键单击**RuleTestApp**，指向**导出**，然后单击**MSI 文件**。  
  
4.  上**欢迎使用导出 MSI 文件向导**页上，单击**下一步**。  
  
5.  上**选择资源**页上，查看所有默认选项，然后单击**下一步**。  
  
6.  上**指定 IIS 主机**页上，单击**下一步**。  
  
7.  上**依赖关系**页上，单击**下一步**。  
  
8.  上**目标**页上，指定的目录和名称作为 MSI **C:\BRE-Walkthroughs\RuleTestApp.msi**。  
  
9. 单击 **“导出”**。  
  
10. 上**摘要**页上，单击**完成**。  
  
    > [!NOTE]
    >  在您导出 RuleTestApp 应用程序时，该应用程序所使用的策略和词汇也将导出到 MSI 文件中。 以后，在您导入该 MSI 文件时，词汇、策略和应用程序也都会重新创建。  
  
#### <a name="to-delete-the-ruletestapp-application"></a>删除 RuleTestApp 应用程序  
  
1.  在 BizTalk Server 管理中，右键单击**RuleTestApp**，并检查如果**删除**菜单是启用还是禁用。  
  
2.  如果**删除**是禁用，右键单击**RuleTestApp**，单击**停止**，选择**句号-终止实例**，然后单击**停止**。  
  
3.  右键单击**RuleTestApp**，然后单击**删除**。  
  
4.  单击**是**以确认删除。  
  
    > [!NOTE]
    >  在您删除某一应用程序时，该应用程序中的所有策略以及相关词汇也将从规则引擎数据库中删除。  
  
#### <a name="to-verify-that-the-processpurchaseorder-policy-and-povocabulary-vocabulary-are-deleted"></a>验证 ProcessPurchaseOrder 策略和 POVocabulary 词汇已删除  
  
1.  上**启动**菜单上，打开**业务规则编辑器**。 如果你有已打开，按 F5 刷新其业务规则编辑器。  
  
    > [!NOTE]
    >  在支持用户帐户控制 (UAC) 的系统上，可能需要具有管理权限才能运行该工具。 要执行此操作，右键单击该应用程序，，然后选择**以管理员身份运行**。  
  
2.  在策略资源管理器窗口中，展开**策略**，并确保 ProcessPurchaseOrder 策略不存在。  
  
3.  在事实浏览器窗口中，展开**词汇**，并确保 POVocabulary 不存在。  
  
#### <a name="to-import-the-msi-file-to-re-create-the-ruletestapp-application"></a>导入 MSI 文件以便重新创建 RuleTestApp 应用程序  
  
1.  上**启动**菜单上，打开**BizTalk Server 管理**。 如果 BizTalk Server 管理控制台已经打开，则按下 F5 键以便刷新它。  
  
2.  展开**控制台根节点**，展开[!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)]，然后展开**BizTalk 组**。  
  
3.  右键单击**应用程序**，指向**导入**，然后单击**MSI 文件**。  
  
4.  上**欢迎使用导入向导**页上，浏览并选择前面导出的 MSI 文件 (RuleTestApp.msi) **MSI 文件以导入**设置。  
  
5.  单击 **“下一步”**。  
  
6.  上**应用程序设置**页上，单击**下一步**。  
  
7.  上**应用程序目标环境设置**页上，单击**下一步**。  
  
8.  上**导入摘要**页上，单击**导入**。  
  
9. 上**导入成功**页上，单击**完成**。 您应该会看到**RuleTestApp**下创建应用程序**应用程序**BizTalk Server 管理控制台中。  
  
#### <a name="to-verify-that-the-processpurchaseorder-policy-is-added-to-ruletestapp"></a>验证 ProcessPurchaseOrder 策略已添加到 RuleTestApp  
  
1.  展开**RuleTestApp** BizTalk Server 管理控制台中。  
  
2.  选择**策略**，你应看到**ProcessPurchaseOrder**在右窗格中的列表中。  
  
#### <a name="to-verify-that-the-processpurchaseorder-policy-and-povocabulary-vocabulary-are-re-created"></a>确认 ProcessPurchaseOrder 策略和 POVocabulary 词汇已重新创建  
  
1.  上**启动**菜单上，打开**业务规则编辑器**。 如果已打开业务规则编辑器，请按 F5 键刷新。  
  
    > [!NOTE]
    >  在支持用户帐户控制 (UAC) 的系统上，可能需要具有管理权限才能运行该工具。 要执行此操作，右键单击该应用程序，，然后选择**以管理员身份运行**。  
  
2.  在策略资源管理器窗口中，展开**策略**，并确保**ProcessPurchaseOrder**存在。  
  
3.  在事实浏览器窗口中，展开**词汇**，并确保**POVocabulary**存在。  
  
#### <a name="to-test-the-solution"></a>若要测试解决方案  
  
1.  上**启动**菜单上，打开**BizTalk Server 管理**。 如果 BizTalk Server 管理控制台已经打开，则按下 F5 键以便刷新它。  
  
2.  展开**控制台根节点**，展开[!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)]，展开**BizTalk 组**，然后展开**应用程序**。  
  
3.  右键单击**RuleTestApp**，然后单击**启动**。  
  
4.  单击**启动**。  
  
5.  复制**SamplePO.xml**在中创建[演练： 测试策略](../core/walkthrough-testing-the-policy.md)到业务流程的输入目录。  
  
6.  你应该在输出目录中看到业务流程的输出文件。 打开输出 XML 文件，可以看到的值**状态**字段设置为**已批准**。  
  
7.  重复步骤 3 和 4 个，带有**SamplePO2.xml**，请注意，和的值**状态**输出文档中的字段是与输入文档中的相同 (**XYZ**)。  
  
## <a name="comments"></a>注释  
  
-   它是**非常重要**记住，当从应用程序中移除策略，你不只是删除应用程序和策略之间的关联; 你还删除策略和其关联的词汇规则引擎数据库。  
  
-   在您开始某一应用程序时，默认情况下，该应用程序将自动部署策略。 同样，当你停止应用程序并选择**句号-终止实例**，关联的策略会自动取消部署。 当选择**部分停止-暂停正在运行的实例**，关联的策略将不自动取消部署。  
  
-   您应该在业务规则编辑器和 BizTalk Server 管理控制台中刷新视图，以便确保在执行任何操作前查看最新信息。  
  
-   如果您创建其先前版本与某一 BizTalk 应用程序关联的策略的新版本，则应手动将该策略的新版本添加到该应用程序。 您不应删除该策略的旧版本，除非确实要从规则引擎数据库中删除它。  
  
-   您可以在导入前将两个或多个 BRL（业务规则语言 XML 文件）文件合并到单个 BRL 文件中。 下面的代码显示三个 BRL 文件。 第一个 BRL 文件包含**POVocabulary**词汇。 第二个 BRL 文件包含**ProcessPurchaseOrder**策略。 第三个 BRL 文件同时包含**POVocabulary**词汇和**ProcessPurchaseOrder**策略。 通过执行以下步骤创建第三个 BRE 文件：  
  
    1.  编辑器创建使用任何文件的新文件并将其保存为 XML 文件 (例如： POPolicyVocabulary.xml)。  
  
    2.  从包含词汇的第一个 BRL 文件复制整个 XML 内容。  
  
    3.  复制 ruleset 块 (开头\<ruleset > 标记和以结尾\</ruleset > 标记) 从第二个 BRL 文件。  
  
    4.  保存该新文件。 你可以导入此单个 XML 文件，以创建**POVocabulary**词汇和**ProcessPurchaseOrder**策略。  
  
    > [!NOTE]
    >  词汇和规则集节点在合并的 BRL 文件中的列出顺序并不重要。 您可以将规则集节点置于词汇节点前。  
  
    ```  
    <?xml version="1.0" encoding="utf-8"?>  
    <brl  
    xmlns="http://schemas.microsoft.com/businessruleslanguage/2002">  
      <vocabulary id="e588676a-ba01-4f37-b59d-91f7e1eb1f1a" name="POVocabulary" uri="" description="">  
           ……   
      </vocabulary>  
    </brl>  
  
    <?xml version="1.0" encoding="utf-8"?>  
    <brl  
    xmlns="http://schemas.microsoft.com/businessruleslanguage/2002">  
      <ruleset name="ProcessPurchaseOrder">  
         ……  
      </ruleset>  
    </brl>  
  
    <brl  
    xmlns="http://schemas.microsoft.com/businessruleslanguage/2002">  
      <vocabulary id="e588676a-ba01-4f37-b59d-91f7e1eb1f1a" name="POVocabulary" uri="" description="">  
           ……   
      </vocabulary>  
      <ruleset name="ProcessPurchaseOrder">  
         ……  
      </ruleset>  
    </brl>  
    ```