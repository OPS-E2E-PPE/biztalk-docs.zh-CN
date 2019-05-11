---
title: 单一登录：Event 10592 | Microsoft Docs
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
ms.openlocfilehash: 0bfd622db90bbafcb4d2af1b45ae2b2286e3345c
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65270948"
---
# <a name="single-sign-on-event-10592"></a><span data-ttu-id="39170-102">单一登录：事件 10592</span><span class="sxs-lookup"><span data-stu-id="39170-102">Single Sign-On: Event 10592</span></span>
## <a name="details"></a><span data-ttu-id="39170-103">详细信息</span><span class="sxs-lookup"><span data-stu-id="39170-103">Details</span></span>  
  
|                 |                                                                                                                                                    |
|-----------------|----------------------------------------------------------------------------------------------------------------------------------------------------|
|  <span data-ttu-id="39170-104">产品名称</span><span class="sxs-lookup"><span data-stu-id="39170-104">Product Name</span></span>   |                                                             <span data-ttu-id="39170-105">企业单一登录</span><span class="sxs-lookup"><span data-stu-id="39170-105">Enterprise Single Sign-On</span></span>                                                              |
| <span data-ttu-id="39170-106">产品版本</span><span class="sxs-lookup"><span data-stu-id="39170-106">Product Version</span></span> |                                             [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]                                             |
|    <span data-ttu-id="39170-107">事件 ID</span><span class="sxs-lookup"><span data-stu-id="39170-107">Event ID</span></span>     |                                                                       <span data-ttu-id="39170-108">10592</span><span class="sxs-lookup"><span data-stu-id="39170-108">10592</span></span>                                                                        |
|  <span data-ttu-id="39170-109">事件源</span><span class="sxs-lookup"><span data-stu-id="39170-109">Event Source</span></span>   |                                                                       <span data-ttu-id="39170-110">ENTSSO</span><span class="sxs-lookup"><span data-stu-id="39170-110">ENTSSO</span></span>                                                                       |
|    <span data-ttu-id="39170-111">组件</span><span class="sxs-lookup"><span data-stu-id="39170-111">Component</span></span>    |                                                                        <span data-ttu-id="39170-112">不可用</span><span class="sxs-lookup"><span data-stu-id="39170-112">N/A</span></span>                                                                         |
|  <span data-ttu-id="39170-113">符号名称</span><span class="sxs-lookup"><span data-stu-id="39170-113">Symbolic Name</span></span>  |                                                           <span data-ttu-id="39170-114">SSO_WARN_TICKET_DECRYPT_FAILED</span><span class="sxs-lookup"><span data-stu-id="39170-114">SSO_WARN_TICKET_DECRYPT_FAILED</span></span>                                                           |
|  <span data-ttu-id="39170-115">消息正文</span><span class="sxs-lookup"><span data-stu-id="39170-115">Message Text</span></span>   | <span data-ttu-id="39170-116">无法解密该票证。</span><span class="sxs-lookup"><span data-stu-id="39170-116">The ticket could not be decrypted.</span></span> <span data-ttu-id="39170-117">票证无效或者它可能具有 expired.%r</span><span class="sxs-lookup"><span data-stu-id="39170-117">The ticket is not valid or it may have expired.%r</span></span><br /><br /> <span data-ttu-id="39170-118">应用程序名称: %1 %r</span><span class="sxs-lookup"><span data-stu-id="39170-118">Application Name: %1%r</span></span><br /><br /> <span data-ttu-id="39170-119">错误代码： %2</span><span class="sxs-lookup"><span data-stu-id="39170-119">Error Code: %2</span></span> |
  
## <a name="explanation"></a><span data-ttu-id="39170-120">解释</span><span class="sxs-lookup"><span data-stu-id="39170-120">Explanation</span></span>  
 <span data-ttu-id="39170-121">票证无效或者可能已过期。</span><span class="sxs-lookup"><span data-stu-id="39170-121">The ticket is not valid or may have expired.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="39170-122">用户操作</span><span class="sxs-lookup"><span data-stu-id="39170-122">User Action</span></span>  
 <span data-ttu-id="39170-123">请确认你想要使用该票证有效，并且未过期。</span><span class="sxs-lookup"><span data-stu-id="39170-123">Confirm that the ticket you want to use is valid and has not expired.</span></span>