---
title: XPath | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 444b5eb9-0c00-4225-918e-b973532c67d0
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 16499791b20f4f7ebd925d1388bc3eb90cf69b1c
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65246490"
---
# <a name="xpath"></a><span data-ttu-id="272ef-102">XPath</span><span class="sxs-lookup"><span data-stu-id="272ef-102">XPath</span></span>
<span data-ttu-id="272ef-103">推送 XPath 语句所指示的值。</span><span class="sxs-lookup"><span data-stu-id="272ef-103">Pushes the value indicated by an XPath statement.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="272ef-104">语法</span><span class="sxs-lookup"><span data-stu-id="272ef-104">Syntax</span></span>  
  
```  
  
<wcf:Operation Name="XPath">  
  <wcf:Argument>//po:POID</wcf:Argument>  
</wcf:Operation>  
```  
  
#### <a name="parameters"></a><span data-ttu-id="272ef-105">Parameters</span><span class="sxs-lookup"><span data-stu-id="272ef-105">Parameters</span></span>  
 <span data-ttu-id="272ef-106">有效 XPath 语句。</span><span class="sxs-lookup"><span data-stu-id="272ef-106">Valid XPath statement.</span></span>  
  
## <a name="pushed-value"></a><span data-ttu-id="272ef-107">推送的值</span><span class="sxs-lookup"><span data-stu-id="272ef-107">Pushed Value</span></span>  
 <span data-ttu-id="272ef-108">执行 XPath 语句所找到的结果的字符串值。</span><span class="sxs-lookup"><span data-stu-id="272ef-108">String value of the result found by executing the XPath statement.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="272ef-109">备注</span><span class="sxs-lookup"><span data-stu-id="272ef-109">Remarks</span></span>  
 <span data-ttu-id="272ef-110">必须使用有效的 XPath 语句。</span><span class="sxs-lookup"><span data-stu-id="272ef-110">You must use a valid XPath statement.</span></span>  
  
 <span data-ttu-id="272ef-111">在出现多个匹配的情况下，仅会使用第一个匹配。</span><span class="sxs-lookup"><span data-stu-id="272ef-111">In the case of multiple matches, only the first match is used.</span></span>  
  
## <a name="example"></a><span data-ttu-id="272ef-112">示例</span><span class="sxs-lookup"><span data-stu-id="272ef-112">Example</span></span>  
 <span data-ttu-id="272ef-113">下面的示例表达式通过将常数“C_”与当前消息中的采购订单 ID 相连接构造了一个相关值。</span><span class="sxs-lookup"><span data-stu-id="272ef-113">The following example expression constructs a correlation value by concatenating a constant "C_" with the purchase order ID from the current message.</span></span> <span data-ttu-id="272ef-114">采购订单 ID 通过 XPath 运算检索。</span><span class="sxs-lookup"><span data-stu-id="272ef-114">The purchase order ID is retrieved by using the XPath operation.</span></span>  
  
```  
<ic:CorrelationID>  
  <ic:Expression>  
    <ic:Operation Name="Constant">  
      <ic:Argument>C_</ic:Argument>  
    </ic:Operation>  
    <wcf:Operation Name="XPath">  
      <wcf:Argument>//po:POID</wcf:Argument>  
    </wcf:Operation>  
    <ic:Operation Name="Concatenate" />  
  </ic:Expression>  
</ic:CorrelationID>  
```  
  
## <a name="see-also"></a><span data-ttu-id="272ef-115">请参阅</span><span class="sxs-lookup"><span data-stu-id="272ef-115">See Also</span></span>  
 [<span data-ttu-id="272ef-116">Windows Communication Foundation 中的操作</span><span class="sxs-lookup"><span data-stu-id="272ef-116">Operations in Windows Communication Foundation</span></span>](../core/operations-in-windows-communication-foundation.md)