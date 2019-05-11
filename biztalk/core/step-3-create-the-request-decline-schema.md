---
title: 步骤 3：创建请求拒绝架构 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: e1ce166c-1be1-4ef4-9d00-3da7038d4ada
caps.latest.revision: 39
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 039fd40448d2545e360c5599b1448c6bcbf9c6e6
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65392646"
---
# <a name="step-3-create-the-request-decline-schema"></a>步骤 3：创建请求拒绝架构
![步骤 3，共 5](../core/media/step-3of5.gif "Step_3of5")  
  
 **若要完成的时间：** 7 分钟  
  
 **目标：** 在此步骤中，创建消息的架构[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]发送回仓库业务流程拒绝库存补货请求。  
  
 **目的：** 该架构定义的数据和请求拒绝消息的结构。 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 使用架构来识别并与消息中的数据进行交互。  
  
## <a name="prerequisites"></a>先决条件  
 在开始此步骤之前，请注意以下要求：  
  
-   在开始此步骤之前，必须完成[步骤 1:创建 EAISchemas 项目](../core/step-1-create-eaischemas-project.md)。  
  
## <a name="procedures"></a>过程  
  
#### <a name="to-create-the-request-decline-schema"></a>若要创建请求拒绝架构  
  
1.  在解决方案资源管理器中右键单击**EAISchemas**项目，指向**添加**，然后单击**新项**。  
  
2.  在中**添加新项-EAISchemas**对话框框中，执行以下操作：  
  
    |使用此选项|执行的操作|  
    |--------------|----------------|  
    |**已安装的模板**|单击**架构文件**，然后单击**架构**。|  
    |**名称**|键入 `RequestDecline.xsd`。|  
  
3.  单击 **“添加”**。  
  
4.  在 BizTalk 编辑器中，在架构树中，单击**根**节点以选择它。  
  
5.  在属性窗格中的值更改**节点名称**属性设置为`DeclineReq`，然后按 ENTER。  
  
6.  在架构树中，右键单击**DeclineReq**节点，指向**插入 Schema 节点**，然后单击**子字段元素**。  
  
7.  类型`ReqID`作为以及该元素，然后按 ENTER 键的新名称。  
  
8.  添加第二个子字段元素，它由名为`GrandTotal`。  
  
9. 在“文件”  菜单上，单击“全部保存” 。  
  
## <a name="what-did-i-just-do"></a>我只需做了什么？  
 在此步骤中，您创建消息的架构的[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]发送回仓库业务流程拒绝库存请求。  
  
## <a name="next-steps"></a>后续步骤  
 创建业务流程所需创建请求拒绝消息重新格式化请求消息的映射。  
  
## <a name="see-also"></a>请参阅  
 [步骤 1：创建 EAISchemas 项目](../core/step-1-create-eaischemas-project.md)  
 [步骤 2：创建库存请求架构](../core/step-2-create-the-inventory-request-schema.md)   
 [步骤 4：创建映射](../core/step-4-create-the-map.md)   
 [步骤 5：生成 EAISchemas 项目](../core/step-5-build-the-eaischemas-project.md)   
 [使用 BizTalk 编辑器创建架构](../core/creating-schemas-using-biztalk-editor.md)