---
title: "EDI 数据元素结构化元素 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 775e8b87-b952-46d2-a506-5174d216a9aa
caps.latest.revision: "6"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 600edb30ff157a520ac67eebce58428a62e27c8e
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="edi-data-element-structural-element"></a><span data-ttu-id="735ca-102">EDI 数据元素：结构元素</span><span class="sxs-lookup"><span data-stu-id="735ca-102">EDI Data Element Structural Element</span></span>
<span data-ttu-id="735ca-103">数据元素是消息中的基本数据单元。</span><span class="sxs-lookup"><span data-stu-id="735ca-103">The data element is the primary unit of data in the message.</span></span> <span data-ttu-id="735ca-104">数据元素由数据元素分隔符分隔，默认情况下 X12 是星号，EDIFACT 是加号。</span><span class="sxs-lookup"><span data-stu-id="735ca-104">Data elements are separated by the data element separator, which is an asterisk by default for X12 and a plus sign by default for EDIFACT.</span></span> <span data-ttu-id="735ca-105">数据元素的可行性定义为：必需、可选或条件。</span><span class="sxs-lookup"><span data-stu-id="735ca-105">The optionality of data elements is defined as mandatory, optional, or conditional.</span></span>  
  
 <span data-ttu-id="735ca-106">数据元素可以是简单或复合。</span><span class="sxs-lookup"><span data-stu-id="735ca-106">A data element can be either simple or composite.</span></span> <span data-ttu-id="735ca-107">简单数据元素为数值型，它们是最低级别的数据。</span><span class="sxs-lookup"><span data-stu-id="735ca-107">Simple data elements are numeric and are the lowest level of data.</span></span> <span data-ttu-id="735ca-108">复合数据元素是一串子元素，这些子元素是由复合元素分隔符分隔的简单数据元素。</span><span class="sxs-lookup"><span data-stu-id="735ca-108">Composite data elements are concatenations of sub element, which are simple data elements separated by a component separator.</span></span> <span data-ttu-id="735ca-109">默认状态下，复合元素分隔符对于 x12 和 EDIFACT 是冒号。</span><span class="sxs-lookup"><span data-stu-id="735ca-109">By default, the component separator is the colon for X12 and EDIFACT.</span></span>  
  
 <span data-ttu-id="735ca-110">对于 EDIFACT 编码的消息，如果经由 EDI 发送的数据需要发送任何定义用作分隔符的字符，则需要使用转义符来指明后面的字符不是分隔符，而是数据的一部分。</span><span class="sxs-lookup"><span data-stu-id="735ca-110">For EDIFACT-encoded messages, if the data to be sent via EDI needs to send any character defined for use as a separator, you need to use a release character to indicate that the following character is not a separator, but is part of the data.</span></span> <span data-ttu-id="735ca-111">默认情况下，转义符为问号 (?)。</span><span class="sxs-lookup"><span data-stu-id="735ca-111">The release character is by default the question mark (?).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="735ca-112">X12 不支持转义符。</span><span class="sxs-lookup"><span data-stu-id="735ca-112">A release character is not supported for X12.</span></span> <span data-ttu-id="735ca-113">如果遇到作为 X12 编码的交换数据一部分的分隔符，则交换将在接收方或发送方挂起。</span><span class="sxs-lookup"><span data-stu-id="735ca-113">If a separator is encountered as part of the data of an X12-encoded interchange, on either the receive or send side, the interchange will be suspended.</span></span>