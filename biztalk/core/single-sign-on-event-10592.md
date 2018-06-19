---
title: 单一登录： 事件 10592 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: e044f9bd-c384-4f08-81f0-699e0c774c45
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 0f03f32a956cabe906c22afe0c89a096a1ad213f
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22270437"
---
# <a name="single-sign-on-event-10592"></a><span data-ttu-id="f02ce-102">单一登录： 事件 10592</span><span class="sxs-lookup"><span data-stu-id="f02ce-102">Single Sign-On: Event 10592</span></span>
## <a name="details"></a><span data-ttu-id="f02ce-103">详细信息</span><span class="sxs-lookup"><span data-stu-id="f02ce-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="f02ce-104">产品名称</span><span class="sxs-lookup"><span data-stu-id="f02ce-104">Product Name</span></span>|<span data-ttu-id="f02ce-105">企业单一登录</span><span class="sxs-lookup"><span data-stu-id="f02ce-105">Enterprise Single Sign-On</span></span>|  
|<span data-ttu-id="f02ce-106">产品版本</span><span class="sxs-lookup"><span data-stu-id="f02ce-106">Product Version</span></span>|[!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]|  
|<span data-ttu-id="f02ce-107">事件 ID</span><span class="sxs-lookup"><span data-stu-id="f02ce-107">Event ID</span></span>|<span data-ttu-id="f02ce-108">10592</span><span class="sxs-lookup"><span data-stu-id="f02ce-108">10592</span></span>|  
|<span data-ttu-id="f02ce-109">事件源</span><span class="sxs-lookup"><span data-stu-id="f02ce-109">Event Source</span></span>|<span data-ttu-id="f02ce-110">ENTSSO</span><span class="sxs-lookup"><span data-stu-id="f02ce-110">ENTSSO</span></span>|  
|<span data-ttu-id="f02ce-111">组件</span><span class="sxs-lookup"><span data-stu-id="f02ce-111">Component</span></span>|<span data-ttu-id="f02ce-112">N/A</span><span class="sxs-lookup"><span data-stu-id="f02ce-112">N/A</span></span>|  
|<span data-ttu-id="f02ce-113">符号名称</span><span class="sxs-lookup"><span data-stu-id="f02ce-113">Symbolic Name</span></span>|<span data-ttu-id="f02ce-114">SSO_WARN_TICKET_DECRYPT_FAILED</span><span class="sxs-lookup"><span data-stu-id="f02ce-114">SSO_WARN_TICKET_DECRYPT_FAILED</span></span>|  
|<span data-ttu-id="f02ce-115">消息正文</span><span class="sxs-lookup"><span data-stu-id="f02ce-115">Message Text</span></span>|<span data-ttu-id="f02ce-116">无法对票证进行解密。</span><span class="sxs-lookup"><span data-stu-id="f02ce-116">The ticket could not be decrypted.</span></span> <span data-ttu-id="f02ce-117">票证无效或者可能已过期。%r</span><span class="sxs-lookup"><span data-stu-id="f02ce-117">The ticket is not valid or it may have expired.%r</span></span><br /><br /> <span data-ttu-id="f02ce-118">应用程序名称: %1 %r</span><span class="sxs-lookup"><span data-stu-id="f02ce-118">Application Name: %1%r</span></span><br /><br /> <span data-ttu-id="f02ce-119">错误代码： %2</span><span class="sxs-lookup"><span data-stu-id="f02ce-119">Error Code: %2</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="f02ce-120">解释</span><span class="sxs-lookup"><span data-stu-id="f02ce-120">Explanation</span></span>  
 <span data-ttu-id="f02ce-121">票证无效或者可能已过期。</span><span class="sxs-lookup"><span data-stu-id="f02ce-121">The ticket is not valid or may have expired.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="f02ce-122">用户操作</span><span class="sxs-lookup"><span data-stu-id="f02ce-122">User Action</span></span>  
 <span data-ttu-id="f02ce-123">确认要使用的票证是有效的并且尚未过期。</span><span class="sxs-lookup"><span data-stu-id="f02ce-123">Confirm that the ticket you want to use is valid and has not expired.</span></span>