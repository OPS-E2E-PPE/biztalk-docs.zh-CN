---
title: 数据类型属性的转换 |Microsoft Docs
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
ms.openlocfilehash: 3846fa8cb6fe30e1cae561f7652aba0a02944a28
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65353035"
---
# <a name="data-type-conversion-of-properties"></a><span data-ttu-id="48e22-102">属性的数据类型转换</span><span class="sxs-lookup"><span data-stu-id="48e22-102">Data Type Conversion of Properties</span></span>
<span data-ttu-id="48e22-103">MQSeries 消息中的标头属性是消息本身中包含的数据结构。</span><span class="sxs-lookup"><span data-stu-id="48e22-103">Header properties in an MQSeries message are data structures contained in the message itself.</span></span> <span data-ttu-id="48e22-104">MQSeries 适配器会自动验证，并将转换时发送和接收消息的 MQSeries 消息标头中的某些值。</span><span class="sxs-lookup"><span data-stu-id="48e22-104">The MQSeries adapter automatically validates and converts certain values in MQSeries message headers when sending and receiving messages.</span></span>  
  
 <span data-ttu-id="48e22-105">下表介绍了 MQSeries 数据类型及其验证和转换。</span><span class="sxs-lookup"><span data-stu-id="48e22-105">The following table describes the MQSeries data types and their validation and conversion.</span></span>  
  
|<span data-ttu-id="48e22-106">MQSeries 数据类型</span><span class="sxs-lookup"><span data-stu-id="48e22-106">MQSeries data type</span></span>|<span data-ttu-id="48e22-107">验证和转换</span><span class="sxs-lookup"><span data-stu-id="48e22-107">Validation and conversion</span></span>|  
|------------------------|-------------------------------|  
|<span data-ttu-id="48e22-108">MQLONG</span><span class="sxs-lookup"><span data-stu-id="48e22-108">MQLONG</span></span>|<span data-ttu-id="48e22-109">MQSeries 执行验证。</span><span class="sxs-lookup"><span data-stu-id="48e22-109">MQSeries performs the validation.</span></span> <span data-ttu-id="48e22-110">将转换为长整型。</span><span class="sxs-lookup"><span data-stu-id="48e22-110">Converts to a long integer.</span></span> <span data-ttu-id="48e22-111">不是有效的值将阻止消息转到 MQSeries 队列。</span><span class="sxs-lookup"><span data-stu-id="48e22-111">Values that are not valid prevent the message from going to the MQSeries queue.</span></span>|  
|<span data-ttu-id="48e22-112">MQCHAR</span><span class="sxs-lookup"><span data-stu-id="48e22-112">MQCHAR</span></span>|<span data-ttu-id="48e22-113">将转换为字符串。</span><span class="sxs-lookup"><span data-stu-id="48e22-113">Converts to a string.</span></span>|  
|<span data-ttu-id="48e22-114">MQBYTE</span><span class="sxs-lookup"><span data-stu-id="48e22-114">MQBYTE</span></span>|<span data-ttu-id="48e22-115">将转换为包含字符 0-9 和 a-f 或 A-F，表示数字的十六进制值的字符串。</span><span class="sxs-lookup"><span data-stu-id="48e22-115">Converts to a string that contains the characters 0-9 and a-f or A-F, representing the hexadecimal value of the number.</span></span>|  
  
 <span data-ttu-id="48e22-116">许多 MQSeries 属性是 32 位 （4 字节） 无符号的整数。</span><span class="sxs-lookup"><span data-stu-id="48e22-116">Many of the MQSeries properties are 32-bit (4-byte) unsigned integers.</span></span> <span data-ttu-id="48e22-117">因为**uint**不是公共语言规范 (CLS) 的符合标准的类型，您必须将其分配给**对象**之前使用它们在.NET 方法中的类型。</span><span class="sxs-lookup"><span data-stu-id="48e22-117">Because **uint** is not a Common Language Specification (CLS)-compliant type, you must assign them to **object** types before using them in .NET methods.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="48e22-118">请参阅</span><span class="sxs-lookup"><span data-stu-id="48e22-118">See Also</span></span>  
 <span data-ttu-id="48e22-119">[MQSeries 适配器属性](../core/mqseries-adapter-properties.md) </span><span class="sxs-lookup"><span data-stu-id="48e22-119">[MQSeries Adapter Properties](../core/mqseries-adapter-properties.md) </span></span>  
 <span data-ttu-id="48e22-120">[与 BizTalk Server 相关的属性](../core/properties-related-to-biztalk-server.md) </span><span class="sxs-lookup"><span data-stu-id="48e22-120">[Properties Related to BizTalk Server](../core/properties-related-to-biztalk-server.md) </span></span>  
 [<span data-ttu-id="48e22-121">MQSeries 上下文属性</span><span class="sxs-lookup"><span data-stu-id="48e22-121">MQSeries Context Properties</span></span>](../core/mqseries-context-properties.md)