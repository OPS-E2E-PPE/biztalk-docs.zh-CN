---
title: 创建 FRR 发送管道 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- FRR, creating send pipelines
- creating, send pipelines
- send pipelines, creating
ms.assetid: c6cd2047-ea53-425f-80cc-b02a1deb5292
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 971fde4a2f0f743574e60911dcb091a325efd079
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65378335"
---
# <a name="creating-the-frr-send-pipeline"></a>创建 FRR 发送管道
若要执行 FIN 响应对帐，您需要创建包含 SWIFT 汇编程序之外的 SWIFTAsmFrrMQSeriesHelper 管道组件的发送管道。  

 **摘要**  

 创建发送管道具有以下阶段：  

|阶段|组件|  
|-----------|---------------|  
|组装阶段|SWIFT 汇编程序|  
|编码阶段|SWIFT 的 Frr MQSeries 发送组件|  

### <a name="to-create-a-custom-send-pipeline-for-frr"></a>若要为 FRR 创建自定义发送管道  

1. 在解决方案资源管理器的 Visual Studio 中，右键单击管道项目，指向**外**，然后单击**新项**。  

2. 在添加新项对话框中，选择**发送管道**从模板窗格。  

3. 在中**名称**框中，键入你的接收管道的名称，如**FRRSendPipeline.btp**。 单击 **“添加”**。  

4. 在中[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]，单击**视图**，然后**工具箱**。  

5. 从 BizTalk 管道组件工具箱拖动**SWIFT 汇编程序**到**在此处放置**下面的框**组装**阶段中的形状**BizTalk 管道设计器**。  

6. 从 BizTalk 管道组件工具箱拖动**SWIFT 的 Frr MQSeries 发送组件**到**在此处放置**下面的框**编码**阶段中的形状**BizTalk 管道设计器**。  

7. 在 BizTalk 浏览器中，右键单击管道项目，单击**Undeploy**，然后单击**是**。  

   > [!NOTE]
   >  取消部署，然后重新部署管道项目之后, 必须重置任何发送端口或接收管道使用以前部署的项目中的位置。  

8. 在解决方案资源管理器，右键单击管道项目，然后依次**生成**。  

9. 已成功生成后，右键单击管道项目，然后依次**部署**。
