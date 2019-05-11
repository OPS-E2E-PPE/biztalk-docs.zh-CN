---
title: SWIFT 文本 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- SWIFT, text
ms.assetid: 90851d38-7789-4b1b-813b-7943f77ab984
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 6dbf2c26518924f1ddf0e1cd77a4ac6e52eec54a
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65376951"
---
# <a name="swift-text"></a><span data-ttu-id="f687d-102">SWIFT 文本</span><span class="sxs-lookup"><span data-stu-id="f687d-102">SWIFT Text</span></span>
<span data-ttu-id="f687d-103">消息文本构成消息负载的财务 (FIN)，并且包含的所有数据字段包含发件人、 收件人和消息类型的字段除外。</span><span class="sxs-lookup"><span data-stu-id="f687d-103">The message text makes up the payload of the financial (FIN) message, and contains all of the data fields except the fields containing the sender, receiver, and message type.</span></span> <span data-ttu-id="f687d-104">这三个字段都包含在标头部分。</span><span class="sxs-lookup"><span data-stu-id="f687d-104">These three fields are contained in the header portion.</span></span> <span data-ttu-id="f687d-105">有些消息还包含一个可选用户标头，它还可能提供处理信息。</span><span class="sxs-lookup"><span data-stu-id="f687d-105">Some messages also contain an optional User Header, which may also provide processing information.</span></span>  
  
 <span data-ttu-id="f687d-106">每个 FIN 消息有效负载包含一系列定义序列中的字段。</span><span class="sxs-lookup"><span data-stu-id="f687d-106">Each FIN message payload consists of a series of fields in a defined sequence.</span></span> <span data-ttu-id="f687d-107">这些字段符合以下规则：</span><span class="sxs-lookup"><span data-stu-id="f687d-107">These fields conform to the following rules:</span></span>  
  
- <span data-ttu-id="f687d-108">字段是必需或可选序列中。</span><span class="sxs-lookup"><span data-stu-id="f687d-108">The fields may be required or optional within the sequence.</span></span>  
  
- <span data-ttu-id="f687d-109">序列可能包含子序列，并在序列内重复子序列可能。</span><span class="sxs-lookup"><span data-stu-id="f687d-109">A sequence may contain subsequences, and a subsequence may repeat within a sequence.</span></span>  
  
- <span data-ttu-id="f687d-110">可以使用几种消息类型中的字段。</span><span class="sxs-lookup"><span data-stu-id="f687d-110">You can use a field in several message types.</span></span>  
  
- <span data-ttu-id="f687d-111">在字段中可能有元素或子字段。</span><span class="sxs-lookup"><span data-stu-id="f687d-111">Within a field, there may be elements or subfields.</span></span> <span data-ttu-id="f687d-112">元素或子字段可能是普遍适用于多个字段。</span><span class="sxs-lookup"><span data-stu-id="f687d-112">An element or subfield may be common to several fields.</span></span>  
  
- <span data-ttu-id="f687d-113">组节点表示每个重复的序列。</span><span class="sxs-lookup"><span data-stu-id="f687d-113">Each repeating sequence is represented by a group node.</span></span>  
  
- <span data-ttu-id="f687d-114">每个字段可能本身具有多个 nodal 级别，每个描述为一条记录。</span><span class="sxs-lookup"><span data-stu-id="f687d-114">Each field may itself have multiple nodal levels, each described as a record.</span></span>  
  
- <span data-ttu-id="f687d-115">架构元素表示只能最低的级别子字段。</span><span class="sxs-lookup"><span data-stu-id="f687d-115">A schema element represents only the lowest level subfield.</span></span>  
  
- <span data-ttu-id="f687d-116">通用记录和元素中定义的通用基础架构，如下所述。</span><span class="sxs-lookup"><span data-stu-id="f687d-116">Common records and elements are defined in the common and base schema, as described below.</span></span>  
  
- <span data-ttu-id="f687d-117">某些字段可能会出现在几种格式 （如参与方字段）。</span><span class="sxs-lookup"><span data-stu-id="f687d-117">Some fields may be represented in several formats (such as party fields).</span></span> <span data-ttu-id="f687d-118">此类字段定义为架构中选择字段。</span><span class="sxs-lookup"><span data-stu-id="f687d-118">Such fields are defined as choice fields in the schema.</span></span>  
  
  <span data-ttu-id="f687d-119">某些字段具有有限的值集。</span><span class="sxs-lookup"><span data-stu-id="f687d-119">Some fields have limited sets of values.</span></span> <span data-ttu-id="f687d-120">大多数情况下，该架构还列出了这些值。</span><span class="sxs-lookup"><span data-stu-id="f687d-120">For the most part, the schema lists these values.</span></span> <span data-ttu-id="f687d-121">架构定义还包括字符集验证。</span><span class="sxs-lookup"><span data-stu-id="f687d-121">Schema definitions also include character set validation.</span></span>