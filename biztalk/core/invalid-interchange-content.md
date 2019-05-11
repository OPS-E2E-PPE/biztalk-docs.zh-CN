---
title: 交换内容无效 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 6b2352c3-d233-4d79-be31-b32dde29c8ee
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 320715ee685b60284d710510521fc7599db22f87
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65381278"
---
# <a name="invalid-interchange-content"></a><span data-ttu-id="629d7-102">交换内容无效</span><span class="sxs-lookup"><span data-stu-id="629d7-102">Invalid Interchange Content</span></span>
## <a name="details"></a><span data-ttu-id="629d7-103">详细信息</span><span class="sxs-lookup"><span data-stu-id="629d7-103">Details</span></span>  
  
|                 |                                                                                        |
|-----------------|----------------------------------------------------------------------------------------|
|  <span data-ttu-id="629d7-104">产品名称</span><span class="sxs-lookup"><span data-stu-id="629d7-104">Product Name</span></span>   |   [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]   |
| <span data-ttu-id="629d7-105">产品版本</span><span class="sxs-lookup"><span data-stu-id="629d7-105">Product Version</span></span> |               [!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]               |
|    <span data-ttu-id="629d7-106">事件 ID</span><span class="sxs-lookup"><span data-stu-id="629d7-106">Event ID</span></span>     |                                           -                                            |
|  <span data-ttu-id="629d7-107">事件源</span><span class="sxs-lookup"><span data-stu-id="629d7-107">Event Source</span></span>   | [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] <span data-ttu-id="629d7-108">EDI</span><span class="sxs-lookup"><span data-stu-id="629d7-108">EDI</span></span> |
|    <span data-ttu-id="629d7-109">组件</span><span class="sxs-lookup"><span data-stu-id="629d7-109">Component</span></span>    |                                       <span data-ttu-id="629d7-110">EDI 引擎</span><span class="sxs-lookup"><span data-stu-id="629d7-110">EDI Engine</span></span>                                       |
|  <span data-ttu-id="629d7-111">符号名称</span><span class="sxs-lookup"><span data-stu-id="629d7-111">Symbolic Name</span></span>  |                       <span data-ttu-id="629d7-112">X12Ta1InvalidInterchangeContentDescription</span><span class="sxs-lookup"><span data-stu-id="629d7-112">X12Ta1InvalidInterchangeContentDescription</span></span>                       |
|  <span data-ttu-id="629d7-113">消息正文</span><span class="sxs-lookup"><span data-stu-id="629d7-113">Message Text</span></span>   |                              <span data-ttu-id="629d7-114">交换内容无效</span><span class="sxs-lookup"><span data-stu-id="629d7-114">Invalid Interchange Content</span></span>                               |
  
## <a name="explanation"></a><span data-ttu-id="629d7-115">解释</span><span class="sxs-lookup"><span data-stu-id="629d7-115">Explanation</span></span>  
 <span data-ttu-id="629d7-116">此错误/警告/信息事件表明接收管道无法处理传入的交换或发送管道无法处理传出的交换，因为交换中的数据未通过由执行消息验证BizTalk Server。</span><span class="sxs-lookup"><span data-stu-id="629d7-116">This Error/Warning/Information event indicates that the receive pipeline could not process the incoming interchange or the send pipeline could not process the outgoing interchange because the data in the interchange did not pass message validation performed by BizTalk Server.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="629d7-117">用户操作</span><span class="sxs-lookup"><span data-stu-id="629d7-117">User Action</span></span>  
 <span data-ttu-id="629d7-118">若要解决此错误，请标识交换的哪个部分未通过验证和未通过哪个验证。</span><span class="sxs-lookup"><span data-stu-id="629d7-118">To resolve this error, identify which part of the interchange failed validation, and which validation it failed.</span></span> <span data-ttu-id="629d7-119">解决造成验证失败，此问题，然后重新发送交换。</span><span class="sxs-lookup"><span data-stu-id="629d7-119">Resolve the issue that caused validation to fail, and then have the interchange resent.</span></span>