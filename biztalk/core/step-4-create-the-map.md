---
title: "步骤 4： 创建映射 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 2f7f1f6d-0e57-4a65-b91d-c81fcc832961
caps.latest.revision: "36"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 9fcbce54a488cb687ad0fb2c7a1931243c8cd882
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/28/2017
---
# <a name="step-4-create-the-map"></a>步骤 4：创建映射
![步骤 4 5](../core/media/step-4of5.gif "Step_4of5")  
  
 **完成时间：** 6 だ 牧  
  
 **目标：**在此步骤中，你创建的地图，转换到 RequestDecline 消息请求消息。  
  
 **用途：**映射可确保，返回到仓库库存系统的请求拒绝消息中包含了申请 ID 号和总计。 使用 BizTalk 映射器，可将传入消息中的字段链接到为传出消息定义的字段。 因为这两种消息的架构结构不同，因此必须这样做。  
  
## <a name="prerequisites"></a>先决条件  
 在开始此步骤之前，请注意以下要求：  
  
-   在开始此步骤之前必须完成[步骤 2： 创建清单请求架构](../core/step-2-create-the-inventory-request-schema.md)和[步骤 3： 创建请求拒绝架构](../core/step-3-create-the-request-decline-schema.md)。  
  
## <a name="procedures"></a>过程  
 此映射依赖于 Request 架构和 RequestDecline 架构。  您必须先使用架构编译项目，然后才可以在映射上使用它们。  
  
#### <a name="to-compile-the-eaischemas-project"></a>编译 EAISchemas 项目  
  
-   在解决方案资源管理器，右键单击**EAISchemas**，然后单击**生成**。  
  
#### <a name="to-create-the-map"></a>若要创建映射  
  
1.  在解决方案资源管理器，右键单击**EAISchemas**项目，指向**添加**，然后单击**新项**。  
  
2.  在**添加新项-EAISchemas**对话框框中，执行以下操作：  
  
    |使用此选项|执行的操作|  
    |--------------|----------------|  
    |**已安装的模板**|单击**映射文件**，然后单击**映射**。|  
    |**名称**|类型**MapToReqDecline.btm**。|  
  
3.  单击 **“添加”**。  
  
     下图显示了“源架构”、“目标架构”和“映射器网格”：  
  
     ![MapToReqDenied 映射](../core/media/tut1-maptoreqden1.jpg "Tut1_MapToReqDen1")  
  
4.  在**源架构**窗格中，单击**打开源架构**。  
  
5.  在**BizTalk 类型选取器**对话框框中，展开**EAISchemas**，展开**架构**，单击**EAISchemas.Request**，然后单击**确定**。  
  
6.  在**源架构**窗格中，右键单击**\<架构\>**，然后单击**展开树节点**。  
  
7.  在**目标架构**窗格中，单击**打开目标架构**。  
  
8.  在**BizTalk 类型选取器**对话框框中，展开**EAISchemas**，展开**架构**，单击**EAISchemas.RequestDecline**，，然后单击**确定**。  
  
9. 在**目标架构**窗格中，右键单击**\<架构\>**，然后单击**展开树节点**。  
  
10. 在**源架构**窗格中，拖动**ReqID**字段**ReqID**中**目标架构**窗格。 将显示一条连接两个元素的直线。  
  
11. 在**源架构**窗格中，拖动**GrandTotal**字段**GrandTotal**字段**目标架构**窗格中映射的数据从到另一个架构。  
  
12. 上**文件**菜单上，单击**保存所有**来保存你的工作。  
  
## <a name="what-did-i-just-do"></a>内容回顾  
 在此步骤中，您创建了一个将 Request 消息转换为 RequestDecline 消息的映射。  
  
## <a name="next-steps"></a>后续步骤  
 生成 EAISchemas 项目。  
  
## <a name="see-also"></a>另请参阅  
 [步骤 1： 创建 EAISchemas 项目](../core/step-1-create-eaischemas-project.md)   
 [步骤 2： 创建清单请求架构](../core/step-2-create-the-inventory-request-schema.md)   
 [步骤 3： 创建请求拒绝架构](../core/step-3-create-the-request-decline-schema.md)   
 [步骤 4： 创建代码图](../core/step-4-create-the-map.md)   
 [步骤 5： 生成 EAISchemas 项目](../core/step-5-build-the-eaischemas-project.md)   
 [创建使用 BizTalk 映射程序图](../core/creating-maps-using-biztalk-mapper.md)