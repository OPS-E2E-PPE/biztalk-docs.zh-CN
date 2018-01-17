---
title: "如何确定 Web 消息部件类型 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- Web messages, message types
- Web services, Web messages
- Web messages, parts
ms.assetid: bdd1f604-ec35-41e3-b5a8-1e0ad0193eff
caps.latest.revision: "10"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 6102e39eb38e919c68405ae18bebde0b46c0b053
ms.sourcegitcommit: 3fd1c85d9dc2ce7b77da75a5c2087cc48cfcbe50
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/17/2018
---
# <a name="how-to-determine-a-web-message-part-type"></a><span data-ttu-id="4f80e-102">如何确定 Web 消息部分类型</span><span class="sxs-lookup"><span data-stu-id="4f80e-102">How to Determine a Web Message Part Type</span></span>
<span data-ttu-id="4f80e-103">你可以使用给定 Web 消息类型的“属性”窗口确定 Web 消息部分类型是基元 .NET 类型还是架构类型。</span><span class="sxs-lookup"><span data-stu-id="4f80e-103">You can determine if a Web message part type is a primitive .NET type or a schema type by using the Properties window for a given Web message type.</span></span>  
  
### <a name="to-determine-a-web-message-part-type"></a><span data-ttu-id="4f80e-104">确定 Web 消息部分类型</span><span class="sxs-lookup"><span data-stu-id="4f80e-104">To determine a Web message part type</span></span>  
  
1.  <span data-ttu-id="4f80e-105">与打开，请在业务流程 **视图** 菜单上，单击 **其他窗口**,，然后单击 **业务流程视图**。</span><span class="sxs-lookup"><span data-stu-id="4f80e-105">With an orchestration open, on the **View** menu, click **Other Windows**,and then click **Orchestration View**.</span></span>  
  
2.  <span data-ttu-id="4f80e-106">展开 **多部分消息类型** 节点，然后展开 Web 消息类型。</span><span class="sxs-lookup"><span data-stu-id="4f80e-106">Expand the **Multi-part Message Types** node, and then expand a Web message type.</span></span>  
  
3.  <span data-ttu-id="4f80e-107">选择消息部分。</span><span class="sxs-lookup"><span data-stu-id="4f80e-107">Select a message part.</span></span>  
  
     <span data-ttu-id="4f80e-108">开始为 Web 消息一部分签名 **\<*项目默认命名空间*\>。\<*Web 引用名称*\>。引用。\<*架构根*\>** 是架构类型。</span><span class="sxs-lookup"><span data-stu-id="4f80e-108">A Web message part signature that begins as **\<*project default namespace*\>.\<*Web reference name*\>.Reference.\<*schema root*\>** is a schema type.</span></span> <span data-ttu-id="4f80e-109"> **\<*架构根*\>** 类型的一部分是构造 Web 消息部分的 Web 引用架构的根元素。</span><span class="sxs-lookup"><span data-stu-id="4f80e-109">The **\<*schema root*\>** part of the type is the root element of the Web reference schema that constructs the Web message part.</span></span> <span data-ttu-id="4f80e-110">否则，消息一部分签名都是基元的.NET 类型如**System.String**或**System.Int32**。</span><span class="sxs-lookup"><span data-stu-id="4f80e-110">Otherwise, the message part signature is a primitive .NET type such as **System.String** or **System.Int32**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4f80e-111">另请参阅</span><span class="sxs-lookup"><span data-stu-id="4f80e-111">See Also</span></span>  
 [<span data-ttu-id="4f80e-112">构造 Web 消息</span><span class="sxs-lookup"><span data-stu-id="4f80e-112">Constructing Web Messages</span></span>](../core/constructing-web-messages.md)