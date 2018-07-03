---
title: 单一登录： 事件 10653 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: a0d85aca-20d9-4d65-8834-b31eacf143c8
caps.latest.revision: 13
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a9f0edb3ce5fa7f8fb59c4b65914a9c8b6640adc
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36969454"
---
# <a name="single-sign-on-event-10653"></a><span data-ttu-id="daf66-102">单一登录： 事件 10653</span><span class="sxs-lookup"><span data-stu-id="daf66-102">Single Sign-On: Event 10653</span></span>
## <a name="details"></a><span data-ttu-id="daf66-103">详细信息</span><span class="sxs-lookup"><span data-stu-id="daf66-103">Details</span></span>  

|                 |                                                            |
|-----------------|------------------------------------------------------------|
|  <span data-ttu-id="daf66-104">产品名称</span><span class="sxs-lookup"><span data-stu-id="daf66-104">Product Name</span></span>   |                 <span data-ttu-id="daf66-105">企业单一登录</span><span class="sxs-lookup"><span data-stu-id="daf66-105">Enterprise Single Sign-On</span></span>                  |
| <span data-ttu-id="daf66-106">产品版本</span><span class="sxs-lookup"><span data-stu-id="daf66-106">Product Version</span></span> | [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)] |
|    <span data-ttu-id="daf66-107">事件 ID</span><span class="sxs-lookup"><span data-stu-id="daf66-107">Event ID</span></span>     |                           <span data-ttu-id="daf66-108">10653</span><span class="sxs-lookup"><span data-stu-id="daf66-108">10653</span></span>                            |
|  <span data-ttu-id="daf66-109">事件源</span><span class="sxs-lookup"><span data-stu-id="daf66-109">Event Source</span></span>   |                           <span data-ttu-id="daf66-110">ENTSSO</span><span class="sxs-lookup"><span data-stu-id="daf66-110">ENTSSO</span></span>                           |
|    <span data-ttu-id="daf66-111">组件</span><span class="sxs-lookup"><span data-stu-id="daf66-111">Component</span></span>    |                            <span data-ttu-id="daf66-112">N\A</span><span class="sxs-lookup"><span data-stu-id="daf66-112">N\A</span></span>                             |
|  <span data-ttu-id="daf66-113">符号名称</span><span class="sxs-lookup"><span data-stu-id="daf66-113">Symbolic Name</span></span>  |        <span data-ttu-id="daf66-114">SSO_ERROR_PS_ADAPTER_CALLBACK_ACCESS_DENIED</span><span class="sxs-lookup"><span data-stu-id="daf66-114">SSO_ERROR_PS_ADAPTER_CALLBACK_ACCESS_DENIED</span></span>         |
|  <span data-ttu-id="daf66-115">消息正文</span><span class="sxs-lookup"><span data-stu-id="daf66-115">Message Text</span></span>   |    <span data-ttu-id="daf66-116">拒绝访问（适用于适配器的）密码同步服务器。%r</span><span class="sxs-lookup"><span data-stu-id="daf66-116">Password sync server (for adapters) access denied.%r</span></span>    |

## <a name="explanation"></a><span data-ttu-id="daf66-117">解释</span><span class="sxs-lookup"><span data-stu-id="daf66-117">Explanation</span></span>  
 <span data-ttu-id="daf66-118">此错误事件表示，客户端尝试与服务器联系，但是调用被拒绝。</span><span class="sxs-lookup"><span data-stu-id="daf66-118">This Error event indicates that a client attempted to contact the server but the call was refused.</span></span> <span data-ttu-id="daf66-119">这可能是由许多不同原因引起的，例如协议不正确或没有足够的安全权限。</span><span class="sxs-lookup"><span data-stu-id="daf66-119">This can be caused by a number of different reasons, such as incorrect protocol or insufficient security permissions.</span></span>  

## <a name="user-action"></a><span data-ttu-id="daf66-120">用户操作</span><span class="sxs-lookup"><span data-stu-id="daf66-120">User Action</span></span>  
 <span data-ttu-id="daf66-121">若要解决此错误，请执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="daf66-121">To resolve this error, do the following:</span></span>  

- <span data-ttu-id="daf66-122">请注意此消息中的信息和事件日志中的任何相关信息，请与 Microsoft 产品支持服务联系。</span><span class="sxs-lookup"><span data-stu-id="daf66-122">Note the information in this message, and any relevant information in the event log, and contact Microsoft Product Support Services.</span></span>  

  <span data-ttu-id="daf66-123">有关详细信息，请参阅 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 帮助中的以下资源：</span><span class="sxs-lookup"><span data-stu-id="daf66-123">For more information, see the following resources in [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Help:</span></span>  

- [<span data-ttu-id="daf66-124">密码同步</span><span class="sxs-lookup"><span data-stu-id="daf66-124">Password Synchronization</span></span>](../core/password-synchronization2.md)
