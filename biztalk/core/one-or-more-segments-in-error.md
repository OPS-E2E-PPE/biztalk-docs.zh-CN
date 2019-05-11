---
title: 一个或多个段出错 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 4ee86667-e72a-4f1b-8d5c-15ca710dbe5d
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 17af00eb0347a1654feafd59046596741829b9b0
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65323410"
---
# <a name="one-or-more-segments-in-error"></a><span data-ttu-id="ab597-102">有一个或多个段出错</span><span class="sxs-lookup"><span data-stu-id="ab597-102">One or more segments in error</span></span>
## <a name="details"></a><span data-ttu-id="ab597-103">详细信息</span><span class="sxs-lookup"><span data-stu-id="ab597-103">Details</span></span>  
  
|                 |                                                                                        |
|-----------------|----------------------------------------------------------------------------------------|
|  <span data-ttu-id="ab597-104">产品名称</span><span class="sxs-lookup"><span data-stu-id="ab597-104">Product Name</span></span>   |   [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]   |
| <span data-ttu-id="ab597-105">产品版本</span><span class="sxs-lookup"><span data-stu-id="ab597-105">Product Version</span></span> |               [!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]               |
|    <span data-ttu-id="ab597-106">事件 ID</span><span class="sxs-lookup"><span data-stu-id="ab597-106">Event ID</span></span>     |                                           -                                            |
|  <span data-ttu-id="ab597-107">事件源</span><span class="sxs-lookup"><span data-stu-id="ab597-107">Event Source</span></span>   | [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] <span data-ttu-id="ab597-108">EDI</span><span class="sxs-lookup"><span data-stu-id="ab597-108">EDI</span></span> |
|    <span data-ttu-id="ab597-109">组件</span><span class="sxs-lookup"><span data-stu-id="ab597-109">Component</span></span>    |                                       <span data-ttu-id="ab597-110">EDI 引擎</span><span class="sxs-lookup"><span data-stu-id="ab597-110">EDI Engine</span></span>                                       |
|  <span data-ttu-id="ab597-111">符号名称</span><span class="sxs-lookup"><span data-stu-id="ab597-111">Symbolic Name</span></span>  |                        <span data-ttu-id="ab597-112">X12TsOneOrMoreSegmentsInErrorDescription</span><span class="sxs-lookup"><span data-stu-id="ab597-112">X12TsOneOrMoreSegmentsInErrorDescription</span></span>                        |
|  <span data-ttu-id="ab597-113">消息正文</span><span class="sxs-lookup"><span data-stu-id="ab597-113">Message Text</span></span>   |                             <span data-ttu-id="ab597-114">有一个或多个段出错</span><span class="sxs-lookup"><span data-stu-id="ab597-114">One or more segments in error</span></span>                              |
  
## <a name="explanation"></a><span data-ttu-id="ab597-115">解释</span><span class="sxs-lookup"><span data-stu-id="ab597-115">Explanation</span></span>  
 <span data-ttu-id="ab597-116">此错误/警告/信息事件表明交换中的一个或多个段不符合管理它们的架构。</span><span class="sxs-lookup"><span data-stu-id="ab597-116">This Error/Warning/Information event indicates that one or more segments in the interchange did not conform to the schema governing them.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="ab597-117">用户操作</span><span class="sxs-lookup"><span data-stu-id="ab597-117">User Action</span></span>  
 <span data-ttu-id="ab597-118">若要解决此错误，请确定哪个段有错误，打开管理该段的架构，并通过该架构确定该段出错的原因。</span><span class="sxs-lookup"><span data-stu-id="ab597-118">To resolve this error, determine which segment is in error, open the schema governing that segment, and determine from that schema why the segment is in error.</span></span>