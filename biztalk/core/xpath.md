---
title: XPath |Microsoft 文档
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
ms.openlocfilehash: 2ee46838596a55512df5d1476f2c3ba34b1f5cb9
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22289645"
---
# <a name="xpath"></a><span data-ttu-id="02569-102">XPath</span><span class="sxs-lookup"><span data-stu-id="02569-102">XPath</span></span>
<span data-ttu-id="02569-103">推送 XPath 语句所指示的值。</span><span class="sxs-lookup"><span data-stu-id="02569-103">Pushes the value indicated by an XPath statement.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="02569-104">语法</span><span class="sxs-lookup"><span data-stu-id="02569-104">Syntax</span></span>  
  
```  
  
<wcf:Operation Name="XPath">  
  <wcf:Argument>//po:POID</wcf:Argument>  
</wcf:Operation>  
```  
  
#### <a name="parameters"></a><span data-ttu-id="02569-105">Parameters</span><span class="sxs-lookup"><span data-stu-id="02569-105">Parameters</span></span>  
 <span data-ttu-id="02569-106">有效 XPath 语句。</span><span class="sxs-lookup"><span data-stu-id="02569-106">Valid XPath statement.</span></span>  
  
## <a name="pushed-value"></a><span data-ttu-id="02569-107">推送的值</span><span class="sxs-lookup"><span data-stu-id="02569-107">Pushed Value</span></span>  
 <span data-ttu-id="02569-108">执行 XPath 语句所找到的结果的字符串值。</span><span class="sxs-lookup"><span data-stu-id="02569-108">String value of the result found by executing the XPath statement.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="02569-109">注释</span><span class="sxs-lookup"><span data-stu-id="02569-109">Remarks</span></span>  
 <span data-ttu-id="02569-110">必须使用有效的 XPath 语句。</span><span class="sxs-lookup"><span data-stu-id="02569-110">You must use a valid XPath statement.</span></span>  
  
 <span data-ttu-id="02569-111">在出现多个匹配的情况下，仅会使用第一个匹配。</span><span class="sxs-lookup"><span data-stu-id="02569-111">In the case of multiple matches, only the first match is used.</span></span>  
  
## <a name="example"></a><span data-ttu-id="02569-112">示例</span><span class="sxs-lookup"><span data-stu-id="02569-112">Example</span></span>  
 <span data-ttu-id="02569-113">下面的示例表达式通过将常数“C_”与当前消息中的采购订单 ID 相连接构造了一个相关值。</span><span class="sxs-lookup"><span data-stu-id="02569-113">The following example expression constructs a correlation value by concatenating a constant "C_" with the purchase order ID from the current message.</span></span> <span data-ttu-id="02569-114">采购订单 ID 通过 XPath 运算检索。</span><span class="sxs-lookup"><span data-stu-id="02569-114">The purchase order ID is retrieved by using the XPath operation.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="02569-115">另请参阅</span><span class="sxs-lookup"><span data-stu-id="02569-115">See Also</span></span>  
 [<span data-ttu-id="02569-116">Windows Communication Foundation 中的操作</span><span class="sxs-lookup"><span data-stu-id="02569-116">Operations in Windows Communication Foundation</span></span>](../core/operations-in-windows-communication-foundation.md)