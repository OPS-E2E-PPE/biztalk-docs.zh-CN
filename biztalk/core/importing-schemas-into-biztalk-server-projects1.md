---
title: "将架构导入到 BizTalk Server Projects1 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- importing schemas
- orchestration variables, messages
- schemas, importing into BizTalk Server
- orchestration types, port types
ms.assetid: fa640195-a735-4201-a893-48f3405ddcb5
caps.latest.revision: "4"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 719679dffa5bcffdeddcbcd889f847f147a705b4
ms.sourcegitcommit: dd7c54feab783ae2f8fe75873363fe9ffc77cd66
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/07/2017
---
# <a name="importing-schemas-into-biztalk-server-projects"></a>将架构导入到 BizTalk Server 项目
以下信息介绍如何将架构导入到 BizTalk Server 项目中。  
  
## <a name="importing-schemas"></a>导入架构  
  
#### <a name="to-import-schemas"></a>若要导入架构  
  
1.  在解决方案资源管理器，右键单击项目，指向**添加**，然后选择**添加生成的项**。  
  
2.  单击**添加适配器**，然后选择**打开**。  
  
3.  选择的适配器**，参考Edwards OneWorld XE**。  
  
4.  在下拉列表中，选择的端口**SSOSendToJD Edwards OneWorld XE**，然后单击**下一步**。  
  
     MyJ.D。 Edwards OneWorld XESSO 逻辑系统将显示在浏览器中 （使用 SSOSendToJ.D 创建此逻辑系统。 Edwards OneWorld XE 端口）。  
  
5.  展开**myJ.D。Edwards OneWorld XESSO**。  
  
6.  单击箭头图标来移动项 （或只需将它拖动） 到**传输**窗口，，然后单击**确定**。  
  
     架构将添加到 SSOSchedule 项目。  
  
7.  在解决方案资源管理器，展开**SSOSchedule 项目**。  
  
8.  右键单击**BizTalk orchestration.odx**，然后单击**删除**。  
  
9. 在解决方案资源管理器中，双击**GetList.odx**检查业务流程。  
  
## <a name="orchestration-types---port-types"></a>业务流程类型 - 端口类型  
  
-   **PortTypeIn/中/请求：** SSOSchedule.myJ.D。 Edwards OneWorld XEsso_transmitService_3.method  
  
-   **PortTypeOut/扩展/响应：** SSOSchedule.myJ.D。 Edwards OneWorld XE sso_transmitService_3.methodResponse  
  
-   **PortTypeInOut/InOut/请求：** SSOSchedule.myJ.D。 Edwards OneWorld XEsso_transmitService_3.method  
  
-   **PortTypeInOut/InOut/响应：** SSOSchedule.myJ.D。 Edwards OneWorld XE sso_transmitService_3.methodResponse  
  
## <a name="orchestration-variables---messages"></a>Orchestration 变量 - 消息  
  
-   **MessageIn:** SSOSchedule.myJ.D。 Edwards OneWorld XEsso_transmitService_3.method  
  
-   **MessageOut:** SSOSchedule.myJ.D。 Edwards OneWorld XE sso_transmitService_3.methodResponse  
  
## <a name="see-also"></a>另请参阅  
 [适配器中的安全](../core/security-in-biztalk-adapter-for-jd-edwards-oneworld.md)