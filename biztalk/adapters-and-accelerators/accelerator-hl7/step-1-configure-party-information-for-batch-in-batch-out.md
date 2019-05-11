---
title: 第 1 步：配置批处理批中扩展的参与方信息 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: a93d774b-1282-40d9-836f-44abeb65f78e
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 188b7cae45ac9cae0076ed129e92147f276a79d6
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65289070"
---
# <a name="step-1-configure-party-information-for-batch-inbatch-out"></a>第 1 步：配置参与方信息中的批处理/出站批处理
在此步骤中，你将关闭碎片的参与方启用批处理的批处理中 / 出站批处理方案。 然后重新启动[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]若要启用配置更改才能生效。  
  
### <a name="to-turn-off-fragmentation-of-batching-for-the-party"></a>若要关闭的批处理的参与方的碎片  
  
1. 单击**启动**，依次指向**所有程序**，指向**Microsoft BizTalk\<版本\>Accelerator for HL7**，然后单击**BTAHL7 配置资源管理器**。  
  
2. BTAHL7 配置资源管理器中上**参与方**选项卡上的左窗格中，单击**Tutorial_BatchSource**。  
  
3. 单击**批定义**选项卡。  
  
4. 选择**否**有关**所需的碎片**，然后单击**保存**。  
  
5. 请确保考虑到这**可恢复交换支持必需**下拉列表中**False**处于选中状态。  
  
   请继续执行[步骤 2:修改或创建发送和接收端口](../../adapters-and-accelerators/accelerator-hl7/step-2-modify-or-create-the-send-and-receive-ports.md)。