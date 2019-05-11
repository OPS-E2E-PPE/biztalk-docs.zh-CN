---
title: 收到的 AS2 消息不包含 AS2-To 标头 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 343a9b41-fcd9-4508-ac65-9b6e05ec6496
caps.latest.revision: 11
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f8bee1ee759a8aefb83aa3045808b6ce22689a6a
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65359239"
---
# <a name="an-as2-message-was-received-that-did-not-contain-the-as2-to-header"></a><span data-ttu-id="a2fd2-102">收到的 AS2 消息不包含 AS2-To 标头</span><span class="sxs-lookup"><span data-stu-id="a2fd2-102">An AS2 message was received that did not contain the AS2-To header</span></span>
## <a name="details"></a><span data-ttu-id="a2fd2-103">详细信息</span><span class="sxs-lookup"><span data-stu-id="a2fd2-103">Details</span></span>  
  
|                 |                                                                                        |
|-----------------|----------------------------------------------------------------------------------------|
|  <span data-ttu-id="a2fd2-104">产品名称</span><span class="sxs-lookup"><span data-stu-id="a2fd2-104">Product Name</span></span>   |   [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]   |
| <span data-ttu-id="a2fd2-105">产品版本</span><span class="sxs-lookup"><span data-stu-id="a2fd2-105">Product Version</span></span> |               [!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]               |
|    <span data-ttu-id="a2fd2-106">事件 ID</span><span class="sxs-lookup"><span data-stu-id="a2fd2-106">Event ID</span></span>     |                                           -                                            |
|  <span data-ttu-id="a2fd2-107">事件源</span><span class="sxs-lookup"><span data-stu-id="a2fd2-107">Event Source</span></span>   | [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] <span data-ttu-id="a2fd2-108">EDI</span><span class="sxs-lookup"><span data-stu-id="a2fd2-108">EDI</span></span> |
|    <span data-ttu-id="a2fd2-109">组件</span><span class="sxs-lookup"><span data-stu-id="a2fd2-109">Component</span></span>    |                                       <span data-ttu-id="a2fd2-110">AS2 引擎</span><span class="sxs-lookup"><span data-stu-id="a2fd2-110">AS2 Engine</span></span>                                       |
|  <span data-ttu-id="a2fd2-111">符号名称</span><span class="sxs-lookup"><span data-stu-id="a2fd2-111">Symbolic Name</span></span>  |                                           -                                            |
|  <span data-ttu-id="a2fd2-112">消息正文</span><span class="sxs-lookup"><span data-stu-id="a2fd2-112">Message Text</span></span>   |           <span data-ttu-id="a2fd2-113">收到的 AS2 消息不包含 AS2-To 标头</span><span class="sxs-lookup"><span data-stu-id="a2fd2-113">An AS2 message was received that did not contain the AS2-To header</span></span>           |
  
## <a name="explanation"></a><span data-ttu-id="a2fd2-114">解释</span><span class="sxs-lookup"><span data-stu-id="a2fd2-114">Explanation</span></span>  
 <span data-ttu-id="a2fd2-115">此错误/警告/信息事件表明 BizTalk Server 无法处理传入的 AS2 消息，因为该消息不包含指明消息源的 AS2-To 标头。</span><span class="sxs-lookup"><span data-stu-id="a2fd2-115">This Error/Warning/Information event indicates BizTalk Server could not process the incoming AS2 message because the message did not contain an AS2-To header indicating the source of the message.</span></span> <span data-ttu-id="a2fd2-116">AS2 消息必须有 AS2-To 标头。</span><span class="sxs-lookup"><span data-stu-id="a2fd2-116">An AS2 message must have an AS2-To header.</span></span> <span data-ttu-id="a2fd2-117">如果消息没有 AS2-To 标头，则会挂起该消息。</span><span class="sxs-lookup"><span data-stu-id="a2fd2-117">The message will be suspended if it does not have an AS2-To header.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="a2fd2-118">用户操作</span><span class="sxs-lookup"><span data-stu-id="a2fd2-118">User Action</span></span>  
 <span data-ttu-id="a2fd2-119">若要解决此错误，请执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="a2fd2-119">To resolve this error, do the following:</span></span>  
  
-   <span data-ttu-id="a2fd2-120">确保在发送之前发送参与方向 AS2 消息的 HTTP、AS2 和 MIME 标头中添加 AS2-To 标头。</span><span class="sxs-lookup"><span data-stu-id="a2fd2-120">Ensure the sending party adds an AS2-To header to the HTTP, AS2, and MIME header of the AS2 message before sending it.</span></span>