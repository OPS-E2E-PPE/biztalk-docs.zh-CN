---
title: 如何构造 Web 消息部分从基元.NET 类型 |Microsoft Docs
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
ms.openlocfilehash: 9ab2390ea0e053fadcd275d8be7c1eea6ea6e903
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65340196"
---
# <a name="how-to-construct-a-web-message-part-from-a-primitive-net-type"></a><span data-ttu-id="5d165-102">如何构造 Web 消息部分从基元.NET 类型</span><span class="sxs-lookup"><span data-stu-id="5d165-102">How to Construct a Web Message Part from a Primitive .NET Type</span></span>
<span data-ttu-id="5d165-103">从基元.NET 类型中使用创建 Web 消息部分**消息赋值**形状。</span><span class="sxs-lookup"><span data-stu-id="5d165-103">You create a Web message part from a primitive .NET type by using a **Message Assignment** shape.</span></span> <span data-ttu-id="5d165-104">或者，可以通过使用.NET 帮助程序类设置各个部分来从基元.NET 类型创建 Web 消息部分。</span><span class="sxs-lookup"><span data-stu-id="5d165-104">Alternatively, you can create a Web message part from a primitive .NET type by using a .NET helper class to set the parts.</span></span> <span data-ttu-id="5d165-105">使用.NET 类创建消息类型的详细信息，请参阅[在用户代码中构造消息](../core/constructing-messages-in-user-code.md)。</span><span class="sxs-lookup"><span data-stu-id="5d165-105">For more information on creating message types by using a .NET class, see [Constructing Messages in User Code](../core/constructing-messages-in-user-code.md).</span></span>  
  
### <a name="to-construct-a-web-message-part-from-a-primitive-net-type"></a><span data-ttu-id="5d165-106">若要构造 Web 消息部分从基元.NET 类型</span><span class="sxs-lookup"><span data-stu-id="5d165-106">To construct a Web message part from a primitive .NET type</span></span>  
  
1.  <span data-ttu-id="5d165-107">与打开业务流程中，打开**工具箱**然后单击**BizTalk 业务流程**选项卡。</span><span class="sxs-lookup"><span data-stu-id="5d165-107">With an orchestration open, open the **Toolbox** and click the **BizTalk Orchestrations** tab.</span></span>  
  
2.  <span data-ttu-id="5d165-108">拖动**构造消息**向业务流程的形状。</span><span class="sxs-lookup"><span data-stu-id="5d165-108">Drag a **Construct Message** shape to the orchestration.</span></span>  
  
3.  <span data-ttu-id="5d165-109">编辑**构造的消息**属性以包含针对相应 Web 消息类型创建的消息实例。</span><span class="sxs-lookup"><span data-stu-id="5d165-109">Edit the **Message Constructed** property to include the message instance that you created for the Web message type.</span></span>  
  
4.  <span data-ttu-id="5d165-110">拖动**消息赋值**形状拖至**构造消息**形状。</span><span class="sxs-lookup"><span data-stu-id="5d165-110">Drag a **Message Assignment** shape onto the **Construct Message** shape.</span></span>  
  
5.  <span data-ttu-id="5d165-111">双击**消息赋值**形状以打开 BizTalk 表达式编辑器。</span><span class="sxs-lookup"><span data-stu-id="5d165-111">Double-click the **Message Assignment** shape to open the BizTalk Expression Editor.</span></span>  
  
6.  <span data-ttu-id="5d165-112">在 BizTalk 表达式编辑器框中为其所需的值设置 Web 消息类型的各个部分。</span><span class="sxs-lookup"><span data-stu-id="5d165-112">Set the parts of the Web message type to their required values in the BizTalk Expression Editor box.</span></span>  
  
     <span data-ttu-id="5d165-113">例如，下面的代码设置为字符串的表达式：</span><span class="sxs-lookup"><span data-stu-id="5d165-113">For example, the following code sets the expression to a string:</span></span>  
  
    ```  
    ItemAvailRequestInstance.Item_ID = "This is Item_ID.";  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="5d165-114">请参阅</span><span class="sxs-lookup"><span data-stu-id="5d165-114">See Also</span></span>  
 [<span data-ttu-id="5d165-115">构造 Web 消息</span><span class="sxs-lookup"><span data-stu-id="5d165-115">Constructing Web Messages</span></span>](../core/constructing-web-messages.md)