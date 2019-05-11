---
title: GetOperationName | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: f858269c-d412-43e3-85e1-398afa9375ab
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 92eba73898b08e89cd1c3c7cdbd5f65c14ba048f
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65387678"
---
# <a name="getoperationname"></a><span data-ttu-id="24fa9-102">GetOperationName</span><span class="sxs-lookup"><span data-stu-id="24fa9-102">GetOperationName</span></span>
<span data-ttu-id="24fa9-103">将当前操作的名称推送到堆栈上。</span><span class="sxs-lookup"><span data-stu-id="24fa9-103">Pushes the name of the current operation onto the stack.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="24fa9-104">语法</span><span class="sxs-lookup"><span data-stu-id="24fa9-104">Syntax</span></span>  
  
```  
  
<wcf:Operation Name="GetOperationName" />  
```  
  
#### <a name="parameters"></a><span data-ttu-id="24fa9-105">Parameters</span><span class="sxs-lookup"><span data-stu-id="24fa9-105">Parameters</span></span>  
 <span data-ttu-id="24fa9-106">无。</span><span class="sxs-lookup"><span data-stu-id="24fa9-106">None.</span></span>  
  
## <a name="pushed-value"></a><span data-ttu-id="24fa9-107">推送的值</span><span class="sxs-lookup"><span data-stu-id="24fa9-107">Pushed Value</span></span>  
 <span data-ttu-id="24fa9-108">包含当前操作名称的字符串。</span><span class="sxs-lookup"><span data-stu-id="24fa9-108">String containing the name of the current operation.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="24fa9-109">备注</span><span class="sxs-lookup"><span data-stu-id="24fa9-109">Remarks</span></span>  
 <span data-ttu-id="24fa9-110">如果使用 GetOperationName，请确保在应用程序调用它时对操作名称进行比较。</span><span class="sxs-lookup"><span data-stu-id="24fa9-110">When using GetOperationName, make sure you compare the operation name as it is invoked by your application.</span></span> <span data-ttu-id="24fa9-111">例如，如果使用服务约定上的名称属性来指定自定义名称，客户端将具有使用该方法的自定义名称生成的默认代理。</span><span class="sxs-lookup"><span data-stu-id="24fa9-111">For example, if you use the name attribute on a service contract to assign a custom name, the client will have its default proxy generated with the custom name for the method.</span></span> <span data-ttu-id="24fa9-112">但是，服务器应用程序将使用对应操作的实际方法名称，而不是在名称属性中指定的名称。</span><span class="sxs-lookup"><span data-stu-id="24fa9-112">However, the server application will use the actual method names for the corresponding operations and not the one specified in the name attribute.</span></span>  
  
## <a name="example"></a><span data-ttu-id="24fa9-113">示例</span><span class="sxs-lookup"><span data-stu-id="24fa9-113">Example</span></span>  
 <span data-ttu-id="24fa9-114">在下面的示例中，`GetOperationName` 用于生成一个可筛选名称为“AuthorizePayment”的操作的表达式。</span><span class="sxs-lookup"><span data-stu-id="24fa9-114">In the following sample, `GetOperationName` is used to build an expression that filters for the operation named "AuthorizePayment".</span></span>  
  
```  
<ic:Filter>  
  <ic:Expression>  
    <wcf:Operation Name="GetOperationName" />  
    <ic:Operation Name="Constant">  
      <ic:Argument>AuthorizePayment</ic:Argument>  
    </ic:Operation>  
  </ic:Expression>  
</ic:Filter>  
```  
  
## <a name="see-also"></a><span data-ttu-id="24fa9-115">请参阅</span><span class="sxs-lookup"><span data-stu-id="24fa9-115">See Also</span></span>  
 [<span data-ttu-id="24fa9-116">Windows Communication Foundation 中的操作</span><span class="sxs-lookup"><span data-stu-id="24fa9-116">Operations in Windows Communication Foundation</span></span>](../core/operations-in-windows-communication-foundation.md)