---
title: 单一登录：Event 10517 | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 2b63e4b0-0ef6-45c2-b8b1-55ac20e79e26
caps.latest.revision: 16
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a9febc85f554b8736d75c9315a37214c8a81ca16
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65279804"
---
# <a name="single-sign-on-event-10517"></a><span data-ttu-id="5762b-102">单一登录：事件 10517</span><span class="sxs-lookup"><span data-stu-id="5762b-102">Single Sign-On: Event 10517</span></span>
## <a name="details"></a><span data-ttu-id="5762b-103">详细信息</span><span class="sxs-lookup"><span data-stu-id="5762b-103">Details</span></span>  

|                 |                                                                                                                                                                                                                                                                                                                             |
|-----------------|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|  <span data-ttu-id="5762b-104">产品名称</span><span class="sxs-lookup"><span data-stu-id="5762b-104">Product Name</span></span>   |                                                                                                                                                  <span data-ttu-id="5762b-105">企业单一登录</span><span class="sxs-lookup"><span data-stu-id="5762b-105">Enterprise Single Sign-On</span></span>                                                                                                                                                  |
| <span data-ttu-id="5762b-106">产品版本</span><span class="sxs-lookup"><span data-stu-id="5762b-106">Product Version</span></span> |                                                                                                                                 [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]                                                                                                                                  |
|    <span data-ttu-id="5762b-107">事件 ID</span><span class="sxs-lookup"><span data-stu-id="5762b-107">Event ID</span></span>     |                                                                                                                                                            <span data-ttu-id="5762b-108">10517</span><span class="sxs-lookup"><span data-stu-id="5762b-108">10517</span></span>                                                                                                                                                            |
|  <span data-ttu-id="5762b-109">事件源</span><span class="sxs-lookup"><span data-stu-id="5762b-109">Event Source</span></span>   |                                                                                                                                                           <span data-ttu-id="5762b-110">ENTSSO</span><span class="sxs-lookup"><span data-stu-id="5762b-110">ENTSSO</span></span>                                                                                                                                                            |
|    <span data-ttu-id="5762b-111">组件</span><span class="sxs-lookup"><span data-stu-id="5762b-111">Component</span></span>    |                                                                                                                                                             <span data-ttu-id="5762b-112">N\A</span><span class="sxs-lookup"><span data-stu-id="5762b-112">N\A</span></span>                                                                                                                                                             |
|  <span data-ttu-id="5762b-113">符号名称</span><span class="sxs-lookup"><span data-stu-id="5762b-113">Symbolic Name</span></span>  |                                                                                                                                                   <span data-ttu-id="5762b-114">SSO_ERROR_BAD_SSO_ADMIN</span><span class="sxs-lookup"><span data-stu-id="5762b-114">SSO_ERROR_BAD_SSO_ADMIN</span></span>                                                                                                                                                   |
|  <span data-ttu-id="5762b-115">消息正文</span><span class="sxs-lookup"><span data-stu-id="5762b-115">Message Text</span></span>   | <span data-ttu-id="5762b-116">SSO 管理员帐户不是有效的。</span><span class="sxs-lookup"><span data-stu-id="5762b-116">The SSO Administrators account is not valid.</span></span> <span data-ttu-id="5762b-117">如果它是本地帐户检查服务器上是否存在此帐户。</span><span class="sxs-lookup"><span data-stu-id="5762b-117">If it is a local account check that this account exists on the server.</span></span> <span data-ttu-id="5762b-118">如果是域帐户与域管理员联系。</span><span class="sxs-lookup"><span data-stu-id="5762b-118">If it is a domain account contact your domain administrator.</span></span> <span data-ttu-id="5762b-119">当帐户 valid.%r 时启用 SSO</span><span class="sxs-lookup"><span data-stu-id="5762b-119">Enable SSO when the account is valid.%r</span></span><br /><br /> <span data-ttu-id="5762b-120">SSO Administrators: %1 %r</span><span class="sxs-lookup"><span data-stu-id="5762b-120">SSO Administrators: %1%r</span></span><br /><br /> <span data-ttu-id="5762b-121">无效帐户: %2 %r</span><span class="sxs-lookup"><span data-stu-id="5762b-121">Invalid accounts: %2%r</span></span><br /><br /> <span data-ttu-id="5762b-122">错误代码： %3</span><span class="sxs-lookup"><span data-stu-id="5762b-122">Error Code: %3</span></span> |

## <a name="explanation"></a><span data-ttu-id="5762b-123">解释</span><span class="sxs-lookup"><span data-stu-id="5762b-123">Explanation</span></span>  
 <span data-ttu-id="5762b-124">此错误事件表示 SSO 管理员帐户指定为企业单一登录不是有效的 Windows 帐户。</span><span class="sxs-lookup"><span data-stu-id="5762b-124">This Error event indicates that the SSO Administrators account specified for Enterprise Single Sign-On is not a valid Windows account.</span></span> <span data-ttu-id="5762b-125">运行企业单一登录服务的服务帐户必须是此帐户的成员。</span><span class="sxs-lookup"><span data-stu-id="5762b-125">The service account running the Enterprise Single Sign-On service must be a member of this account.</span></span> <span data-ttu-id="5762b-126">SSO 管理员帐户可以是 Windows 组帐户或个人帐户。</span><span class="sxs-lookup"><span data-stu-id="5762b-126">The SSO Administrators account can be either a Windows group account or an individual account.</span></span> <span data-ttu-id="5762b-127">SSO 管理员帐户也可以是域或本地组帐户。</span><span class="sxs-lookup"><span data-stu-id="5762b-127">The SSO Administrators account can also be either a domain or local group account.</span></span> <span data-ttu-id="5762b-128">如果使用个人帐户，则无法更改此帐户到另一个个人帐户。</span><span class="sxs-lookup"><span data-stu-id="5762b-128">When using an individual account, you cannot change this account to another individual account.</span></span>  

## <a name="user-action"></a><span data-ttu-id="5762b-129">用户操作</span><span class="sxs-lookup"><span data-stu-id="5762b-129">User Action</span></span>  
 <span data-ttu-id="5762b-130">若要解决此错误，请执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="5762b-130">To resolve this error, do the following:</span></span>  

- <span data-ttu-id="5762b-131">验证 SSO 管理员帐户存在。</span><span class="sxs-lookup"><span data-stu-id="5762b-131">Verify the SSO Administrators account exists.</span></span>  

  <span data-ttu-id="5762b-132">有关详细信息，请参阅中的以下资源[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]帮助：</span><span class="sxs-lookup"><span data-stu-id="5762b-132">For more information, see the following resources in [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Help:</span></span>  

- [<span data-ttu-id="5762b-133">SSO 用户组</span><span class="sxs-lookup"><span data-stu-id="5762b-133">SSO User Groups</span></span>](../core/sso-user-groups.md)
