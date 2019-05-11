---
title: 演练：跟踪 BizTalk Server 中的策略执行 |Microsoft Docs
description: 本教程启用跟踪，并在 BizTalk Server 中查看策略的跟踪详细信息
ms.custom: ''
ms.date: 04/05/2016
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: ef88eae7-f0f8-4f3f-85d0-3961a47395b6
caps.latest.revision: 17
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 2285353afb1049574e5f78eafeba41931102ac56
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65395948"
---
# <a name="walkthrough-tracking-policy-execution"></a>演练：跟踪策略执行
有关启用跟踪的分步过程**ProcessPurchaseOrder**策略，并执行策略后查看跟踪信息。  
  
## <a name="prerequisites"></a>先决条件  
完成[演练：修改策略](../core/walkthrough-modifying-the-policy.md)执行本演练中之前的演练。  
  
## <a name="enable-tracking-for-the-processpurchaseorder-policy"></a>启用 ProcessPurchaseOrder 策略跟踪  
  
1.  打开 **“BizTalk Server 管理”**。 如果已打开，请按 f5 键刷新。  
  
2.  展开**控制台根节点**，展开**BizTalk Server 管理**，展开**BizTalk 组**，展开**应用程序**，然后展开**RuleTestApp**。  
  
3.  右键单击**策略**，选择**添加**，然后选择**策略**。  
  
    > [!NOTE]
    >  若要启用跟踪的策略，你必须将策略添加到 BizTalk 应用程序通过使用 BizTalk Server 管理控制台。  
  
4.  在中**添加策略**对话框框中，展开**ProcessPurchaseOrder**，然后选择版本**1.3**。  
  
5.  单击“确定” 。  
  
6.  如果没有看到**ProcessPurchaseOrder**在列表中，选择 f5 键以刷新视图。
  
7.  右键单击**ProcessPurchaseOrder**，然后选择**跟踪。**  
  
8.  在中**策略跟踪选项**对话框中，选择所有复选都框**事实活动**，**条件评估**，**规则触发**，并**议程更新**。  
  
9. 单击“确定” 。  
  
## <a name="test-the-solution-and-view-the-tracking-information"></a>测试解决方案和查看跟踪信息  
  
1.  打开**SamplePO.xml**并**SamplePO2.xml**在记事本中，并将的值更改**状态**字段**XYZ**。  
  
2.  复制**SamplePO.xml**中创建[演练：测试策略](../core/walkthrough-testing-the-policy.md)到业务流程的输入目录。  
  
3.  您应看到业务流程的输出目录中输出文件。 打开输出 XML 文件，可以看到的值**状态**字段设置为**Approved**。  
  
4.  在中**BizTalk Server 管理**，请转到**组概述**页上，单击**组中心**选项卡，然后单击**跟踪的服务实例**.  
  
5.  右键单击业务流程 (RuleTest.Orchestration_1) 的名称，然后单击**消息流**。  
  
6.  单击**单击此链接可查看该业务流程实例的策略执行详细信息**。 请确保您看到的窗口的外观如下图所示：  
  
     ![BRE&#45;演练&#45;FirstScreen](../core/media/1e59fe9e-cf2d-407a-81cd-102b57a515d2.gif "1e59fe9e-cf2d-407a-81cd-102b57a515d2")  
  
7. 单击时间或**ProcessPurchaseOrder1.3**若要查看下面的屏幕。 在此屏幕中，可以看到请求策略执行、 业务流程，该策略的执行的时间，ID 和策略的 ID 的服务 （业务流程）。  
  
     ![BRE&#45;演练&#45;PolicyExecDetails](../core/media/a65fd48f-2a54-4cc5-9b45-4cd3c211da33.gif "a65fd48f-2a54-4cc5-9b45-4cd3c211da33")  
  
8. 单击**事实活动**若要查看的事实 （数据），已添加到规则引擎工作内存和从规则引擎工作内存中取消的事实数据。  
  
     ![BRE&#45;Walkthrough&#45;FactActivity](../core/media/27bc0d84-f202-4f5a-87a1-8b53006b3cee.gif "27bc0d84-f202-4f5a-87a1-8b53006b3cee")  
  
9. 上**文件**菜单上，单击**Navigate 后**。  
  
10. 单击**条件计算的**。 请参阅有关已评估的条件的详细信息。 在这种情况下，在策略中，有两个规则和每个策略有一个条件。 您可以看到，评估两个条件;其中一个计算结果为`true`，和另一个计算结果为`false`。  
  
     ![BRE&#45;演练&#45;ConditionEvaluation](../core/media/ac772d01-919f-4b22-995b-409501a96848.gif "ac772d01-919f-4b22-995b-409501a96848")  
  
11. 上**文件**菜单上，单击**Navigate 后**。  
  
12. 单击**议程更新**。 您所见，只有 ApprovalRule 添加到议程。 DeniedRule 并未添加到议程，因为其条件计算结果为`false`。  
  
     ![BRE&#45;Walkthrough&#45;Agenda](../core/media/bc85d9ea-fc76-44de-aa75-134f47a5ec20.gif "bc85d9ea-fc76-44de-aa75-134f47a5ec20")  
  
13. 单击**ApprovalRule**看到 ApprovalRule 的定义。  
  
14. 上**文件**菜单上，单击**Navigate 后**。  
  
15. 上**文件**菜单上，单击**Navigate 后**试。  
  
16. 单击**触发的规则**。 您可以看到已触发只有 ApprovalRule （已执行针对 ApprovalRule 的操作）。  
  
17. 上**文件**菜单上，单击**Navigate 后**。  
  
18. 单击**没有启用的规则**。 您可以看到，DeniedRule 并未触发，因为它不在议程中。  
  
19. 重复步骤 1-使用 18 **SamplePO2.xml**。  
  
## <a name="key-details"></a>关键详细信息  
  
-   跟踪信息的策略是非常类似于测试策略时，将业务规则编辑器中显示的跟踪信息。  
  
-   尽管业务流程名称是 RuleTest.odx，但您看到的业务流程名称 orchestration_1，因为即使更改了名称，该业务流程类型名称设置为 Orchestration_1。 跟踪显示业务流程名称采用格式\<Namespace\>。\<键入名称\>。  
  
-   如果使用 BizTalk Server 管理控制台从 BizTalk 应用程序删除策略，该工具将删除策略，不仅从应用程序，而且还从规则引擎数据库。 你将无法再看到业务规则编辑器 （按 F5 刷新） 中的策略。 因此，你应从应用程序中删除策略时请小心。  
  
-   在停止 RuleTestApp 并选中**完全停止**选项，ProcessPurchaseOrder 策略 （版本 1.3） 将自动取消部署。  
  
-   如果策略由多个应用程序，创建单独的应用程序策略，并创建对它的客户端应用程序。 如果将策略添加到所有客户端应用程序，当你停止其中一个客户端应用程序时，该策略将取消部署，并对其他客户端应用程序无需再使用该策略。 因此最好创建单独的应用程序的两个或多个应用程序间共享的策略。  
  
-   当你启动 RuleTestApp 时，ProcessPurchaseOrder 策略 （版本 1.3） 将自动部署。  
  
## <a name="next-steps"></a>后续步骤  
 现在，已完成本演练，请转到[演练：部署策略](../core/walkthrough-deploying-the-policy.md)演练中，为您提供用于部署策略的分步说明。  
  
## <a name="see-also"></a>请参阅  
 [如何配置跟踪的策略](../core/how-to-configure-tracking-for-a-policy.md)   
 [管理策略](../core/managing-policies.md)