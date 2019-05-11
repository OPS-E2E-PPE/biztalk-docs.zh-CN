---
title: 第 2 步：创建库存请求架构 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 0fa9ad9f-b815-4baf-8299-556869b8dde7
caps.latest.revision: 45
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c0729083983aad67ad751aa3dd25d63c6a4c031f
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65392752"
---
# <a name="step-2-create-the-inventory-request-schema"></a>第 2 步：创建库存请求架构
![步骤 2，共 5](../core/media/step-2of5.gif "Step_2of5")  

 **若要完成的时间：** 7 分钟  

 **目标：** 在此步骤中，定义库存补货消息的架构。  仓库系统发送此消息以请求库存补货。  这是一个必须为此项目创建的两个架构。  

 **目的：** XML 不仅结构和标识信息与标准化的标记代码，但也有使用架构的功能。 架构是由其他 XML 文档的 XML 文档的工作方式类似于字典和用作参考。 架构代码定义 XML 元素的拼写和由这些元素括起来的数据类型。 使用架构为 XML 文档，并确保结构和类型的信息是正确的处理程序提供一种简便方法。  

## <a name="prerequisites"></a>先决条件  
 在开始此步骤之前，请注意以下要求：  

-   在开始此步骤之前，必须完成[步骤 1:创建 EAISchemas 项目](../core/step-1-create-eaischemas-project.md)。  

## <a name="procedures"></a>过程  
 在[步骤 1:创建 EAISchemas 项目](../core/step-1-create-eaischemas-project.md)，创建了一个新[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]项目。  如果您关闭[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]窗口中，您可以使用以下过程以打开该项目。  否则，则可以跳过此过程中，"若要打开 Visual Studio 项目"。  

#### <a name="to-open-the-visual-studio-project"></a>若要打开 Visual Studio 项目  

1. 启动**Microsoft Visual Studio**。  

2. 在[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]，然后在**文件**菜单中，依次指向**打开**，然后单击**项目/解决方案**。  

3. 在中**打开项目**对话框中，浏览到**C:\BTSTutorials\EAISolution\EAISolution.sln**解决方案文件，然后单击**打开**。  

   在下面的过程中，向库存补货消息的项目添加新的架构文件。  

#### <a name="to-add-a-new-schema-to-the-project"></a>若要向项目添加新架构  

1. 在解决方案资源管理器中右键单击**EAISchemas**项目，指向**添加**，然后单击**新项**。  

2. 在中**添加新项-EAISchemas**对话框框中，执行以下操作：  


   |        使用此选项         |                   执行的操作                   |
   |-------------------------|------------------------------------------------|
   | **已安装的模板** | 单击**架构文件**，然后单击**架构**。 |
   |        **名称**         |             类型**Request.xsd**。              |


3. 单击 **“添加”**。 显示架构树和 XSD 窗格。 此区域[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]称为作为 BizTalk 编辑器。 此外，新添加的架构将显示在解决方案资源管理器中的 EAISchemas 项目下。  

    ![BizTalk 项目的不同部分](../core/media/differentpartsofbiztalkserver.gif "DifferentpartsofBizTalkServer")  

#### <a name="to-add-elements-to-the-schema"></a>若要将元素添加到架构  

1. 在架构树中，单击**根**节点。  

2. 在属性窗格中的值更改**节点名称**属性设置为`Request`，然后按 ENTER。  

3. 在架构树中，右键单击**请求**节点，指向**插入 Schema 节点**，然后单击**子记录**。  

4. 类型`Header`作为子记录，然后按 ENTER 键的新名称。  

5. 重复步骤 3 和 4，以创建另一个子记录**请求**节点，并将其命名`Items`。  

6. 在架构树中，右键单击**标头**节点，指向**插入 Schema 节点**，然后单击**子字段元素**。  

7. 类型`ReqID`作为以及该元素，然后按 ENTER 键的新名称。  

8. 重复步骤 6 和 7，创建另一个子字段元素**标头**节点，并将其命名`OrderDate`。

9. 重复步骤 6 和 7，以创建第三个子字段元素**标头**节点，并将其命名`GrandTotal`。

10. 在架构树中，右键单击**项**节点，指向**插入 Schemas 节点**，然后单击**子记录**。  

11. 类型`Item`作为子记录，然后按 ENTER 键的新名称。  

12. 在架构树中，右键单击**项**节点，并添加下列子字段元素：  

    - `Description`  

    - `Quantity`  

    - `UnitPrice`  

      已完成的 Request.xsd 应类似于下图。  

      ![使用请求架构的解决方案资源管理器](../core/media/solutionexplorerwiththerequestschema.gif "SolutionExplorerwiththeRequestSchema")  

    时将节点添加到架构，BizTalk 编辑器提供一组默认值为其属性。  必须将它们根据要求配置。  

#### <a name="to-configure-the-elements"></a>若要配置的元素  

1. 在架构树中，单击**OrderDate**以将其选中。  

2. 在属性窗格中更改**数据类型**到**xs: datetime**。  

3. 重复步骤 1 和 2 来配置以下属性：  

   |元素|属性|ReplTest1|  
   |-------------|--------------|-----------|  
   |**GrandTotal**|**数据类型**|**Xs:decimal**|  
   |**项**|**最大出现次数**|**不受限制**|  
   |**项**|**最小出现次数**|**1**|  
   |**数量**|**数据类型**|**xs:unsignedInt**|  

   架构可以具有多个元素，但你的应用程序可能只需进行数据处理使用其中几个。 若要保存的计算机资源，BizTalk Server 不自动读取每个架构元素。 如果你想要从特定元素中读取数据的 BizTalk Server，必须通过使用 BizTalk 编辑器以升级其属性来标识该元素。  

   我们将在中创建的业务流程[第 2 课：定义业务流程](../core/lesson-2-define-the-business-process.md)会基于 GrandTotal 字段来路由消息。  因此，必须升级 GrandTotal 字段。  

#### <a name="to-promote-an-element"></a>若要升级元素  

1.  在架构树中，右键单击**GrandTotal**，依次指向**Promote**，然后单击**快速升级**。  

2.  单击**确定**以确认添加属性架构。  

3.  在“文件”  菜单上，单击“全部保存” 。  

## <a name="what-did-i-just-do"></a>我只需做了什么？  
 在此步骤中，您将定义仓库库存补货消息架构。  

## <a name="next-steps"></a>后续步骤  
 定义请求拒绝消息架构。  

## <a name="see-also"></a>请参阅  
 [步骤 1：创建 EAISchemas 项目](../core/step-1-create-eaischemas-project.md)   
 [步骤 3：创建请求拒绝架构](../core/step-3-create-the-request-decline-schema.md)   
 [步骤 4：创建映射](../core/step-4-create-the-map.md)   
 [步骤 5：生成 EAISchemas 项目](../core/step-5-build-the-eaischemas-project.md)   
 [使用 BizTalk 编辑器创建架构](../core/creating-schemas-using-biztalk-editor.md)   
 [关于 BizTalk 消息上下文属性](../core/about-biztalk-message-context-properties.md)
