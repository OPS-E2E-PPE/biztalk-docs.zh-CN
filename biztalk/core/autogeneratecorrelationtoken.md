---
title: AutoGenerateCorrelationToken | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: a24357c9-34e5-4caa-b41c-19551cfe81f9
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: cf2b3fd5ea662af08cf5613570ba65c4fd1017f6
ms.sourcegitcommit: d27732e569b0897361dfaebca8352aa97bb7efe1
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/10/2019
ms.locfileid: "65528902"
---
# <a name="autogeneratecorrelationtoken"></a><span data-ttu-id="ff3b6-102">AutoGenerateCorrelationToken</span><span class="sxs-lookup"><span data-stu-id="ff3b6-102">AutoGenerateCorrelationToken</span></span>
<span data-ttu-id="ff3b6-103">自动生成相关标记，并将其放置到堆栈上。</span><span class="sxs-lookup"><span data-stu-id="ff3b6-103">Automatically generates a correlation token and places it onto the stack.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ff3b6-104">语法</span><span class="sxs-lookup"><span data-stu-id="ff3b6-104">Syntax</span></span>  
  
```  
  
<wcf:Operation Name="AutoGenerateCorrelationToken" />  
```  
  
#### <a name="parameters"></a><span data-ttu-id="ff3b6-105">Parameters</span><span class="sxs-lookup"><span data-stu-id="ff3b6-105">Parameters</span></span>  
 <span data-ttu-id="ff3b6-106">无。</span><span class="sxs-lookup"><span data-stu-id="ff3b6-106">None.</span></span>  
  
## <a name="pushed-value"></a><span data-ttu-id="ff3b6-107">推送的值</span><span class="sxs-lookup"><span data-stu-id="ff3b6-107">Pushed Value</span></span>  
 <span data-ttu-id="ff3b6-108">包含相关标记的字符串。</span><span class="sxs-lookup"><span data-stu-id="ff3b6-108">String containing the correlation token.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="ff3b6-109">备注</span><span class="sxs-lookup"><span data-stu-id="ff3b6-109">Remarks</span></span>  
 <span data-ttu-id="ff3b6-110">消息中出现任何相关标记，但您仍想要将请求和答复中的信息相关联时，可以使用此操作。</span><span class="sxs-lookup"><span data-stu-id="ff3b6-110">This operation can be used when there is no correlation token present in the message but you still want to correlate the information from a request and a reply.</span></span> <span data-ttu-id="ff3b6-111">它可以用于将特定客户端或服务端上请求/答复相关联。</span><span class="sxs-lookup"><span data-stu-id="ff3b6-111">It can be used to correlate a particular request/reply on either the client or the service side.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="ff3b6-112">如果你想要将请求和答复的客户端和服务 （延续） 收集的数据相关联，您需要使用数据元素或从您的消息的元素。</span><span class="sxs-lookup"><span data-stu-id="ff3b6-112">If you want to correlate the data gathered by the request and the reply for both the client and the service (a continuation), you will need to use a data element or elements from your message.</span></span>  
  
## <a name="example"></a><span data-ttu-id="ff3b6-113">示例</span><span class="sxs-lookup"><span data-stu-id="ff3b6-113">Example</span></span>  
 <span data-ttu-id="ff3b6-114">下面的示例关联表达式依靠`AutoGenerateCorrelationToken`生成相关标记。</span><span class="sxs-lookup"><span data-stu-id="ff3b6-114">The following example correlation expression relies on the `AutoGenerateCorrelationToken` to generate a correlation token.</span></span>  
  
```  
<ic:CorrelationID>  
  <ic:Expression>            
    <wcf:Operation Name="AutoGenerateCorrelationToken"/>  
  </ic:Expression>  
</ic:CorrelationID>  
```  
  
## <a name="see-also"></a><span data-ttu-id="ff3b6-115">请参阅</span><span class="sxs-lookup"><span data-stu-id="ff3b6-115">See Also</span></span>  
 [<span data-ttu-id="ff3b6-116">Windows Communication Foundation 中的操作</span><span class="sxs-lookup"><span data-stu-id="ff3b6-116">Operations in Windows Communication Foundation</span></span>](../core/operations-in-windows-communication-foundation.md)