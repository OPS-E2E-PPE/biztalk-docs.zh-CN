---
title: 端到端 Tutorial1 |Microsoft 文档
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
ms.openlocfilehash: 90dc31ac286f8ce1e38d9a511eb319828d8ae939
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="end-to-end-tutorial"></a>端到端教程
本教程包含的详细的步骤，描述如何使用[!INCLUDE[btsCoName](../../includes/btsconame-md.md)][!INCLUDE[HL7_CurrentVersion_FirstRef](../../includes/hl7-currentversion-firstref-md.md)]为了便于在订阅服务器和发布服务器方案中的业务流程。  
  
> [!IMPORTANT]
>  若要使用本教程，必须安装 BTAHL7 时安装的测试工具。 如果执行典型的安装，以安装 BTAHL7，然后必须运行自定义安装，并按本教程中正常工作的顺序安装的测试工具。 在**自定义安装**BTAHL7 自定义安装中，选择屏幕**MLLP 测试工具**从**适配器**文件夹，并选择**测试实例**从**项目**文件夹。 有关详细信息，请参阅[HL7 安装 BizTalk 快捷键](../../adapters-and-accelerators/accelerator-hl7/install-biztalk-accelerator-for-hl7.md)。  
  
## <a name="declarative-scenario"></a>声明性方案  
 本教程使用的发布/订阅或声明性方案。 在声明性的方案中，业务流程是类似于下图中所示。 下图的编号的列表描述工作流。  
  
 ![](../../adapters-and-accelerators/accelerator-hl7/media/hl7-e2e-wkflw.gif "hl7_e2e_wkflw")  
该图显示的声明性方案的业务流程  
  
1.  当发布服务器，例如，许可放电并传输系统将一条消息发送到特定的订阅服务器时，将开始工作流。 工作流中的发布服务器是"Tutorial_ADTSystem"，并且调用了消息"**ADT ^ A103**。"  
  
2.  将消息路由到 BTAHL7 接口引擎，后者反过来接收、 处理、 验证、 重新格式化，并随后将消息路由到订阅服务器。  
  
3.  在此方案中的订阅服务器是医院信息系统 (Tutorial_HISystem) 和药房系统 (Tutorial_RXSystem)。 此方案使用文件和 MLLP 适配器类型。 发布服务器不需要注意的订阅服务器和 BTAHL7 处理消息之后中适当地将确认发送到发布服务器。  
  
4.  发布服务器发送 ADT ^ A03 消息通过单向 MLLP 适配器 (Tutorial_1WayReceivePort)。  
  
5.  此消息的目标是 BTAHL7 接口引擎，因此传入消息包含源消息 (MSH3 = Tutorial_ADTSystem) 和目标消息 (MSH5 = BTAHL7InterfaceEngine)。  
  
6.  BTAHL7 在适当地验证消息之后, 生成的确认 (ACK)，并随后将确认发送到通过文件适配器 Tutorial_ADTSystem。  
  
7.  Tutorial_HISystem 系统和 Tutorial_RXSystem 系统订阅接收 BTAHL7 接口引擎的 ADT 消息。  
  
8.  使用指定的相应字段的值时发生转换**MSH 映射**BTAHL7 配置资源管理器中的选项卡。  
  
     例如，当事方 Tutorial_RXSystem 具有 MSH3 = 中指定的 BTHL7 **MSH 映射**选项卡。因此，通过将订阅者收到的消息将具有"BTAHL7"与 MSH3 字段的值。  
  
## <a name="in-this-section"></a>在本节中  
  
-   [测试安装](../../adapters-and-accelerators/accelerator-hl7/testing-your-installation.md)  
  
-   [准备使用本教程](../../adapters-and-accelerators/accelerator-hl7/preparing-to-use-the-tutorial2.md)  
  
-   [步骤 1： 创建和部署标头和确认架构](../../adapters-and-accelerators/accelerator-hl7/step-1-create-and-deploy-header-and-acknowledgment-schemas.md)  
  
-   [步骤 2： 创建常见 v2.3.1 架构](../../adapters-and-accelerators/accelerator-hl7/step-2-create-common-schemas-for-v2-3-1.md)  
  
-   [步骤 3： 创建和部署的触发器事件 （消息） 项目](../../adapters-and-accelerators/accelerator-hl7/step-3-create-and-deploy-a-trigger-event-message-project.md)  
  
-   [步骤 4： 创建用于接受 ADT 接收端口 ^ A03 消息从 ADT 系统使用 MLLP 适配器](../../adapters-and-accelerators/accelerator-hl7/step-4-create-receive-port-to-accept-adt^a03-messages-from-adt-using-mllp.md)  
  
-   [步骤 5： 创建发送端口将确认传递到使用文件适配器的 ADT 系统](../../adapters-and-accelerators/accelerator-hl7/step-5-create-send-port-to-deliver-acknowledgments-to-adt-system-using-file.md)  
  
-   [步骤 6： 创建发送端口，以提供 ADT ^ 到 RX 系统使用了文件适配器 A03 消息](../../adapters-and-accelerators/accelerator-hl7/step-6-create-send-port-to-deliver-adt^a03-message-to-rx-system-using-file.md)  
  
-   [步骤 7： 创建发送端口，以提供 ADT ^ 到他使用 MLLP 适配器 A03 消息](../../adapters-and-accelerators/accelerator-hl7/step-7-create-send-port-to-deliver-adt^a03-message-to-his-using-mllp-adapter.md)  
  
-   [步骤 8： 配置当事方信息](../../adapters-and-accelerators/accelerator-hl7/step-8-configure-party-information.md)  
  
-   [步骤 9： 重新启动 BizTalk Server](../../adapters-and-accelerators/accelerator-hl7/step-9-restart-biztalk-server.md)  
  
-   [步骤 10： 验证端到端方案](../../adapters-and-accelerators/accelerator-hl7/step-10-verify-the-end-to-end-scenario.md)

## <a name="see-also"></a>另请参阅
[入门 HL7 BizTalk 快捷键](../../adapters-and-accelerators/accelerator-hl7/get-started-with-the-biztalk-accelerator-for-hl7.md)