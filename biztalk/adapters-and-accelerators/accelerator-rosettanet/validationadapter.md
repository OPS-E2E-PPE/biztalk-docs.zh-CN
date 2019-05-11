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
ms.openlocfilehash: 0e4c6ba197f12de8236faed0f8494251fe858aeb
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65299907"
---
# <a name="validationadapter"></a>ValidationAdapter
ValidationAdapter 示例演示如何在响应方公用流程中对消息运行特殊验证规则。 Microsoft®[!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)]本机执行验证，在发送或接收管道以及业务流程中。 如果你想要执行其他验证，可以创建验证适配器。 其他验证可以包括跨字段验证或不能使用 XSD 实现的特定于业务的验证规则。  
  
 可以通过添加创建验证适配器[!INCLUDE[btsCSharp](../../includes/btscsharp-md.md)]到 ValidationAdapter 示例中，发布这些接口和协议属性中输入适配器的代码。 [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] 消息处理过程中将然后调用该验证适配器。  
  
 由于 ValidationAdapter 由公用流程业务流程，它在托管该业务流程的 BizTalk 主机服务相同的凭据下运行。  
  
 ValidationAdapter 示例位于\<*驱动器*\>: \Program Files\\Microsoft BizTalk\<版本\>Accelerator for RosettaNet\SDK\ValidationAdapter。  
  
## <a name="demonstrates"></a>演示  
 ValidationAdapter 示例演示如何验证服务内容中的电子邮件地址。 此示例实现`IValidateRNIFMessageParts`接口。 它将返回`RNIFException`如果的电子邮件地址不在正确的格式。 XML 文档**preambleToValidate**， **serviceHeaderToValidate**， **deliveryHeaderToValidate**，和**serviceContentToValidate**定义的验证。  
  
 ValidationAdapter 使用 RNIFerror.IsOkToSendException 属性来确定要发生错误时发送的消息类型。 如果验证不成功，则 ValidationAdapter 将 RNIFerror.ErrorCode 设置为非零值。 如果 RNIFerror.IsOkToSendException 属性为 true，则流程将发送否定确认。 对于 RNIF 2.0，这是一条异常消息。 对于 RNIF 1.1 中，这是确认回执异常消息。 如果 RNIFerror.IsOkToSendException 属性为 false 并且配置 0A1，则流程将发送 0A1 消息。 一旦进程发送异常消息、 确认回执异常消息或 0A1 消息，它将终止。  
  
 如果 RNIFerror.IsOkToSendException 属性为 false，并且未配置 0A1，则流程将发送异常既不 0A1。 它将记录该错误，然后终止。  
  
 如果验证成功，则 ValidationAdapter 将 RNIFerror.ErrorCode 设置为 0，，和 BTARN 将消息路由到专用流程。 它将消息路由到专用流程如果验证成功。  
  
## <a name="to-implement-this-sample"></a>若要实现此示例  
 若要实现该 ValidationAdapter 示例，必须向协议添加验证适配器。  
  
#### <a name="to-add-the-validation-adapter-to-the-agreement"></a>若要向协议添加验证适配器  
  
1. 单击**启动**，依次指向**所有程序**，指向 Microsoft [!INCLUDE[btaBTARNNoVersion](../../includes/btabtarnnoversion-md.md)]，然后单击[!INCLUDE[btaBTARNNoVersionui](../../includes/btabtarnnoversionui-md.md)]**管理控制台**。  
  
2. 在中[!INCLUDE[btaBTARNNoVersion](../../includes/btabtarnnoversion-md.md)]管理控制台中，展开[!INCLUDE[btaBTARNNoVersionui](../../includes/btabtarnnoversionui-md.md)]，然后单击**协议**。  
  
3. 双击你想要添加验证适配器的协议。  
  
4. 在中**验证适配器**对话框框中，单击省略号按钮 (**...**) 右侧的按钮**程序集名称**，转到包含验证适配器程序集的位置，选择相应的.dll 文件，然后单击**打开**。  
  
5. 单击向下的箭头**类名**，选择验证适配器类，并单击**确定**。  
  
## <a name="see-also"></a>请参阅  
 [适配器示例](../../adapters-and-accelerators/accelerator-rosettanet/adapter-samples.md)