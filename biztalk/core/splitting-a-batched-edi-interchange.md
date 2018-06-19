---
title: 拆分批处理的 EDI 交换 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 29c79b06-cc88-4cc8-aa99-40f24a1bdcde
caps.latest.revision: 16
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 441eafe79de57963dc1df5ac19334542f41a23d1
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22277981"
---
# <a name="splitting-a-batched-edi-interchange"></a>拆分批处理的 EDI 交换
> [!NOTE]
>  本主题中提到的所有用户界面选项都位于**本地主机设置**页 (**接收方设置**部分) 中的单向协议选项卡的**协议属性**对话框。  
  
 EDI 接收管道拆分的传入 EDI 交换批处理如果设置了**入站批处理选项**协议属性**将交换拆分为事务集**。  
  
 当 EDI 接收管道拆分传入批处理 EDI 交换时，将为每个 EDI 事务集/消息创建一个 XML 文件。 该管道将整个交换和组标头升级为从交换拆分的每个事务集的上下文。 它还会升级某些特定交换和组标头（如 ISA6、GS1 和 GS2），以便可以使用这些字段进行路由。 你可以通过选择屏蔽标头中的安全信息**屏蔽安全/授权/密码信息**属性。  
  
 当 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 尝试将某个交换拆分为事务集时，某个 ISA（ISA1 至 ISA13）或 UNB 标头字段中的任何错误都将导致该交换被拒绝。 如果在协议或后备协议属性中启用了对重复交换控制编号的检查，则在交换控制编号重复时，同样会出现此种情况。 其他交换标头字段（X12 交换中除 ISA1 至 ISA13 之外的字段）或组标头字段中的错误将不会导致交换处理失败。  
  
 如果**将交换拆分为事务集-出错时暂停事务集**在协议属性中，选择[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]将会挂起事务集如果发生错误。 如果**将交换拆分为事务集-出错时暂停交换**选中，则[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]将挂起该交换。  
  
 每个 XML 批元素均被路由到 MessageBox，并由订阅此批元素的发送端口或业务流程处理。 在将事务集作为已拆分消息处理后，可能不会保留这些事务集在交换中的排序。 在接收端，将按消息在交换中的显示顺序来处理消息，并按此顺序将其放置在 MessageBox 中，但是在发送端，您必须使用保护或按序送达发送端口来保持此排序。  
  
 如果从批处理拆分的元素将包含在传出批中，BatchMarker 管道组件将升级所需属性。 有关详细信息，请参阅[批处理传出的 EDI 消息](../core/batching-outgoing-edi-messages.md)。  
  
## <a name="see-also"></a>另请参阅  
 [处理传入的批次](../core/processing-incoming-batches.md)   
 [对传出的 EDI 消息进行批处理](../core/batching-outgoing-edi-messages.md)