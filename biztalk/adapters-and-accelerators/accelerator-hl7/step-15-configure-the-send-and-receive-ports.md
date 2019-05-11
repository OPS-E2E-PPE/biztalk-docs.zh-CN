---
title: 步骤 15:配置发送和接收端口 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- message enrichment tutorial, ports
ms.assetid: d532b196-473e-4c8f-b4ed-acef674fc698
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: efb16b8222e3ef2c6afebe0aaf63a0e203afc73e
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65289030"
---
# <a name="step-15-configure-the-send-and-receive-ports"></a>步骤 15:配置发送和接收端口
在上一步骤中，创建逻辑发送和接收端口使用业务流程设计器并设置为"以后指定"端口绑定。 在此步骤中，使用 BizTalk 浏览器通过定义物理源和目标位置，并将物理端口绑定到业务流程中创建的逻辑端口完成端口配置。  
  
## <a name="configure-the-send-and-receive-ports"></a>配置发送和接收端口  
  
1.  在 BizTalk Server 管理控制台中，展开**BizTalk Server 管理**，展开**BizTalk 组**，展开**应用程序**，然后展开**BizTalk 应用程序 1**。  
  
2.  右键单击**发送端口**，指向新建，，然后单击**静态单向发送端口**。  
  
3.  在发送端口属性对话框中，在**名称**框中，键入**MLLPSendPort**。  
  
4.  有关**类型**，选择**MLLP**。  
  
5.  单击**配置**右侧的按钮**类型**字段。  
  
6.  在处的 MLLP 传输属性对话框中，对于**连接名称**输入**MLLPConnection**。 有关**主机**输入**localhost**。 单击“确定” 。  
  
7.  在发送端口属性对话框中，对于**发送管道**，选择**BTAHL72XPipelines.BTAHL72XSendPipeline**，然后单击**确定**。  
  
8.  在管理控制台中，右键单击**MLLPSendPort**端口，，然后单击**启动**。  
  
9. 展开**平台设置**，单击**主机实例**，右键单击**BizTalkServerApplication**，然后单击**启动**。 如果主机已在运行，请单击**重新启动**。  
  
10. 单击**业务流程**，右键单击**BTAHL7_Project.Doorbell_Orchestration**，然后单击**属性**。  
  
11. 在业务流程属性对话框中，在控制台树中，单击**绑定**。  
  
12. 在中**绑定**窗格中，对于**主机**，选择**BizTalkServerApplication**。  
  
13. 有关**SOAPReceivePort**，选择**WebPort_BTAHL7_Project_Proxy/BTAHL7_Project_Doorbell_Orchestration_SOAPReceivePort**中**接收端口**列。  
  
14. 有关**MLLPSendPort**，选择**MLLPSendPort**中**发送端口/发送端口组**列。  
  
15. 单击**确定**以保存所做的更改。  
  
## <a name="msh-5-and-msh-6"></a>MSH 5 和 MSH 6  
 MSH 5 和 MSH 6 标头字段包含的目标应用程序和工具，分别。 在配置资源管理器，可以为每个 MSH 5 和 MSH 6，在你想要更改的消息中的目标信息的情况下的三个组件指定值。 原始消息不包括特定于参与方信息时，这是可能的方案。 此步骤是在声明性 （发布服务器/订阅服务器） 模型中适用。 如果适用您的环境中，执行此步骤。 有关设置这些值的详细信息，请参阅[参与方-BTAHL7 配置资源管理器](parties-tab.md)。  
  
 请继续执行[步骤 16:启动业务流程](../../adapters-and-accelerators/accelerator-hl7/step-16-start-the-orchestration.md)。  
  
## <a name="see-also"></a>请参阅  
 [消息充实教程](../../adapters-and-accelerators/accelerator-hl7/message-enrichment-tutorial.md)