---
title: GetUserData |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: c243555b-109f-47e3-8084-ab13a8e22ac5
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 57bc0ffcefc00e9fae20c7b2c8449c21c549b377
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22246381"
---
# <a name="getuserdata"></a><span data-ttu-id="52056-102">GetUserData</span><span class="sxs-lookup"><span data-stu-id="52056-102">GetUserData</span></span>
<span data-ttu-id="52056-103">推送到堆栈的当前用户数据。</span><span class="sxs-lookup"><span data-stu-id="52056-103">Pushes the current user data onto the stack.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="52056-104">语法</span><span class="sxs-lookup"><span data-stu-id="52056-104">Syntax</span></span>  
  
```  
  
<wf:Operation Name="GetUserData" />  
```  
  
#### <a name="parameters"></a><span data-ttu-id="52056-105">Parameters</span><span class="sxs-lookup"><span data-stu-id="52056-105">Parameters</span></span>  
 <span data-ttu-id="52056-106">无。</span><span class="sxs-lookup"><span data-stu-id="52056-106">None.</span></span>  
  
## <a name="pushed-value"></a><span data-ttu-id="52056-107">推送的值</span><span class="sxs-lookup"><span data-stu-id="52056-107">Pushed Value</span></span>  
 <span data-ttu-id="52056-108">包含当前的用户数据的字符串。</span><span class="sxs-lookup"><span data-stu-id="52056-108">String containing the current user data.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="52056-109">注释</span><span class="sxs-lookup"><span data-stu-id="52056-109">Remarks</span></span>  
 <span data-ttu-id="52056-110">此操作无效，不能在筛选器。</span><span class="sxs-lookup"><span data-stu-id="52056-110">This operation is not valid inside of a filter.</span></span>  
  
## <a name="example"></a><span data-ttu-id="52056-111">示例</span><span class="sxs-lookup"><span data-stu-id="52056-111">Example</span></span>  
 <span data-ttu-id="52056-112">以下示例包含使用 `GetUserData` 运算的针对数据项“UserData”的更新表达式。</span><span class="sxs-lookup"><span data-stu-id="52056-112">The following sample contains an update expression for the data item "UserData" using the `GetUserData` operation.</span></span>  
  
```  
<ic:Update DataItemName="UserData" Type="NVARCHAR">  
  <ic:Expression>  
    <wf:Operation Name="GetUserData" />  
  </ic:Expression>  
</ic:Update>  
```