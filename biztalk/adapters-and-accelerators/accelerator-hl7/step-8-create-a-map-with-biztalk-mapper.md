---
title: 步骤 8： 使用 BizTalk 映射程序创建一个映射 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- message enrichment tutorial, maps
- creating, maps
- maps, creating
- BizTalk Mapper
ms.assetid: 785426c7-5651-48be-b3f4-7f9d8051ba23
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 48e2578211d65ade2a50916e909c87a6fd84bf44
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22207069"
---
# <a name="step-8-create-a-map-with-biztalk-mapper"></a>步骤 8： 创建 BizTalk 映射程序的映射
在此步骤中，使用 BizTalk 映射程序来创建映射。 你在此地图创建将数据 （字段） 相关联的链接的文档中使用补货请求请求被拒绝文档中的数据。  
  
### <a name="to-create-a-map"></a>创建映射的步骤  
  
1.  在解决方案资源管理器，右键单击**BTAHL7 项目**，指向**添加**，然后单击**新项**。  
  
2.  在**添加新项**对话框中，在**类别**窗格中，单击**映射文件**。  
  
3.  在**名称**字段中，键入**DoorbellMap**对图中，命名，然后单击**添加**启动 BizTalk 映射程序。  
  
4.  在**源架构**窗格 （左侧），单击**打开源架构**。  
  
5.  在 BizTalk 类型选取器对话框中，展开**BTAHL7 项目**，展开**架构**，单击**BTAHL7_Project.Doorbell**，然后单击**确定**.  
  
6.  在**目标架构**窗格 （右侧），单击**打开目标架构**。  
  
7.  在 BizTalk 类型选择器，展开**BTAHL7 项目**，展开**架构**，单击**BTAHL7Schemas.ADT_A04_22_GLO_DEF**，然后单击**确定**.  
  
8.  在**目标架构**窗格 （右侧） 中展开**ADT_A04_22_GLO_DEF**，展开**PID_PatientIdentification**，然后展开**PID.5_PatientName**.  
  
9. 在**源架构**窗格 （左侧），展开**DoorbellRoot**。 拖动**LastName**字段**PN_0_FamilyName**字段**目标架构**窗格。  
  
10. 在**源架构**窗格中，拖动**FirstName**字段**PN_1_GivenName**字段**目标架构**窗格。  
  
11. 在**源架构**窗格中，拖动**MiddleName**字段**PN_2_MiddleInitialOrName**字段**目标架构**窗格.  
  
12. 在**目标架构**窗格中，展开**PID_3_PatientIdInternalId**。  
  
13. 在**源架构**窗格中，拖动**SSN**字段**CM_PAT_ID_0_PatientID**中**目标架构**窗格。  
  
14. 在**文件**菜单上，单击**保存所有**。  
  
 在典型的消息扩充方案中，如果任何患者信息中缺少，你将在您的业务流程中进行患者记录数据库调用并添加缺失的信息，然后使用附加信息以完成映射。 例如，可能会从患者记录数据库中，检索一个患者的家庭地址由于入站的 XML 门铃触发器事件消息未提供。  
  
 继续执行[步骤 9： 验证和生成映射项目](../../adapters-and-accelerators/accelerator-hl7/step-9-validate-and-build-the-map-project.md)。  
  
## <a name="see-also"></a>另请参阅  
 [消息扩充教程](../../adapters-and-accelerators/accelerator-hl7/message-enrichment-tutorial.md)