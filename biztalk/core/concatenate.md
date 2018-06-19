---
title: 连接 |Microsoft 文档
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
ms.openlocfilehash: 4766f65fb0cbe26c8f3c545c38235d83abb283a4
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22231693"
---
# <a name="concatenate"></a><span data-ttu-id="bc411-102">连接</span><span class="sxs-lookup"><span data-stu-id="bc411-102">Concatenate</span></span>
<span data-ttu-id="bc411-103">删除堆栈最上方的两项，连接这两项，然后将结果推送到堆栈上。</span><span class="sxs-lookup"><span data-stu-id="bc411-103">Removes the top two items from the stack, concatenates them, and then pushes the result onto the stack.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="bc411-104">语法</span><span class="sxs-lookup"><span data-stu-id="bc411-104">Syntax</span></span>  
  
```  
  
<ic:Operation Name="Concatenate" />  
```  
  
#### <a name="parameters"></a><span data-ttu-id="bc411-105">Parameters</span><span class="sxs-lookup"><span data-stu-id="bc411-105">Parameters</span></span>  
 <span data-ttu-id="bc411-106">堆栈最上方的两项。</span><span class="sxs-lookup"><span data-stu-id="bc411-106">Top two items on the stack.</span></span>  
  
## <a name="pushed-value"></a><span data-ttu-id="bc411-107">推送的值</span><span class="sxs-lookup"><span data-stu-id="bc411-107">Pushed Value</span></span>  
 <span data-ttu-id="bc411-108">连接操作的字符串结果。</span><span class="sxs-lookup"><span data-stu-id="bc411-108">String result of the concatenation operation.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="bc411-109">注释</span><span class="sxs-lookup"><span data-stu-id="bc411-109">Remarks</span></span>  
  
## <a name="example"></a><span data-ttu-id="bc411-110">示例</span><span class="sxs-lookup"><span data-stu-id="bc411-110">Example</span></span>  
 <span data-ttu-id="bc411-111">在下面的示例更新表达式，常量字符串"启动:"是"EventTime"上下文属性的值连接在一起并保存到数据库列 NewOrderCreateTime。</span><span class="sxs-lookup"><span data-stu-id="bc411-111">In the following example update expression, the constant string "Start:" is concatenated with the value of the "EventTime" context property and persisted to the database column NewOrderCreateTime.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="bc411-112">另请参阅</span><span class="sxs-lookup"><span data-stu-id="bc411-112">See Also</span></span>  
 [<span data-ttu-id="bc411-113">拦截器操作</span><span class="sxs-lookup"><span data-stu-id="bc411-113">Interceptor Operations</span></span>](../core/interceptor-operations.md)