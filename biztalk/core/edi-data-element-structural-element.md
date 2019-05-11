---
title: EDI 数据元素结构元素 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 775e8b87-b952-46d2-a506-5174d216a9aa
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b36433f3cf4cf4a8f14ac70467d870a727db7dd9
ms.sourcegitcommit: d27732e569b0897361dfaebca8352aa97bb7efe1
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/10/2019
ms.locfileid: "65530832"
---
# <a name="edi-data-element-structural-element"></a><span data-ttu-id="4384e-102">EDI 数据元素结构元素</span><span class="sxs-lookup"><span data-stu-id="4384e-102">EDI Data Element Structural Element</span></span>
<span data-ttu-id="4384e-103">数据元素是消息中数据的主计价单位。</span><span class="sxs-lookup"><span data-stu-id="4384e-103">The data element is the primary unit of data in the message.</span></span> <span data-ttu-id="4384e-104">数据元素由数据元素分隔符，这是默认情况下，对于 X12 是星号，默认情况下，对于 EDIFACT 是加号分隔。</span><span class="sxs-lookup"><span data-stu-id="4384e-104">Data elements are separated by the data element separator, which is an asterisk by default for X12 and a plus sign by default for EDIFACT.</span></span> <span data-ttu-id="4384e-105">数据元素的可行性定义为必需、 可选或条件。</span><span class="sxs-lookup"><span data-stu-id="4384e-105">The optionality of data elements is defined as mandatory, optional, or conditional.</span></span>  
  
 <span data-ttu-id="4384e-106">数据元素可以是简单或复合。</span><span class="sxs-lookup"><span data-stu-id="4384e-106">A data element can be either simple or composite.</span></span> <span data-ttu-id="4384e-107">简单数据元素为数值型，它们的数据的最低级别。</span><span class="sxs-lookup"><span data-stu-id="4384e-107">Simple data elements are numeric and are the lowest level of data.</span></span> <span data-ttu-id="4384e-108">复合数据元素是一串子元素，这是由复合元素分隔符分隔的简单数据元素。</span><span class="sxs-lookup"><span data-stu-id="4384e-108">Composite data elements are concatenations of sub element, which are simple data elements separated by a component separator.</span></span> <span data-ttu-id="4384e-109">默认情况下，组件分隔符是 X12 和 EDIFACT 的冒号。</span><span class="sxs-lookup"><span data-stu-id="4384e-109">By default, the component separator is the colon for X12 and EDIFACT.</span></span>  
  
 <span data-ttu-id="4384e-110">对于 EDIFACT 编码的消息，如果经由 EDI 发送的数据需要发送任何定义用作分隔符的字符需要使用转义符来指明后面的字符不是一个分隔符，而是数据的一部分。</span><span class="sxs-lookup"><span data-stu-id="4384e-110">For EDIFACT-encoded messages, if the data to be sent via EDI needs to send any character defined for use as a separator, you need to use a release character to indicate that the following character is not a separator, but is part of the data.</span></span> <span data-ttu-id="4384e-111">转义符为问号 （？） 默认情况下。</span><span class="sxs-lookup"><span data-stu-id="4384e-111">The release character is by default the question mark (?).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="4384e-112">对于 X12 不支持转义符。</span><span class="sxs-lookup"><span data-stu-id="4384e-112">A release character is not supported for X12.</span></span> <span data-ttu-id="4384e-113">如果遇到作为 X12 编码的交换，在接收或发送端的数据的一部分分隔符将挂起交换。</span><span class="sxs-lookup"><span data-stu-id="4384e-113">If a separator is encountered as part of the data of an X12-encoded interchange, on either the receive or send side, the interchange will be suspended.</span></span>