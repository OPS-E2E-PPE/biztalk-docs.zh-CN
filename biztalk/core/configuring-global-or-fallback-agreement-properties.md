---
title: 配置全局或后备协议属性 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 1c375d03-6f22-4a67-9eac-d8896de2f7ee
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: d44624a4f505cf7d3c4e53fe55e4203917cf41f9
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65391075"
---
# <a name="configuring-global-or-fallback-agreement-properties"></a><span data-ttu-id="e2d51-102">配置全局或后备协议属性</span><span class="sxs-lookup"><span data-stu-id="e2d51-102">Configuring Global or Fallback Agreement Properties</span></span>
[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] <span data-ttu-id="e2d51-103">使用后备协议属性来处理一条消息时不会发现的交换解析为该协议。</span><span class="sxs-lookup"><span data-stu-id="e2d51-103">uses fallback agreement properties to process a message when it does not discover an agreement to resolve to for an interchange.</span></span> <span data-ttu-id="e2d51-104">当已知协议时，不使用后备协议属性并不适用于任何或所有协议。</span><span class="sxs-lookup"><span data-stu-id="e2d51-104">Fallback agreement properties are not used when the agreement is known, and do not apply to any or all agreements.</span></span>  
  
 <span data-ttu-id="e2d51-105">当[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]接收消息时，它将尝试匹配与消息中的发件人信息协议的发送方信息。</span><span class="sxs-lookup"><span data-stu-id="e2d51-105">When [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] receives a message, it attempts to match the sender information for an agreement with the sender information in the message.</span></span> <span data-ttu-id="e2d51-106">发件人信息位于 ISA5 和 ISA6 数据元素中的 X12 消息，以及对于 EDIFACT UNB2.1 和 UNB 2.2 数据元素。</span><span class="sxs-lookup"><span data-stu-id="e2d51-106">The sender information is in the ISA5 and ISA6 data elements for X12 message, and the UNB2.1 and UNB 2.2 data elements for EDIFACT.</span></span> <span data-ttu-id="e2d51-107">在单向协议选项卡中的标识符选项卡中的协议信息是**协议属性**对话框。</span><span class="sxs-lookup"><span data-stu-id="e2d51-107">The agreement information is in the Identifier tabs in the one-way agreement tab of the **Agreement Properties** dialog box.</span></span> <span data-ttu-id="e2d51-108">如果[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]不会发现协议，[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]使用后备协议属性来确定的命名空间、 处理消息，并发送任何确认。</span><span class="sxs-lookup"><span data-stu-id="e2d51-108">If [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] does not discover the agreement, [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] uses the fallback agreement properties to determine the namespace, process the message, and send any acknowledgments.</span></span>  
  
 <span data-ttu-id="e2d51-109">当[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]协议消息解析到由匹配的发送端口订阅到该 XML 消息在 MessageBox 中，并且与该协议关联的发送端口发送消息，EDI 发送管道确定。</span><span class="sxs-lookup"><span data-stu-id="e2d51-109">When [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] sends a message, the EDI send pipeline determines the agreement that the message resolves to by matching the send port that subscribes to the XML message in the MessageBox, with the send port associated with the agreement.</span></span> <span data-ttu-id="e2d51-110">如果发送端口不是与某个协议关联[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]使用后备协议属性来处理发送的消息。</span><span class="sxs-lookup"><span data-stu-id="e2d51-110">If the send port is not associated with an agreement, [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] uses the fallback agreement properties to process the message for sending.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="e2d51-111">发送端口关联是执行协议解析的只有一种方法。</span><span class="sxs-lookup"><span data-stu-id="e2d51-111">Send port association is only one way of doing agreement resolution.</span></span> <span data-ttu-id="e2d51-112">有关对传出消息的协议解析的详细信息，请参阅[协议解析和架构确定传出 EDI 消息的](../core/agreement-resolution-and-schema-determination-for-outgoing-edi-messages.md)。</span><span class="sxs-lookup"><span data-stu-id="e2d51-112">For more information about agreement resolution for outgoing messages, see [Agreement Resolution and Schema Determination for Outgoing EDI Messages](../core/agreement-resolution-and-schema-determination-for-outgoing-edi-messages.md).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="e2d51-113">本节内容</span><span class="sxs-lookup"><span data-stu-id="e2d51-113">In This Section</span></span>  
  
-   [<span data-ttu-id="e2d51-114">配置 X12 后备协议属性</span><span class="sxs-lookup"><span data-stu-id="e2d51-114">Configuring X12 Fallback Agreement Properties</span></span>](../core/configuring-x12-fallback-agreement-properties.md)  
  
-   [<span data-ttu-id="e2d51-115">配置 EDIFACT 后备协议属性</span><span class="sxs-lookup"><span data-stu-id="e2d51-115">Configuring EDIFACT Fallback Agreement Properties</span></span>](../core/configuring-edifact-fallback-agreement-properties.md)  
  
## <a name="see-also"></a><span data-ttu-id="e2d51-116">请参阅</span><span class="sxs-lookup"><span data-stu-id="e2d51-116">See Also</span></span>  
 [<span data-ttu-id="e2d51-117">协议在 EDI 处理中的角色</span><span class="sxs-lookup"><span data-stu-id="e2d51-117">The Role of Agreements in EDI Processing</span></span>](../core/the-role-of-agreements-in-edi-processing.md)