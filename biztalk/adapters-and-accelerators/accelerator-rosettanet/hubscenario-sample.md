---
title: HubScenario 示例 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: eb6990ec-aea2-4362-8573-7f737a4fc7f1
caps.latest.revision: 15
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: bcd7f7d08e1451bfe50d2558b8f7c6b24d897957
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65283604"
---
# <a name="hubscenario-sample"></a>HubScenario 示例
HubScenario 示例演示如何管理集线器方案中的消息传输。 它会将转换为消息要发送到最终接收人发送到中间网络集线器的消息。  
  
 HubScenario 从服务内容中提取最终接收人的邓氏数。 它管理签名和加密证书和目标 URL。 为最终接收人生成一封新邮件。  
  
 此示例处理 3A4 请求和响应消息和 0 C 1 个请求消息。 当你使用 HubScenario 创建您的要求的应用程序时，必须生成为每个消息合作伙伴接口流程 (PIP) 的例程。  
  
 HubScenario 示例包含 hubhelper.cs 项目和 HubScenario.odx 项目。  
  
 HubScenario 示例还包括可用于导入绑定接收端口 (MessagesToLOB_Receive_Port) 和接收位置 (MessagesToLOB_Receive_Location) 的绑定文件，以用于 HubScenario.odx 业务流程。 此绑定文件 (HubScenarioBinding.xml) 位于*\<驱动器\>*: \Program Files\Microsoft BizTalk\<版本\>Accelerator for RosettaNet \SDK\HubScenario。 使用 BTSTask 命令导入绑定。 有关详细信息，请参阅 BizTalk Server 帮助中的"ImportBindings 命令"主题。  
  
### <a name="to-build-and-initialize-this-sample"></a>若要生成并初始化本示例  
  
1. 在 Visual Studio 中打开\<驱动器\>: \Program Files\Microsoft BizTalk\<版本\>Accelerator for RosettaNet\SDK\HubScenario\HubScenario.btproj。 在解决方案资源管理器，右键单击 HubScenario 项目，然后单击属性。 在 HubScenario 项目的属性页中，在签名选项卡上选择**为程序集签名**复选框，然后选择**HubScenario.snk**中**选择强名称密钥文件**并单击**确定**。  
  
2. 在解决方案资源管理器，右键单击 HubHelper 项目，然后单击属性。 在 HubHelper 项目属性页中，在签名选项卡中选中签名程序集复选框。 在选择强名称密钥文件字段中，选择新的类型**HubHelper.snk**作为密钥文件名称，然后单击**确定**。  
  
   > [!NOTE]
   >  如果你没有在 HubScenario 和 HubHelper 项目中手动输入程序集密钥文件，将不会部署程序集。  
  
3. 在命令提示符处，转到*\<驱动器\>*: \Program Files\Microsoft BizTalk\<版本\>Accelerator for RosettaNet\SDK\HubScenario 文件夹。 运行文件 Setup.bat （或在 64 位计算机上运行 Setupx64.bat）。  
  
## <a name="demonstrates"></a>演示  
 HubScenario.ods 业务流程演示如何执行以下任务：  
  
1. 从业务线应用程序接收的消息。  
  
2. 删除`CDATA`服务内容，返回 XML 字符串中的元素。  
  
3. 检索最后一条消息的目标参与方名称、 PIPCode、 PIPInstanceID 和 PIPVersion。  
  
4. 检索最终接收人的邓氏数。  
  
5. 确定消息的类别，并添加包含对服务内容到相应的架构的引用的 DOCTYPE 元素。  
  
6. 构造新的目标参与方名称、 邓氏、 PIP 代码信息和服务内容的消息。  
  
7. 提交消息以供处理[!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)]。 这是调用`SubmitRNIF.SubmitMessage`。  
  
## <a name="see-also"></a>请参阅  
 [示例基于中心的方案](../../adapters-and-accelerators/accelerator-rosettanet/sample-hub-based-scenario.md)   
 [业务流程示例](../../adapters-and-accelerators/accelerator-rosettanet/orchestration-samples.md)