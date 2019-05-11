---
title: ApplicationAdapter |Microsoft Docs
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
ms.openlocfilehash: a738003a3afb9f34e4546d1a1865e99376e8fba6
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65284907"
---
# <a name="applicationadapter"></a>ApplicationAdapter
ApplicationAdapter 示例演示如何从公共和专用流程 （响应方或发起方） 发送通知时收到一条消息。 具有所需的任何其他功能，可以自定义示例。  
  
 ApplicationAdapter 示例演示如何实现`IApplicationAdapter`接口`ApplicationAdapter1`类。 此类包括两种方法`BeginNotify`和`Notify`。 每个类的参数包括消息类别、 源参与方名称、 目标参与方名称、 合作伙伴接口流程 (PIP) 代码、 PIP 实例 ID，以及 PIP 版本。  
  
 通过在输入程序集名称和类名设置为协议 ApplicationAdapter**常规**Microsoft® 中的协议选项卡[!INCLUDE[btaBTARNNoVersion](../../includes/btabtarnnoversion-md.md)]([!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)]) 管理控制台。 与 BizTalk 主机服务相同的凭据下运行的应用程序适配器.dll 文件。  
  
 如果您更改了 ApplicationAdapter 示例或者 ApplicationAdapter 示例依赖于任何外部环境变量，请重新启动托管的 BizTalk 主机服务[!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)]公用流程。  
  
 ApplicationAdapter 示例代码位于\<*驱动器*\>: files\ BizTalk\<版本\>Accelerator for RosettaNet\SDK\ApplicationAdapter\\.  
  
## <a name="demonstrates"></a>演示  
 ApplicationAdapter 示例演示如何通知响应方专用流程公用流程已收到一条消息。 通知指明消息类别、 源参与方名称、 目标参与方名称、 PIP 代码、 PIP 版本和 PIP 实例 id。 可以发送此通知的操作或响应消息。  
  
 `BeginNotify`和`Notify`方法的工作原理，如下所示：  
  
1.  响应方公用流程接收消息。  
  
    > [!NOTE]
    >  以下步骤，还有适用于在其中公用发起方接收响应消息从响应方的方案。  
  
2.  如果验证由接收管道、 公用流程和验证适配器，如果适用，成功，响应方公用流程会调用`BeginNotify`中的方法`ApplicationAdapter`类。 此方法通知响应方专用流程公用流程已收到新消息和该消息保存在 MessageBox 数据库中。  
  
3.  响应方公用流程将信号消息发送回发起方。  
  
4.  响应方公用流程将消息服务内容发送到响应方专用流程。  
  
5.  响应方专用流程将该消息放在 BTARNDATA 数据库的 MessagesToLOB 表中。  
  
6.  响应方专用流程调用`Notify`中的方法`ApplicationAdapter`类返回到响应方公用流程发送最终通知消息。 响应方公用流程必须接收进程才算成功完成通知结束消息。 否则，则会挂起消息。  
  
> [!NOTE]
>  可以使用`Notify`消息通知业务 (LOB) 应用程序消息正在 MessagesToLOB 表中等待。 如很快系统会提醒 LOB 应用程序，LOB 应用程序可以从该表中检索消息。  
  
## <a name="to-implement-this-sample"></a>若要实现此示例  
 若要实现该 ApplicationAdapter 示例，必须向协议添加应用程序适配器。  
  
#### <a name="to-add-the-application-adapter-to-an-agreement"></a>若要向协议添加应用程序适配器  
  
1. 单击**启动**，依次指向**所有程序**，指向 Microsoft **BizTalk\<版本\>Accelerator for RosettaNet**，然后单击[!INCLUDE[btaBTARNNoVersionui](../../includes/btabtarnnoversionui-md.md)]**管理控制台**。  
  
2. 在中[!INCLUDE[btaBTARNNoVersion](../../includes/btabtarnnoversion-md.md)]管理控制台中，展开[!INCLUDE[btaBTARNNoVersionui](../../includes/btabtarnnoversionui-md.md)]，然后单击**协议**。  
  
3. 双击你想要添加应用程序适配器的协议。  
  
4. 在中**应用程序适配器**框中，单击省略号按钮 (**...**) 右侧的按钮**程序集名称**，转到包含应用程序适配器程序集的位置，选择相应的.dll 文件，然后单击**打开**。  
  
5. 单击向下的箭头**类名**，选择应用程序适配器类，并单击**确定**。  
  
## <a name="see-also"></a>请参阅  
 [适配器示例](../../adapters-and-accelerators/accelerator-rosettanet/adapter-samples.md)