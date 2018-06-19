---
title: 单一登录： 事件 10765 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: e28fe42e-aa2b-4be4-b757-bc9c5c37526b
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 6c0fbc04f4c8fc98a87de87a4cd48529a3ca7e2e
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22278413"
---
# <a name="single-sign-on-event-10765"></a><span data-ttu-id="07824-102">单一登录： 事件 10765</span><span class="sxs-lookup"><span data-stu-id="07824-102">Single Sign-On: Event 10765</span></span>
## <a name="details"></a><span data-ttu-id="07824-103">详细信息</span><span class="sxs-lookup"><span data-stu-id="07824-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="07824-104">产品名称</span><span class="sxs-lookup"><span data-stu-id="07824-104">Product Name</span></span>|<span data-ttu-id="07824-105">企业单一登录</span><span class="sxs-lookup"><span data-stu-id="07824-105">Enterprise Single Sign-On</span></span>|  
|<span data-ttu-id="07824-106">产品版本</span><span class="sxs-lookup"><span data-stu-id="07824-106">Product Version</span></span>|[!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]|  
|<span data-ttu-id="07824-107">事件 ID</span><span class="sxs-lookup"><span data-stu-id="07824-107">Event ID</span></span>|<span data-ttu-id="07824-108">10765</span><span class="sxs-lookup"><span data-stu-id="07824-108">10765</span></span>|  
|<span data-ttu-id="07824-109">事件源</span><span class="sxs-lookup"><span data-stu-id="07824-109">Event Source</span></span>|<span data-ttu-id="07824-110">ENTSSO</span><span class="sxs-lookup"><span data-stu-id="07824-110">ENTSSO</span></span>|  
|<span data-ttu-id="07824-111">组件</span><span class="sxs-lookup"><span data-stu-id="07824-111">Component</span></span>|<span data-ttu-id="07824-112">N/A</span><span class="sxs-lookup"><span data-stu-id="07824-112">N/A</span></span>|  
|<span data-ttu-id="07824-113">符号名称</span><span class="sxs-lookup"><span data-stu-id="07824-113">Symbolic Name</span></span>|<span data-ttu-id="07824-114">ENTSSO_E_NO_CREDENTIALS</span><span class="sxs-lookup"><span data-stu-id="07824-114">ENTSSO_E_NO_CREDENTIALS</span></span>|  
|<span data-ttu-id="07824-115">消息正文</span><span class="sxs-lookup"><span data-stu-id="07824-115">Message Text</span></span>|<span data-ttu-id="07824-116">尚未为此映射设置凭据。</span><span class="sxs-lookup"><span data-stu-id="07824-116">No credentials have been set for the mapping.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="07824-117">解释</span><span class="sxs-lookup"><span data-stu-id="07824-117">Explanation</span></span>  
 <span data-ttu-id="07824-118">您请求了一个映射的 GetCredentials，但指定的映射没有凭据。</span><span class="sxs-lookup"><span data-stu-id="07824-118">You have requested a GetCredentials on a mapping, and the mapping specified has no credentials.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="07824-119">用户操作</span><span class="sxs-lookup"><span data-stu-id="07824-119">User Action</span></span>  
 <span data-ttu-id="07824-120">使用命令行或 MMC 管理单元为映射设置凭据。</span><span class="sxs-lookup"><span data-stu-id="07824-120">Use the command line or the MMC Snap-in to set credentials for the mapping.</span></span>