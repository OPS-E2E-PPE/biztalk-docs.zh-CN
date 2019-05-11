---
title: 单一登录：Event 10855 | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: ba244f8e-bc61-475f-913c-475ebf1c69ee
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 9519453d0209caf46fa75c1bce52d60fe792d0e3
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65306652"
---
# <a name="single-sign-on-event-10855"></a><span data-ttu-id="72663-102">单一登录：事件 10855</span><span class="sxs-lookup"><span data-stu-id="72663-102">Single Sign-On: Event 10855</span></span>

|                 |                                                                        |
|-----------------|------------------------------------------------------------------------|
|  <span data-ttu-id="72663-103">产品名称</span><span class="sxs-lookup"><span data-stu-id="72663-103">Product Name</span></span>   |                       <span data-ttu-id="72663-104">企业单一登录</span><span class="sxs-lookup"><span data-stu-id="72663-104">Enterprise Single Sign-On</span></span>                        |
| <span data-ttu-id="72663-105">产品版本</span><span class="sxs-lookup"><span data-stu-id="72663-105">Product Version</span></span> |       [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]       |
|    <span data-ttu-id="72663-106">事件 ID</span><span class="sxs-lookup"><span data-stu-id="72663-106">Event ID</span></span>     |                                 <span data-ttu-id="72663-107">10855</span><span class="sxs-lookup"><span data-stu-id="72663-107">10855</span></span>                                  |
|  <span data-ttu-id="72663-108">事件源</span><span class="sxs-lookup"><span data-stu-id="72663-108">Event Source</span></span>   |                                 <span data-ttu-id="72663-109">ENTSSO</span><span class="sxs-lookup"><span data-stu-id="72663-109">ENTSSO</span></span>                                 |
|    <span data-ttu-id="72663-110">组件</span><span class="sxs-lookup"><span data-stu-id="72663-110">Component</span></span>    |                                  <span data-ttu-id="72663-111">不可用</span><span class="sxs-lookup"><span data-stu-id="72663-111">N/A</span></span>                                   |
|  <span data-ttu-id="72663-112">符号名称</span><span class="sxs-lookup"><span data-stu-id="72663-112">Symbolic Name</span></span>  |                    <span data-ttu-id="72663-113">ENTSSO_E_PASSWORD_FILTER_FAILED</span><span class="sxs-lookup"><span data-stu-id="72663-113">ENTSSO_E_PASSWORD_FILTER_FAILED</span></span>                     |
|  <span data-ttu-id="72663-114">消息正文</span><span class="sxs-lookup"><span data-stu-id="72663-114">Message Text</span></span>   | <span data-ttu-id="72663-115">无法返回凭据，因为密码筛选器失败。</span><span class="sxs-lookup"><span data-stu-id="72663-115">The credentials cannot be returned because the password filter failed.</span></span> |

## <a name="explanation"></a><span data-ttu-id="72663-116">解释</span><span class="sxs-lookup"><span data-stu-id="72663-116">Explanation</span></span>  
 <span data-ttu-id="72663-117">密码筛选器无效。</span><span class="sxs-lookup"><span data-stu-id="72663-117">The password filter is not valid.</span></span> <span data-ttu-id="72663-118">最可能的原因是，该筛选器手动创建的但并不推荐。</span><span class="sxs-lookup"><span data-stu-id="72663-118">The most likely cause of this is that the filter was created manually, which is not recommended.</span></span>  

## <a name="user-action"></a><span data-ttu-id="72663-119">用户操作</span><span class="sxs-lookup"><span data-stu-id="72663-119">User Action</span></span>  
 <span data-ttu-id="72663-120">创建密码筛选器再次使用创建筛选器向导。</span><span class="sxs-lookup"><span data-stu-id="72663-120">Create the password filter again using the Create Filter wizard.</span></span>