---
title: 创建 FRR 发送管道 |Microsoft 文档
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
ms.openlocfilehash: 87733b6b3a93d2543d26cd6d11b366b84218d207
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22209453"
---
# <a name="creating-the-frr-send-pipeline"></a>创建 FRR 发送管道
若要执行 FIN 响应对帐，你需要创建包含 SWIFTAsmFrrMQSeriesHelper 管道组件，除了 SWIFT 汇编程序发送管道。  
  
 **摘要**  
  
 创建具有以下几个阶段的发送管道：  
  
|阶段|组件|  
|-----------|---------------|  
|组装阶段|SWIFT 汇编程序|  
|编码阶段|SWIFT Frr MQSeries 发送组件|  
  
### <a name="to-create-a-custom-send-pipeline-for-frr"></a>若要为 FRR 创建自定义发送管道  
  
1.  在解决方案资源管理器的 Visual Studio 中，右键单击你的管道项目，指向**添加**，然后单击**新项**。  
  
2.  在添加新项对话框中，选择**发送管道**从模板窗格。  
  
3.  在**名称**框中，键入接收管道的名称，如**FRRSendPipeline.btp**。 单击 **“添加”**。  
  
4.  在[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]，单击**视图**然后**工具箱**。  
  
5.  从 BizTalk 管道组件工具箱中，拖动**SWIFT 汇编程序**到**拖至此处**下面框**装配**阶段中的形状**BizTalk 管道设计器**。  
  
6.  从 BizTalk 管道组件工具箱中，拖动**SWIFT Frr MQSeries 发送组件**到**拖至此处**下面框**编码**阶段中的形状**BizTalk 管道设计器**。  
  
7.  在 BizTalk 资源管理器，右键单击你的管道项目，单击**取消部署后再次**，然后单击**是**。  
  
    > [!NOTE]
    >  在取消部署，然后重新部署管道项目后必须重置任何发送端口或接收在以前部署的项目中使用的管道的位置。  
  
8.  在解决方案资源管理器，右键单击你的管道项目，然后单击**生成**。  
  
9. 已成功生成后，右键单击你的管道项目，然后单击**部署**。