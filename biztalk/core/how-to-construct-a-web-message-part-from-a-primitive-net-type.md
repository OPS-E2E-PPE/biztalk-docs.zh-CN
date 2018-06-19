---
title: 如何构造中的基元.NET 类型的 Web 消息部件 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- creating, Web messages
- Web messages, Message Assignment shape [Orchestration Designer]
- Web messages, creating
- Message Assignment shape [Orchestration Designer], Web messages
- Web messages, parts
- Web messages, .NET types
ms.assetid: 1fe52412-d2bc-484c-8925-c7ff3ca7704b
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 991970d5b0d40da1ec00b54919d2742cfd48353c
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22248021"
---
# <a name="how-to-construct-a-web-message-part-from-a-primitive-net-type"></a><span data-ttu-id="b259f-102">如何从基元 .NET 类型构造 Web 消息部分</span><span class="sxs-lookup"><span data-stu-id="b259f-102">How to Construct a Web Message Part from a Primitive .NET Type</span></span>
<span data-ttu-id="b259f-103">自.NET 的基元类型中使用创建的 Web 消息部分**消息分配**形状。</span><span class="sxs-lookup"><span data-stu-id="b259f-103">You create a Web message part from a primitive .NET type by using a **Message Assignment** shape.</span></span> <span data-ttu-id="b259f-104">也可以通过使用 .NET 帮助程序类设置各个部分来从基元 .NET 类型创建 Web 消息部分。</span><span class="sxs-lookup"><span data-stu-id="b259f-104">Alternatively, you can create a Web message part from a primitive .NET type by using a .NET helper class to set the parts.</span></span> <span data-ttu-id="b259f-105">通过使用一个.NET 类创建消息类型的详细信息，请参阅[在用户代码中构造消息](../core/constructing-messages-in-user-code.md)。</span><span class="sxs-lookup"><span data-stu-id="b259f-105">For more information on creating message types by using a .NET class, see [Constructing Messages in User Code](../core/constructing-messages-in-user-code.md).</span></span>  
  
### <a name="to-construct-a-web-message-part-from-a-primitive-net-type"></a><span data-ttu-id="b259f-106">从基元 .NET 类型构造 Web 消息部分</span><span class="sxs-lookup"><span data-stu-id="b259f-106">To construct a Web message part from a primitive .NET type</span></span>  
  
1.  <span data-ttu-id="b259f-107">与打开的业务流程，打开**工具箱**单击**BizTalk 业务流程**选项卡。</span><span class="sxs-lookup"><span data-stu-id="b259f-107">With an orchestration open, open the **Toolbox** and click the **BizTalk Orchestrations** tab.</span></span>  
  
2.  <span data-ttu-id="b259f-108">拖动**构造消息**形状上的与业务流程。</span><span class="sxs-lookup"><span data-stu-id="b259f-108">Drag a **Construct Message** shape to the orchestration.</span></span>  
  
3.  <span data-ttu-id="b259f-109">编辑**构造消息**属性以包含你创建的 Web 消息类型的消息实例。</span><span class="sxs-lookup"><span data-stu-id="b259f-109">Edit the **Message Constructed** property to include the message instance that you created for the Web message type.</span></span>  
  
4.  <span data-ttu-id="b259f-110">拖动**消息分配**形状拖到**构造消息**形状。</span><span class="sxs-lookup"><span data-stu-id="b259f-110">Drag a **Message Assignment** shape onto the **Construct Message** shape.</span></span>  
  
5.  <span data-ttu-id="b259f-111">双击**消息分配**形状以打开 BizTalk 表达式编辑器。</span><span class="sxs-lookup"><span data-stu-id="b259f-111">Double-click the **Message Assignment** shape to open the BizTalk Expression Editor.</span></span>  
  
6.  <span data-ttu-id="b259f-112">在 BizTalk 表达式编辑器框中，将 Web 消息类型的各个部分设置为其所需的值。</span><span class="sxs-lookup"><span data-stu-id="b259f-112">Set the parts of the Web message type to their required values in the BizTalk Expression Editor box.</span></span>  
  
     <span data-ttu-id="b259f-113">例如，以下代码将表达式设置为字符串：</span><span class="sxs-lookup"><span data-stu-id="b259f-113">For example, the following code sets the expression to a string:</span></span>  
  
    ```  
    ItemAvailRequestInstance.Item_ID = "This is Item_ID.";  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="b259f-114">另请参阅</span><span class="sxs-lookup"><span data-stu-id="b259f-114">See Also</span></span>  
 [<span data-ttu-id="b259f-115">构造 Web 消息</span><span class="sxs-lookup"><span data-stu-id="b259f-115">Constructing Web Messages</span></span>](../core/constructing-web-messages.md)