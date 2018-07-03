---
title: 对函数和 Oracle 数据库中的存储的过程的操作 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- REF CURSOR
- packaged functions and procedures
- operations, on functions and stored procedures
- stored procedure
- RECORD type
- overloaded functions and procedures
ms.assetid: 18072b58-65b2-4da5-9433-ea0da4e2d4f4
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 856e6bf882605737380f0bbe6185dce8a56c5828
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36979606"
---
# <a name="operations-on-functions-and-stored-procedures-in-oracle-database"></a><span data-ttu-id="7def5-102">对函数和 Oracle 数据库中的存储的过程的操作</span><span class="sxs-lookup"><span data-stu-id="7def5-102">Operations on functions and stored procedures in Oracle Database</span></span>
<span data-ttu-id="7def5-103">[!INCLUDE[adapteroracle](../../includes/adapteroracle-md.md)]按以下方式支持 Oracle 函数、 过程和包：</span><span class="sxs-lookup"><span data-stu-id="7def5-103">The [!INCLUDE[adapteroracle](../../includes/adapteroracle-md.md)] supports Oracle functions, procedures, and packages in the following manner:</span></span>  
  
- <span data-ttu-id="7def5-104">**函数**作为操作。</span><span class="sxs-lookup"><span data-stu-id="7def5-104">**Functions** are surfaced as operations.</span></span> <span data-ttu-id="7def5-105">操作的名称是该 Oracle 函数的名称。</span><span class="sxs-lookup"><span data-stu-id="7def5-105">The name of the operation is the name of the Oracle function.</span></span> <span data-ttu-id="7def5-106">在中，扩展，并在扩展参数支持，以及，返回值。</span><span class="sxs-lookup"><span data-stu-id="7def5-106">IN, OUT, and IN OUT parameters are supported, as well as, RETURN values.</span></span>  
  
- <span data-ttu-id="7def5-107">**过程**作为操作。</span><span class="sxs-lookup"><span data-stu-id="7def5-107">**Procedures** are surfaced as operations.</span></span> <span data-ttu-id="7def5-108">操作的名称是该 Oracle 过程的名称。</span><span class="sxs-lookup"><span data-stu-id="7def5-108">The name of the operation is the name of the Oracle procedure.</span></span> <span data-ttu-id="7def5-109">在中，扩展，并在扩展中支持参数。</span><span class="sxs-lookup"><span data-stu-id="7def5-109">IN, OUT, and IN OUT parameters are supported.</span></span>  
  
- <span data-ttu-id="7def5-110">**打包函数和过程**作为操作。</span><span class="sxs-lookup"><span data-stu-id="7def5-110">**Packaged functions and procedures** are surfaced as operations.</span></span> <span data-ttu-id="7def5-111">由 Oracle 包的名称进行限定的名称和命名空间的操作 （函数或过程）。</span><span class="sxs-lookup"><span data-stu-id="7def5-111">The name and namespace of the operation (function or procedure) is qualified by the name of the Oracle package.</span></span> <span data-ttu-id="7def5-112">重载都受支持 （请参阅下一个项目符号） 的包中。</span><span class="sxs-lookup"><span data-stu-id="7def5-112">Overloads are supported in packages (see next bullet).</span></span>  
  
- <span data-ttu-id="7def5-113">**重载函数和过程**作为操作会显示在包中。</span><span class="sxs-lookup"><span data-stu-id="7def5-113">**Overloaded functions and procedures** in packages are surfaced as operations.</span></span> <span data-ttu-id="7def5-114">每个重载函数或过程显示与附加到标识重载其名称的字符串。</span><span class="sxs-lookup"><span data-stu-id="7def5-114">Each overloaded function or procedure is surfaced with a string appended to its name that identifies the overload.</span></span> <span data-ttu-id="7def5-115">此字符串是序列"overload1"、"overload2"、"overload3"等的一部分。</span><span class="sxs-lookup"><span data-stu-id="7def5-115">This string is part of the sequence "overload1", "overload2", "overload3", and so on.</span></span>  
  
- <span data-ttu-id="7def5-116">**REF CURSOR 类型**IN、 OUT，支持，以及在 OUT 参数的过程和函数，以及函数的返回值。</span><span class="sxs-lookup"><span data-stu-id="7def5-116">**REF CURSOR types** are supported for IN, OUT, and IN OUT parameters for procedures and functions, as well as for function RETURN values.</span></span> <span data-ttu-id="7def5-117">有关详细信息，请参阅[对包含 REF CURSOR 参数函数和过程的操作](../../adapters-and-accelerators/adapter-oracle-ebs/operations-on-functions-and-procedures-with-ref-cursor-parameters1.md)。</span><span class="sxs-lookup"><span data-stu-id="7def5-117">For more information, see [Operations on Functions and Procedures with REF CURSOR Parameters](../../adapters-and-accelerators/adapter-oracle-ebs/operations-on-functions-and-procedures-with-ref-cursor-parameters1.md).</span></span>  
  
- <span data-ttu-id="7def5-118">**记录类型**IN、 OUT，支持，以及在 OUT 参数的过程和函数，以及函数的返回值。</span><span class="sxs-lookup"><span data-stu-id="7def5-118">**RECORD types** are supported for IN, OUT, and IN OUT parameters for procedures and functions, as well as for function RETURN values.</span></span> <span data-ttu-id="7def5-119">支持简单和复杂 （嵌套） 的记录类型。</span><span class="sxs-lookup"><span data-stu-id="7def5-119">Both simple and complex (nested) RECORD types are supported.</span></span> [<span data-ttu-id="7def5-120">对包含 RECORD 类型的函数和过程的操作</span><span class="sxs-lookup"><span data-stu-id="7def5-120">Operations on Functions and Procedures with RECORD Types</span></span>](../../adapters-and-accelerators/adapter-oracle-ebs/operations-on-functions-and-procedures-with-record-types1.md)  
  
  <span data-ttu-id="7def5-121">有关详细信息：</span><span class="sxs-lookup"><span data-stu-id="7def5-121">For more information about:</span></span>  
  
- <span data-ttu-id="7def5-122">通过使用调用 Oracle 过程或函数[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]，请参阅[调用的函数和使用 BizTalk Server 的 Oracle 数据库中的过程](../../adapters-and-accelerators/adapter-oracle-database/invoke-functions-and-procedures-in-oracle-database-using-biztalk-server.md)和[调用重载函数和过程中使用 Oracle 数据库BizTalk Server](../../adapters-and-accelerators/adapter-oracle-database/run-overloaded-functions-and-procedures-in-oracle-database-using-biztalk-server.md)。</span><span class="sxs-lookup"><span data-stu-id="7def5-122">Invoking an Oracle procedure or function by using [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)], see [Invoke Functions and Procedures in Oracle Database using BizTalk Server](../../adapters-and-accelerators/adapter-oracle-database/invoke-functions-and-procedures-in-oracle-database-using-biztalk-server.md) and [Invoke Overload Functions and Procedures in Oracle Database using BizTalk Server](../../adapters-and-accelerators/adapter-oracle-database/run-overloaded-functions-and-procedures-in-oracle-database-using-biztalk-server.md).</span></span>  
  
- <span data-ttu-id="7def5-123">Oracle 过程或函数使用调用的 WCF 服务模型，请参阅[调用的函数和 Oracle 数据库使用 WCF 服务模型中的过程](../../adapters-and-accelerators/adapter-oracle-database/invoke-functions-and-procedures-in-oracle-database-using-the-wcf-service-model.md)。</span><span class="sxs-lookup"><span data-stu-id="7def5-123">Invoking an Oracle procedure or function by using the WCF service model, see [Invoke Functions and Procedures in Oracle Database using the WCF Service model](../../adapters-and-accelerators/adapter-oracle-database/invoke-functions-and-procedures-in-oracle-database-using-the-wcf-service-model.md).</span></span>  
  
- <span data-ttu-id="7def5-124">Oracle 过程或函数使用调用的 WCF 通道模型，请参阅[调用的函数在 Oracle 数据库中使用 WCF 通道模型](../../adapters-and-accelerators/adapter-oracle-database/invoke-a-function-in-oracle-database-using-the-wcf-channel-model.md)。</span><span class="sxs-lookup"><span data-stu-id="7def5-124">Invoking an Oracle procedure or function by using the WCF channel model, see [Invoke a Function in Oracle Database using the WCF Channel Model](../../adapters-and-accelerators/adapter-oracle-database/invoke-a-function-in-oracle-database-using-the-wcf-channel-model.md).</span></span>  
  
- <span data-ttu-id="7def5-125">消息结构和 SOAP 操作用于调用 Oracle 过程和函数，请参阅[函数和过程的消息架构](../../adapters-and-accelerators/adapter-oracle-database/message-schemas-for-functions-and-procedures.md)。</span><span class="sxs-lookup"><span data-stu-id="7def5-125">Message structure and SOAP actions used to invoke Oracle procedures and functions, see [Message Schemas for Functions and Procedures](../../adapters-and-accelerators/adapter-oracle-database/message-schemas-for-functions-and-procedures.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7def5-126">请参阅</span><span class="sxs-lookup"><span data-stu-id="7def5-126">See Also</span></span>  
 <span data-ttu-id="7def5-127">[哪些操作可以是执行使用适配器？](https://msdn.microsoft.com/library/cc185219(v=bts.10).aspx)</span><span class="sxs-lookup"><span data-stu-id="7def5-127">[What Operations Can be Performed Using the Adapter?](https://msdn.microsoft.com/library/cc185219(v=bts.10).aspx)</span></span>