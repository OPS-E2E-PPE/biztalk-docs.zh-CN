---
title: GetUserData | Microsoft Docs
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
ms.openlocfilehash: 8348e510d168725bf61ab05075162f15768915d6
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65344901"
---
# <a name="getuserdata"></a><span data-ttu-id="954a5-102">GetUserData</span><span class="sxs-lookup"><span data-stu-id="954a5-102">GetUserData</span></span>
<span data-ttu-id="954a5-103">将推送到堆栈上的当前用户数据。</span><span class="sxs-lookup"><span data-stu-id="954a5-103">Pushes the current user data onto the stack.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="954a5-104">语法</span><span class="sxs-lookup"><span data-stu-id="954a5-104">Syntax</span></span>  
  
```  
  
<wf:Operation Name="GetUserData" />  
```  
  
#### <a name="parameters"></a><span data-ttu-id="954a5-105">Parameters</span><span class="sxs-lookup"><span data-stu-id="954a5-105">Parameters</span></span>  
 <span data-ttu-id="954a5-106">无。</span><span class="sxs-lookup"><span data-stu-id="954a5-106">None.</span></span>  
  
## <a name="pushed-value"></a><span data-ttu-id="954a5-107">推送的值</span><span class="sxs-lookup"><span data-stu-id="954a5-107">Pushed Value</span></span>  
 <span data-ttu-id="954a5-108">包含当前用户数据的字符串。</span><span class="sxs-lookup"><span data-stu-id="954a5-108">String containing the current user data.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="954a5-109">备注</span><span class="sxs-lookup"><span data-stu-id="954a5-109">Remarks</span></span>  
 <span data-ttu-id="954a5-110">此操作无效，不能在筛选器。</span><span class="sxs-lookup"><span data-stu-id="954a5-110">This operation is not valid inside of a filter.</span></span>  
  
## <a name="example"></a><span data-ttu-id="954a5-111">示例</span><span class="sxs-lookup"><span data-stu-id="954a5-111">Example</span></span>  
 <span data-ttu-id="954a5-112">下面的示例包含数据的项"UserData"使用的更新表达式`GetUserData`操作。</span><span class="sxs-lookup"><span data-stu-id="954a5-112">The following sample contains an update expression for the data item "UserData" using the `GetUserData` operation.</span></span>  
  
```  
<ic:Update DataItemName="UserData" Type="NVARCHAR">  
  <ic:Expression>  
    <wf:Operation Name="GetUserData" />  
  </ic:Expression>  
</ic:Update>  
```