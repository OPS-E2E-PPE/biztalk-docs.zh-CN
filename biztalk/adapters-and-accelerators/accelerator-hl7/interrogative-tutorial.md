---
title: "Interrogative 教程 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- interrogative tutorial
- interrogative tutorial, about the tutorial
- tutorials, interrogative tutorial
ms.assetid: 93988429-5544-4920-821f-54f0a67bda72
caps.latest.revision: "8"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 0b35a5bc8ba7574df7499fef5d63a100993c4201
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="interrogative-tutorial"></a>Interrogative 教程
本教程包含的详细的步骤，描述如何使用[!INCLUDE[btsCoName](../../includes/btsconame-md.md)][!INCLUDE[HL7_CurrentVersion_FirstRef](../../includes/hl7-currentversion-firstref-md.md)]以便在查询/响应方案中的业务流程。  
  
> [!NOTE]
>  若要使用本教程，你必须安装 MLLP 测试工具。 通过 BTAHL7 的典型安装未安装这些工具。 你必须运行自定义安装，并选择**MLLP 测试工具**从适配器文件夹和**测试实例**项目文件夹中。 如果安装的测试工具，你的系统将包含文件夹\<*驱动器*: > files\microsoft BizTalk\<版本 > Accelerator for HL7\SDK\MLLP 实用程序。 请参阅[为 HL7 安装 BizTalk Accelerator](../../adapters-and-accelerators/accelerator-hl7/install-biztalk-accelerator-for-hl7.md)。  
  
## <a name="interrogative-scenario"></a>Interrogative 方案  
 本教程使用的查询/响应或 Interrogative 方案。 在此方案中，业务流程是类似于下图中所示。 下图的编号的列表描述工作流。  
  
 ![](../../adapters-and-accelerators/accelerator-hl7/media/hl7-intertutorial.gif "hl7_intertutorial")  
  
1.  工作流开始时许可放电并传输 (ADT) 的系统将查询发送到医院信息系统。 HL7 消息使用"**QRY ^ Q01**"架构。 在本教程，MllpSend 实用工具模拟 ADT 查询将消息发送到通过 ADT 医院信息系统的系统接收 BTAHL7 集成引擎中的端口。  
  
2.  BTAHL7 集成引擎从 ADT 系统接收查询消息，并对它进行验证。 然后，BTAHL7 管道将确认发送回 ADT。  
  
3.  BTAHL7 接口引擎处理消息，然后再路由到 HIS 目标查询消息方通过 HIS 发送端口。  
  
4.  在从原始查询接收该确认后, ADT 系统等待响应。 响应消息通过 HIS 回来医院信息系统发送接收端口。 对于本教程，MllpSend 实用工具模拟医院信息系统发送响应消息。  
  
5.  BTAHL7 接口引擎处理响应消息，并随后将它路由到通过 ADT 发送端口目标参与方。  
  
## <a name="in-this-section"></a>在本节中  
  
-   [准备使用本教程](../../adapters-and-accelerators/accelerator-hl7/preparing-to-use-the-tutorial-hl7-main.md)  
  
-   [步骤 1： 创建和部署常见标头和确认架构](../../adapters-and-accelerators/accelerator-hl7/step-1-create-and-deploy-common-header-and-acknowledgment-schemas.md)  
  
-   [步骤 2： 为 V2.4 创建通用架构](../../adapters-and-accelerators/accelerator-hl7/step-2-create-common-schemas-for-v2-4.md)  
  
-   [步骤 3： 创建和部署的触发器事件 （消息） 项目](../../adapters-and-accelerators/accelerator-hl7/step-3-create-and-deploy-a-trigger-event-message-project-hl7-main.md)  
  
-   [步骤 4： 创建用于接受 ADT 查询消息接收端口](../../adapters-and-accelerators/accelerator-hl7/step-4-create-the-receive-port-for-accepting-adt-query-messages.md)  
  
-   [步骤 5： 创建用于接受其消息接收端口](../../adapters-and-accelerators/accelerator-hl7/step-5-create-the-receive-port-for-accepting-his-messages.md)  
  
-   [步骤 6： 创建发送端口将查询消息传递](../../adapters-and-accelerators/accelerator-hl7/step-6-create-a-send-port-to-deliver-query-messages.md)  
  
-   [步骤 7： 创建发送端口将响应消息传递](../../adapters-and-accelerators/accelerator-hl7/step-7-create-a-send-port-to-deliver-response-messages.md)  
  
-   [步骤 8： 配置当事方信息](../../adapters-and-accelerators/accelerator-hl7/step-8-configure-party-information-hl7-main.md)  
  
-   [步骤 9： 重新启动 BizTalk Server](../../adapters-and-accelerators/accelerator-hl7/step-9-restart-biztalk-server-hl7-main.md)  
  
-   [步骤 10： 验证 Interrogative 方案](../../adapters-and-accelerators/accelerator-hl7/step-10-verify-the-interrogative-scenario.md)  

## <a name="next-step"></a>下一步  
 [准备使用本教程](../../adapters-and-accelerators/accelerator-hl7/preparing-to-use-the-tutorial-hl7-main.md)
  
## <a name="see-also"></a>另请参阅  
[入门 HL7 BizTalk 快捷键](../../adapters-and-accelerators/accelerator-hl7/get-started-with-the-biztalk-accelerator-for-hl7.md)