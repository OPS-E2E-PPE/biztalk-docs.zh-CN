---
title: 步骤 7： 创建示例 LOB 消息 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- messages, LOB
- loopback tutorial, creating LOB message
- creating, LOB messages
- LOBs, creating messages
ms.assetid: 3023bbc0-5bc4-4e5a-a345-c3253874f0d3
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: d2b8450f196a1619b55b08a0771508daafa421a4
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36977998"
---
# <a name="step-7-create-a-sample-lob-message"></a>步骤 7： 创建示例 LOB 消息
在此步骤中，你将使用 LOB 应用程序实用工具创建一个业务线 (LOB) 消息示例。  

### <a name="to-create-a-sample-message-using-the-lob-application-utility"></a>使用 LOB 应用程序实用工具创建示例消息  

1. 在中[!INCLUDE[btsWinNoVersion](../../includes/btswinnoversion-md.md)]资源管理器，转到\<*驱动器*\>: \Program 文件 (x86) \Microsoft BizTalk\<版本\>Accelerator for RosettaNet\SDK 文件夹，然后双击**LOBApplication.exe**。  

2. 在中**LOB 应用程序**对话框框中，执行以下操作：  


   |       **使用此**       |                                                                                                                       **若要执行此操作**                                                                                                                       |
   |--------------------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
   |  **本组织配置文件名称**   |                                                                                                                       类型**主页**。                                                                                                                       |
   | **贸易合作伙伴名称** |                                                                                                                     类型**合作伙伴**。                                                                                                                      |
   |       **PIP 名称**       |                                                                                                                       类型**0c1**。                                                                                                                        |
   |     **PIP 版本**      |                                                                                                                      类型**R01.02**。                                                                                                                      |
   |      **文件名**       | 单击省略号按钮 (**...**)，并将移至\<*驱动器*:\>\Program 文件 (x86) \Microsoft BizTalk\<版本\>Accelerator for RosettaNet\SDK\LOBApplication\SampleInstances. 选择**0C1_Request.xml**从列表中的文件，并单击**打开**。 |
   |   **消息类别**   |                                                                                                         选择**操作**从下拉列表。                                                                                                         |


3. 在中**LOB 应用程序**对话框中，单击**提交消息**。  

   LOB 应用程序为 Microsoft 生成一条消息[!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)]模拟的 LOB 应用程序生成的原始消息。 可以在“状态”窗口中查看消息的状态。  

> [!NOTE]
>  该消息示例假设“HOME”和“PARTNER”的全局业务标识符 (GBI) 分别为 123456789 和 987654321。 若要使用不同的 GBI，必须修改这些文件的内容。  

## <a name="see-also"></a>请参阅  
 [步骤 8：在 BTARN 数据库中查看消息](../../adapters-and-accelerators/accelerator-rosettanet/step-8-view-messages-in-the-btarn-databases.md)
