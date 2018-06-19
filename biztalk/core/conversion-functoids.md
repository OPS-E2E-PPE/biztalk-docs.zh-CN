---
title: 转换 Functoid |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 0cd7abcf-f524-4e85-b8d5-d6123767490f
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 192db4b03f80674f2eb90be2255a8682454bde2b
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22237885"
---
# <a name="conversion-functoids"></a><span data-ttu-id="ebd12-102">“转换”Functoid</span><span class="sxs-lookup"><span data-stu-id="ebd12-102">Conversion Functoids</span></span>

## <a name="overview"></a><span data-ttu-id="ebd12-103">概述</span><span class="sxs-lookup"><span data-stu-id="ebd12-103">Overview</span></span>
<span data-ttu-id="ebd12-104">**转换**functoid 用于数字和其 ASCII 等效项，之间进行转换和将 10 个基本数字转换为其以 8 为基数和基本 16 等效项。</span><span class="sxs-lookup"><span data-stu-id="ebd12-104">**Conversion** functoids are used to convert between numbers and their ASCII equivalents, and to convert base 10 numbers to their base 8 and base 16 equivalents.</span></span>  
  
 <span data-ttu-id="ebd12-105">所有“转换”functoid 都只有一个输入参数。</span><span class="sxs-lookup"><span data-stu-id="ebd12-105">All of the conversion functoids take a single input parameter.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="ebd12-106">由于在基础类型系统中，更改**转换**在此版本的 BizTalk 映射程序 functoid 产生在早期版本生成的那些略有不同的结果。</span><span class="sxs-lookup"><span data-stu-id="ebd12-106">Due to changes in the underlying type system, the **Conversion** functoids in this version of BizTalk Mapper produce slightly different results than those produced in previous versions.</span></span> <span data-ttu-id="ebd12-107">例如，在以前版本的 BizTalk 映射器-20 的输入值到**十六进制**functoid 导致 0xFFEC 的输出。</span><span class="sxs-lookup"><span data-stu-id="ebd12-107">For example, in previous versions of BizTalk Mapper an input value of -20 to the **Hexadecimal** functoid resulted in an output of 0xFFEC.</span></span> <span data-ttu-id="ebd12-108">而在此版本中，同样输入值 -20 则会导致输出 0xFFFFFFEC。</span><span class="sxs-lookup"><span data-stu-id="ebd12-108">In this version, the same input value of -20 will result in an output of 0xFFFFFFEC.</span></span>  

## <a name="available-functoids"></a><span data-ttu-id="ebd12-109">可用的 functoid</span><span class="sxs-lookup"><span data-stu-id="ebd12-109">Available functoids</span></span>  
 <span data-ttu-id="ebd12-110">**转换**functoid 均：</span><span class="sxs-lookup"><span data-stu-id="ebd12-110">The **Conversion** functoids are:</span></span> 

* <span data-ttu-id="ebd12-111">ASCII 到字符</span><span class="sxs-lookup"><span data-stu-id="ebd12-111">ASCII to Character</span></span>
* <span data-ttu-id="ebd12-112">字符到 ASCII</span><span class="sxs-lookup"><span data-stu-id="ebd12-112">Character to ASCII</span></span>
* <span data-ttu-id="ebd12-113">Hexadecimal</span><span class="sxs-lookup"><span data-stu-id="ebd12-113">Hexadecimal</span></span>
* <span data-ttu-id="ebd12-114">八进制</span><span class="sxs-lookup"><span data-stu-id="ebd12-114">Octal</span></span>

<span data-ttu-id="ebd12-115">描述了这些 functoid [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]。</span><span class="sxs-lookup"><span data-stu-id="ebd12-115">These functoids are described [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)].</span></span> 

## <a name="see-also"></a><span data-ttu-id="ebd12-116">另请参阅</span><span class="sxs-lookup"><span data-stu-id="ebd12-116">See Also</span></span>  
 [<span data-ttu-id="ebd12-117">如何在向地图添加基本 Functoid</span><span class="sxs-lookup"><span data-stu-id="ebd12-117">How to Add Basic Functoids to a Map</span></span>](../core/how-to-add-basic-functoids-to-a-map.md)   
