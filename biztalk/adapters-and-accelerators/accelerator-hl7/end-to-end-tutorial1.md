---
title: 端到端 Tutorial1 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- btahl7.endtoendtutorial
helpviewer_keywords:
- end-to-end tutorial, about the tutorial
- end-to-end tutorial
- tutorials, end-to-end tutorial
ms.assetid: 90625edc-70a0-42c9-a2fb-8eeb5465d766
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 264a6eee008b9b327185c931ad4e5ac60cdc995a
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "37000734"
---
# <a name="end-to-end-tutorial"></a>端到端教程
本教程包含详细的步骤，描述如何使用 Microsoft[!INCLUDE[HL7_CurrentVersion_FirstRef](../../includes/hl7-currentversion-firstref-md.md)]来推进业务流程在订阅服务器和发布服务器的方案。  
  
> [!IMPORTANT]
>  若要使用本教程，必须安装 BTAHL7 时安装的测试工具。 如果您执行典型安装中安装 BTAHL7，然后必须运行自定义安装，并按本教程中正常工作的顺序安装测试工具。 在**自定义安装**BTAHL7 自定义安装中，选择屏幕**MLLP 测试工具**从**适配器**文件夹，然后选择**测试实例**从**项目**文件夹。 有关详细信息，请参阅[安装 BizTalk Accelerator for HL7](../../adapters-and-accelerators/accelerator-hl7/install-biztalk-accelerator-for-hl7.md)。  
  
## <a name="declarative-scenario"></a>声明性方案  
 本教程使用的发布/订阅或声明性的方案。 在声明性的方案中流程是业务的类似于下图中所示。 编号的列表下图描述的工作流。  
  
 ![](../../adapters-and-accelerators/accelerator-hl7/media/hl7-e2e-wkflw.gif "hl7_e2e_wkflw")  
显示的声明性方案的业务流图  
  
1.  在工作流开始时发布服务器，例如，一个病人入院出院事项和传输系统中，将消息发送到特定的订阅服务器。 工作流中的发布服务器进行"Tutorial_ADTSystem"，并调用消息"**ADT ^ A103**。"  
  
2.  消息路由到 BTAHL7 接口引擎，又接收、 处理、 验证、 重新格式化，并随后将消息路由到订阅服务器。  
  
3.  在此方案中的订阅服务器是医院信息系统 (Tutorial_HISystem) 和药房系统 (Tutorial_RXSystem)。 此方案使用文件和 MLLP 适配器类型。 发布服务器不需要注意的订阅服务器并 BTAHL7 处理消息之后中适当地将确认发送到发布服务器。  
  
4.  发布服务器发送 ADT ^ A03 消息通过单向 MLLP 适配器 (Tutorial_1WayReceivePort)。  
  
5.  此消息的目标是 BTAHL7 接口引擎，因此传入消息包含源消息 (MSH3 = Tutorial_ADTSystem) 和目标消息 (MSH5 = BTAHL7InterfaceEngine)。  
  
6.  BTAHL7 适当地验证消息后, 生成的确认 (ACK)，并随后将确认发送到通过文件适配器 Tutorial_ADTSystem。  
  
7.  Tutorial_HISystem 系统和 Tutorial_RXSystem 系统订阅 BTAHL7 接口引擎接收的 ADT 消息。  
  
8.  使用指定的相应字段的值时发生转换**MSH 映射**BTAHL7 配置资源管理器中的选项卡。  
  
     例如，参与方 Tutorial_RXSystem 具有 MSH3 = 中指定的 BTHL7 **MSH 映射**选项卡。因此，订阅服务器接收的消息将具有"BTAHL7"与 MSH3 字段的值。  
  
## <a name="in-this-section"></a>本节内容  
  
-   [测试安装](../../adapters-and-accelerators/accelerator-hl7/testing-your-installation.md)  
  
-   [为使用教程做准备](../../adapters-and-accelerators/accelerator-hl7/preparing-to-use-the-tutorial2.md)  
  
-   [步骤 1：创建和部署标头及确认架构](../../adapters-and-accelerators/accelerator-hl7/step-1-create-and-deploy-header-and-acknowledgment-schemas.md)  
  
-   [步骤 2： 创建适用于 v2.3.1 的通用架构](../../adapters-and-accelerators/accelerator-hl7/step-2-create-common-schemas-for-v2-3-1.md)  
  
-   [步骤 3：创建和部署触发器事件（消息）项目](../../adapters-and-accelerators/accelerator-hl7/step-3-create-and-deploy-a-trigger-event-message-project.md)  
  
-   [步骤 4：使用 MLLP 适配器，创建从 ADT 系统接收 ADT^A03 消息的接收端口](../../adapters-and-accelerators/accelerator-hl7/step-4-create-receive-port-to-accept-adt^a03-messages-from-adt-using-mllp.md)  
  
-   [步骤 5：使用文件适配器创建发送端口以将确认传递至 ADT 系统](../../adapters-and-accelerators/accelerator-hl7/step-5-create-send-port-to-deliver-acknowledgments-to-adt-system-using-file.md)  
  
-   [步骤 6：使用文件适配器创建发送端口以将 ADT^A03 消息传递至 RX 系统](../../adapters-and-accelerators/accelerator-hl7/step-6-create-send-port-to-deliver-adt^a03-message-to-rx-system-using-file.md)  
  
-   [步骤 7：使用 MLLP 适配器创建发送端口以将 ADT^A03 消息传递至 HIS](../../adapters-and-accelerators/accelerator-hl7/step-7-create-send-port-to-deliver-adt^a03-message-to-his-using-mllp-adapter.md)  
  
-   [步骤 8：配置参与方信息](../../adapters-and-accelerators/accelerator-hl7/step-8-configure-party-information.md)  
  
-   [步骤 9：重启 BizTalk Server](../../adapters-and-accelerators/accelerator-hl7/step-9-restart-biztalk-server.md)  
  
-   [步骤 10：验证端到端方案](../../adapters-and-accelerators/accelerator-hl7/step-10-verify-the-end-to-end-scenario.md)

## <a name="see-also"></a>另请参阅
[BizTalk Accelerator for HL7 入门](../../adapters-and-accelerators/accelerator-hl7/get-started-with-the-biztalk-accelerator-for-hl7.md)