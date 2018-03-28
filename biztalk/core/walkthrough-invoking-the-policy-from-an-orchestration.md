---
title: 演练： 调用从业务流程的策略 |Microsoft 文档
ms.custom: ''
ms.date: 2016-04-05
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: cb2d2974-8a36-4d36-905c-799e4236ef99
caps.latest.revision: ''
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 36de942d34a4235b689b464192a460451e7c921a
ms.sourcegitcommit: 8418b1a8f38b7f56979cd6e203f0b591e2f40fe1
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/28/2018
---
# <a name="walkthrough-invoking-the-policy-from-an-orchestration"></a>演练： 调用从业务流程的策略
你可以通过以下方式之一从业务流程调用策略：  
  
-   通过使用 **调用规则** 形状  
  
-   通过使用 **表达式** 形状，并以编程方式调用以执行策略的规则引擎 (**Policy.Execute** 方法)  
  
 使用 **调用规则** 形状的最常见方法是也是调用从业务流程的策略的推荐的方式。 本演练提供了分步过程使用 **调用规则** 形状来调用 **ProcessPurchaseOrder** 策略。  
  
## <a name="prerequisites"></a>先决条件  
 必须完成[演练： 测试策略](../core/walkthrough-testing-the-policy.md)执行本演练之前的演练。  
  
## <a name="overview-of-this-walkthrough"></a>本演练的概述  
 本演练包含七个过程，如下表所述。  
  
|过程标题|过程说明|  
|---------------------|---------------------------|  
|创建具有架构和业务流程的 BizTalk 项目|提供用于创建架构和时，将调用一个业务流程的分步说明 **ProcessPurchaseOrder** 策略。|  
|创建消息变量|提供创建在业务流程中使用的消息变量的分步说明。|  
|配置形状|提供在业务流程中配置形状的分步说明。|  
|若要创建端口|提供在业务流程中创建端口的分步说明。|  
|将端口与形状连接|提供将端口与形状连接的分步说明。|  
|若要生成和部署解决方案|提供生成和部署解决方案的分步说明。|  
|若要测试解决方案|提供用于测试解决方案的分步说明。|  
  
### <a name="to-create-a-biztalk-project-with-a-schema-and-an-orchestration"></a>创建具有架构和业务流程的 BizTalk 项目  
  
1.  启动 **Microsoft Visual Studio**。  
  
2.  在 [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)], 上 **文件** 菜单上，指向 **新建**, ，然后单击 **项目**。  
  
3.  在 **新项目** 对话框框中，执行以下操作︰  
  
    |使用此选项|执行的操作|  
    |--------------|----------------|  
    |**项目类型**|单击 **BizTalk 项目**。|  
    |**模板**|单击 **空 BizTalk 服务器项目**。|  
    |**名称**|类型 **RuleTest**。|  
    |**位置**|指定 **C:\BRE-Walkthroughs**。|  
    |**解决方案名称**|类型 **RuleTestSol**。|  
    |**创建解决方案的目录**|选中此复选框以便为解决方案文件创建目录。|  
  
4.  单击 **“确定”**。 **RuleTest** 项目应显示在解决方案资源管理器中。 如果看不到解决方案资源管理器，请单击 **解决方案资源管理器** 上 **视图** 菜单。  
  
5.  在解决方案资源管理器，右键单击 **RuleTest**, ，指向 **添加**, ，然后单击 **现有项**。  
  
6.  浏览并添加**PO.xsd**中创建的架构文件[演练： 创建简单的业务策略](../core/walkthrough-creating-a-simple-business-policy.md)演练。 Visual Studio，你可以一份 **PO.xsd** 文件并将其添加到项目。  
  
7.  在解决方案资源管理器，右键单击 **RuleTest**, ，指向 **添加**, ，然后单击 **新项**。  
  
8.  在 **添加新项** 对话框框中，执行以下操作︰  
  
    |使用此选项|执行的操作|  
    |--------------|----------------|  
    |**类别**|单击 **Orchestration 文件**。|  
    |**模板**|单击 **BizTalk 业务流程**。|  
    |**名称**|类型 **RuleTest.odx**。|  
  
9. 单击 **“添加”**。  
  
10. 右键单击 **从工具箱中删除形状**, ，指向 **插入形状**, ，然后单击 **接收**。  
  
11. 在属性窗口中，将名称更改 **接收** 形状变为 **ReceivePO**, ，并将的值设置 **激活** 属性 `true`。  
  
12. 在工具箱中，在 **BizTalk 业务流程** 选项卡上，拖动 **调用规则** 形状拖到下面的连线 **接收** 形状。  
  
13. 在属性窗口中，将名称更改 **调用规则** 形状变为 **CallProcessPOPolicy**。  
  
14. 右键单击以下 **调用规则** 形状，指向 **插入形状**, ，然后单击 **发送**。  
  
15. 在属性窗口中，将名称更改 **发送** 形状变为 **SendPO**。 业务流程如下图所示。  
  
     ![BRE&#45;Walkthrough&#45;UnconfiguredOrch](../core/media/1f3502ac-82a9-40bf-ae31-6e8356a283e2.gif "1f3502ac-82a9-40bf-ae31-6e8356a283e2")  
  
### <a name="to-create-message-variables"></a>创建消息变量  
  
1.  在业务流程视图窗口中，右键单击 **消息**, ，然后单击 **新消息**。 如果看不到业务流程视图窗口，请单击 **视图** 菜单上，指向 **其他窗口**, ，然后单击 **业务流程视图**。 通常，“业务流程视图”窗口显示在“解决方案资源管理器”选项卡的旁边。默认情况下，名为新消息 **Message_1**。  
  
     ![BRE&#45;Walkthrough&#45;OrchViewNewMsg](../core/media/a0b7fee3-af90-4c01-9464-146f0ca449e5.gif "a0b7fee3-af90-4c01-9464-146f0ca449e5")  
  
2.  在业务流程视图窗口中，单击 **Message_1**。  
  
3.  在“属性”窗口中，执行以下操作：  
  
    |使用此选项|执行的操作|  
    |--------------|----------------|  
    |**标识符**|类型 **POInst**, ，然后按 ENTER。|  
    |**消息类型**|从下拉列表中，展开 **架构**, ，然后选择 **RuleTest.PO**。|  
  
     ![BRE&#45;Walkthrough&#45;MsgProps](../core/media/c82cfb67-63f6-4133-95bf-daadac0e213a.gif "c82cfb67-63f6-4133-95bf-daadac0e213a")  
  
### <a name="to-configure-shapes"></a>配置形状  
  
1.  选择 **接收** 中业务流程设计器形状。  
  
2.  在属性窗口中，选择 **POInst** 为 **消息** 属性。  
  
3.  双击 **调用规则** 中业务流程设计器形状。  
  
4.  在 **调用规则策略配置** 对话框中，选择 **ProcessPurchaseOrder** 策略。  
  
5.  单击下一步 **\***, 下面 **参数名称**, ，然后选择 **POInst** 作为参数传递给策略。  
  
     ![BRE&#45;Walkthrough&#45;ConfigureCallRules](../core/media/0e7dab04-41db-433b-bbf5-b13901033b41.gif "0e7dab04-41db-433b-bbf5-b13901033b41")  
  
6.  单击 **“确定”**。  
  
7.  选择 **发送** 形状中业务流程。  
  
8.  在属性窗口中，将的值设置 **消息类型** 属性 **POInst**。  
  
### <a name="to-create-ports"></a>若要创建端口  
  
1.  创建两个文件夹 **输入** 和 **输出**, ，C:\BRE-Walkthroughs\RuleTestSol 文件夹中。  
  
2.  右击的业务流程，左的端口图面，然后单击 **新配置端口**。  
  
3.  单击“下一步” 。 类型 **ReceivePOPrt** 端口名称。  
  
4.  单击 **下一步** 两次。  
  
5.  选择 **现在指定** 为 **端口绑定**。  
  
6.  指定 **文件** 为 **传输**, ，键入作为输入的目录的名称和 **C:\BRE-Walkthroughs\RuleTestSol\Input\\\*.xml** 以及文件掩码 (**\*.xml**) uri。  
  
7.  单击“下一步” ，然后单击“完成” 。  
  
8.  右击业务流程的正确端口图面，然后单击 **新配置端口**。  
  
9. 单击“下一步” 。 类型 **SendPOPort** 端口名称。  
  
10. 单击 **下一步** 两次。  
  
11. 更改 **端口的通信的方向** 到 **我将始终发送消息上此端口**。  
  
12. 选择 **现在指定** 为 **端口绑定**。  
  
13. 指定 **文件** 为 **传输**, ，键入作为输出目录的名称和 **C:\BRE-Walkthroughs\RuleTestSol\Output**,，和 %MessageID%.xml 作为输出文件的名称。  
  
14. 单击“下一步” ，然后单击“完成” 。  
  
### <a name="to-connect-ports-with-the-shapes"></a>将端口与形状连接  
  
1.  连接 **ReceivePOPrt** 端口到 **ReceivePO** 形状。 （将端口图面上 ReceivePOPrt 端口右侧的箭头拖到 ReceivePO 形状上的框。）  
  
     ![BRE&#45;Walkthrough&#45;ConnectRP](../core/media/75bdf79e-ca98-43bb-8ff6-5f46005a6490.gif "75bdf79e-ca98-43bb-8ff6-5f46005a6490")  
  
2.  连接 **SendPO** 形状变为 **SendPOPrt** 端口。  
  
     ![BRE&#45;Walkthrough&#45;ConnectSP](../core/media/7513f52b-2782-4357-b8eb-1874dec33869.gif "7513f52b-2782-4357-b8eb-1874dec33869")  
  
### <a name="to-build-and-deploy-the-solution"></a>若要生成和部署解决方案  
  
1.  启动 **Microsoft Visual Studio**。  
  
2.  在[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]，在解决方案资源管理器，右键单击**RuleTest**项目，，然后单击**属性**。  
  
3.  在项目设计器中 （中心窗格） 中，单击 **签名**。  
  
4.  在签名选项卡上，选中 **对程序集签名** 的复选框。在下拉列表中 **选择强名称密钥文件**, ，单击 **新建**;在 **密钥文件名称** 字段中，输入规则测试;在 **密码** 字段 （可选）、 设置密码，然后再单击 **确定**。  
  
5.  在项目设计器中，单击 **部署** 切换到部署选项卡。  
  
6.  指定 **RuleTestApp** 作为应用程序名称。  
  
     ![BRE&#45;Walkthrough&#45;RuleTestApp](../core/media/b153e5b0-ca46-4d27-bfa1-9ad4e58e9787.gif "b153e5b0-ca46-4d27-bfa1-9ad4e58e9787")  
  
7.  单击 **“确定”**。  
  
8.  右键单击 **RuleTest** 项目，，然后单击 **生成**。  
  
9. 右键单击 **RuleTest** 项目，，然后单击 **部署**。  
  
### <a name="to-test-the-solution"></a>若要测试解决方案  
  
1.  在业务规则编辑器，展开 **策略**, ，展开 **ProcessPurchaseOrder**, ，右键单击 **版本 1.0**, ，然后单击 **发布**。  
  
2.  右键单击 **版本 1.0-发布**, ，然后单击 **部署**。  
  
3.  在 **启动** 菜单上，打开 **BizTalk Server 管理**。 如果 BizTalk Server 管理控制台已经打开，则按下 F5 键以便刷新它。  
  
4.  展开**控制台根节点**，展开[!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)]，展开**BizTalk 组**，然后展开**应用程序**。  
  
5.  右键单击 **RuleTestApp**, ，然后单击 **配置**。  
  
6.  单击 **Orchestration_1**, ，并指定 **BizTalkServerApplication** 作为主机。  
  
     ![BRE&#45;Walkthrough&#45;AppHost](../core/media/ba348a98-661f-4e71-8b9b-b8c5fadf035a.gif "ba348a98-661f-4e71-8b9b-b8c5fadf035a")  
  
7.  单击 **“确定”**。  
  
8.  右键单击 **RuleTestApp**, ，然后单击 **启动**。  
  
9. 在 **开始 RuleTestApp 应用程序** 对话框中，单击 **启动**, ，并已成功启动应用程序，然后等待。  
  
10. 打开 **SamplePO.xml** 和 **SamplePO2.xml** 在记事本中，将的值更改 **状态** 字段 **XYZ**。  
  
11. 复制 **SamplePO.xml** 文件从 C:\BRE-Walkthroughs 目录到 C:\BRE-Walkthroughs\RuleTestSol\Input 目录业务流程。  
  
12. 你应该在业务流程的 C:\BRE-Walkthroughs\RuleTestSol\Output 目录中看到输出文件。 打开输出 XML 文件，可以看到的值 **状态** 字段设置为 **已批准**。  
  
13. 重复步骤 11 和 12 个 **SamplePO2.xml**, ，请注意，和的值 **状态** 输出文档中的字段是与输入文档中的相同 (**xyz**)。  
  
## <a name="comments"></a>注释  
  
-   在此业务流程中，为了向业务流程添加形状，你没有使用工具栏中的形状。 相反，你单击了鼠标右键，并选择了要插入的形状。  
  
-   有关配置 **调用规则** 形状考察已保存的最新版本时确定使用的类型。 运行时，将使用部署的最新版本。  
  
-   如果你打算使用策略版本不是已部署的最新版本，则应使用 **表达式** 形状，并调用规则引擎以编程方式以执行该特定版本的策略。 有关详细信息，请参阅[如何执行策略](../core/how-to-execute-policies.md)。  
  
-   **调用规则** 形状重新构造消息，就像使用 **构造消息** 形状，这又可能导致丢失消息的上下文属性。  
  
-   策略在发布之后不能修改。  
  
-   客户端应用程序只能访问已部署的策略。 如果客户端应用程序调用未部署的策略，生成的规则引擎 **RuleEngineDeploymentNotDeployedException** 异常。 在应用程序事件日志中可看到详细的错误消息。  
  
## <a name="next-steps"></a>后续步骤  
 现在，你已完成本演练中，执行[演练： 创建和使用该策略中的词汇](../core/walkthrough-creating-and-using-a-vocabulary-in-the-policy.md)演练中，这为你提供分步说明来创建词汇和使用中的词汇**ProcessPurchaseOrder**策略。  
  
## <a name="see-also"></a>另请参阅  
 [条件计算和操作执行](../core/condition-evaluation-and-action-execution.md)   
 [安排和优先级](../core/agenda-and-priority.md)   
 [在业务流程中调用业务规则](../core/invoking-business-rules-in-orchestrations.md)