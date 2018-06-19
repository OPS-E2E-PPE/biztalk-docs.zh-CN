---
title: 数据类型的属性转换 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- MQSeries adapters, data type conversion
- MQBYTE property [MQSeries adapters]
- MQLONG property [MQSeries adapters]
- MQCHAR property [MQSeries adapters]
- configuring [MQSeries adapters], data type conversion
ms.assetid: 5b81eab0-f7a1-42f3-b212-a211b2893fd5
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 3705f1d0a20a48f0683a15588891ef3fe60889cd
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22238661"
---
# <a name="data-type-conversion-of-properties"></a><span data-ttu-id="7a020-102">数据类型转换的属性</span><span class="sxs-lookup"><span data-stu-id="7a020-102">Data Type Conversion of Properties</span></span>
<span data-ttu-id="7a020-103">MQSeries 消息中的标头属性即为消息本身所包含的数据结构。</span><span class="sxs-lookup"><span data-stu-id="7a020-103">Header properties in an MQSeries message are data structures contained in the message itself.</span></span> <span data-ttu-id="7a020-104">在发送和接收消息时，MQSeries 适配器会自动对 MQSeries 消息头中的某些值进行验证和转换。</span><span class="sxs-lookup"><span data-stu-id="7a020-104">The MQSeries adapter automatically validates and converts certain values in MQSeries message headers when sending and receiving messages.</span></span>  
  
 <span data-ttu-id="7a020-105">下表介绍了 MQSeries 数据类型以及这些类型的验证和转换：</span><span class="sxs-lookup"><span data-stu-id="7a020-105">The following table describes the MQSeries data types and their validation and conversion.</span></span>  
  
|<span data-ttu-id="7a020-106">MQSeries 数据类型</span><span class="sxs-lookup"><span data-stu-id="7a020-106">MQSeries data type</span></span>|<span data-ttu-id="7a020-107">验证和转换</span><span class="sxs-lookup"><span data-stu-id="7a020-107">Validation and conversion</span></span>|  
|------------------------|-------------------------------|  
|<span data-ttu-id="7a020-108">MQLONG</span><span class="sxs-lookup"><span data-stu-id="7a020-108">MQLONG</span></span>|<span data-ttu-id="7a020-109">MQSeries 执行验证。</span><span class="sxs-lookup"><span data-stu-id="7a020-109">MQSeries performs the validation.</span></span> <span data-ttu-id="7a020-110">转换为长整型。</span><span class="sxs-lookup"><span data-stu-id="7a020-110">Converts to a long integer.</span></span> <span data-ttu-id="7a020-111">如果值无效，则将阻止将消息传至 MQSeries 队列中。</span><span class="sxs-lookup"><span data-stu-id="7a020-111">Values that are not valid prevent the message from going to the MQSeries queue.</span></span>|  
|<span data-ttu-id="7a020-112">MQCHAR</span><span class="sxs-lookup"><span data-stu-id="7a020-112">MQCHAR</span></span>|<span data-ttu-id="7a020-113">转换为字符串。</span><span class="sxs-lookup"><span data-stu-id="7a020-113">Converts to a string.</span></span>|  
|<span data-ttu-id="7a020-114">MQBYTE</span><span class="sxs-lookup"><span data-stu-id="7a020-114">MQBYTE</span></span>|<span data-ttu-id="7a020-115">转换为包含字符 0-9 和 a-f 或 A-F 的字符串，表示该数字的十六进制值。</span><span class="sxs-lookup"><span data-stu-id="7a020-115">Converts to a string that contains the characters 0-9 and a-f or A-F, representing the hexadecimal value of the number.</span></span>|  
  
 <span data-ttu-id="7a020-116">许多 MQSeries 属性是 32 位（4 字节）无符号整数。</span><span class="sxs-lookup"><span data-stu-id="7a020-116">Many of the MQSeries properties are 32-bit (4-byte) unsigned integers.</span></span> <span data-ttu-id="7a020-117">因为**uint**不是公共语言规范 (CLS) 的符合标准的类型，你必须将它们分配给**对象**之前在.NET 方法中使用这些类型。</span><span class="sxs-lookup"><span data-stu-id="7a020-117">Because **uint** is not a Common Language Specification (CLS)-compliant type, you must assign them to **object** types before using them in .NET methods.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7a020-118">另请参阅</span><span class="sxs-lookup"><span data-stu-id="7a020-118">See Also</span></span>  
 <span data-ttu-id="7a020-119">[MQSeries 适配器属性](../core/mqseries-adapter-properties.md) </span><span class="sxs-lookup"><span data-stu-id="7a020-119">[MQSeries Adapter Properties](../core/mqseries-adapter-properties.md) </span></span>  
 <span data-ttu-id="7a020-120">[与 BizTalk Server 相关的属性](../core/properties-related-to-biztalk-server.md) </span><span class="sxs-lookup"><span data-stu-id="7a020-120">[Properties Related to BizTalk Server](../core/properties-related-to-biztalk-server.md) </span></span>  
 [<span data-ttu-id="7a020-121">MQSeries 上下文属性</span><span class="sxs-lookup"><span data-stu-id="7a020-121">MQSeries Context Properties</span></span>](../core/mqseries-context-properties.md)