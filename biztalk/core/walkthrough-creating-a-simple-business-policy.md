---
title: "演练： 创建简单的业务策略 |Microsoft 文档"
ms.custom: 
ms.date: 2016-04-05
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 02d35735-dce2-4ee2-965e-dae307a125b0
caps.latest.revision: "25"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 0c894ab80926d2fad66af540c492dd053570aaa4
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="walkthrough-creating-a-simple-business-policy"></a>演练： 创建简单的业务策略
本演练提供了使用业务规则编辑器创建名为的简单的业务策略的分步过程**ProcessPurchaseOrder**包含一个名为规则**ApprovedRule**。 **ApprovedRule**规则需要用户提交 XML 文档作为一个事实中，并设置的值**状态**字段到文档中**已批准**如果的值**数量**字段是否小于或等于**500**。  
  
## <a name="prerequisites"></a>先决条件  
 你必须熟悉要执行本演练的业务规则框架的基础知识。 如果你不熟悉业务规则框架，我们建议你阅读在业务规则框架的体系结构概述[业务规则引擎](../core/business-rules-engine.md)执行本演练之前。  
  
## <a name="overview-of-this-walkthrough"></a>本演练的概述  
 本概览包含两个过程，如下表所述。  
  
|过程标题|过程说明|  
|---------------------|---------------------------|  
|若要创建的采购订单架构文件|提供用于创建文档的架构的分步说明**ProcessPurchaseOrder**策略使用。|  
|若要创建 ProcessPurchaseOrder 策略|提供有关创建的分步说明**ProcessPurchaseOrder**通过业务规则编辑器的策略。|  
  
### <a name="to-create-the-po-schema-file"></a>若要创建的采购订单架构文件  
  
1.  上**启动**菜单上，打开**记事本**。  
  
2.  在 **“文件”** 菜单上，指向 **“新建”**，然后单击 **“文件”**。  
  
3.  将以下 XML 文本复制到编辑器：  
  
    ```  
    <?xml version="1.0" encoding="utf-16"?>  
    <xs:schema xmlns:b="http://schemas.microsoft.com/BizTalk/2003" xmlns="http://EAISolution.PurchaseOrder" targetNamespace="http://EAISolution.PurchaseOrder" xmlns:xs="http://www.w3.org/2001/XMLSchema">  
      <xs:element name="PurchaseOrder">  
        <xs:complexType>  
          <xs:sequence>  
            <xs:element name="Header">  
              <xs:complexType>  
                <xs:sequence>  
                  <xs:element name="ReqID" type="xs:string" />  
                  <xs:element name="Date" type="xs:string" />  
                </xs:sequence>  
              </xs:complexType>  
            </xs:element>  
            <xs:element name="Item">  
              <xs:complexType>  
                <xs:sequence>  
                  <xs:element name="Description" type="xs:string" />  
                  <xs:element name="Quantity" type="xs:int" />  
                  <xs:element name="UnitPrice" type="xs:string" />  
                </xs:sequence>  
              </xs:complexType>  
            </xs:element>  
            <xs:element name="Status" type="xs:string" />  
          </xs:sequence>  
        </xs:complexType>  
      </xs:element>  
    </xs:schema>  
    ```  
  
4.  上**文件**菜单上，单击**TextFile1.txt 另存为**。  
  
5.  值更改**另存为类型**从**文本文档 (\*.txt)**到**所有文件**。  
  
6.  类型**PO.xsd**中**文件名**文本框中，将目录更改为**C:\BRE-Walkthroughs**，更改的值**编码**到**Unicode** ，然后单击**保存**。  
  
    > [!NOTE]
    >  创建目录**BRE 演练**下**c:\\** 如果它不存在，，然后单击**保存**。  
  
7.  关闭记事本。  
  
### <a name="to-create-the-processpurchaseorder-business-policy"></a>若要创建 ProcessPurchaseOrder 业务策略  
  
1.  上**启动**菜单上，打开**业务规则编辑器**。  
  
    > [!NOTE]
    >  在支持用户帐户控制 (UAC) 的系统上，可能需要具有管理权限才能运行该工具。 要执行此操作，右键单击该应用程序，，然后选择**以管理员身份运行**。  
  
    > [!NOTE]
    >  业务规则编辑器显示**打开规则存储**对话框中的计算机上首次打开时。 如果你看到**打开规则存储**对话框中，单击**确定**后验证的 SQL server 名称和数据库名称。  
  
2.  在策略资源管理器窗口中，右键单击**策略**，然后单击**添加新策略**。  
  
3.  编辑策略，该名称**策略 1**到**ProcessPurchaseOrder** ，然后按 enter 键。 你还可以更改中的策略的名称**属性**窗口。  
  
4.  右键单击**版本 1.0**，然后单击**AddNewRule**。  
  
5.  编辑规则的名称**规则 1**到**ApprovalRule** ，然后按 enter 键**。** 你还可以更改中的规则的名称**属性**窗口。  
  
6.  在事实浏览器窗口中，单击**XML 架构**选项卡。  
  
7.  右键单击**架构**，单击**浏览**，然后选择**PO.xsd**前面创建的文件。  
  
8.  在属性窗口中，更改值**文档类型**属性从**PO**到**RuleTest.PO**。  
  
    > [!NOTE]
    >  你将需要创建一个名为的 BizTalk 项目**RuleTest**后面[演练： 调用从业务流程策略](../core/walkthrough-invoking-the-policy-from-an-orchestration.md)演练。 在于演练中，你将添加**PO.xsd**到项目文件中，创建时，将调用一个业务流程**ProcessPurchaseOrder**策略，以及然后测试策略。 若要测试的策略与业务流程，你需要确保你更改**文档类型**属性**\<项目名称 >。\<SchemaName >**，即**RuleTest.PO**在这种情况下。  
  
     ![BRE &#45;演练 &#45;ChangeDocType](../core/media/e9a370fd-d9b2-48f0-ad0e-85a5428a9c21.gif "e9a370fd-d9b2-48f0-ad0e-85a5428a9c21")  
  
9. 在事实浏览器窗口中，展开**PurchaseOrder**，然后展开**项**。  
  
10. 在 IF （顶端） 右侧窗格中，右键单击**条件**，单击**谓词**，然后单击**LessThanEqual**。  
  
     ![业务规则编辑器 &#45;小于或等于](../core/media/1e6418a6-5e5b-4f77-8b7e-dd31d0a753e7.gif "1e6418a6-5e5b-4f77-8b7e-dd31d0a753e7")  
  
11. 拖动**数量**从事实浏览器窗口中对节点**argument1**如果窗格中。  
  
     ![业务规则编辑器 &#45;DragQuantity](../core/media/4742eca6-4a8a-401d-8989-cab4e8025fb3.gif "4742eca6-4a8a-401d-8989-cab4e8025fb3")  
  
     ![业务规则编辑器 &#45;UseQuantity](../core/media/ee4f61b1-0f15-4329-b0b5-9badd21dcd61.gif "ee4f61b1-0f15-4329-b0b5-9badd21dcd61")  
  
12. 在 IF 窗格中，单击**argument2**，类型`500`，然后按 ENTER。  
  
13. 拖动**状态**在业务规则编辑器的底部右侧的 THEN 窗格中的事实数据资源管理器窗口中的节点。  
  
     ![业务规则编辑器 &#45; DragStatus](../core/media/3617251a-a192-4aec-9474-81f6290c0832.gif "3617251a-a192-4aec-9474-81f6290c0832")  
  
14. 在 THEN 窗格中，单击**\<输入值 >**然后键入**已批准**。  
  
15. 在策略资源管理器窗口中，右键单击**（不保存） 1.0 版**，然后单击**保存**。  
  
## <a name="comments"></a>注释  
  
-   一个策略可拥有一个或多个规则。 你将添加另一个规则， **DeniedRule**中[演练： 将规则添加到策略](../core/walkthrough-adding-a-rule-to-the-policy.md)演练。  
  
-   当策略处于“已保存”状态时，您可以修改策略以添加更多规则及更改条件和操作。  
  
-   你可以设置规则的执行优先级通过指定**优先级**上业务规则编辑器中的规则的属性。 例如，如果你单击**ApprovedRule**策略资源管理器窗口中的节点，你可以看到**优先级**属性窗口中的属性。 数字越大，规则优先级越高。  
  
-   策略作为数据源，可以使用 XML 架构、 数据库或.NET 程序集。 在本演练中，您使用 XML 架构作为数据源。 你应与给规则引擎，以执行策略的事实提交架构的 XML 文档实例。  
  
## <a name="next-steps"></a>后续步骤  
 现在，你已完成本演练中，执行[演练： 测试策略](../core/walkthrough-testing-the-policy.md)演练中，这为你提供用于测试的分步说明**ProcessPurchaseOrder**策略你在本演练中创建。  
  
## <a name="see-also"></a>另请参阅  
 [有关业务规则](../core/about-business-rules.md)