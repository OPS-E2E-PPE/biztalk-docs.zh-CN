---
title: 无效的引用时遇到的 HTTP 标头 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: bb530ee6-ec6a-4791-ae99-b9db426c0896
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 7ca0d7463f4604e8a159c12fab690e494a13fb60
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36971006"
---
# <a name="an-invalid-quoted-http-header-encountered"></a><span data-ttu-id="7bd32-102">遇到无效的引用 HTTP 标头</span><span class="sxs-lookup"><span data-stu-id="7bd32-102">An invalid quoted HTTP header encountered</span></span>
## <a name="details"></a><span data-ttu-id="7bd32-103">详细信息</span><span class="sxs-lookup"><span data-stu-id="7bd32-103">Details</span></span>  
  
|                 |                                                                                                              |
|-----------------|--------------------------------------------------------------------------------------------------------------|
|  <span data-ttu-id="7bd32-104">产品名称</span><span class="sxs-lookup"><span data-stu-id="7bd32-104">Product Name</span></span>   |              [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]              |
| <span data-ttu-id="7bd32-105">产品版本</span><span class="sxs-lookup"><span data-stu-id="7bd32-105">Product Version</span></span> |                          [!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]                          |
|    <span data-ttu-id="7bd32-106">事件 ID</span><span class="sxs-lookup"><span data-stu-id="7bd32-106">Event ID</span></span>     |                                                      -                                                       |
|  <span data-ttu-id="7bd32-107">事件源</span><span class="sxs-lookup"><span data-stu-id="7bd32-107">Event Source</span></span>   |            [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]<span data-ttu-id="7bd32-108"> EDI</span><span class="sxs-lookup"><span data-stu-id="7bd32-108"> EDI</span></span>            |
|    <span data-ttu-id="7bd32-109">组件</span><span class="sxs-lookup"><span data-stu-id="7bd32-109">Component</span></span>    |                                                  <span data-ttu-id="7bd32-110">AS2 引擎</span><span class="sxs-lookup"><span data-stu-id="7bd32-110">AS2 Engine</span></span>                                                  |
|  <span data-ttu-id="7bd32-111">符号名称</span><span class="sxs-lookup"><span data-stu-id="7bd32-111">Symbolic Name</span></span>  |                                                      -                                                       |
|  <span data-ttu-id="7bd32-112">消息正文</span><span class="sxs-lookup"><span data-stu-id="7bd32-112">Message Text</span></span>   | <span data-ttu-id="7bd32-113">遇到无效的引用 HTTP 标头。</span><span class="sxs-lookup"><span data-stu-id="7bd32-113">An invalid quoted HTTP header encountered.</span></span>  <span data-ttu-id="7bd32-114">详细信息如下： 标头名称:"{0}"标头值:"{1}"</span><span class="sxs-lookup"><span data-stu-id="7bd32-114">Details are as follows:  Header Name: "{0}"  Header Value: "{1}"</span></span> |
  
## <a name="explanation"></a><span data-ttu-id="7bd32-115">解释</span><span class="sxs-lookup"><span data-stu-id="7bd32-115">Explanation</span></span>  
 <span data-ttu-id="7bd32-116">此错误/警告/信息事件表明 AS2 接收管道或 AS2 发送管道无法处理 AS2 消息，因为消息中 AS2-From 或 AS2-To HTTP 标头的名称未用引号正确括起来。</span><span class="sxs-lookup"><span data-stu-id="7bd32-116">This Error/Warning/Information event indicates that the AS2 receive pipeline or the AS2 send pipeline could not process the AS2 message because the name of the AS2-From or AS2-To HTTP header in the message was not quoted correctly.</span></span> <span data-ttu-id="7bd32-117">用引号将标头名称括起来以便在名称中包含空格、反斜杠或双引号。</span><span class="sxs-lookup"><span data-stu-id="7bd32-117">The header name is quoted in order to accommodate a space, backslash, or double quotes within the name.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="7bd32-118">用户操作</span><span class="sxs-lookup"><span data-stu-id="7bd32-118">User Action</span></span>  
 <span data-ttu-id="7bd32-119">若要解决此错误，请按照 RFC 4130“MIME-Based Secure Peer-to-Peer Business Data Interchange Using HTTP, Applicability Statement 2 (AS2)（针对使用 HTTP 进行基于 MIME 的安全对等业务数据交换的 Applicability Statement 2 (AS2)）”中第 6.2 节“AS2 系统标识符”中所述的规则用引号将 AS2 消息中的标头名称括起来。</span><span class="sxs-lookup"><span data-stu-id="7bd32-119">To resolve this error, quote the header name in the AS2 message in accordance with the rules stated in section 6.2, "AS2 System Identifiers", in RFC 4130, "MIME-Based Secure Peer-to-Peer Business Data Interchange Using HTTP, Applicability Statement 2 (AS2)".</span></span>