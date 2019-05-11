---
title: 单一登录：Event 10655 | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 1bb6a8dd-35e4-40a6-8900-450a9b6de249
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: d357eaf5433823f8b21f6d6a6757f06c59bdbd9f
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65397639"
---
# <a name="single-sign-on-event-10655"></a><span data-ttu-id="a09fd-102">单一登录：事件 10655</span><span class="sxs-lookup"><span data-stu-id="a09fd-102">Single Sign-On: Event 10655</span></span>
## <a name="details"></a><span data-ttu-id="a09fd-103">详细信息</span><span class="sxs-lookup"><span data-stu-id="a09fd-103">Details</span></span>  

|                 |                                                                              |
|-----------------|------------------------------------------------------------------------------|
|  <span data-ttu-id="a09fd-104">产品名称</span><span class="sxs-lookup"><span data-stu-id="a09fd-104">Product Name</span></span>   |                          <span data-ttu-id="a09fd-105">企业单一登录</span><span class="sxs-lookup"><span data-stu-id="a09fd-105">Enterprise Single Sign-On</span></span>                           |
| <span data-ttu-id="a09fd-106">产品版本</span><span class="sxs-lookup"><span data-stu-id="a09fd-106">Product Version</span></span> |          [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]          |
|    <span data-ttu-id="a09fd-107">事件 ID</span><span class="sxs-lookup"><span data-stu-id="a09fd-107">Event ID</span></span>     |                                    <span data-ttu-id="a09fd-108">10655</span><span class="sxs-lookup"><span data-stu-id="a09fd-108">10655</span></span>                                     |
|  <span data-ttu-id="a09fd-109">事件源</span><span class="sxs-lookup"><span data-stu-id="a09fd-109">Event Source</span></span>   |                                    <span data-ttu-id="a09fd-110">ENTSSO</span><span class="sxs-lookup"><span data-stu-id="a09fd-110">ENTSSO</span></span>                                    |
|    <span data-ttu-id="a09fd-111">组件</span><span class="sxs-lookup"><span data-stu-id="a09fd-111">Component</span></span>    |                                     <span data-ttu-id="a09fd-112">N\A</span><span class="sxs-lookup"><span data-stu-id="a09fd-112">N\A</span></span>                                      |
|  <span data-ttu-id="a09fd-113">符号名称</span><span class="sxs-lookup"><span data-stu-id="a09fd-113">Symbolic Name</span></span>  |                   <span data-ttu-id="a09fd-114">SSO_ERROR_PS_PING_CALLBACK_ACCESS_DENIED</span><span class="sxs-lookup"><span data-stu-id="a09fd-114">SSO_ERROR_PS_PING_CALLBACK_ACCESS_DENIED</span></span>                   |
|  <span data-ttu-id="a09fd-115">消息正文</span><span class="sxs-lookup"><span data-stu-id="a09fd-115">Message Text</span></span>   | <span data-ttu-id="a09fd-116">密码同步服务器 （用于 ping) 访问 denied.%r</span><span class="sxs-lookup"><span data-stu-id="a09fd-116">Password sync server (for ping) access denied.%r</span></span><br /><br /> <span data-ttu-id="a09fd-117">客户端用户： %1</span><span class="sxs-lookup"><span data-stu-id="a09fd-117">Client User: %1</span></span> |

## <a name="explanation"></a><span data-ttu-id="a09fd-118">解释</span><span class="sxs-lookup"><span data-stu-id="a09fd-118">Explanation</span></span>  
 <span data-ttu-id="a09fd-119">此错误事件表示一条消息发送到 [名称] 服务器但回复受到阻止。</span><span class="sxs-lookup"><span data-stu-id="a09fd-119">This Error event indicates that a message was sent to the [name] server but the reply was blocked.</span></span> <span data-ttu-id="a09fd-120">原因可能是多种不同原因，例如协议不正确或服务器上没有足够的安全权限。</span><span class="sxs-lookup"><span data-stu-id="a09fd-120">This can be caused by a number of different reasons, such as incorrect protocol or insufficient security permissions on the server.</span></span>  

## <a name="user-action"></a><span data-ttu-id="a09fd-121">用户操作</span><span class="sxs-lookup"><span data-stu-id="a09fd-121">User Action</span></span>  
 <span data-ttu-id="a09fd-122">若要解决此错误，请执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="a09fd-122">To resolve this error, do the following:</span></span>  

- <span data-ttu-id="a09fd-123">请注意此消息中的信息和事件日志中的任何相关信息，请与 Microsoft 产品支持服务联系。</span><span class="sxs-lookup"><span data-stu-id="a09fd-123">Note the information in this message, and any relevant information in the event log, and contact Microsoft Product Support Services.</span></span>  

  <span data-ttu-id="a09fd-124">有关详细信息，请参阅中的以下资源[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]帮助：</span><span class="sxs-lookup"><span data-stu-id="a09fd-124">For more information, see the following resources in [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Help:</span></span>  

- [<span data-ttu-id="a09fd-125">密码同步</span><span class="sxs-lookup"><span data-stu-id="a09fd-125">Password Synchronization</span></span>](../core/password-synchronization2.md)
