---
title: 单一登录： 事件 10654 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 49372d5a-8136-4bdd-8004-b5736ddbe058
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 6ca59040b340d033ab6c355c0440378f09d87000
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36974478"
---
# <a name="single-sign-on-event-10654"></a><span data-ttu-id="5a17d-102">单一登录： 事件 10654</span><span class="sxs-lookup"><span data-stu-id="5a17d-102">Single Sign-On: Event 10654</span></span>
## <a name="details"></a><span data-ttu-id="5a17d-103">详细信息</span><span class="sxs-lookup"><span data-stu-id="5a17d-103">Details</span></span>  

|                 |                                                            |
|-----------------|------------------------------------------------------------|
|  <span data-ttu-id="5a17d-104">产品名称</span><span class="sxs-lookup"><span data-stu-id="5a17d-104">Product Name</span></span>   |                 <span data-ttu-id="5a17d-105">企业单一登录</span><span class="sxs-lookup"><span data-stu-id="5a17d-105">Enterprise Single Sign-On</span></span>                  |
| <span data-ttu-id="5a17d-106">产品版本</span><span class="sxs-lookup"><span data-stu-id="5a17d-106">Product Version</span></span> | [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)] |
|    <span data-ttu-id="5a17d-107">事件 ID</span><span class="sxs-lookup"><span data-stu-id="5a17d-107">Event ID</span></span>     |                           <span data-ttu-id="5a17d-108">10654</span><span class="sxs-lookup"><span data-stu-id="5a17d-108">10654</span></span>                            |
|  <span data-ttu-id="5a17d-109">事件源</span><span class="sxs-lookup"><span data-stu-id="5a17d-109">Event Source</span></span>   |                           <span data-ttu-id="5a17d-110">ENTSSO</span><span class="sxs-lookup"><span data-stu-id="5a17d-110">ENTSSO</span></span>                           |
|    <span data-ttu-id="5a17d-111">组件</span><span class="sxs-lookup"><span data-stu-id="5a17d-111">Component</span></span>    |                            <span data-ttu-id="5a17d-112">N\A</span><span class="sxs-lookup"><span data-stu-id="5a17d-112">N\A</span></span>                             |
|  <span data-ttu-id="5a17d-113">符号名称</span><span class="sxs-lookup"><span data-stu-id="5a17d-113">Symbolic Name</span></span>  |        <span data-ttu-id="5a17d-114">SSO_ERROR_PS_WINDOWS_CALLBACK_ACCESS_DENIED</span><span class="sxs-lookup"><span data-stu-id="5a17d-114">SSO_ERROR_PS_WINDOWS_CALLBACK_ACCESS_DENIED</span></span>         |
|  <span data-ttu-id="5a17d-115">消息正文</span><span class="sxs-lookup"><span data-stu-id="5a17d-115">Message Text</span></span>   |    <span data-ttu-id="5a17d-116">密码同步服务器 （适用于 Windows) 访问 denied.%r</span><span class="sxs-lookup"><span data-stu-id="5a17d-116">Password sync server (for Windows) access denied.%r</span></span>     |

## <a name="explanation"></a><span data-ttu-id="5a17d-117">解释</span><span class="sxs-lookup"><span data-stu-id="5a17d-117">Explanation</span></span>  
 <span data-ttu-id="5a17d-118">此错误事件表明消息发送到 [名称] 服务器但回复受到阻止。</span><span class="sxs-lookup"><span data-stu-id="5a17d-118">This Error event indicates that a message was sent to the [name] server but the reply was blocked.</span></span> <span data-ttu-id="5a17d-119">此错误可能由许多不同原因导致，如协议不正确或对服务器没有足够的安全权限。</span><span class="sxs-lookup"><span data-stu-id="5a17d-119">This can be caused by a number of different reasons, such as incorrect protocol or insufficient security permissions on the server.</span></span>  

## <a name="user-action"></a><span data-ttu-id="5a17d-120">用户操作</span><span class="sxs-lookup"><span data-stu-id="5a17d-120">User Action</span></span>  
 <span data-ttu-id="5a17d-121">若要解决此错误，请执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="5a17d-121">To resolve this error, do the following:</span></span>  

- <span data-ttu-id="5a17d-122">请注意此消息中的信息和事件日志中的任何相关信息，请与 Microsoft 产品支持服务联系。</span><span class="sxs-lookup"><span data-stu-id="5a17d-122">Note the information in this message, and any relevant information in the event log, and contact Microsoft Product Support Services.</span></span>  

  <span data-ttu-id="5a17d-123">有关详细信息，请参阅 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 帮助中的以下资源：</span><span class="sxs-lookup"><span data-stu-id="5a17d-123">For more information, see the following resources in [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Help:</span></span>  

- [<span data-ttu-id="5a17d-124">密码同步</span><span class="sxs-lookup"><span data-stu-id="5a17d-124">Password Synchronization</span></span>](../core/password-synchronization2.md)
