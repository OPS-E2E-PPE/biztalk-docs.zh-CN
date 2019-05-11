---
title: 转换 Functoid |Microsoft Docs
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
ms.openlocfilehash: 0b042428f3a67227db6fb53966149458bc279926
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65390250"
---
# <a name="conversion-functoids"></a><span data-ttu-id="85630-102">转换 Functoid</span><span class="sxs-lookup"><span data-stu-id="85630-102">Conversion Functoids</span></span>

## <a name="overview"></a><span data-ttu-id="85630-103">概述</span><span class="sxs-lookup"><span data-stu-id="85630-103">Overview</span></span>
<span data-ttu-id="85630-104">**转换**functoid 用于数字和其 ASCII 等效，之间进行转换和十进制数字转换为其八进制和十六进制的等效值。</span><span class="sxs-lookup"><span data-stu-id="85630-104">**Conversion** functoids are used to convert between numbers and their ASCII equivalents, and to convert base 10 numbers to their base 8 and base 16 equivalents.</span></span>  
  
 <span data-ttu-id="85630-105">转换 functoid 的所有采用一个输入的参数。</span><span class="sxs-lookup"><span data-stu-id="85630-105">All of the conversion functoids take a single input parameter.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="85630-106">由于基础类型系统中的更改**转换**中此版本的 BizTalk 映射器 functoid 的计算产生比以前版本中生成略有不同的结果。</span><span class="sxs-lookup"><span data-stu-id="85630-106">Due to changes in the underlying type system, the **Conversion** functoids in this version of BizTalk Mapper produce slightly different results than those produced in previous versions.</span></span> <span data-ttu-id="85630-107">例如，在以前版本的 BizTalk 映射器输入值-20 到**十六进制**functoid 导致输出 0xffec。</span><span class="sxs-lookup"><span data-stu-id="85630-107">For example, in previous versions of BizTalk Mapper an input value of -20 to the **Hexadecimal** functoid resulted in an output of 0xFFEC.</span></span> <span data-ttu-id="85630-108">在此版本中，同一输入的值-20 会导致输出 0xffffffec。</span><span class="sxs-lookup"><span data-stu-id="85630-108">In this version, the same input value of -20 will result in an output of 0xFFFFFFEC.</span></span>  

## <a name="available-functoids"></a><span data-ttu-id="85630-109">可用的 functoid</span><span class="sxs-lookup"><span data-stu-id="85630-109">Available functoids</span></span>  
 <span data-ttu-id="85630-110">**转换**functoid 包括：</span><span class="sxs-lookup"><span data-stu-id="85630-110">The **Conversion** functoids are:</span></span> 

* <span data-ttu-id="85630-111">ASCII 到字符</span><span class="sxs-lookup"><span data-stu-id="85630-111">ASCII to Character</span></span>
* <span data-ttu-id="85630-112">字符到 ASCII</span><span class="sxs-lookup"><span data-stu-id="85630-112">Character to ASCII</span></span>
* <span data-ttu-id="85630-113">十六进制</span><span class="sxs-lookup"><span data-stu-id="85630-113">Hexadecimal</span></span>
* <span data-ttu-id="85630-114">八进制</span><span class="sxs-lookup"><span data-stu-id="85630-114">Octal</span></span>

<span data-ttu-id="85630-115">介绍了这些 functoid [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]。</span><span class="sxs-lookup"><span data-stu-id="85630-115">These functoids are described [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)].</span></span> 

## <a name="see-also"></a><span data-ttu-id="85630-116">请参阅</span><span class="sxs-lookup"><span data-stu-id="85630-116">See Also</span></span>  
 [<span data-ttu-id="85630-117">如何向映射添加基本 Functoid</span><span class="sxs-lookup"><span data-stu-id="85630-117">How to Add Basic Functoids to a Map</span></span>](../core/how-to-add-basic-functoids-to-a-map.md)   
