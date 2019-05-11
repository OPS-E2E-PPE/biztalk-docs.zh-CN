---
title: 单一登录：Event 10530 | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 4bb37305-26fe-46a7-958d-3ed7f6876a7b
caps.latest.revision: 12
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ccdea8c120bba407f22f24f28afd425768ff24b3
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65262393"
---
# <a name="single-sign-on-event-10530"></a><span data-ttu-id="64470-102">单一登录：事件 10530</span><span class="sxs-lookup"><span data-stu-id="64470-102">Single Sign-On: Event 10530</span></span>
## <a name="details"></a><span data-ttu-id="64470-103">详细信息</span><span class="sxs-lookup"><span data-stu-id="64470-103">Details</span></span>  

|                 |                                                                                                                    |
|-----------------|--------------------------------------------------------------------------------------------------------------------|
|  <span data-ttu-id="64470-104">产品名称</span><span class="sxs-lookup"><span data-stu-id="64470-104">Product Name</span></span>   |                                             <span data-ttu-id="64470-105">企业单一登录</span><span class="sxs-lookup"><span data-stu-id="64470-105">Enterprise Single Sign-On</span></span>                                              |
| <span data-ttu-id="64470-106">产品版本</span><span class="sxs-lookup"><span data-stu-id="64470-106">Product Version</span></span> |                             [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]                             |
|    <span data-ttu-id="64470-107">事件 ID</span><span class="sxs-lookup"><span data-stu-id="64470-107">Event ID</span></span>     |                                                       <span data-ttu-id="64470-108">10530</span><span class="sxs-lookup"><span data-stu-id="64470-108">10530</span></span>                                                        |
|  <span data-ttu-id="64470-109">事件源</span><span class="sxs-lookup"><span data-stu-id="64470-109">Event Source</span></span>   |                                                       <span data-ttu-id="64470-110">ENTSSO</span><span class="sxs-lookup"><span data-stu-id="64470-110">ENTSSO</span></span>                                                       |
|    <span data-ttu-id="64470-111">组件</span><span class="sxs-lookup"><span data-stu-id="64470-111">Component</span></span>    |                                                        <span data-ttu-id="64470-112">N\A</span><span class="sxs-lookup"><span data-stu-id="64470-112">N\A</span></span>                                                         |
|  <span data-ttu-id="64470-113">符号名称</span><span class="sxs-lookup"><span data-stu-id="64470-113">Symbolic Name</span></span>  |                                            <span data-ttu-id="64470-114">SSO_INFO_GOT_PREVIOUS_SECRET</span><span class="sxs-lookup"><span data-stu-id="64470-114">SSO_INFO_GOT_PREVIOUS_SECRET</span></span>                                            |
|  <span data-ttu-id="64470-115">消息正文</span><span class="sxs-lookup"><span data-stu-id="64470-115">Message Text</span></span>   | <span data-ttu-id="64470-116">从主 server.%r 获取以前的密钥</span><span class="sxs-lookup"><span data-stu-id="64470-116">Got the previous secret from the master secret server.%r</span></span><br /><br /> <span data-ttu-id="64470-117">密钥服务器名称: %1 %r</span><span class="sxs-lookup"><span data-stu-id="64470-117">Secret Server Name: %1%r</span></span><br /><br /> <span data-ttu-id="64470-118">MSID: %2</span><span class="sxs-lookup"><span data-stu-id="64470-118">MSID: %2</span></span> |

## <a name="explanation"></a><span data-ttu-id="64470-119">解释</span><span class="sxs-lookup"><span data-stu-id="64470-119">Explanation</span></span>  
 <span data-ttu-id="64470-120">此信息事件表明 SSO 具有之前的主密钥。</span><span class="sxs-lookup"><span data-stu-id="64470-120">This Information event indicates that SSO has the previous master secret.</span></span>  

## <a name="user-action"></a><span data-ttu-id="64470-121">用户操作</span><span class="sxs-lookup"><span data-stu-id="64470-121">User Action</span></span>  

- <span data-ttu-id="64470-122">不不需要任何用户操作。</span><span class="sxs-lookup"><span data-stu-id="64470-122">No user action is necessary.</span></span>  

  <span data-ttu-id="64470-123">有关详细信息，请参阅中的以下资源[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]帮助：</span><span class="sxs-lookup"><span data-stu-id="64470-123">For more information, see the following resources in [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Help:</span></span>  

- [<span data-ttu-id="64470-124">如何生成主密钥</span><span class="sxs-lookup"><span data-stu-id="64470-124">How to Generate the Master Secret</span></span>](../core/how-to-generate-the-master-secret.md)  

- [<span data-ttu-id="64470-125">管理主密钥</span><span class="sxs-lookup"><span data-stu-id="64470-125">Managing the Master Secret</span></span>](../core/managing-the-master-secret.md)
