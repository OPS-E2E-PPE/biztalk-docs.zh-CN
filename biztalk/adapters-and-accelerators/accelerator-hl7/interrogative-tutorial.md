---
title: 询问教程 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- interrogative tutorial
- interrogative tutorial, about the tutorial
- tutorials, interrogative tutorial
ms.assetid: 93988429-5544-4920-821f-54f0a67bda72
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 92c832de8b6572e5ac70b79db1cbcc75d3812ea6
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "37003198"
---
# <a name="interrogative-tutorial"></a>询问教程
本教程包含详细的步骤，描述如何使用 Microsoft[!INCLUDE[HL7_CurrentVersion_FirstRef](../../includes/hl7-currentversion-firstref-md.md)]来推进业务流程中查询/响应方案。  
  
> [!NOTE]
>  若要使用本教程，必须安装 MLLP 测试工具。 通过 BTAHL7 的典型安装未安装这些工具。 必须运行自定义安装，然后选择**MLLP 测试工具**从适配器文件夹并**测试实例**项目文件夹中。 如果安装了测试工具，系统将包含文件夹\<*驱动器*:\>\Program Files\Microsoft BizTalk\<版本\>Accelerator for HL7\SDK\MLLP 实用程序。 请参阅[安装 BizTalk Accelerator for HL7](../../adapters-and-accelerators/accelerator-hl7/install-biztalk-accelerator-for-hl7.md)。  
  
## <a name="interrogative-scenario"></a>询问方案  
 本教程使用的查询/响应或询问方案。 在此方案中流程是业务的类似于下图中所示。 编号的列表下图描述的工作流。  
  
 ![](../../adapters-and-accelerators/accelerator-hl7/media/hl7-intertutorial.gif "hl7_intertutorial")  
  
1.  在工作流开始时的病人入院出院事项和传输 (ADT) 系统将查询发送到医院信息系统。 HL7 消息使用"**QRY ^ Q01**"架构。 在本教程中，MllpSend 实用程序模拟 ADT 查询消息发送到医院信息系统通过 ADT 系统接收端口 BTAHL7 集成引擎中。  
  
2.  BTAHL7 集成引擎从 ADT 系统接收查询消息，并对其进行验证。 然后，BTAHL7 管道将确认发送回 ADT。  
  
3.  BTAHL7 接口引擎处理该消息，然后路由到 HIS 目标查询消息的参与方通过 HIS 发送端口。  
  
4.  从原始查询收到确认之后, ADT 系统等待响应。 响应消息通过 HIS 回来医院信息系统将发送接收端口。 对于本教程，MllpSend 实用程序模拟发送响应消息的医院信息系统。  
  
5.  BTAHL7 接口引擎处理响应消息，并随后将它路由到目标参与方通过 ADT 发送端口。  
  
## <a name="in-this-section"></a>本节内容  
  
-   [为使用教程做准备](../../adapters-and-accelerators/accelerator-hl7/preparing-to-use-the-tutorial-hl7-main.md)  
  
-   [步骤 1：创建和部署通用标头及确认架构](../../adapters-and-accelerators/accelerator-hl7/step-1-create-and-deploy-common-header-and-acknowledgment-schemas.md)  
  
-   [步骤 2：创建适用于 V2.4 的通用架构](../../adapters-and-accelerators/accelerator-hl7/step-2-create-common-schemas-for-v2-4.md)  
  
-   [步骤 3：创建和部署触发器事件（消息）项目](../../adapters-and-accelerators/accelerator-hl7/step-3-create-and-deploy-a-trigger-event-message-project-hl7-main.md)  
  
-   [步骤 4：创建用于接收 ADT 查询消息的接收端口](../../adapters-and-accelerators/accelerator-hl7/step-4-create-the-receive-port-for-accepting-adt-query-messages.md)  
  
-   [步骤 5：创建用于接收 HIS 消息的接收端口](../../adapters-and-accelerators/accelerator-hl7/step-5-create-the-receive-port-for-accepting-his-messages.md)  
  
-   [步骤 6：创建用于传递查询消息的发送端口](../../adapters-and-accelerators/accelerator-hl7/step-6-create-a-send-port-to-deliver-query-messages.md)  
  
-   [步骤 7：创建用于传递响应消息的发送端口](../../adapters-and-accelerators/accelerator-hl7/step-7-create-a-send-port-to-deliver-response-messages.md)  
  
-   [步骤 8：配置参与方信息](../../adapters-and-accelerators/accelerator-hl7/step-8-configure-party-information-hl7-main.md)  
  
-   [步骤 9：重启 BizTalk Server](../../adapters-and-accelerators/accelerator-hl7/step-9-restart-biztalk-server-hl7-main.md)  
  
-   [步骤 10：验证询问方案](../../adapters-and-accelerators/accelerator-hl7/step-10-verify-the-interrogative-scenario.md)  

## <a name="next-step"></a>下一步  
 [为使用教程做准备](../../adapters-and-accelerators/accelerator-hl7/preparing-to-use-the-tutorial-hl7-main.md)
  
## <a name="see-also"></a>请参阅  
[BizTalk Accelerator for HL7 入门](../../adapters-and-accelerators/accelerator-hl7/get-started-with-the-biztalk-accelerator-for-hl7.md)