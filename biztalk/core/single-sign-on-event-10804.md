---
title: 单一登录： 事件 10804 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: b4d98bef-fdc3-4627-bb5b-663fa502b965
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b65c59ce736804215cd7c70428905d776d8e0e4b
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22276645"
---
# <a name="single-sign-on-event-10804"></a><span data-ttu-id="00b7f-102">单一登录： 事件 10804</span><span class="sxs-lookup"><span data-stu-id="00b7f-102">Single Sign-On: Event 10804</span></span>
## <a name="details"></a><span data-ttu-id="00b7f-103">详细信息</span><span class="sxs-lookup"><span data-stu-id="00b7f-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="00b7f-104">产品名称</span><span class="sxs-lookup"><span data-stu-id="00b7f-104">Product Name</span></span>|<span data-ttu-id="00b7f-105">企业单一登录</span><span class="sxs-lookup"><span data-stu-id="00b7f-105">Enterprise Single Sign-On</span></span>|  
|<span data-ttu-id="00b7f-106">产品版本</span><span class="sxs-lookup"><span data-stu-id="00b7f-106">Product Version</span></span>|[!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]|  
|<span data-ttu-id="00b7f-107">事件 ID</span><span class="sxs-lookup"><span data-stu-id="00b7f-107">Event ID</span></span>|<span data-ttu-id="00b7f-108">10804</span><span class="sxs-lookup"><span data-stu-id="00b7f-108">10804</span></span>|  
|<span data-ttu-id="00b7f-109">事件源</span><span class="sxs-lookup"><span data-stu-id="00b7f-109">Event Source</span></span>|<span data-ttu-id="00b7f-110">ENTSSO</span><span class="sxs-lookup"><span data-stu-id="00b7f-110">ENTSSO</span></span>|  
|<span data-ttu-id="00b7f-111">组件</span><span class="sxs-lookup"><span data-stu-id="00b7f-111">Component</span></span>|<span data-ttu-id="00b7f-112">N/A</span><span class="sxs-lookup"><span data-stu-id="00b7f-112">N/A</span></span>|  
|<span data-ttu-id="00b7f-113">符号名称</span><span class="sxs-lookup"><span data-stu-id="00b7f-113">Symbolic Name</span></span>|<span data-ttu-id="00b7f-114">ENTSSO_E_INCORRECT_COMPUTER</span><span class="sxs-lookup"><span data-stu-id="00b7f-114">ENTSSO_E_INCORRECT_COMPUTER</span></span>|  
|<span data-ttu-id="00b7f-115">消息正文</span><span class="sxs-lookup"><span data-stu-id="00b7f-115">Message Text</span></span>|<span data-ttu-id="00b7f-116">此适配器未配置为此计算机使用。</span><span class="sxs-lookup"><span data-stu-id="00b7f-116">This adapter is not configured for this computer.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="00b7f-117">解释</span><span class="sxs-lookup"><span data-stu-id="00b7f-117">Explanation</span></span>  
 <span data-ttu-id="00b7f-118">每个适配器都配置为在特定计算机上运行，由长名称识别。</span><span class="sxs-lookup"><span data-stu-id="00b7f-118">Each adapter is configured to run on a specific computer, which is identified by its long name.</span></span> <span data-ttu-id="00b7f-119">名称不正确，或正在尝试在不同计算机上运行适配器。</span><span class="sxs-lookup"><span data-stu-id="00b7f-119">Either the name is incorrect, or you are trying to run the adapter on a different computer.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="00b7f-120">用户操作</span><span class="sxs-lookup"><span data-stu-id="00b7f-120">User Action</span></span>  
 <span data-ttu-id="00b7f-121">请查看此适配器的配置以确定相应计算机的正确名称。</span><span class="sxs-lookup"><span data-stu-id="00b7f-121">See the configuration for this adapter to determine the proper name of the appropriate computer.</span></span>