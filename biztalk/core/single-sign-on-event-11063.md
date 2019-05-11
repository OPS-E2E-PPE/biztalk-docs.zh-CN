---
title: 单一登录：事件 11063 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: c84f91de-221d-43c4-8d23-3d1b7fd29cf7
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a5971a2ace4307128d094a6b88c4928616173694
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65258680"
---
# <a name="single-sign-on-event-11063"></a><span data-ttu-id="8f35d-102">单一登录：事件 11063</span><span class="sxs-lookup"><span data-stu-id="8f35d-102">Single Sign-On: Event 11063</span></span>
## <a name="details"></a><span data-ttu-id="8f35d-103">详细信息</span><span class="sxs-lookup"><span data-stu-id="8f35d-103">Details</span></span>  
  
|                 |                                                            |
|-----------------|------------------------------------------------------------|
|  <span data-ttu-id="8f35d-104">产品名称</span><span class="sxs-lookup"><span data-stu-id="8f35d-104">Product Name</span></span>   |                 <span data-ttu-id="8f35d-105">企业单一登录</span><span class="sxs-lookup"><span data-stu-id="8f35d-105">Enterprise Single Sign-On</span></span>                  |
| <span data-ttu-id="8f35d-106">产品版本</span><span class="sxs-lookup"><span data-stu-id="8f35d-106">Product Version</span></span> | [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)] |
|    <span data-ttu-id="8f35d-107">事件 ID</span><span class="sxs-lookup"><span data-stu-id="8f35d-107">Event ID</span></span>     |                           <span data-ttu-id="8f35d-108">11063</span><span class="sxs-lookup"><span data-stu-id="8f35d-108">11063</span></span>                            |
|  <span data-ttu-id="8f35d-109">事件源</span><span class="sxs-lookup"><span data-stu-id="8f35d-109">Event Source</span></span>   |                           <span data-ttu-id="8f35d-110">ENTSSO</span><span class="sxs-lookup"><span data-stu-id="8f35d-110">ENTSSO</span></span>                           |
|    <span data-ttu-id="8f35d-111">组件</span><span class="sxs-lookup"><span data-stu-id="8f35d-111">Component</span></span>    |                            <span data-ttu-id="8f35d-112">不可用</span><span class="sxs-lookup"><span data-stu-id="8f35d-112">N/A</span></span>                             |
|  <span data-ttu-id="8f35d-113">符号名称</span><span class="sxs-lookup"><span data-stu-id="8f35d-113">Symbolic Name</span></span>  |          <span data-ttu-id="8f35d-114">SSO_ERROR_PS_MIIS_CALLBACK_ACCESS_DENIED</span><span class="sxs-lookup"><span data-stu-id="8f35d-114">SSO_ERROR_PS_MIIS_CALLBACK_ACCESS_DENIED</span></span>          |
|  <span data-ttu-id="8f35d-115">消息正文</span><span class="sxs-lookup"><span data-stu-id="8f35d-115">Message Text</span></span>   |      <span data-ttu-id="8f35d-116">密码同步服务器 （用于 MIIS) 访问 denied.%r</span><span class="sxs-lookup"><span data-stu-id="8f35d-116">Password sync server (for MIIS) access denied.%r</span></span>      |
  
## <a name="explanation"></a><span data-ttu-id="8f35d-117">解释</span><span class="sxs-lookup"><span data-stu-id="8f35d-117">Explanation</span></span>  
 <span data-ttu-id="8f35d-118">MIIS 回拨访问已被拒绝。</span><span class="sxs-lookup"><span data-stu-id="8f35d-118">MIIS Callback access has been denied.</span></span> <span data-ttu-id="8f35d-119">此错误最可能原因是未能使用 Kerberos 身份验证之间的 ENTSSO 系统和 MIIS。</span><span class="sxs-lookup"><span data-stu-id="8f35d-119">The most likely cause of this error is failure to use the Kerberos authentication between the ENTSSO system and MIIS.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="8f35d-120">用户操作</span><span class="sxs-lookup"><span data-stu-id="8f35d-120">User Action</span></span>  
 <span data-ttu-id="8f35d-121">确认您的 ENTSSO 系统使用 Kerberos 身份验证。</span><span class="sxs-lookup"><span data-stu-id="8f35d-121">Confirm that your ENTSSO system is using Kerberos authentication.</span></span> <span data-ttu-id="8f35d-122">有关详细信息，请参阅[SSO 安全建议](../core/sso-security-recommendations.md)。</span><span class="sxs-lookup"><span data-stu-id="8f35d-122">For more information, see [SSO Security Recommendations](../core/sso-security-recommendations.md).</span></span>