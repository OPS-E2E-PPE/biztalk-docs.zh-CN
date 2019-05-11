---
title: 收到的 AS2 消息不包含 AS2-From 标头 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 899f9b21-b321-49a3-84bd-a5410c883968
caps.latest.revision: 11
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a8ef67be41cc161921b6bd973cb17c6eacba103d
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65360317"
---
# <a name="an-as2-message-was-received-that-did-not-contain-the-as2-from-header"></a><span data-ttu-id="5acd4-102">收到的 AS2 消息不包含 AS2-From 标头</span><span class="sxs-lookup"><span data-stu-id="5acd4-102">An AS2 message was received that did not contain the AS2-From header</span></span>
## <a name="details"></a><span data-ttu-id="5acd4-103">详细信息</span><span class="sxs-lookup"><span data-stu-id="5acd4-103">Details</span></span>  
  
|                 |                                                                                        |
|-----------------|----------------------------------------------------------------------------------------|
|  <span data-ttu-id="5acd4-104">产品名称</span><span class="sxs-lookup"><span data-stu-id="5acd4-104">Product Name</span></span>   |   [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]   |
| <span data-ttu-id="5acd4-105">产品版本</span><span class="sxs-lookup"><span data-stu-id="5acd4-105">Product Version</span></span> |               [!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]               |
|    <span data-ttu-id="5acd4-106">事件 ID</span><span class="sxs-lookup"><span data-stu-id="5acd4-106">Event ID</span></span>     |                                           -                                            |
|  <span data-ttu-id="5acd4-107">事件源</span><span class="sxs-lookup"><span data-stu-id="5acd4-107">Event Source</span></span>   | [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] <span data-ttu-id="5acd4-108">EDI</span><span class="sxs-lookup"><span data-stu-id="5acd4-108">EDI</span></span> |
|    <span data-ttu-id="5acd4-109">组件</span><span class="sxs-lookup"><span data-stu-id="5acd4-109">Component</span></span>    |                                       <span data-ttu-id="5acd4-110">AS2 引擎</span><span class="sxs-lookup"><span data-stu-id="5acd4-110">AS2 Engine</span></span>                                       |
|  <span data-ttu-id="5acd4-111">符号名称</span><span class="sxs-lookup"><span data-stu-id="5acd4-111">Symbolic Name</span></span>  |                                           -                                            |
|  <span data-ttu-id="5acd4-112">消息正文</span><span class="sxs-lookup"><span data-stu-id="5acd4-112">Message Text</span></span>   |          <span data-ttu-id="5acd4-113">收到的 AS2 消息不包含 AS2-From 标头</span><span class="sxs-lookup"><span data-stu-id="5acd4-113">An AS2 message was received that did not contain the AS2-From header</span></span>          |
  
## <a name="explanation"></a><span data-ttu-id="5acd4-114">解释</span><span class="sxs-lookup"><span data-stu-id="5acd4-114">Explanation</span></span>  
 <span data-ttu-id="5acd4-115">此错误/警告/信息事件表明 BizTalk Server 无法处理传入的 AS2 消息，因为该消息不包含指明消息源的 AS2-From 标头。</span><span class="sxs-lookup"><span data-stu-id="5acd4-115">This Error/Warning/Information event indicates BizTalk Server could not process the incoming AS2 message because the message did not contain an AS2-From header indicating the source of the message.</span></span> <span data-ttu-id="5acd4-116">AS2 消息必须有 AS2-From 标头。</span><span class="sxs-lookup"><span data-stu-id="5acd4-116">An AS2 message must have an AS2-From header.</span></span> <span data-ttu-id="5acd4-117">如果消息没有 AS2-From 标头，则会挂起该消息。</span><span class="sxs-lookup"><span data-stu-id="5acd4-117">The message will be suspended if it does not have an AS2-From header.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="5acd4-118">用户操作</span><span class="sxs-lookup"><span data-stu-id="5acd4-118">User Action</span></span>  
 <span data-ttu-id="5acd4-119">若要解决此错误，请执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="5acd4-119">To resolve this error, do the following:</span></span>  
  
-   <span data-ttu-id="5acd4-120">确保在发送之前发送参与方向 AS2 消息的 HTTP、AS2 和 MIME 标头中添加 AS2-To 标头。</span><span class="sxs-lookup"><span data-stu-id="5acd4-120">Ensure the sending party adds an AS2-To header to the HTTP, AS2, and MIME header of the AS2 message before sending it.</span></span>