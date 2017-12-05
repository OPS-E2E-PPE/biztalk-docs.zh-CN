---
title: "步骤 7： 创建示例 LOB 消息 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- messages, LOB
- loopback tutorial, creating LOB message
- creating, LOB messages
- LOBs, creating messages
ms.assetid: 3023bbc0-5bc4-4e5a-a345-c3253874f0d3
caps.latest.revision: "7"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 1246f56615381d2627db3058dc821ba85bf8b74d
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/28/2017
---
# <a name="step-7-create-a-sample-lob-message"></a>步骤 7： 创建示例 LOB 消息
在此步骤中，你将使用 LOB 应用程序实用工具创建一个业务线 (LOB) 消息示例。  
  
### <a name="to-create-a-sample-message-using-the-lob-application-utility"></a>使用 LOB 应用程序实用工具创建示例消息  
  
1.  在[!INCLUDE[btsWinNoVersion](../../includes/btswinnoversion-md.md)]资源管理器中，移动到\<*驱动器*\>: files\microsoft BizTalk\<版本\>Accelerator for RosettaNet\SDK 文件夹，然后双击**LOBApplication.exe**。  
  
2.  在**LOB 应用程序**对话框框中，执行以下操作：  
  
    |**使用此方法**|**若要执行此操作**|  
    |------------------|--------------------|  
    |**主配置文件名称**|类型**主页**。|  
    |**贸易合作伙伴名称**|类型**合作伙伴**。|  
    |**PIP 名称**|类型**0 C 1**。|  
    |**PIP 版本**|类型**R01.02**。|  
    |**文件名**|单击省略号按钮 (**...**)，并将移至\<*驱动器*:\>files\microsoft BizTalk\<版本\>RosettaNet\SDK\LOBApplication\SampleInstances 快捷键。 选择**0C1_Request.xml**从列表中的文件，然后单击**打开**。|  
    |**消息类别**|选择**操作**从下拉列表。|  
  
3.  在**LOB 应用程序**对话框中，单击**提交消息**。  
  
 LOB 应用程序为 Microsoft 生成一条消息[!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)]模拟 LOB 应用程序生成的原始消息。 可以在“状态”窗口中查看消息的状态。  
  
> [!NOTE]
>  该消息示例假设“HOME”和“PARTNER”的全局业务标识符 (GBI) 分别为 123456789 和 987654321。 若要使用不同的 GBI，必须修改这些文件的内容。  
  
## <a name="see-also"></a>另请参阅  
 [步骤 8：在 BTARN 数据库中查看消息](../../adapters-and-accelerators/accelerator-rosettanet/step-8-view-messages-in-the-btarn-databases.md)