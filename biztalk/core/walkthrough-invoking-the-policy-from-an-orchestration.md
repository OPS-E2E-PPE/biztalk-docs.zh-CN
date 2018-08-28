---
title: 演练： 调用从业务流程的策略 |Microsoft Docs
ms.custom: ''
ms.date: 2016-04-05
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: cb2d2974-8a36-4d36-905c-799e4236ef99
caps.latest.revision: 30
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 33bef51b2c702e71fcf6ef0ea0c4fd63b28fbde8
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36976551"
---
# <a name="walkthrough-invoking-the-policy-from-an-orchestration"></a>演练： 调用的策略与业务流程
你可以通过以下方式之一从业务流程调用策略：  

- 通过使用**调用规则**形状  

- 通过使用**表达式**形状，并以编程方式调用规则引擎来执行策略 (**Policy.Execute**方法)  

  使用**调用规则**形状是最常见的方式，还从业务流程调用策略的推荐的方法。 本演练提供了使用的分步过程**调用规则**形状来调用**ProcessPurchaseOrder**策略。  

## <a name="prerequisites"></a>必要條件  
 必须完成[演练： 测试策略](../core/walkthrough-testing-the-policy.md)执行本演练中之前的演练。  

## <a name="overview-of-this-walkthrough"></a>本演练概述  
 本演练包含七个过程，如下表所述。  

|过程标题|过程说明|  
|---------------------|---------------------------|  
|创建具有架构和业务流程的 BizTalk 项目|提供用于创建架构和调用的业务流程的分步说明**ProcessPurchaseOrder**策略。|  
|创建消息变量|提供创建在业务流程中使用的消息变量的分步说明。|  
|配置形状|提供在业务流程中配置形状的分步说明。|  
|若要创建端口|提供在业务流程中创建端口的分步说明。|  
|将端口与形状连接|提供将端口与形状连接的分步说明。|  
|若要生成并部署解决方案|提供生成和部署解决方案的分步说明。|  
|若要测试解决方案|提供用于测试解决方案的分步说明。|  

### <a name="to-create-a-biztalk-project-with-a-schema-and-an-orchestration"></a>创建具有架构和业务流程的 BizTalk 项目  

1. 启动**Microsoft Visual Studio**。  

2. 在中[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]，然后在**文件**菜单中，依次指向**新建**，然后单击**项目**。  

3. 在中**新的项目**对话框框中，执行以下操作：  


   |             使用此选项              |                             执行的操作                              |
   |-----------------------------------|---------------------------------------------------------------------|
   |         **项目类型**         |                     单击**BizTalk 项目**。                     |
   |           **模板**           |               单击**为空的 BizTalk Server 项目**。               |
   |             **名称**              |                         类型**RuleTest**。                          |
   |           **位置**            |                  指定**C:\BRE-Walkthroughs**。                   |
   |         **解决方案名称**         |                        类型**RuleTestSol**。                        |
   | **创建解决方案的目录** | 选中此复选框以便为解决方案文件创建目录。 |


4. 单击“确定” 。 **RuleTest**项目应该显示在解决方案资源管理器。 如果看不到解决方案资源管理器，请单击**解决方案资源管理器**上**视图**菜单。  

5. 在解决方案资源管理器中右键单击**RuleTest**，依次指向**添加**，然后单击**现有项**。  

6. 浏览并添加**PO.xsd**中创建的架构文件[演练： 创建简单业务策略](../core/walkthrough-creating-a-simple-business-policy.md)演练。 Visual Studio，可以一份**PO.xsd**文件，并将其添加到项目。  

7. 在解决方案资源管理器中右键单击**RuleTest**，依次指向**添加**，然后单击**新项**。  

8. 在中**添加新项**对话框框中，执行以下操作：  


   |    使用此选项    |            执行的操作            |
   |----------------|----------------------------------|
   | **类别** |  单击**业务流程文件**。  |
   | **模板**  | 单击**BizTalk 业务流程**。 |
   |    **名称**    |      类型**RuleTest.odx**。      |


9. 单击 **“添加”**。  

10. 右键单击**从工具箱中删除形状**，依次指向**插入形状**，然后单击**接收**。  

11. 在属性窗口中，将名称更改**接收**形状变为**ReceivePO**，并将值设置**激活**属性设置为`true`。  

12. 在工具箱中，在**BizTalk 业务流程**选项卡上，拖动**调用规则**形状下方的连接线**接收**形状。  

13. 在属性窗口中，将名称更改**调用规则**形状变为**CallProcessPOPolicy**。  

14. 下单击鼠标右键**调用规则**形状中，依次指向**插入形状**，然后单击**发送**。  

15. 在属性窗口中，将名称更改**发送**形状变为**SendPO**。 业务流程如下图所示。  

     ![BRE&#45;演练&#45;UnconfiguredOrch](../core/media/1f3502ac-82a9-40bf-ae31-6e8356a283e2.gif "1f3502ac-82a9-40bf-ae31-6e8356a283e2")  

### <a name="to-create-message-variables"></a>创建消息变量  

1.  在业务流程视图窗口中，右键单击**消息**，然后单击**新消息**。 如果看不到业务流程视图窗口，请单击**视图**菜单，依次指向**其他 Windows**，然后单击**业务流程视图**。 通常，“业务流程视图”窗口显示在“解决方案资源管理器”选项卡的旁边。默认情况下，命名为新的消息**Message_1**。  

     ![BRE&#45;演练&#45;OrchViewNewMsg](../core/media/a0b7fee3-af90-4c01-9464-146f0ca449e5.gif "a0b7fee3-af90-4c01-9464-146f0ca449e5")  

2.  在业务流程视图窗口中，单击**Message_1**。  

3.  在“属性”窗口中，执行以下操作：  

    |使用此选项|执行的操作|  
    |--------------|----------------|  
    |**Identifier**|类型**POInst**，然后按 ENTER。|  
    |**消息类型**|从下拉列表中，展开**架构**，然后选择**RuleTest.PO**。|  

     ![BRE&#45;Walkthrough&#45;MsgProps](../core/media/c82cfb67-63f6-4133-95bf-daadac0e213a.gif "c82cfb67-63f6-4133-95bf-daadac0e213a")  

### <a name="to-configure-shapes"></a>配置形状  

1. 选择**接收**形状在业务流程设计器中的。  

2. 在属性窗口中，选择**POInst**有关**消息**属性。  

3. 双击**调用规则**形状在业务流程设计器中的。  

4. 在中**调用规则策略配置**对话框中，选择**ProcessPurchaseOrder**策略。  

5. 旁边**\\**<em>下文 * * 参数名称</em><em>，然后选择 **POInst</em>* 作为策略的参数。  

    ![BRE&#45;演练&#45;ConfigureCallRules](../core/media/0e7dab04-41db-433b-bbf5-b13901033b41.gif "0e7dab04-41db-433b-bbf5-b13901033b41")  

6. 单击“确定” 。  

7. 选择**发送**形状在业务流程中的。  

8. 在属性窗口中设置的值**消息类型**属性设置为**POInst**。  

### <a name="to-create-ports"></a>若要创建端口  

1.  创建两个文件夹**输入**并**输出**，C:\BRE-Walkthroughs\RuleTestSol 文件夹中。  

2.  右键单击该业务流程的左侧的端口图面，然后单击**新建配置的端口**。  

3.  单击“下一步” 。 类型**ReceivePOPrt**为端口名称。  

4.  单击**下一步**两次。  

5.  选择**立即指定**有关**端口绑定**。  

6.  指定**文件**有关**传输**，然后键入输入目录的名称**C:\BRE-Walkthroughs\RuleTestSol\Input\\\*.xml**文件掩码以及 (**\*.xml**) uri。  

7.  单击“下一步” ，然后单击“完成” 。  

8.  右键单击该业务流程的右侧端口图面，然后单击**新建配置端口**。  

9. 单击“下一步” 。 类型**SendPOPort**为端口名称。  

10. 单击**下一步**两次。  

11. 更改**端口通信方向**到**我始终在发送消息此端口上**。  

12. 选择**立即指定**有关**端口绑定**。  

13. 指定**文件**有关**传输**，并键入输出目录的名称**C:\BRE-Walkthroughs\RuleTestSol\Output**，和 %MessageID%.xml 与输出文件名称。  

14. 单击“下一步” ，然后单击“完成” 。  

### <a name="to-connect-ports-with-the-shapes"></a>将端口与形状连接  

1.  连接**ReceivePOPrt**到端口**ReceivePO**形状。 （将端口图面上 ReceivePOPrt 端口右侧的箭头拖到 ReceivePO 形状上的框。）  

     ![BRE&#45;Walkthrough&#45;ConnectRP](../core/media/75bdf79e-ca98-43bb-8ff6-5f46005a6490.gif "75bdf79e-ca98-43bb-8ff6-5f46005a6490")  

2.  连接**SendPO**形状变为**SendPOPrt**端口。  

     ![BRE&#45;Walkthrough&#45;ConnectSP](../core/media/7513f52b-2782-4357-b8eb-1874dec33869.gif "7513f52b-2782-4357-b8eb-1874dec33869")  

### <a name="to-build-and-deploy-the-solution"></a>若要生成并部署解决方案  

1. 启动**Microsoft Visual Studio**。  

2. 在中[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]，在解决方案资源管理器中右键单击**RuleTest**项目，然后依次**属性**。  

3. 在项目设计器 （在中心窗格） 中，单击**签名**。  

4. 在签名选项卡上，选中**为程序集签名**的复选框。在下拉列表**选择强名称密钥文件**，单击**新建**;在中**密钥文件名称**字段中，输入规则测试;在中**密码**字段 （可选）、 设置密码，然后依次**确定**。  

5. 在项目设计器中，单击**部署**切换到部署选项卡。  

6. 指定**RuleTestApp**作为应用程序名称。  

    ![BRE&#45;演练&#45;RuleTestApp](../core/media/b153e5b0-ca46-4d27-bfa1-9ad4e58e9787.gif "b153e5b0-ca46-4d27-bfa1-9ad4e58e9787")  

7. 单击“确定” 。  

8. 右键单击**RuleTest**项目，并单击**生成**。  

9. 右键单击**RuleTest**项目，并单击**部署**。  

### <a name="to-test-the-solution"></a>若要测试解决方案  

1. 在业务规则编辑器中，展开**策略**，展开**ProcessPurchaseOrder**，右键单击**版本 1.0**，然后单击**发布**.  

2. 右键单击**版本 1.0-已发布**，然后单击**部署**。  

3. 在中**启动**菜单中，打开**BizTalk Server 管理**。 如果 BizTalk Server 管理控制台已经打开，则按下 F5 键以便刷新它。  

4. 展开**控制台根节点**，展开[!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)]，展开**BizTalk 组**，然后展开**应用程序**。  

5. 右键单击**RuleTestApp**，然后单击**配置**。  

6. 单击**Orchestration_1**，并指定**BizTalkServerApplication**作为主机。  

    ![BRE&#45;演练&#45;AppHost](../core/media/ba348a98-661f-4e71-8b9b-b8c5fadf035a.gif "ba348a98-661f-4e71-8b9b-b8c5fadf035a")  

7. 单击“确定” 。  

8. 右键单击**RuleTestApp**，然后单击**启动**。  

9. 在中**启动 'RuleTestApp' 应用程序**对话框中，单击**启动**，，然后等到已成功启动应用程序。  

10. 打开**SamplePO.xml**并**SamplePO2.xml**在记事本中，将的值更改**状态**字段**XYZ**。  

11. 复制**SamplePO.xml**文件从 C:\BRE-Walkthroughs 目录的 C:\BRE-Walkthroughs\RuleTestSol\Input 目录到业务流程。  

12. 你应该在业务流程的 C:\BRE-Walkthroughs\RuleTestSol\Output 目录中看到输出文件。 打开输出 XML 文件，可以看到的值**状态**字段设置为**Approved**。  

13. 重复步骤 11 和 12 个**SamplePO2.xml**，您会发现的值**状态**输出文档中的字段是与输入文档中的相同 (**xyz**)。  

## <a name="comments"></a>注释  

-   在此业务流程中，为了向业务流程添加形状，你没有使用工具栏中的形状。 相反，你单击了鼠标右键，并选择了要插入的形状。  

-   配置**调用规则**形状的外观保存的最新版本时确定使用的类型。 运行时，将使用部署的最新版本。  

-   如果你打算使用策略版本，而不是最新的已部署版本，则应使用**表达式**形状，并调用规则引擎以编程方式来执行该特定版本的策略。 有关详细信息，请参阅[如何执行策略](../core/how-to-execute-policies.md)。  

-   **调用规则**形状重新构造消息，如同使用**构造消息**形状，因而可能导致消息丢失的上下文属性。  

-   策略在发布之后不能修改。  

-   客户端应用程序只能访问已部署的策略。 如果客户端应用程序调用未部署的策略，规则引擎将生成**RuleEngineDeploymentNotDeployedException**异常。 在应用程序事件日志中可看到详细的错误消息。  

## <a name="next-steps"></a>后续步骤  
 现在，已完成本演练中，执行[演练： 创建和使用策略中的某一词汇](../core/walkthrough-creating-and-using-a-vocabulary-in-the-policy.md)演练中，为您提供用于创建词汇和使用词汇的分步说明**ProcessPurchaseOrder**策略。  

## <a name="see-also"></a>请参阅  
 [条件评估和操作执行](../core/condition-evaluation-and-action-execution.md)   
 [议程和优先级](../core/agenda-and-priority.md)   
 [在业务流程中调用业务规则](../core/invoking-business-rules-in-orchestrations.md)