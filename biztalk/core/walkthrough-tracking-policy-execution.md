---
title: "演练： 跟踪 BizTalk Server 中的策略执行 |Microsoft 文档"
description: "教程启用跟踪，并在 BizTalk Server 中查看策略跟踪详细信息"
ms.custom: 
ms.date: 04/05/2016
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: ef88eae7-f0f8-4f3f-85d0-3961a47395b6
caps.latest.revision: "17"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f20b35aca2c4fb35419153ccfb149aa34501b21a
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/28/2017
---
# <a name="walkthrough-tracking-policy-execution"></a>演练： 跟踪策略执行
启用跟踪的分步过程**ProcessPurchaseOrder**策略，以及执行策略后，请查看跟踪信息。  
  
## <a name="prerequisites"></a>先决条件  
完成[演练： 修改策略](../core/walkthrough-modifying-the-policy.md)执行本演练之前的演练。  
  
## <a name="enable-tracking-for-the-processpurchaseorder-policy"></a>启用跟踪 ProcessPurchaseOrder 策略  
  
1.  打开 **“BizTalk Server 管理”**。 如果已打开，按 F5 刷新它。  
  
2.  展开**控制台根节点**，展开**BizTalk Server 管理**，展开**BizTalk 组**，展开**应用程序**，然后展开**RuleTestApp**。  
  
3.  右键单击**策略**，选择**添加**，然后选择**策略**。  
  
    > [!NOTE]
    >  若要启用策略跟踪，则必须使用 BizTalk Server 管理控制台，向 BizTalk 应用程序添加策略。  
  
4.  在**添加策略**对话框框中，展开**ProcessPurchaseOrder**，并选择版本**1.3**。  
  
5.  单击 **“确定”**。  
  
6.  如果看不到**ProcessPurchaseOrder**在列表中，选择 f5 键以刷新视图。
  
7.  右键单击**ProcessPurchaseOrder**，然后选择**跟踪。**  
  
8.  在**策略跟踪选项**对话框中，选择所有的复选框**事实活动**，**条件评估**，**规则触发**，和**安排更新**。  
  
9. 单击 **“确定”**。  
  
## <a name="test-the-solution-and-view-the-tracking-information"></a>测试解决方案和查看跟踪信息  
  
1.  打开**SamplePO.xml**和**SamplePO2.xml**在记事本中，并将的值更改**状态**字段**XYZ**。  
  
2.  复制**SamplePO.xml**在中创建[演练： 测试策略](../core/walkthrough-testing-the-policy.md)到业务流程的输入目录。  
  
3.  你应该在输出目录中看到业务流程的输出文件。 打开输出 XML 文件，可以看到的值**状态**字段设置为**已批准**。  
  
4.  在**BizTalk Server 管理**，请转到**组概述**页上，单击**组中心数据库**选项卡上，然后单击**跟踪服务实例**.  
  
5.  右击业务流程 (RuleTest.Orchestration_1) 的名称，然后单击**消息流**。  
  
6.  单击**点击此链接以查看此业务流程实例的策略执行详细信息**。 请确保你看到类似于下图窗口：  
  
     ![BRE &#45;演练 &#45;FirstScreen](../core/media/1e59fe9e-cf2d-407a-81cd-102b57a515d2.gif "1e59fe9e-cf2d-407a-81cd-102b57a515d2")  
  
7. 单击相应的时间或**ProcessPurchaseOrder1.3**以查看下面的屏幕。 在此屏幕中，你可看到请求策略执行的服务（业务流程）、业务流程的 ID、策略的执行时间以及策略的 ID。  
  
     ![BRE &#45;演练 &#45;PolicyExecDetails](../core/media/a65fd48f-2a54-4cc5-9b45-4cd3c211da33.gif "a65fd48f-2a54-4cc5-9b45-4cd3c211da33")  
  
8. 单击**事实活动**若要查看已声明转换规则的事实数据 （数据） 引擎的工作内存和已收回从规则引擎的工作内存的事实数据。  
  
     ![BRE &#45;演练 &#45;FactActivity](../core/media/27bc0d84-f202-4f5a-87a1-8b53006b3cee.gif "27bc0d84-f202-4f5a-87a1-8b53006b3cee")  
  
9. 上**文件**菜单上，单击**导航回**。  
  
10. 单击**条件计算**。 你将看到有关已评估的条件的详细信息。 在本例中，策略中存在两条规则，并且每个策略都有一个条件。 你可以看到，评估两个条件;一个计算结果为`true`，和另一个计算结果为`false`。  
  
     ![BRE &#45;演练 &#45;ConditionEvaluation](../core/media/ac772d01-919f-4b22-995b-409501a96848.gif "ac772d01-919f-4b22-995b-409501a96848")  
  
11. 上**文件**菜单上，单击**导航回**。  
  
12. 单击**安排更新**。 可以看到，只有 ApprovalRule 添加到了议程中。 并未将 DeniedRule 添加到议程中，因为其条件的评估结果为 `false`。  
  
     ![BRE &#45;演练 &#45;安排](../core/media/bc85d9ea-fc76-44de-aa75-134f47a5ec20.gif "bc85d9ea-fc76-44de-aa75-134f47a5ec20")  
  
13. 单击**ApprovalRule**若要查看 ApprovalRule 的定义。  
  
14. 上**文件**菜单上，单击**导航回**。  
  
15. 上**文件**菜单上，单击**导航回**试。  
  
16. 单击**激发的规则**。 你可以看到，只触发了 ApprovalRule（已执行针对 ApprovalRule 的操作）。  
  
17. 上**文件**菜单上，单击**导航回**。  
  
18. 单击**未不会触发的规则**。 可以看到，DeniedRule 并未触发，因为它不在议程中。  
  
19. 重复步骤 1-18 与**SamplePO2.xml**。  
  
## <a name="key-details"></a>密钥的详细信息  
  
-   当你测试策略时，策略跟踪信息非常类似于你在业务规则编辑器中看到的跟踪信息。  
  
-   尽管业务流程名称是 RuleTest.odx，但你看到的业务流程名称却是 Orchestration_1，因为尽管“名称”改变，业务流程的“类型名”仍设置为 Orchestration_1。 跟踪显示你的业务流程名称格式\<Namespace\>。\<键入名称\>。  
  
-   如果使用 BizTalk Server 管理控制台从 BizTalk 应用程序中删除某个策略，则工具不仅将从应用程序中删除策略，而且还将从规则引擎数据库中删除策略。 你将无法在业务规则编辑器中看到策略（按 F5 刷新）。 因此，在将策略从应用程序中删除时务必小心。  
  
-   在停止 RuleTestApp 并选中**句号**选项，正在自动取消部署 ProcessPurchaseOrder 策略 （1.3 版）。  
  
-   如果多个应用程序共享一个策略，则将为该策略创建一个单独的应用程序，然后从客户端应用程序创建对该应用程序的引用。 如果将策略添加到所有客户端应用程序，那么，当你停止其中一个客户端应用程序时，该策略将取消部署，其他客户端应用程序将不再能够使用此策略。 因此，如果两个或多个应用程序间共享某个策略，则最好为该策略创建一个单独的应用程序。  
  
-   如果启动 RuleTestApp，ProcessPurchaseOrder 策略（版本 1.3）将自动部署。  
  
## <a name="next-steps"></a>后续步骤  
 现在，你已完成本演练，请转到[演练： 部署策略](../core/walkthrough-deploying-the-policy.md)演练中，这为你提供部署策略的分步说明。  
  
## <a name="see-also"></a>另请参阅  
 [如何配置策略的跟踪](../core/how-to-configure-tracking-for-a-policy.md)   
 [管理策略](../core/managing-policies.md)