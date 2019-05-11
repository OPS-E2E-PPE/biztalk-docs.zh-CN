---
title: GetUserKey |Microsoft Docs
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
ms.openlocfilehash: cc4f163d35901a0cec9919e3053f84fd21cb712f
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65344889"
---
# <a name="getuserkey"></a><span data-ttu-id="f784b-102">GetUserKey</span><span class="sxs-lookup"><span data-stu-id="f784b-102">GetUserKey</span></span>
<span data-ttu-id="f784b-103">将推送到堆栈上的当前用户密钥。</span><span class="sxs-lookup"><span data-stu-id="f784b-103">Pushes the current user key onto the stack.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f784b-104">语法</span><span class="sxs-lookup"><span data-stu-id="f784b-104">Syntax</span></span>  
  
```  
  
<wf:Operation Name="GetUserKey" />  
```  
  
#### <a name="parameters"></a><span data-ttu-id="f784b-105">Parameters</span><span class="sxs-lookup"><span data-stu-id="f784b-105">Parameters</span></span>  
 <span data-ttu-id="f784b-106">无。</span><span class="sxs-lookup"><span data-stu-id="f784b-106">None.</span></span>  
  
## <a name="pushed-value"></a><span data-ttu-id="f784b-107">推送的值</span><span class="sxs-lookup"><span data-stu-id="f784b-107">Pushed Value</span></span>  
 <span data-ttu-id="f784b-108">包含当前用户密钥的字符串。</span><span class="sxs-lookup"><span data-stu-id="f784b-108">String containing the current user key.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="f784b-109">备注</span><span class="sxs-lookup"><span data-stu-id="f784b-109">Remarks</span></span>  
 <span data-ttu-id="f784b-110">此操作是仅在用户跟踪点中有效。</span><span class="sxs-lookup"><span data-stu-id="f784b-110">This operation is valid only in user track points.</span></span>  
  
## <a name="example"></a><span data-ttu-id="f784b-111">示例</span><span class="sxs-lookup"><span data-stu-id="f784b-111">Example</span></span>  
 <span data-ttu-id="f784b-112">下面的示例包含的事件筛选器表达式的计算结果将为`true`用户密钥等于"DocumentUrl"时。</span><span class="sxs-lookup"><span data-stu-id="f784b-112">The following sample contains an event filter expression that will evaluate to `true` when the user key is equal to "DocumentUrl".</span></span>  
  
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