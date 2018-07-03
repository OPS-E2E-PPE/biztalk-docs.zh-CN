---
title: 单一登录： 事件 10528 |Microsoft Docs
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
ms.openlocfilehash: d2e91944de7399f8bee3e03f3facdb91263d2761
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36974822"
---
# <a name="single-sign-on-event-10528"></a><span data-ttu-id="cdc6f-102">单一登录： 事件 10528</span><span class="sxs-lookup"><span data-stu-id="cdc6f-102">Single Sign-On: Event 10528</span></span>
## <a name="details"></a><span data-ttu-id="cdc6f-103">详细信息</span><span class="sxs-lookup"><span data-stu-id="cdc6f-103">Details</span></span>  

|                 |                                                                                                                                                                            |
|-----------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|  <span data-ttu-id="cdc6f-104">产品名称</span><span class="sxs-lookup"><span data-stu-id="cdc6f-104">Product Name</span></span>   |                                                                         <span data-ttu-id="cdc6f-105">企业单一登录</span><span class="sxs-lookup"><span data-stu-id="cdc6f-105">Enterprise Single Sign-On</span></span>                                                                          |
| <span data-ttu-id="cdc6f-106">产品版本</span><span class="sxs-lookup"><span data-stu-id="cdc6f-106">Product Version</span></span> |                                                         [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]                                                         |
|    <span data-ttu-id="cdc6f-107">事件 ID</span><span class="sxs-lookup"><span data-stu-id="cdc6f-107">Event ID</span></span>     |                                                                                   <span data-ttu-id="cdc6f-108">10528</span><span class="sxs-lookup"><span data-stu-id="cdc6f-108">10528</span></span>                                                                                    |
|  <span data-ttu-id="cdc6f-109">事件源</span><span class="sxs-lookup"><span data-stu-id="cdc6f-109">Event Source</span></span>   |                                                                                   <span data-ttu-id="cdc6f-110">ENTSSO</span><span class="sxs-lookup"><span data-stu-id="cdc6f-110">ENTSSO</span></span>                                                                                   |
|    <span data-ttu-id="cdc6f-111">组件</span><span class="sxs-lookup"><span data-stu-id="cdc6f-111">Component</span></span>    |                                                                                    <span data-ttu-id="cdc6f-112">N\A</span><span class="sxs-lookup"><span data-stu-id="cdc6f-112">N\A</span></span>                                                                                     |
|  <span data-ttu-id="cdc6f-113">符号名称</span><span class="sxs-lookup"><span data-stu-id="cdc6f-113">Symbolic Name</span></span>  |                                                                           <span data-ttu-id="cdc6f-114">SSO_INFO_REENCRYPT_OK</span><span class="sxs-lookup"><span data-stu-id="cdc6f-114">SSO_INFO_REENCRYPT_OK</span></span>                                                                            |
|  <span data-ttu-id="cdc6f-115">消息正文</span><span class="sxs-lookup"><span data-stu-id="cdc6f-115">Message Text</span></span>   | <span data-ttu-id="cdc6f-116">已成功完成 SSO 数据库重新加密。%r</span><span class="sxs-lookup"><span data-stu-id="cdc6f-116">SSO database re-encryption has completed successfully.%r</span></span><br /><br /> <span data-ttu-id="cdc6f-117">重新加密的凭据数: %1 %r</span><span class="sxs-lookup"><span data-stu-id="cdc6f-117">Number of Credentials re-encrypted: %1%r</span></span><br /><br /> <span data-ttu-id="cdc6f-118">当前 MSID: %2 %r</span><span class="sxs-lookup"><span data-stu-id="cdc6f-118">Current MSID: %2%r</span></span><br /><br /> <span data-ttu-id="cdc6f-119">上一个 MSID: %3</span><span class="sxs-lookup"><span data-stu-id="cdc6f-119">Previous MSID: %3</span></span> |

## <a name="explanation"></a><span data-ttu-id="cdc6f-120">解释</span><span class="sxs-lookup"><span data-stu-id="cdc6f-120">Explanation</span></span>  
 <span data-ttu-id="cdc6f-121">此信息性事件表示 SSO 数据库的重新加密已经成功完成。</span><span class="sxs-lookup"><span data-stu-id="cdc6f-121">This Information event indicates that re-encryption of the SSO database has completed successfully.</span></span>  

## <a name="user-action"></a><span data-ttu-id="cdc6f-122">用户操作</span><span class="sxs-lookup"><span data-stu-id="cdc6f-122">User Action</span></span>  

- <span data-ttu-id="cdc6f-123">不需要用户进行任何操作。</span><span class="sxs-lookup"><span data-stu-id="cdc6f-123">No user action is necessary.</span></span>  

  <span data-ttu-id="cdc6f-124">有关详细信息，请参阅 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 帮助中的以下资源：</span><span class="sxs-lookup"><span data-stu-id="cdc6f-124">For more information, see the following resources in [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Help:</span></span>  

- [<span data-ttu-id="cdc6f-125">如何更新 SSO 数据库</span><span class="sxs-lookup"><span data-stu-id="cdc6f-125">How to Update the SSO Database</span></span>](../core/how-to-update-the-sso-database.md)  

- [<span data-ttu-id="cdc6f-126">如何显示 SSO 数据库信息</span><span class="sxs-lookup"><span data-stu-id="cdc6f-126">How to Display the SSO Database Information</span></span>](../core/how-to-display-the-sso-database-information.md)
