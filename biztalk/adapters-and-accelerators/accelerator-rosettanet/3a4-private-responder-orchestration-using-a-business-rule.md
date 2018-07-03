---
title: 使用业务规则的 3A4 专用响应方业务流程 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 33d87952-def6-4202-b535-3d80171332eb
caps.latest.revision: 11
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a9ca606aa3d8ce6cdb74d4653e910f7db7639ec3
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36986094"
---
# <a name="3a4-private-responder-orchestration-using-a-business-rule"></a>使用业务规则的 3A4 专用响应方业务流程
PIP3A4PrivateResponder.odx 示例是一个专用业务流程，该业务流程演示如何实现合并了业务规则的特定于合作伙伴接口流程 (PIP) 的响应方专用流程。 有关此过程的详细信息，请参阅[专用业务流程中定义的业务规则](../../adapters-and-accelerators/accelerator-rosettanet/defining-a-business-rule-for-a-private-process-orchestration.md)。  
  
 默认情况下，Microsoft®[!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)]安装程序将安装中的示例\<*驱动器*\>: \Program Files\Microsoft BizTalk\<版本\>Accelerator for RosettaNet\SDK\PipAutomation\3A4。  
  
## <a name="procedures"></a>过程  
  
#### <a name="to-build-and-initialize-this-sample"></a>构建和初始化此示例  
  
1.  在命令提示符处，找到*\<驱动器\>*: files\ Microsoft BizTalk Accelerator for RosettaNet\<版本\>\SDK\PIPAutomation\3A4 文件夹。  
  
2.  运行文件 Setup.bat，该文件使用 Binding.xml 绑定文件来执行以下操作：  
  
    -   编译 Helper 项目，并在全局程序集缓存中注册该程序集。  
  
    -   编译 PIP3APrivateResponder 项目，并在全局程序集缓存中注册该程序集。  
  
    -   创建 LOB_To_PrivateResponder 接收端口。  
  
    -   创建 LOB_To_PrivateResponder 接收位置。  
  
    -   创建并启动 PrivateResponder_To_LOB 发送端口。  
  
    -   编译并部署 PIP3A4PrivateResponderProcess 业务流程。  
  
    > [!NOTE]
    >  必须使用 BizTalk 浏览器完成 PIP3A4PrivateResponderProcess 业务流程的端口绑定配置。  
  
    > [!NOTE]
    >  若要撤消 setup.bat 所做的更改，请手动取消登记 PIP3A4PrivateResponder.odx 业务流程，取消部署 Helper 和 PIP3A4PrivateResponder 程序集，然后取消部署并删除 samplebtarnpolicy 规则策略。 不能使用中的 Cleanup.bat *\<驱动器\>*: files\ Microsoft BizTalk Accelerator for RosettaNet\<版本\>\SDK\PIPAutomation\3A4 文件夹，若要撤消更改setup.bat 所做的。  
  
## <a name="demonstrates"></a>演示  
 此示例订阅 3A4 请求操作消息和信号消息。 该示例在 3A4 同步流程和异步流程中都可执行。 所有其他 PIP 消息仍通过通用 [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] 专用流程路由。 此示例调用 [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] 业务规则引擎，并将传入 3A4 请求消息传递给规则引擎。  
  
> [!NOTE]
>  [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] 提供了一个名为中的 samplebtarnpolicy.xml 的示例业务规则策略\<*驱动器*\>: files\ Microsoft BizTalk Accelerator for RosettaNet\<版本\>\SDK\PipAutomation\3A4。 有关详细信息，请参阅[BTARN 业务策略示例](../../adapters-and-accelerators/accelerator-rosettanet/sample-btarn-business-policy.md)。  
  
 要使用此示例，请设置业务规则。 如果消息满足业务规则的要求，则流程会将传入操作消息保存在 MessagesToLOB 表中，并将“传递状态”设置为 2。 “已传递”列值必须非零，以便业务线应用程序知道不必生成此请求的确认消息。 然后，流程将 3A4 请求消息映射为 3A4 确认消息，并使用 `SubmitRNIF` 方法将响应提交给 MessageStorageIn 表。  
  
 如果消息不满足业务规则，则流程会将传入操作消息保存在 MessageStorageOut 表中，并将“传递状态”设置为 0。  
  
 此示例包含一个绑定文件 (Binding.xml)，可用于设置发送端口 (PrivateResponder_To_LOB)、接收端口 (LOB_To_PrivateResponder) 和接收位置 (LOB_To_PrivateResponder)，以便将它们用于 PIP3A4PrivateResponder.odx 业务流程。 使用 BTSTask 命令可以导入 Binding.xml 文件中的绑定。 有关详细信息，请参阅 BizTalk Server 帮助中的"ImportBindings 命令"主题。  
  
## <a name="see-also"></a>请参阅  
 [双操作 PIPAutomation 业务流程](../../adapters-and-accelerators/accelerator-rosettanet/double-action-pipautomation-orchestration.md)   
 [BTARN 业务策略示例](../../adapters-and-accelerators/accelerator-rosettanet/sample-btarn-business-policy.md)   
 [业务流程示例](../../adapters-and-accelerators/accelerator-rosettanet/orchestration-samples.md)