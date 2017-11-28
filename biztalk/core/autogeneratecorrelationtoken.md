---
title: "AutoGenerateCorrelationToken |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: a24357c9-34e5-4caa-b41c-19551cfe81f9
caps.latest.revision: "9"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 2e396fd0b2c6153a5252d336b9af9c22bf9421fd
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="autogeneratecorrelationtoken"></a><span data-ttu-id="d37b0-102">AutoGenerateCorrelationToken</span><span class="sxs-lookup"><span data-stu-id="d37b0-102">AutoGenerateCorrelationToken</span></span>
<span data-ttu-id="d37b0-103">自动生成相关标记，并将其放到堆栈上。</span><span class="sxs-lookup"><span data-stu-id="d37b0-103">Automatically generates a correlation token and places it onto the stack.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d37b0-104">语法</span><span class="sxs-lookup"><span data-stu-id="d37b0-104">Syntax</span></span>  
  
```  
  
<wcf:Operation Name="AutoGenerateCorrelationToken" />  
```  
  
#### <a name="parameters"></a><span data-ttu-id="d37b0-105">Parameters</span><span class="sxs-lookup"><span data-stu-id="d37b0-105">Parameters</span></span>  
 <span data-ttu-id="d37b0-106">无。</span><span class="sxs-lookup"><span data-stu-id="d37b0-106">None.</span></span>  
  
## <a name="pushed-value"></a><span data-ttu-id="d37b0-107">推送的值</span><span class="sxs-lookup"><span data-stu-id="d37b0-107">Pushed Value</span></span>  
 <span data-ttu-id="d37b0-108">包含相关标记的字符串。</span><span class="sxs-lookup"><span data-stu-id="d37b0-108">String containing the correlation token.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="d37b0-109">注释</span><span class="sxs-lookup"><span data-stu-id="d37b0-109">Remarks</span></span>  
 <span data-ttu-id="d37b0-110">当没有相关标记的消息中存在，但你仍想要关联请求和答复中的信息时，可以使用此操作。</span><span class="sxs-lookup"><span data-stu-id="d37b0-110">This operation can be used when there is no correlation token present in the message but you still want to correlate the information from a request and a reply.</span></span> <span data-ttu-id="d37b0-111">它可以用于将特定客户端或服务端上请求/答复关联起来。</span><span class="sxs-lookup"><span data-stu-id="d37b0-111">It can be used to correlate a particular request/reply on either the client or the service side.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="d37b0-112">如果你想要关联的请求和答复的客户端和服务 （延续） 收集的数据，你将需要使用的数据元素或从你的消息的元素。</span><span class="sxs-lookup"><span data-stu-id="d37b0-112">If you want to correlate the data gathered by the request and the reply for both the client and the service (a continuation), you will need to use a data element or elements from your message.</span></span>  
  
## <a name="example"></a><span data-ttu-id="d37b0-113">示例</span><span class="sxs-lookup"><span data-stu-id="d37b0-113">Example</span></span>  
 <span data-ttu-id="d37b0-114">下面的示例关联表达式依靠 `AutoGenerateCorrelationToken` 来生成相关标记。</span><span class="sxs-lookup"><span data-stu-id="d37b0-114">The following example correlation expression relies on the `AutoGenerateCorrelationToken` to generate a correlation token.</span></span>  
  
```  
<ic:CorrelationID>  
  <ic:Expression>            
    <wcf:Operation Name="AutoGenerateCorrelationToken"/>  
  </ic:Expression>  
</ic:CorrelationID>  
```  
  
## <a name="see-also"></a><span data-ttu-id="d37b0-115">另请参阅</span><span class="sxs-lookup"><span data-stu-id="d37b0-115">See Also</span></span>  
 [<span data-ttu-id="d37b0-116">Windows Communication Foundation 中的操作</span><span class="sxs-lookup"><span data-stu-id="d37b0-116">Operations in Windows Communication Foundation</span></span>](../core/operations-in-windows-communication-foundation.md)