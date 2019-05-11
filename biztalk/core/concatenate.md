---
title: 串联 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: e21a773d-a9cc-4a6f-b548-46badcd92aab
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 4d47db49e60b95071b48393735b3b4b0e7cee528
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65391631"
---
# <a name="concatenate"></a><span data-ttu-id="9431d-102">连接</span><span class="sxs-lookup"><span data-stu-id="9431d-102">Concatenate</span></span>
<span data-ttu-id="9431d-103">从堆栈移除的前两个项，将它们，连接，然后将推送到堆栈上的结果。</span><span class="sxs-lookup"><span data-stu-id="9431d-103">Removes the top two items from the stack, concatenates them, and then pushes the result onto the stack.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9431d-104">语法</span><span class="sxs-lookup"><span data-stu-id="9431d-104">Syntax</span></span>  
  
```  
  
<ic:Operation Name="Concatenate" />  
```  
  
#### <a name="parameters"></a><span data-ttu-id="9431d-105">Parameters</span><span class="sxs-lookup"><span data-stu-id="9431d-105">Parameters</span></span>  
 <span data-ttu-id="9431d-106">在堆栈上前两个项。</span><span class="sxs-lookup"><span data-stu-id="9431d-106">Top two items on the stack.</span></span>  
  
## <a name="pushed-value"></a><span data-ttu-id="9431d-107">推送的值</span><span class="sxs-lookup"><span data-stu-id="9431d-107">Pushed Value</span></span>  
 <span data-ttu-id="9431d-108">字符串串联操作的结果。</span><span class="sxs-lookup"><span data-stu-id="9431d-108">String result of the concatenation operation.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="9431d-109">备注</span><span class="sxs-lookup"><span data-stu-id="9431d-109">Remarks</span></span>  
  
## <a name="example"></a><span data-ttu-id="9431d-110">示例</span><span class="sxs-lookup"><span data-stu-id="9431d-110">Example</span></span>  
 <span data-ttu-id="9431d-111">在下面的示例更新表达式中，常量字符串"启动:"与"EventTime"上下文属性的值连接和持久保存到 NewOrderCreateTime 数据库列中。</span><span class="sxs-lookup"><span data-stu-id="9431d-111">In the following example update expression, the constant string "Start:" is concatenated with the value of the "EventTime" context property and persisted to the database column NewOrderCreateTime.</span></span>  
  
```  
<ic:Update DataItemName="NewOrderCreateTime" Type="NVARCHAR">  
  <ic:Expression>  
    <ic:Operation Name="Constant">  
      <ic:Argument>Start:</ic:Argument>  
    </ic:Operation>  
    <wf:Operation Name="GetContextProperty">  
      <wf:Argument>EventTime</wf:Argument>  
    </wf:Operation>  
    <ic:Operation Name="Concatenate" />  
  </ic:Expression>  
</ic:Update>  
```  
  
## <a name="see-also"></a><span data-ttu-id="9431d-112">请参阅</span><span class="sxs-lookup"><span data-stu-id="9431d-112">See Also</span></span>  
 [<span data-ttu-id="9431d-113">侦听器运算</span><span class="sxs-lookup"><span data-stu-id="9431d-113">Interceptor Operations</span></span>](../core/interceptor-operations.md)