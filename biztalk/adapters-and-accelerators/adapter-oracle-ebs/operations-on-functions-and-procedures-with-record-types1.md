---
title: 对包含记录类型 1> 函数和过程的操作 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: afc1c84f-2e36-493c-9ea8-4bc2248331db
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 6b7d4f392e863dd8966f5c011abfd6e602f2514c
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "37006430"
---
# <a name="operations-on-functions-and-procedures-with-record-types"></a><span data-ttu-id="3bfcb-102">对函数和过程的记录类型的操作</span><span class="sxs-lookup"><span data-stu-id="3bfcb-102">Operations on Functions and Procedures with RECORD Types</span></span>
<span data-ttu-id="3bfcb-103">Oracle 记录类型用于表示层次结构中传递到 PL/SQL 函数和过程的参数信息。</span><span class="sxs-lookup"><span data-stu-id="3bfcb-103">Oracle RECORD types are used to represent hierarchical information in parameters passed to PL/SQL functions and procedures.</span></span> <span data-ttu-id="3bfcb-104">[!INCLUDE[adapteroracle](../../includes/adapteroracle-md.md)]呈现为 XML 的复杂类型的记录类型。</span><span class="sxs-lookup"><span data-stu-id="3bfcb-104">The [!INCLUDE[adapteroracle](../../includes/adapteroracle-md.md)] surfaces RECORD types as complex XML types.</span></span> 

## <a name="supported-record-types"></a><span data-ttu-id="3bfcb-105">支持的记录类型</span><span class="sxs-lookup"><span data-stu-id="3bfcb-105">Supported RECORD types</span></span>
<span data-ttu-id="3bfcb-106">[!INCLUDE[adapteroracleebusinesslong](../../includes/adapteroracleebusinesslong-md.md)]支持以下类型的记录类型：</span><span class="sxs-lookup"><span data-stu-id="3bfcb-106">The [!INCLUDE[adapteroracleebusinesslong](../../includes/adapteroracleebusinesslong-md.md)] supports the following kinds of RECORD types:</span></span>  
  
- <span data-ttu-id="3bfcb-107">声明为表 %行类型参数在存储的过程和函数中的记录类型。</span><span class="sxs-lookup"><span data-stu-id="3bfcb-107">RECORD types that are declared as TABLE%ROWTYPE parameters in stored procedures and functions.</span></span>  
  
- <span data-ttu-id="3bfcb-108">声明为类型的记录参数 PL/SQL 包中的记录类型。</span><span class="sxs-lookup"><span data-stu-id="3bfcb-108">RECORD types that are declared as TYPE of RECORD parameters in PL/SQL packages.</span></span> <span data-ttu-id="3bfcb-109">例如，键入 rec_type1 是 RECORD(name varchar2(100), age number(3));</span><span class="sxs-lookup"><span data-stu-id="3bfcb-109">For example, TYPE rec_type1 IS RECORD(name varchar2(100), age number(3));</span></span>  
  
- <span data-ttu-id="3bfcb-110">包含嵌套的记录的记录类型。</span><span class="sxs-lookup"><span data-stu-id="3bfcb-110">RECORD types that contain nested records.</span></span>  
  
- <span data-ttu-id="3bfcb-111">缩小，显示作为中的记录类型或为过程或函数在 OUT 参数。</span><span class="sxs-lookup"><span data-stu-id="3bfcb-111">RECORD types that appear as IN, OUT, or IN OUT parameters to procedures or functions.</span></span>  
  
- <span data-ttu-id="3bfcb-112">是函数的返回值的记录类型。</span><span class="sxs-lookup"><span data-stu-id="3bfcb-112">RECORD types that are RETURN values of functions.</span></span>  
  
  > [!NOTE]
  >  <span data-ttu-id="3bfcb-113">[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]不支持 BFILE 作为记录成员的类型。</span><span class="sxs-lookup"><span data-stu-id="3bfcb-113">The [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] does not support BFILE types as RECORD members.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3bfcb-114">请参阅</span><span class="sxs-lookup"><span data-stu-id="3bfcb-114">See Also</span></span>  
 <span data-ttu-id="3bfcb-115">[哪些操作可以是执行使用适配器？](https://msdn.microsoft.com/library/cc185219(v=bts.10).aspx)</span><span class="sxs-lookup"><span data-stu-id="3bfcb-115">[What Operations Can be Performed Using the Adapter?](https://msdn.microsoft.com/library/cc185219(v=bts.10).aspx)</span></span>