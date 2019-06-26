---
title: 步骤 5：修改 Contoso 专用业务流程 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- private processes, orchestrations
- private process tutorial, modifying private process orchestration
ms.assetid: a5430db8-e5f0-48a6-abb9-e268d8ec2ec4
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 298a6ab0728928347b33f65ba5819a62897511cb
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65280855"
---
# <a name="step-5-modifying-the-contoso-private-process-orchestration"></a>步骤 5：修改 Contoso 专用业务流程
在此步骤中，修改专用业务流程与企业资源规划 (ERP) 系统集成，为 Contoso。 Contoso ERP 系统使用的产品价格与可用性的内部定义的架构。 通过自定义专用流程 3a2-价格与可用性合作伙伴接口流程 (PIP)，你将能够通过使用架构映射信息与 ERP 系统集成。  
  
### <a name="to-add-a-reference-to-the-contoso-priceandavailability-and-rnpips-assemblies"></a>若要添加对 Contoso PriceAndAvailability 和 Rnpip 程序集的引用  
  
1. Contoso 解决方案显示在解决方案资源管理器中，右键单击**PrivateResponder**项目，并单击**添加引用**。  
  
2. 在添加引用对话框中，单击**浏览**。 将移动到 *\<驱动器\>* : \Program Files\Microsoft BizTalk\<版本\>Accelerator for RosettaNet\Bin 文件夹，然后选择以下程序集<strong>:</strong>  
  
   -   Microsoft.Solutions.BTARN.CommonTypes.dll  
  
   -   Microsoft.Solutions.BTARN.ConfigurationManager.dll  
  
   -   Microsoft.Solutions.BTARN.GlobalSchemas.dll  
  
   -   Microsoft.Solutions.BTARN.PublicResponder.dll  
  
   -   Microsoft.Solutions.BTARN.Schemas.RNPIPs.dll  
  
   -   Microsoft.Solutions.BTARN.Shared.dll  
  
   -   Microsoft.Solutions.BTARN.XSDClasses.GlobalSchemas.dll  
  
3. 单击 **“添加”** 。  
  
4. 在添加引用对话框中，单击**项目**选项卡上，选择**ContosoPriceAndAvailability**并**HeaderHelper**项目，并单击**添加**。  
  
5. 单击“确定”  。  
  
6. 在 Microsoft 的开发环境对话框中，单击**确定**。  
  
### <a name="to-create-new-message-types"></a>若要创建新的消息类型  
  
1.  在解决方案资源管理器中双击**PrivateResponder**业务流程以将其打开。  
  
2.  在解决方案资源管理器，单击**业务流程视图**。  
  
3.  在业务流程视图中，右键单击**消息**，然后单击**新消息**。  
  
4.  在属性窗口中**标识符**框中，键入**PIP3A2RequestMessage**。  
  
5.  在中**消息类型**框中，单击下拉箭头，展开**架构**，然后选择 **\<从引用的程序集选择\>** 。  
  
6.  在选择项目类型框中，选择**Microsoft.Solutions.BTARN.Schemas.RNPIPs**在左窗格中，选择 **_3A2PriceAndAvailabilityQueryMessageGuideline_v1_3**在右窗格中，并然后单击**确定**。  
  
7.  重复步骤 3 至 6 以创建使用以下信息的解决方案的所有消息类型：  
  
    |Identifier|Assembly|消息类型|  
    |----------------|--------------|------------------|  
    |PIP3A2ResponseMessage|Microsoft.Solutions.BTARN.<br />Schemas.RNPips|_3A2PriceAndAvailability<br />ResponseMessageGuideline_v1_3|  
    |Contoso3A2ResponseMessage|ContosoPriceAndAvailability|rootPriceResponse|  
    |Contoso3A2RequestMessage|ContosoPriceAndAvailability|rootPriceRequest|  
  
8.  你已创建解决方案的消息类型。  
  
### <a name="to-create-new-variables"></a>若要创建新变量  
  
1.  在业务流程视图中，右键单击**变量，** ，然后单击**新变量**。  
  
2.  在属性窗口中**标识符**框中，键入**contosoResponseXML**。  
  
3.  在中**类型**框中，选择 **\<.NET 类\>** 从下拉列表。  
  
4.  在选择项目中，在键入对话框中，在左窗格中，**当前项目**并**引用**节点，选择**System.Xml**，选择**XmlDocument**从列表中在右窗格中，然后单击**确定**。  
  
5.  在中**业务流程视图**，单击**变量**，然后单击**新变量**。  
  
6.  在属性窗口中**标识符**框中，键入**submitMessage**。  
  
7.  在中**类型**框中，选择 **\<.NET 类\>** 从下拉列表。  
  
8.  在选择项目类型对话框中，在左窗格中，展开**当前项目**并**引用**节点，选择**再**，选择**SubmitRNIF**从列表中在右窗格中，然后单击**确定**。  
  
### <a name="to-change-the-orchestration-filter-expression"></a>若要更改的业务流程筛选器表达式  
  
1.  在业务流程设计器中，选择**ReceiveFromPublicProcessResponder**形状。  
  
2.  在属性窗口中**筛选器表达式**框中，单击值框，然后单击省略号按钮 ( **...** ) 以打开筛选器表达式对话框。  
  
3.  在筛选器表达式对话框中，在**Group By**部分中，单击**或者**值的第一行上，然后选择**AND**从下拉列表。  
  
4.  在筛选器表达式对话框中，单击**单击此处可添加新行**，然后选择**Microsoft.Solutions.BTARN.GlobalSchemas.SCPIPCode**从下拉列表。  
  
5.  在同一行中，单击**值**，然后键入 **"3A2"** 。  
  
6.  在同一行中，单击**AND**中**Group By**框，并选择**或**从下拉列表。  
  
7.  在筛选器表达式对话框中，选择刚创建的行，然后单击上的箭头按钮一次移动一次一行。  
  
8.  单击**单击此处可添加新行**，然后选择**Microsoft.Solutions.BTARN.GlobalSchemas.SCPIPCode**从下拉列表。  
  
9. 在同一行中，单击**值**，然后键入 **"3A2"** 。  
  
10. 单击“确定”。  
  
### <a name="to-modify-the-business-process-workflow"></a>若要修改业务流程工作流  
  
1. 拖动**消息赋值**形状从工具箱拖到设计图面并将其下放置**ReceiveFromPublicProcessResponder**形状。 选择**ConstructMessage_1**已创建的形状并在**属性**窗口中，在**名称**框中，键入**ConstructPIP3A2RequestMessage**.  
  
2. 拖动**转换**形状到设计图面并将其下放置**ConstructPIP3A2RequestMessage**形状。 选择**ConstructMessage_1**已创建的形状并在**属性**窗口中，在**名称**框中，键入**ConstructContoso3A2RequestMessage**.  
  
3. 拖动**发送**形状到设计图面并将其下放置**ConstructContoso3A2RequestMessage**形状。  
  
4. 拖动**接收**形状到设计图面并将其下放置**Send_1**形状。  
  
5. 在业务流程设计图面上，单击空白区域。  
  
6. 在属性窗口中，选择**事务类型**属性，，然后单击**长期**。  
  
7. 拖动**作用域**形状到设计图面并将其下放置**Receive_1**形状。  
  
8. 在属性窗口中，从**事务类型**属性下拉列表中，选择**原子**有关**范围**形状。  
  
9. 拖动**调用规则**至设计图面上形状，然后将其放上显示的标签**从工具箱中删除形状**内部**范围**形状。 中的属性窗口**调用规则**形状，在**名称**框中，键入**Execute3A2Vocabulary**。  
  
10. 拖动**转换**形状到设计图面并将其下放置**Scope_1**形状。 单击**ConstructMessage_1**形状。 在属性窗口中**名称**框中，键入**Construct3A2ResponseMessage**。  
  
11. 拖动**表达式**形状到设计图面并将其下放置**Construct3A2ResponseMessageTransform**形状。  
  
12. 在[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]，然后在**文件**，单击**全部保存**以保存项目。  
  
## <a name="see-also"></a>请参阅  
 [步骤 6：配置业务流程形状 (Contoso)](../../adapters-and-accelerators/accelerator-rosettanet/step-6-configuring-orchestration-shapes-contoso.md)