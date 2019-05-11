---
title: 单一登录：Event 10533 | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 31abd828-5f10-43f7-b99e-f3195250130c
caps.latest.revision: 13
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a0ce83b8d2c7ff6973900088dcb0c0028e31f0e5
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65262313"
---
# <a name="single-sign-on-event-10533"></a><span data-ttu-id="f6183-102">单一登录：事件 10533</span><span class="sxs-lookup"><span data-stu-id="f6183-102">Single Sign-On: Event 10533</span></span>
## <a name="details"></a><span data-ttu-id="f6183-103">详细信息</span><span class="sxs-lookup"><span data-stu-id="f6183-103">Details</span></span>  

|                 |                                                                                                                   |
|-----------------|-------------------------------------------------------------------------------------------------------------------|
|  <span data-ttu-id="f6183-104">产品名称</span><span class="sxs-lookup"><span data-stu-id="f6183-104">Product Name</span></span>   |                                             <span data-ttu-id="f6183-105">企业单一登录</span><span class="sxs-lookup"><span data-stu-id="f6183-105">Enterprise Single Sign-On</span></span>                                             |
| <span data-ttu-id="f6183-106">产品版本</span><span class="sxs-lookup"><span data-stu-id="f6183-106">Product Version</span></span> |                            [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]                             |
|    <span data-ttu-id="f6183-107">事件 ID</span><span class="sxs-lookup"><span data-stu-id="f6183-107">Event ID</span></span>     |                                                       <span data-ttu-id="f6183-108">10533</span><span class="sxs-lookup"><span data-stu-id="f6183-108">10533</span></span>                                                       |
|  <span data-ttu-id="f6183-109">事件源</span><span class="sxs-lookup"><span data-stu-id="f6183-109">Event Source</span></span>   |                                                      <span data-ttu-id="f6183-110">ENTSSO</span><span class="sxs-lookup"><span data-stu-id="f6183-110">ENTSSO</span></span>                                                       |
|    <span data-ttu-id="f6183-111">组件</span><span class="sxs-lookup"><span data-stu-id="f6183-111">Component</span></span>    |                                                        <span data-ttu-id="f6183-112">N\A</span><span class="sxs-lookup"><span data-stu-id="f6183-112">N\A</span></span>                                                        |
|  <span data-ttu-id="f6183-113">符号名称</span><span class="sxs-lookup"><span data-stu-id="f6183-113">Symbolic Name</span></span>  |                                            <span data-ttu-id="f6183-114">SSO_INFO_GOT_CURRENT_SECRET</span><span class="sxs-lookup"><span data-stu-id="f6183-114">SSO_INFO_GOT_CURRENT_SECRET</span></span>                                            |
|  <span data-ttu-id="f6183-115">消息正文</span><span class="sxs-lookup"><span data-stu-id="f6183-115">Message Text</span></span>   | <span data-ttu-id="f6183-116">已从主 server.%r 获得当前密钥</span><span class="sxs-lookup"><span data-stu-id="f6183-116">Got the current secret from the master secret server.%r</span></span><br /><br /> <span data-ttu-id="f6183-117">密钥服务器名称: %1 %r</span><span class="sxs-lookup"><span data-stu-id="f6183-117">Secret Server Name: %1%r</span></span><br /><br /> <span data-ttu-id="f6183-118">MSID: %2</span><span class="sxs-lookup"><span data-stu-id="f6183-118">MSID: %2</span></span> |

## <a name="explanation"></a><span data-ttu-id="f6183-119">解释</span><span class="sxs-lookup"><span data-stu-id="f6183-119">Explanation</span></span>  
 <span data-ttu-id="f6183-120">此信息事件表明 SSO 具有当前的主密钥。</span><span class="sxs-lookup"><span data-stu-id="f6183-120">This Information event indicates that SSO has the current master secret.</span></span>  

## <a name="user-action"></a><span data-ttu-id="f6183-121">用户操作</span><span class="sxs-lookup"><span data-stu-id="f6183-121">User Action</span></span>  

- <span data-ttu-id="f6183-122">不不需要任何用户操作。</span><span class="sxs-lookup"><span data-stu-id="f6183-122">No user action is necessary.</span></span>  

  <span data-ttu-id="f6183-123">有关详细信息，请参阅中的以下资源[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]帮助：</span><span class="sxs-lookup"><span data-stu-id="f6183-123">For more information, see the following resources in [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Help:</span></span>  

- [<span data-ttu-id="f6183-124">如何生成主密钥</span><span class="sxs-lookup"><span data-stu-id="f6183-124">How to Generate the Master Secret</span></span>](../core/how-to-generate-the-master-secret.md)  

- [<span data-ttu-id="f6183-125">管理主密钥</span><span class="sxs-lookup"><span data-stu-id="f6183-125">Managing the Master Secret</span></span>](../core/managing-the-master-secret.md)
