---
title: 单一登录：Event 10528 | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: d96c1645-70f4-4d15-a0d7-0ae37669ad2a
caps.latest.revision: 12
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f7e39b0c781b417bcf8eca635e9a47b1fd2f2b18
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65262383"
---
# <a name="single-sign-on-event-10528"></a><span data-ttu-id="684e0-102">单一登录：事件 10528</span><span class="sxs-lookup"><span data-stu-id="684e0-102">Single Sign-On: Event 10528</span></span>
## <a name="details"></a><span data-ttu-id="684e0-103">详细信息</span><span class="sxs-lookup"><span data-stu-id="684e0-103">Details</span></span>  

|                 |                                                                                                                                                                            |
|-----------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|  <span data-ttu-id="684e0-104">产品名称</span><span class="sxs-lookup"><span data-stu-id="684e0-104">Product Name</span></span>   |                                                                         <span data-ttu-id="684e0-105">企业单一登录</span><span class="sxs-lookup"><span data-stu-id="684e0-105">Enterprise Single Sign-On</span></span>                                                                          |
| <span data-ttu-id="684e0-106">产品版本</span><span class="sxs-lookup"><span data-stu-id="684e0-106">Product Version</span></span> |                                                         [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]                                                         |
|    <span data-ttu-id="684e0-107">事件 ID</span><span class="sxs-lookup"><span data-stu-id="684e0-107">Event ID</span></span>     |                                                                                   <span data-ttu-id="684e0-108">10528</span><span class="sxs-lookup"><span data-stu-id="684e0-108">10528</span></span>                                                                                    |
|  <span data-ttu-id="684e0-109">事件源</span><span class="sxs-lookup"><span data-stu-id="684e0-109">Event Source</span></span>   |                                                                                   <span data-ttu-id="684e0-110">ENTSSO</span><span class="sxs-lookup"><span data-stu-id="684e0-110">ENTSSO</span></span>                                                                                   |
|    <span data-ttu-id="684e0-111">组件</span><span class="sxs-lookup"><span data-stu-id="684e0-111">Component</span></span>    |                                                                                    <span data-ttu-id="684e0-112">N\A</span><span class="sxs-lookup"><span data-stu-id="684e0-112">N\A</span></span>                                                                                     |
|  <span data-ttu-id="684e0-113">符号名称</span><span class="sxs-lookup"><span data-stu-id="684e0-113">Symbolic Name</span></span>  |                                                                           <span data-ttu-id="684e0-114">SSO_INFO_REENCRYPT_OK</span><span class="sxs-lookup"><span data-stu-id="684e0-114">SSO_INFO_REENCRYPT_OK</span></span>                                                                            |
|  <span data-ttu-id="684e0-115">消息正文</span><span class="sxs-lookup"><span data-stu-id="684e0-115">Message Text</span></span>   | <span data-ttu-id="684e0-116">SSO 数据库重新加密已 successfully.%r 完成</span><span class="sxs-lookup"><span data-stu-id="684e0-116">SSO database re-encryption has completed successfully.%r</span></span><br /><br /> <span data-ttu-id="684e0-117">重新加密的凭据数: %1 %r</span><span class="sxs-lookup"><span data-stu-id="684e0-117">Number of Credentials re-encrypted: %1%r</span></span><br /><br /> <span data-ttu-id="684e0-118">当前 MSID: %2 %r</span><span class="sxs-lookup"><span data-stu-id="684e0-118">Current MSID: %2%r</span></span><br /><br /> <span data-ttu-id="684e0-119">上一个 MSID: %3</span><span class="sxs-lookup"><span data-stu-id="684e0-119">Previous MSID: %3</span></span> |

## <a name="explanation"></a><span data-ttu-id="684e0-120">解释</span><span class="sxs-lookup"><span data-stu-id="684e0-120">Explanation</span></span>  
 <span data-ttu-id="684e0-121">此信息事件表明该重新加密的 SSO 数据库已成功完成。</span><span class="sxs-lookup"><span data-stu-id="684e0-121">This Information event indicates that re-encryption of the SSO database has completed successfully.</span></span>  

## <a name="user-action"></a><span data-ttu-id="684e0-122">用户操作</span><span class="sxs-lookup"><span data-stu-id="684e0-122">User Action</span></span>  

- <span data-ttu-id="684e0-123">不不需要任何用户操作。</span><span class="sxs-lookup"><span data-stu-id="684e0-123">No user action is necessary.</span></span>  

  <span data-ttu-id="684e0-124">有关详细信息，请参阅中的以下资源[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]帮助：</span><span class="sxs-lookup"><span data-stu-id="684e0-124">For more information, see the following resources in [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Help:</span></span>  

- [<span data-ttu-id="684e0-125">如何更新 SSO 数据库</span><span class="sxs-lookup"><span data-stu-id="684e0-125">How to Update the SSO Database</span></span>](../core/how-to-update-the-sso-database.md)  

- [<span data-ttu-id="684e0-126">如何显示 SSO 数据库信息</span><span class="sxs-lookup"><span data-stu-id="684e0-126">How to Display the SSO Database Information</span></span>](../core/how-to-display-the-sso-database-information.md)
