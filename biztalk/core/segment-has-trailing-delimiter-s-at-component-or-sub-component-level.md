---
title: 段具有在组件或子组件级别的尾随 delimiter(s) |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 517f1cfc-66c1-47e6-be94-2c76c1f89230
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 3eede2923da1ed206a897b879b7b6be589800e4c
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22269661"
---
# <a name="segment-has-trailing-delimiters-at-component-or-sub-component-level"></a><span data-ttu-id="0c715-102">段在组件或子组件级别上具有尾部分隔符</span><span class="sxs-lookup"><span data-stu-id="0c715-102">Segment has trailing delimiter(s) at component or sub-component level</span></span>
## <a name="details"></a><span data-ttu-id="0c715-103">详细信息</span><span class="sxs-lookup"><span data-stu-id="0c715-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="0c715-104">产品名称</span><span class="sxs-lookup"><span data-stu-id="0c715-104">Product Name</span></span>|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]|  
|<span data-ttu-id="0c715-105">产品版本</span><span class="sxs-lookup"><span data-stu-id="0c715-105">Product Version</span></span>|[!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]|  
|<span data-ttu-id="0c715-106">事件 ID</span><span class="sxs-lookup"><span data-stu-id="0c715-106">Event ID</span></span>|-|  
|<span data-ttu-id="0c715-107">事件源</span><span class="sxs-lookup"><span data-stu-id="0c715-107">Event Source</span></span>|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]<span data-ttu-id="0c715-108"> EDI</span><span class="sxs-lookup"><span data-stu-id="0c715-108"> EDI</span></span>|  
|<span data-ttu-id="0c715-109">组件</span><span class="sxs-lookup"><span data-stu-id="0c715-109">Component</span></span>|<span data-ttu-id="0c715-110">EDI 引擎</span><span class="sxs-lookup"><span data-stu-id="0c715-110">EDI Engine</span></span>|  
|<span data-ttu-id="0c715-111">符号名称</span><span class="sxs-lookup"><span data-stu-id="0c715-111">Symbolic Name</span></span>|<span data-ttu-id="0c715-112">X12SeSegmentHasTrailingDelimiterDescription</span><span class="sxs-lookup"><span data-stu-id="0c715-112">X12SeSegmentHasTrailingDelimiterDescription</span></span>|  
|<span data-ttu-id="0c715-113">消息正文</span><span class="sxs-lookup"><span data-stu-id="0c715-113">Message Text</span></span>|<span data-ttu-id="0c715-114">段在组件或子组件级别上具有尾部分隔符</span><span class="sxs-lookup"><span data-stu-id="0c715-114">Segment has trailing delimiter(s) at component or sub-component level</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="0c715-115">解释</span><span class="sxs-lookup"><span data-stu-id="0c715-115">Explanation</span></span>  
 <span data-ttu-id="0c715-116">此错误/警告/信息事件表明接收管道无法处理传入的交换，因为该交换包含尾部分隔符，但没有为“作为交换发送方的参与方”启用尾部分隔符。</span><span class="sxs-lookup"><span data-stu-id="0c715-116">This Error/Warning/Information event indicates that the receive pipeline could not process the incoming interchange because the interchange contained trailing delimiters, but trailing delimiters were not enabled for the party as interchange sender.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="0c715-117">用户操作</span><span class="sxs-lookup"><span data-stu-id="0c715-117">User Action</span></span>  
 <span data-ttu-id="0c715-118">若要解决此错误，请按照如下方式启用尾部分隔符：</span><span class="sxs-lookup"><span data-stu-id="0c715-118">To resolve this error, enable trailing separators as follows:</span></span>  
  
1.  <span data-ttu-id="0c715-119">打开 BizTalk Server 管理控制台，移动到“参与方”文件夹，打开该参与方的“EDI 属性”。</span><span class="sxs-lookup"><span data-stu-id="0c715-119">Open the BizTalk Server Administration Console, move to the Parties folder, and open the EDI Properties for the party.</span></span>  
  
2.  <span data-ttu-id="0c715-120">对于 X12 或 EDIFACT，根据需要移动到“验证和 ACK 生成”页。</span><span class="sxs-lookup"><span data-stu-id="0c715-120">Move to the Validation and ACK Generation page for X12 or EDIFACT, as appropriate.</span></span>  
  
3.  <span data-ttu-id="0c715-121">单击“允许尾部分隔符”。</span><span class="sxs-lookup"><span data-stu-id="0c715-121">Click "Allow trailing separators".</span></span>