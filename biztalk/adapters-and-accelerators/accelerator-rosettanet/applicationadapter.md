---
title: ApplicationAdapter |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 2f9b876b-cd37-4e24-a476-186adc155ac0
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ee9d04f98da5e9b8aa1faba81f32fe5ec37d23b9
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/28/2017
ms.locfileid: "25963187"
---
# <a name="applicationadapter"></a>ApplicationAdapter
ApplicationAdapter 示例演示如何在接收消息时从响应方或发起方的公用流程和专用流程发送通知。 你可以自定义该示例，使其具有任何你需要的其他功能。  
  
 ApplicationAdapter 示例演示如何将 `IApplicationAdapter` 接口实现到 `ApplicationAdapter1` 类。 此类包含 `BeginNotify` 和 `Notify` 这两个方法。 每个类的参数包括消息类别、源参与方名称、目标参与方名称、合作伙伴接口流程 (PIP) 代码、PIP 实例 ID 以及 PIP 版本。  
  
 在输入的程序集名称和类名设置了协议 ApplicationAdapter**常规**选项卡中的协议[!INCLUDE[btsCoName](../../includes/btsconame-md.md)]® [!INCLUDE[btaBTARNNoVersion](../../includes/btabtarnnoversion-md.md)] ([!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)]) 管理控制台。 应用程序适配器 .dll 文件运行所用的凭据与 BizTalk 主机服务的凭据相同。  
  
 如果更改了 ApplicationAdapter 示例或者 ApplicationAdapter 示例依赖的任何外部环境变量，请重新启动 [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] 公用流程的宿主 BizTalk 主机服务。  
  
 ApplicationAdapter 示例代码位于\<*驱动器*\>: files\ BizTalk\<版本\>Accelerator for RosettaNet\SDK\ApplicationAdapter\\.  
  
## <a name="demonstrates"></a>演示  
 ApplicationAdapter 示例演示如何通知响应方专用流程公用流程已收到消息。 通知指明消息类别、源参与方名称、目标参与方名称、PIP 代码、PIP 版本以及 PIP 实例 ID。 可以为操作或响应消息发送此通知。  
  
 `BeginNotify` 和 `Notify` 方法的工作方式如下所示：  
  
1.  响应方公用流程接收消息。  
  
    > [!NOTE]
    >  以下步骤也适用于公用发起方从响应方接收响应消息的情况。  
  
2.  如果接收管道、公用流程和验证适配器（如果有）执行的验证成功，则响应方公用流程会调用 `BeginNotify` 类中的 `ApplicationAdapter` 方法。 此方法通知响应方专用流程公用流程已收到新消息并将该消息保存在 MessageBox 数据库中。  
  
3.  响应方公用流程向发起方回送信号消息。  
  
4.  响应方公用流程向响应方专用流程发送消息服务内容。  
  
5.  响应方专用流程将消息放入 BTARNDATA 数据库的 MessagesToLOB 表中。  
  
6.  响应方专用流程调用 `Notify` 类中的 `ApplicationAdapter` 方法，将“通知结束”消息回送给响应方公用流程。 只有在响应方公用流程收到“通知结束”消息时，该流程才算成功完成。 否则，消息被挂起。  
  
> [!NOTE]
>  可以使用 `Notify` 消息通知业务线 (LOB) 应用程序消息正在 MessagesToLOB 表中等待。 系统向 LOB 应用程序发出警报后，LOB 应用程序可立即从该表中检索此消息。  
  
## <a name="to-implement-this-sample"></a>实现此示例  
 要实现该 ApplicationAdapter 示例，必须向协议添加应用程序适配器。  
  
#### <a name="to-add-the-application-adapter-to-an-agreement"></a>向协议添加应用程序适配器  
  
1.  单击**启动**，指向**所有程序**，指向[!INCLUDE[btsCoName](../../includes/btsconame-md.md)] **BizTalk\<版本\>Accelerator for RosettaNet**，，然后单击[!INCLUDE[btaBTARNNoVersionui](../../includes/btabtarnnoversionui-md.md)]**管理控制台**。  
  
2.  在[!INCLUDE[btaBTARNNoVersion](../../includes/btabtarnnoversion-md.md)]管理控制台中，展开[!INCLUDE[btaBTARNNoVersionui](../../includes/btabtarnnoversionui-md.md)]，然后单击**协议**。  
  
3.  双击要添加应用程序适配器的协议。  
  
4.  在**应用程序适配器**框中，单击省略号按钮 (**...**) 的右侧的按钮**程序集名称**，移到包含的应用程序适配器程序集的位置，选择相应的.dll 文件，然后单击**打开**。  
  
5.  单击向下的箭头**类名**，选择应用程序的适配器类，，然后单击**确定**。  
  
## <a name="see-also"></a>另请参阅  
 [适配器示例](../../adapters-and-accelerators/accelerator-rosettanet/adapter-samples.md)