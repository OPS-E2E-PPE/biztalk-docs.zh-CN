---
title: 步骤 4：创建映射 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 2f7f1f6d-0e57-4a65-b91d-c81fcc832961
caps.latest.revision: 36
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 6cf9def7682b9334af451b5230cc2790fb7a6021
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65392544"
---
# <a name="step-4-create-the-map"></a>步骤 4：创建映射
![步骤 4 5](../core/media/step-4of5.gif "Step_4of5")  
  
 **若要完成的时间：** 6 分钟  
  
 **目标：** 在此步骤中，创建请求消息转换为 RequestDecline 消息的映射。  
  
 **目的：** 此映射确保返回到仓库库存系统的请求拒绝消息中包含请求 ID 号和总计。 使用 BizTalk 映射器将传入消息中的字段链接到传出消息定义的字段。 这是必需的因为这两条消息不具有相同的架构结构。  
  
## <a name="prerequisites"></a>先决条件  
 在开始此步骤之前，请注意以下要求：  
  
-   在开始此步骤之前，必须完成[步骤 2:创建库存请求架构](../core/step-2-create-the-inventory-request-schema.md)和[步骤 3:创建请求拒绝架构](../core/step-3-create-the-request-decline-schema.md)。  
  
## <a name="procedures"></a>过程  
 此映射依赖于 Request 架构和 RequestDecline 架构。  在地图上使用它们之前，您得多编译具有架构的项目。  
  
#### <a name="to-compile-the-eaischemas-project"></a>若要编译 EAISchemas 项目  
  
-   在解决方案资源管理器中右键单击**EAISchemas**，然后单击**生成**。  
  
#### <a name="to-create-the-map"></a>若要创建映射  
  
1.  在解决方案资源管理器中右键单击**EAISchemas**项目，指向**添加**，然后单击**新项**。  
  
2.  在中**添加新项-EAISchemas**对话框框中，执行以下操作：  
  
    |使用此选项|执行的操作|  
    |--------------|----------------|  
    |**已安装的模板**|单击**地图文件**，然后单击**映射**。|  
    |**名称**|类型**MapToReqDecline.btm**。|  
  
3.  单击 **“添加”**。  
  
     下图显示了源架构、 目标架构和映射器网格。  
  
     ![MapToReqDenied map](../core/media/tut1-maptoreqden1.jpg "Tut1_MapToReqDen1")  
  
4.  在中**源架构**窗格中，单击**打开源架构**。  
  
5.  在中**BizTalk 类型选取器**对话框框中，展开**EAISchemas**，展开**架构**，单击**EAISchemas.Request**，然后单击**确定**。  
  
6.  在中**源架构**窗格中，右键单击**\<架构\>**，然后单击**展开树节点**。  
  
7.  在中**目标架构**窗格中，单击**打开目标架构**。  
  
8.  在中**BizTalk 类型选取器**对话框框中，展开**EAISchemas**，展开**架构**，单击**EAISchemas.RequestDecline**，，然后单击**确定**。  
  
9. 在中**目标架构**窗格中，右键单击**\<架构\>**，然后单击**展开树节点**。  
  
10. 在中**源架构**窗格中，拖动**ReqID**字段**ReqID**中**目标架构**窗格。 连接两个元素将显示的行。  
  
11. 在中**源架构**窗格中，拖动**GrandTotal**字段**GrandTotal**字段中**目标架构**窗格，可以将数据映射从另一个架构。  
  
12. 上**文件**菜单上，单击**全部保存**以保存所做的工作。  
  
## <a name="what-did-i-just-do"></a>我只需做了什么？  
 在此步骤中，创建的是请求消息转换为 RequestDecline 消息的映射。  
  
## <a name="next-steps"></a>后续步骤  
 生成 EAISchemas 项目。  
  
## <a name="see-also"></a>请参阅  
 [步骤 1：创建 EAISchemas 项目](../core/step-1-create-eaischemas-project.md)   
 [步骤 2：创建库存请求架构](../core/step-2-create-the-inventory-request-schema.md)   
 [步骤 3：创建请求拒绝架构](../core/step-3-create-the-request-decline-schema.md)   
 [步骤 4：创建映射](../core/step-4-create-the-map.md)   
 [步骤 5：生成 EAISchemas 项目](../core/step-5-build-the-eaischemas-project.md)   
 [使用 BizTalk 映射器创建映射](../core/creating-maps-using-biztalk-mapper.md)