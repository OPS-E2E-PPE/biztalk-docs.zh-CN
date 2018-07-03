---
title: 步骤 8： 使用 BizTalk 映射器创建映射 |Microsoft Docs
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
ms.openlocfilehash: d1b9edeca21fe9967f816f05d2ceb12ffe5c5ded
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36968454"
---
# <a name="step-8-create-a-map-with-biztalk-mapper"></a>步骤 8： 使用 BizTalk 映射器创建映射
在此步骤中，使用 BizTalk 映射器创建映射。 就使用此映射来创建将数据 （字段） 相关联的链接请求被拒绝文档中的数据中的补货请求文档中。  
  
### <a name="to-create-a-map"></a>创建映射的步骤  
  
1. 在解决方案资源管理器中右键单击**BTAHL7 项目**，依次指向**添加**，然后单击**新项**。  
  
2. 在中**添加新项**对话框中**类别**窗格中，单击**映射文件**。  
  
3. 在中**名称**字段中，键入**DoorbellMap**以该映射，然后单击**添加**启动 BizTalk 映射器。  
  
4. 在中**源架构**窗格 （左侧），单击**打开源架构**。  
  
5. 在 BizTalk 类型选取器对话框中，展开**BTAHL7 项目**，展开**架构**，单击**BTAHL7_Project.Doorbell**，然后单击**确定**.  
  
6. 在中**目标架构**窗格 （右侧），单击**打开目标架构**。  
  
7. 在 BizTalk 类型选取器中，展开**BTAHL7 项目**，展开**架构**，单击**BTAHL7Schemas.ADT_A04_22_GLO_DEF**，然后单击**确定**.  
  
8. 在中**目标架构**窗格 （右侧），展开**ADT_A04_22_GLO_DEF**，展开**PID_PatientIdentification**，然后展开**PID.5_PatientName**.  
  
9. 在中**源架构**窗格 （左侧），展开**DoorbellRoot**。 拖动**LastName**字段**PN_0_FamilyName**字段中**目标架构**窗格。  
  
10. 在中**源架构**窗格中，拖动**FirstName**字段**PN_1_GivenName**字段中**目标架构**窗格。  
  
11. 在中**源架构**窗格中，拖动**MiddleName**字段**PN_2_MiddleInitialOrName**字段中**目标架构**窗格.  
  
12. 在中**目标架构**窗格中，展开**PID_3_PatientIdInternalId**。  
  
13. 在中**源架构**窗格中，拖动**SSN**字段**CM_PAT_ID_0_PatientID**中**目标架构**窗格。  
  
14. 在中**文件**菜单上，单击**全部保存**。  
  
    在典型的消息扩充方案中，如果任何患者信息已丢失，则会调用患者记录数据库中您的业务流程和添加缺少的信息，然后使用的其他信息以完成映射。 例如，由于入站的 XML 门铃触发器事件消息未提供，因此可能会从患者记录数据库中，检索患者的家庭地址。  
  
    请继续执行[步骤 9： 验证和生成映射项目](../../adapters-and-accelerators/accelerator-hl7/step-9-validate-and-build-the-map-project.md)。  
  
## <a name="see-also"></a>请参阅  
 [消息充实教程](../../adapters-and-accelerators/accelerator-hl7/message-enrichment-tutorial.md)