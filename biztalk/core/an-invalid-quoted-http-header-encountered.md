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
ms.openlocfilehash: ff1372dc2eea57843d6d671e617aeeb2b8e90dea
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65359340"
---
# <a name="an-invalid-quoted-http-header-encountered"></a><span data-ttu-id="8e81f-102">无效的引用 HTTP 标头时遇到</span><span class="sxs-lookup"><span data-stu-id="8e81f-102">An invalid quoted HTTP header encountered</span></span>
## <a name="details"></a><span data-ttu-id="8e81f-103">详细信息</span><span class="sxs-lookup"><span data-stu-id="8e81f-103">Details</span></span>  
  
|                 |                                                                                                              |
|-----------------|--------------------------------------------------------------------------------------------------------------|
|  <span data-ttu-id="8e81f-104">产品名称</span><span class="sxs-lookup"><span data-stu-id="8e81f-104">Product Name</span></span>   |              [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]              |
| <span data-ttu-id="8e81f-105">产品版本</span><span class="sxs-lookup"><span data-stu-id="8e81f-105">Product Version</span></span> |                          [!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]                          |
|    <span data-ttu-id="8e81f-106">事件 ID</span><span class="sxs-lookup"><span data-stu-id="8e81f-106">Event ID</span></span>     |                                                      -                                                       |
|  <span data-ttu-id="8e81f-107">事件源</span><span class="sxs-lookup"><span data-stu-id="8e81f-107">Event Source</span></span>   |            [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] <span data-ttu-id="8e81f-108">EDI</span><span class="sxs-lookup"><span data-stu-id="8e81f-108">EDI</span></span>            |
|    <span data-ttu-id="8e81f-109">组件</span><span class="sxs-lookup"><span data-stu-id="8e81f-109">Component</span></span>    |                                                  <span data-ttu-id="8e81f-110">AS2 引擎</span><span class="sxs-lookup"><span data-stu-id="8e81f-110">AS2 Engine</span></span>                                                  |
|  <span data-ttu-id="8e81f-111">符号名称</span><span class="sxs-lookup"><span data-stu-id="8e81f-111">Symbolic Name</span></span>  |                                                      -                                                       |
|  <span data-ttu-id="8e81f-112">消息正文</span><span class="sxs-lookup"><span data-stu-id="8e81f-112">Message Text</span></span>   | <span data-ttu-id="8e81f-113">无效的引用时遇到的 HTTP 标头。</span><span class="sxs-lookup"><span data-stu-id="8e81f-113">An invalid quoted HTTP header encountered.</span></span>  <span data-ttu-id="8e81f-114">详细信息如下所示：标头名称:"{0}"标头值:"{1}"</span><span class="sxs-lookup"><span data-stu-id="8e81f-114">Details are as follows:  Header Name: "{0}"  Header Value: "{1}"</span></span> |
  
## <a name="explanation"></a><span data-ttu-id="8e81f-115">解释</span><span class="sxs-lookup"><span data-stu-id="8e81f-115">Explanation</span></span>  
 <span data-ttu-id="8e81f-116">此错误/警告/信息事件表明 AS2 接收管道或 AS2 发送管道无法处理 AS2 消息，因为 AS2 的名称-从或 AS2-To HTTP 标头消息中的不带引号正确。</span><span class="sxs-lookup"><span data-stu-id="8e81f-116">This Error/Warning/Information event indicates that the AS2 receive pipeline or the AS2 send pipeline could not process the AS2 message because the name of the AS2-From or AS2-To HTTP header in the message was not quoted correctly.</span></span> <span data-ttu-id="8e81f-117">标头名称是以适应一个空格、 反斜杠或在名称中的双引号引起来。</span><span class="sxs-lookup"><span data-stu-id="8e81f-117">The header name is quoted in order to accommodate a space, backslash, or double quotes within the name.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="8e81f-118">用户操作</span><span class="sxs-lookup"><span data-stu-id="8e81f-118">User Action</span></span>  
 <span data-ttu-id="8e81f-119">若要解决此错误，引号中的规则的 AS2 消息的标头名称中所述在 RFC 4130 第 6.2，"AS2 系统标识符"节"基于 MIME 的安全对等业务数据交换使用 HTTP，Applicability Statement 2 (AS2)"。</span><span class="sxs-lookup"><span data-stu-id="8e81f-119">To resolve this error, quote the header name in the AS2 message in accordance with the rules stated in section 6.2, "AS2 System Identifiers", in RFC 4130, "MIME-Based Secure Peer-to-Peer Business Data Interchange Using HTTP, Applicability Statement 2 (AS2)".</span></span>