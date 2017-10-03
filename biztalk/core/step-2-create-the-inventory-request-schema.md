---
title: "步骤 2： 创建清单请求架构 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 0fa9ad9f-b815-4baf-8299-556869b8dde7
caps.latest.revision: "45"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 5199b20a75b82e12ad76b96903538487a3128668
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="step-2-create-the-inventory-request-schema"></a>步骤 2：创建库存请求架构
![步骤 2 5](../core/media/step-2of5.gif "Step_2of5")  
  
 **完成时间：** 7 分钟  
  
 **目标：**在此步骤中，定义库存补货消息的架构。  仓库系统发送此消息以请求库存补货。  此架构是必须为该项目创建的两个架构之一。  
  
 **用途：** XML 不仅结构和标识信息与标准化的标记代码，但也有使用架构的能力。 架构是一类工作方式与字典类似的 XML 文档，可供其他 XML 文档用作参考。 架构代码定义 XML 元素的拼写以及用这些元素括起来的数据类型。 通过使用架构，程序可轻松处理 XML 文档，并确保信息的结构和类型正确。  
  
## <a name="prerequisites"></a>先决条件  
 在开始此步骤之前，请注意以下要求：  
  
-   在开始此步骤之前必须完成[步骤 1： 创建 EAISchemas 项目](../core/step-1-create-eaischemas-project.md)。  
  
## <a name="procedures"></a>过程  
 在[步骤 1： 创建 EAISchemas 项目](../core/step-1-create-eaischemas-project.md)，你创建的新[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]项目。  如果关闭 [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] 窗口，可使用以下过程打开该项目。  否则，可跳过“打开 Visual Studio 项目”这一步骤。  
  
#### <a name="to-open-the-visual-studio-project"></a>打开 Visual Studio 项目  
  
1.  启动**Microsoft Visual Studio**。  
  
2.  在[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]上**文件**菜单上，指向**打开**，然后单击**项目/解决方案**。  
  
3.  在**打开项目**对话框中，浏览到**C:\BTSTutorials\EAISolution\EAISolution.sln**解决方案文件，然后单击**打开**。  
  
 在下面的过程中，针对库存补货消息向项目添加新架构文件。  
  
#### <a name="to-add-a-new-schema-to-the-project"></a>向项目添加新架构  
  
1.  在解决方案资源管理器，右键单击**EAISchemas**项目，指向**添加**，然后单击**新项**。  
  
2.  在**添加新项-EAISchemas**对话框框中，执行以下操作：  
  
    |使用此选项|执行的操作|  
    |--------------|----------------|  
    |**已安装的模板**|单击**架构文件**，然后单击**架构**。|  
    |**名称**|类型**Request.xsd**。|  
  
3.  单击 **“添加”**。 此时，将显示架构树和 XSD 窗格。 在 [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] 中，此区域称为“BizTalk 编辑器”。 此外，新添加的架构将显示在解决方案资源管理器中的 EAISchemas 项目下。  
  
     ![BizTalk 项目不同部分](../core/media/differentpartsofbiztalkserver.gif "DifferentpartsofBizTalkServer")  
  
#### <a name="to-add-elements-to-the-schema"></a>向架构添加元素  
  
1.  在架构树中，单击**根**节点。  
  
2.  在属性窗格中，将的值更改**节点名称**属性`Request`，然后按 ENTER。  
  
3.  在架构树中，右键单击**请求**节点，指向**插入架构节点**，然后单击**子记录**。  
  
4.  类型`Header`作为子记录，然后按 enter 键的新名称。  
  
5.  重复步骤 3 和 4，以创建第二个子记录**请求**节点，并将其命名`Items`。  
  
6.  在架构树中，右键单击**标头**节点，指向**插入架构节点**，然后单击**子字段元素**。  
  
7.  类型`ReqID`作为以及该元素，然后按 enter 键的新名称。  
  
8.  重复步骤 6 和 7，以创建第二个子字段元素**标头**节点，并将其命名`OrderDate`。  
  
9. 在架构树中，右键单击**项**节点，指向**插入架构节点**，然后单击**子记录**。  
  
10. 类型`Item`作为子记录，然后按 enter 键的新名称。  
  
11. 在架构树中，右键单击**项**节点，并添加以下子字段元素：  
  
    -   `Description`  
  
    -   `Quantity`  
  
    -   `UnitPrice`  
  
     完成的 Request.xsd 应类似于下图：  
  
     ![解决方案资源管理器的请求架构与](../core/media/solutionexplorerwiththerequestschema.gif "SolutionExplorerwiththeRequestSchema")  
  
 在向架构添加节点时，BizTalk 编辑器会为这些节点的属性分配一组默认值。  必须按照要求配置它们。  
  
#### <a name="to-configure-the-elements"></a>若要配置的元素  
  
1.  在架构树中，单击**OrderDate**以将其选中。  
  
2.  在属性窗格中，更改**数据类型**到**xs: datetime**。  
  
3.  重复步骤 1 和 2 来配置以下属性：  
  
    |元素|属性|值|  
    |-------------|--------------|-----------|  
    |**GrandTotal**|**数据类型**|**Xs: decimal**|  
    |**项**|**最大出现次数**|**不受限制**|  
    |**项**|**最小出现次数**|**1**|  
    |**数量**|**数据类型**|**xs:unsignedInt**|  
  
 虽然一个架构可包含多个元素，但应用程序可能只需要使用其中的几个元素来处理数据。 为了节约计算机资源，BizTalk Server 不自动读取每个架构元素。 如果你希望 BizTalk Server 读取来自某个特定元素的数据，则必须使用 BizTalk 编辑器标识该元素以升级其属性。  
  
 我们将在创建业务流程[第 2 课： 定义业务流程](../core/lesson-2-define-the-business-process.md)将基于则 GrandTotal 字段设置为将消息路由。  因此，必须升级 GrandTotal 字段。  
  
#### <a name="to-promote-an-element"></a>升级元素  
  
1.  在架构树中，右键单击**GrandTotal**，指向**Promote**，然后单击**快速提升**。  
  
2.  单击**确定**以确认添加属性架构。  
  
3.  在“文件”  菜单上，单击“全部保存” 。  
  
## <a name="what-did-i-just-do"></a>内容回顾  
 在此步骤中，定义了仓库库存补货消息架构。  
  
## <a name="next-steps"></a>后续步骤  
 定义请求拒绝消息架构。  
  
## <a name="see-also"></a>另请参阅  
 [步骤 1： 创建 EAISchemas 项目](../core/step-1-create-eaischemas-project.md)   
 [步骤 3： 创建请求拒绝架构](../core/step-3-create-the-request-decline-schema.md)   
 [步骤 4： 创建代码图](../core/step-4-create-the-map.md)   
 [步骤 5： 生成 EAISchemas 项目](../core/step-5-build-the-eaischemas-project.md)   
 [创建使用 BizTalk 编辑器的架构](../core/creating-schemas-using-biztalk-editor.md)   
 [有关 BizTalk 消息上下文属性](../core/about-biztalk-message-context-properties.md)