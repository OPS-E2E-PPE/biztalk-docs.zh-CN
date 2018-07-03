---
title: ValidationAdapter |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 5fe99350-14c0-4ddb-b257-af9a0c4258f6
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: fbcf26ee8a3a97d2df34bb29dad5d0cf31d4db1a
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36987902"
---
# <a name="validationadapter"></a>ValidationAdapter
该 ValidationAdapter 示例演示了如何对响应方公用流程中的消息运行特殊验证规则。 Microsoft®[!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)]本机执行验证，在发送或接收管道以及业务流程中。 如果要执行其他验证，可以创建验证适配器。 其他验证可以包括无法使用 XSD 实现的跨字段验证规则或业务特定的验证规则。  
  
 可以通过添加创建验证适配器[!INCLUDE[btsCSharp](../../includes/btscsharp-md.md)]到 ValidationAdapter 示例中，发布这些接口和协议属性中输入适配器的代码。 [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] 消息处理过程中将然后调用该验证适配器。  
  
 由于 ValidationAdapter 由公用业务流程使用，因此，ValidationAdapter 运行时使用的凭据与该业务流程的宿主 BizTalk 主机服务的凭据相同。  
  
 ValidationAdapter 示例位于\<*驱动器*\>: \Program Files\\Microsoft BizTalk\<版本\>Accelerator for RosettaNet\SDK\ValidationAdapter。  
  
## <a name="demonstrates"></a>演示  
 ValidationAdapter 示例演示如何验证服务内容中的电子邮件地址。 该示例实现 `IValidateRNIFMessageParts` 接口。 如果电子邮件地址的格式不正确，它将返回 `RNIFException`。 XML 文档**preambleToValidate**， **serviceHeaderToValidate**， **deliveryHeaderToValidate**，和**serviceContentToValidate**定义的验证。  
  
 ValidationAdapter 使用 RNIFerror.IsOkToSendException 属性来确定在发生错误时要发送的消息种类。 如果验证不成功，则 ValidationAdapter 将 RNIFerror.ErrorCode 设置为一个非零值。 如果 RNIFerror.IsOkToSendException 属性为 true，则流程将发送一个负的确认值。 对于 RNIF 2.0，它是异常消息。 对于 RNIF 1.1，它是确认回执异常消息。 如果 RNIFerror.IsOkToSendException 属性为 false 并且配置了 0A1，则流程将发送 0A1 消息。 流程发送异常消息、确认回执异常消息或 0A1 消息后，它将终止运行。  
  
 如果 RNIFerror.IsOkToSendException 属性为 false 但未配置 0A1，则流程将不发送异常消息，也不发送 0A1。 它将记录错误然后终止运行。  
  
 如果验证成功，则 ValidationAdapter 将 RNIFerror.ErrorCode 设置为 0，BTARN 将消息路由至专用流程。 只有验证成功后，BTARN 才将消息路由到专用流程。  
  
## <a name="to-implement-this-sample"></a>实现此示例  
 若要实现该 ValidationAdapter 示例，必须向协议中添加验证适配器。  
  
#### <a name="to-add-the-validation-adapter-to-the-agreement"></a>向协议中添加验证适配器  
  
1. 单击**启动**，依次指向**所有程序**，指向 Microsoft [!INCLUDE[btaBTARNNoVersion](../../includes/btabtarnnoversion-md.md)]，然后单击[!INCLUDE[btaBTARNNoVersionui](../../includes/btabtarnnoversionui-md.md)]**管理控制台**。  
  
2. 在中[!INCLUDE[btaBTARNNoVersion](../../includes/btabtarnnoversion-md.md)]管理控制台中，展开[!INCLUDE[btaBTARNNoVersionui](../../includes/btabtarnnoversionui-md.md)]，然后单击**协议**。  
  
3. 双击要添加验证适配器的协议。  
  
4. 在中**验证适配器**对话框框中，单击省略号按钮 (**...**) 右侧的按钮**程序集名称**，转到包含验证适配器程序集的位置，选择相应的.dll 文件，然后单击**打开**。  
  
5. 单击向下的箭头**类名**，选择验证适配器类，并单击**确定**。  
  
## <a name="see-also"></a>请参阅  
 [适配器示例](../../adapters-and-accelerators/accelerator-rosettanet/adapter-samples.md)