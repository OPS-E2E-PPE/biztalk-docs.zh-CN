---
title: GetUserKey |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 9353a7f0-9bbd-4cfa-92e6-ed2b86e3a88e
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 0701ff1df912cc113205bad573b6cebc0f02a13a
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22246117"
---
# <a name="getuserkey"></a><span data-ttu-id="c8852-102">GetUserKey</span><span class="sxs-lookup"><span data-stu-id="c8852-102">GetUserKey</span></span>
<span data-ttu-id="c8852-103">将当前用户密钥推送到堆栈上。</span><span class="sxs-lookup"><span data-stu-id="c8852-103">Pushes the current user key onto the stack.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c8852-104">语法</span><span class="sxs-lookup"><span data-stu-id="c8852-104">Syntax</span></span>  
  
```  
  
<wf:Operation Name="GetUserKey" />  
```  
  
#### <a name="parameters"></a><span data-ttu-id="c8852-105">Parameters</span><span class="sxs-lookup"><span data-stu-id="c8852-105">Parameters</span></span>  
 <span data-ttu-id="c8852-106">无。</span><span class="sxs-lookup"><span data-stu-id="c8852-106">None.</span></span>  
  
## <a name="pushed-value"></a><span data-ttu-id="c8852-107">推送的值</span><span class="sxs-lookup"><span data-stu-id="c8852-107">Pushed Value</span></span>  
 <span data-ttu-id="c8852-108">包含当前用户密钥的字符串。</span><span class="sxs-lookup"><span data-stu-id="c8852-108">String containing the current user key.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="c8852-109">注释</span><span class="sxs-lookup"><span data-stu-id="c8852-109">Remarks</span></span>  
 <span data-ttu-id="c8852-110">此操作仅在用户跟踪点中有效。</span><span class="sxs-lookup"><span data-stu-id="c8852-110">This operation is valid only in user track points.</span></span>  
  
## <a name="example"></a><span data-ttu-id="c8852-111">示例</span><span class="sxs-lookup"><span data-stu-id="c8852-111">Example</span></span>  
 <span data-ttu-id="c8852-112">下面的示例包含计算结果将为事件筛选器表达式`true`时用户密钥等同于"DocumentUrl"。</span><span class="sxs-lookup"><span data-stu-id="c8852-112">The following sample contains an event filter expression that will evaluate to `true` when the user key is equal to "DocumentUrl".</span></span>  
  
```  
<ic:Filter>  
  <ic:Expression>  
    <wf:Operation Name="GetUserKey" />  
    <ic:Operation Name="Constant">  
      <ic:Argument>DocumentUrl</ic:Argument>  
    </ic:Operation>  
    <ic:Operation Name="Equals" />  
  </ic:Expression>  
</ic:Filter>  
```