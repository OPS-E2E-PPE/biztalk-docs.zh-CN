---
title: Xlang-s 数据类型 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- orchestrations, expressions
- Orchestration Designer, managing data
- Orchestration Designer, variables
- orchestrations, variables
- Orchestration Designer, expressions
ms.assetid: 5b08aaa6-1533-4bac-a76d-f9162e39bf4f
caps.latest.revision: 17
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 6cc0d20336169ec1198c21dcbe932ff5a823a568
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65394713"
---
# <a name="xlang-s-data-types"></a><span data-ttu-id="5ca5c-102">Xlang-s 数据类型</span><span class="sxs-lookup"><span data-stu-id="5ca5c-102">XLANG-s Data Types</span></span>
<span data-ttu-id="5ca5c-103">XLANG/s 定义反映的标准值类型及其C#对应项。</span><span class="sxs-lookup"><span data-stu-id="5ca5c-103">XLANG/s defines standard value types that are reflections of their C# counterparts.</span></span> <span data-ttu-id="5ca5c-104">其中包括**布尔**，**字节**， **Char**，**十进制**， **Double**， **Int16**， **Int32**， **Int64**， **SByte**，**单一**，**字符串**， **UInt16**， **UInt32**，和**UInt64**。</span><span class="sxs-lookup"><span data-stu-id="5ca5c-104">These include **Boolean**, **Byte**, **Char**, **Decimal**, **Double**, **Int16**, **Int32**, **Int64**, **SByte**, **Single**, **String**, **UInt16**, **UInt32**, and **UInt64**.</span></span> <span data-ttu-id="5ca5c-105">XLANG/s 支持一维数组，但不支持数组文本。</span><span class="sxs-lookup"><span data-stu-id="5ca5c-105">XLANG/s supports single-dimensional arrays, but does not support array literals.</span></span>  
  
 <span data-ttu-id="5ca5c-106">XLANG/s 还提供消息处理的丰富支持。</span><span class="sxs-lookup"><span data-stu-id="5ca5c-106">XLANG/s also has rich support for message handling.</span></span> <span data-ttu-id="5ca5c-107">消息可以基于架构、.NET 类，Web 消息类型 (WSDL) 或复杂的消息类型。</span><span class="sxs-lookup"><span data-stu-id="5ca5c-107">Messages can be based on schemas, .NET classes, Web message types (WSDL), or complex message types.</span></span> <span data-ttu-id="5ca5c-108">XLANG/s 支持以下复杂数据类型：</span><span class="sxs-lookup"><span data-stu-id="5ca5c-108">XLANG/s supports the following complex data types:</span></span>  
  
-   <span data-ttu-id="5ca5c-109">**messagetype.**</span><span class="sxs-lookup"><span data-stu-id="5ca5c-109">**messagetype.**</span></span> <span data-ttu-id="5ca5c-110">此数据类型定义多部分消息类型定义为数据元素和基于 XSD 的消息的组合和方法消息类型 （类或接口的方法的签名格式匹配的消息）。</span><span class="sxs-lookup"><span data-stu-id="5ca5c-110">This data type defines multipart message types which are defined as combinations of data elements and XSD-based messages and Method-Message types (messages that match the signature format of a method of a class or interface).</span></span>  
  
-   <span data-ttu-id="5ca5c-111">**porttype.**</span><span class="sxs-lookup"><span data-stu-id="5ca5c-111">**porttype.**</span></span> <span data-ttu-id="5ca5c-112">此数据类型定义该类型的端口实例可以对其执行操作的端口操作的集合。</span><span class="sxs-lookup"><span data-stu-id="5ca5c-112">This data type defines a collection of port operations that a port instance of that type can act upon.</span></span>  
  
-   <span data-ttu-id="5ca5c-113">**correlationsettype.**</span><span class="sxs-lookup"><span data-stu-id="5ca5c-113">**correlationsettype.**</span></span> <span data-ttu-id="5ca5c-114">此数据类型定义相关集变量的任何实例中将使用的数据。</span><span class="sxs-lookup"><span data-stu-id="5ca5c-114">This data type defines the data that will be used in any instance of a correlation set variable.</span></span> <span data-ttu-id="5ca5c-115">相关集数据是用于确保整个系统的消息将调度到相应正在运行的业务流程实例的路由机制。</span><span class="sxs-lookup"><span data-stu-id="5ca5c-115">Correlation set data is the routing mechanism used to ensure that messages moving through the system are dispatched to the appropriate running instance of a business process.</span></span> <span data-ttu-id="5ca5c-116">例如，如果采购订单发送到贸易合作伙伴进行处理，则正确的对应于该采购订单的业务流程实例在其返回上调用命令性。</span><span class="sxs-lookup"><span data-stu-id="5ca5c-116">For example, if a purchase order is sent to a trading partner for processing, it is imperative that the correct instance of the business process corresponding to that purchase order be invoked on its return.</span></span>  
  
-   <span data-ttu-id="5ca5c-117">**servicelinktype.**</span><span class="sxs-lookup"><span data-stu-id="5ca5c-117">**servicelinktype.**</span></span> <span data-ttu-id="5ca5c-118">此数据类型定义的一套**porttype**形成一个逻辑上一致的业务流程中使用的端口组的值。</span><span class="sxs-lookup"><span data-stu-id="5ca5c-118">This data type defines the set of **porttype** values that form a logically consistent group of ports used in a business process.</span></span> <span data-ttu-id="5ca5c-119">服务链接的使用是强大的机制，允许在运行时动态分配到的端口组。</span><span class="sxs-lookup"><span data-stu-id="5ca5c-119">The use of service links is a powerful mechanism that allows dynamic assignment to a group of ports at run time.</span></span> <span data-ttu-id="5ca5c-120">这样，您可以定义可用于与多个贸易合作伙伴进行交互的单个业务流程。</span><span class="sxs-lookup"><span data-stu-id="5ca5c-120">This allows you to define a single business process that can be used to interact with multiple trading partners.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5ca5c-121">请参阅</span><span class="sxs-lookup"><span data-stu-id="5ca5c-121">See Also</span></span>  
 <span data-ttu-id="5ca5c-122">[Xlang-s 语句](../core/xlang-s-statements.md) </span><span class="sxs-lookup"><span data-stu-id="5ca5c-122">[XLANG-s Statements](../core/xlang-s-statements.md) </span></span>  
 <span data-ttu-id="5ca5c-123">[Xlang-s 变量和运算符](../core/xlang-s-variables-and-operators.md) </span><span class="sxs-lookup"><span data-stu-id="5ca5c-123">[XLANG-s Variables and Operators](../core/xlang-s-variables-and-operators.md) </span></span>  
 <span data-ttu-id="5ca5c-124">[Xlang-s 表达式](../core/xlang-s-expressions.md) </span><span class="sxs-lookup"><span data-stu-id="5ca5c-124">[XLANG-s Expressions](../core/xlang-s-expressions.md) </span></span>  
 <span data-ttu-id="5ca5c-125">[Xlang-s 保留字](../core/xlang-s-reserved-words.md) </span><span class="sxs-lookup"><span data-stu-id="5ca5c-125">[XLANG-s Reserved Words](../core/xlang-s-reserved-words.md) </span></span>  
 [<span data-ttu-id="5ca5c-126">XLANG-s 到 BPEL4WS 的类型转换</span><span class="sxs-lookup"><span data-stu-id="5ca5c-126">XLANG-s to BPEL4WS Type Conversions</span></span>](../core/xlang-s-to-bpel4ws-type-conversions.md)