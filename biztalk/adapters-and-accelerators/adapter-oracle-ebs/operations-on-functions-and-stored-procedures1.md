---
title: 对函数和存储的 Procedures1 操作 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 1e6bdaa7-ed3c-43bc-bed5-70fe43f9c2d1
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c0c108490d9ce280f6926bc66ba2d2665254f636
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65375338"
---
# <a name="operations-on-functions-and-stored-procedures"></a><span data-ttu-id="5de6a-102">对函数和存储的过程的操作</span><span class="sxs-lookup"><span data-stu-id="5de6a-102">Operations on Functions and Stored Procedures</span></span>
<span data-ttu-id="5de6a-103">[!INCLUDE[adapteroracleebusinesslong](../../includes/adapteroracleebusinesslong-md.md)]支持 Oracle 函数和过程。</span><span class="sxs-lookup"><span data-stu-id="5de6a-103">The [!INCLUDE[adapteroracleebusinesslong](../../includes/adapteroracleebusinesslong-md.md)] supports Oracle functions and procedures.</span></span>

## <a name="functions-and-procedures"></a><span data-ttu-id="5de6a-104">函数和过程</span><span class="sxs-lookup"><span data-stu-id="5de6a-104">Functions and procedures</span></span>

<span data-ttu-id="5de6a-105">[!INCLUDE[adapteroracleebusinesslong](../../includes/adapteroracleebusinesslong-md.md)]按以下方式支持 Oracle 函数和过程：</span><span class="sxs-lookup"><span data-stu-id="5de6a-105">The [!INCLUDE[adapteroracleebusinesslong](../../includes/adapteroracleebusinesslong-md.md)] supports Oracle functions and procedures in the following manner:</span></span>  
  
- <span data-ttu-id="5de6a-106">**函数**作为操作。</span><span class="sxs-lookup"><span data-stu-id="5de6a-106">**Functions** are surfaced as operations.</span></span> <span data-ttu-id="5de6a-107">操作的名称是该 Oracle 函数的名称。</span><span class="sxs-lookup"><span data-stu-id="5de6a-107">The name of the operation is the name of the Oracle function.</span></span> <span data-ttu-id="5de6a-108">在中，扩展，并在扩展参数支持，以及，返回值。</span><span class="sxs-lookup"><span data-stu-id="5de6a-108">IN, OUT, and IN OUT parameters are supported, as well as, RETURN values.</span></span>  
  
  > [!IMPORTANT]
  >  <span data-ttu-id="5de6a-109">如果在函数中传递了无效的参数 （即，将传递数值字段的字符串值）[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]可能引发取决于 ODP.NET 行为异常。</span><span class="sxs-lookup"><span data-stu-id="5de6a-109">If you pass an invalid parameter in a function (that is, pass a string value for a numeric field), the [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] might throw an exception depending on the ODP.NET behavior.</span></span> <span data-ttu-id="5de6a-110">这是因为[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]使用 ODP.NET 与 Oracle E-business Suite 进行通信。</span><span class="sxs-lookup"><span data-stu-id="5de6a-110">This is because the [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] uses ODP.NET to communicate with Oracle E-Business Suite.</span></span>  
  
- <span data-ttu-id="5de6a-111">**过程**作为操作。</span><span class="sxs-lookup"><span data-stu-id="5de6a-111">**Procedures** are surfaced as operations.</span></span> <span data-ttu-id="5de6a-112">操作的名称是该 Oracle 过程的名称。</span><span class="sxs-lookup"><span data-stu-id="5de6a-112">The name of the operation is the name of the Oracle procedure.</span></span> <span data-ttu-id="5de6a-113">在中，扩展，并在扩展中支持参数。</span><span class="sxs-lookup"><span data-stu-id="5de6a-113">IN, OUT, and IN OUT parameters are supported.</span></span>  
  
  > [!IMPORTANT]
  >  <span data-ttu-id="5de6a-114">过程，如果在插入或更新到接口表或数据库表的数值字段的十进制值 (例如，15.2)[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]将引发异常。</span><span class="sxs-lookup"><span data-stu-id="5de6a-114">As part of a procedure, if you insert or update a decimal value (for example, 15.2) into a numeric field of an interface table or database table, the [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] will throw an exception.</span></span> <span data-ttu-id="5de6a-115">这是因为[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]使用 ODP.NET 通信与 Oracle E-business Suite 和 ODP.NET 不支持接受数值字段的十进制值。</span><span class="sxs-lookup"><span data-stu-id="5de6a-115">This is because the [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] uses ODP.NET to communicate with Oracle E-Business Suite, and ODP.NET does not support accepting decimal values for the numeric fields.</span></span>  
  
- <span data-ttu-id="5de6a-116">**REF CURSOR 类型**支持 IN 和 OUT 参数的过程和函数，以及函数的返回值。</span><span class="sxs-lookup"><span data-stu-id="5de6a-116">**REF CURSOR types** are supported for IN and OUT parameters for procedures and functions, as well as for function RETURN values.</span></span> <span data-ttu-id="5de6a-117">有关详细信息，请参阅[对包含 REF CURSOR 参数函数和过程的操作](../../adapters-and-accelerators/adapter-oracle-ebs/operations-on-functions-and-procedures-with-ref-cursor-parameters1.md)。</span><span class="sxs-lookup"><span data-stu-id="5de6a-117">For more information, see [Operations on Functions and Procedures with REF CURSOR Parameters](../../adapters-and-accelerators/adapter-oracle-ebs/operations-on-functions-and-procedures-with-ref-cursor-parameters1.md).</span></span>  
  
- <span data-ttu-id="5de6a-118">**记录类型**IN、 OUT，支持，以及在 OUT 参数的过程和函数，以及函数的返回值。</span><span class="sxs-lookup"><span data-stu-id="5de6a-118">**RECORD types** are supported for IN, OUT, and IN OUT parameters for procedures and functions, as well as for function RETURN values.</span></span> <span data-ttu-id="5de6a-119">支持简单和复杂 （嵌套） 的记录类型。</span><span class="sxs-lookup"><span data-stu-id="5de6a-119">Both simple and complex (nested) RECORD types are supported.</span></span> [<span data-ttu-id="5de6a-120">对包含 RECORD 类型的函数和过程的操作</span><span class="sxs-lookup"><span data-stu-id="5de6a-120">Operations on Functions and Procedures with RECORD Types</span></span>](../../adapters-and-accelerators/adapter-oracle-ebs/operations-on-functions-and-procedures-with-record-types1.md)  
  
> [!NOTE]
>  <span data-ttu-id="5de6a-121">此外可以设置为函数和存储的过程中的应用程序上下文[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="5de6a-121">You can also set the application context for functions and stored procedures in [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)].</span></span> <span data-ttu-id="5de6a-122">有关应用程序上下文中，以及如何将其设置的信息，请参阅[设置应用程序上下文](../../adapters-and-accelerators/adapter-oracle-ebs/set-application-context.md)。</span><span class="sxs-lookup"><span data-stu-id="5de6a-122">For information about application context, and how to set it, see [Set Application Context](../../adapters-and-accelerators/adapter-oracle-ebs/set-application-context.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5de6a-123">请参阅</span><span class="sxs-lookup"><span data-stu-id="5de6a-123">See Also</span></span>  
 <span data-ttu-id="5de6a-124">[哪些操作可以是执行使用适配器？](https://msdn.microsoft.com/library/cc185219(v=bts.10).aspx)</span><span class="sxs-lookup"><span data-stu-id="5de6a-124">[What Operations Can be Performed Using the Adapter?](https://msdn.microsoft.com/library/cc185219(v=bts.10).aspx)</span></span>