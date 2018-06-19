---
title: 字符串 Functoid |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 2d73be02-9c93-481f-81e4-39b60bcfa2df
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 06bcb1d42a5e72a57765d17c18a48b6f4808d412
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22278525"
---
# <a name="string-functoids"></a><span data-ttu-id="003f7-102">“字符串”Functoid</span><span class="sxs-lookup"><span data-stu-id="003f7-102">String Functoids</span></span>

## <a name="overview"></a><span data-ttu-id="003f7-103">概述</span><span class="sxs-lookup"><span data-stu-id="003f7-103">Overview</span></span>
<span data-ttu-id="003f7-104">**字符串**functoid 用于操作字符串转换为全部大写或全部为小写，字符串串联，确定的字符串长度，空白区域，如的标准方式，依次类推。</span><span class="sxs-lookup"><span data-stu-id="003f7-104">**String** functoids are used to manipulate strings in standard ways such as conversions to all uppercase or all lowercase, string concatenation, determination of string length, white space trimming, and so on.</span></span>  
  
 <span data-ttu-id="003f7-105">Functoid**所有字母都大写**，**小写**，**大小**，**字符串右侧 Trim**，和**字符串左侧 Trim**接受一个输入的参数。</span><span class="sxs-lookup"><span data-stu-id="003f7-105">The functoids **Uppercase**, **Lowercase**, **Size**, **String Right Trim**, and **String Left Trim** accept only one input parameter.</span></span> <span data-ttu-id="003f7-106">Functoid**字符串查找**，**字符串左侧**，和**字符串右侧**接受两个输入参数。</span><span class="sxs-lookup"><span data-stu-id="003f7-106">The functoids **String Find**, **String Left**, and **String Right** accept two input parameters.</span></span> <span data-ttu-id="003f7-107">**字符串提取**functoid 接受三个输入，而**字符串连接**functoid 接受介于 1 和 100 之间的输入的参数。</span><span class="sxs-lookup"><span data-stu-id="003f7-107">The **String Extract** functoid accepts three inputs, whereas the **String Concatenate** functoid accepts input parameters between 1 and 100.</span></span>  
  
 <span data-ttu-id="003f7-108">两个**字符串**functoid 指字符串中字符的数值位置：**字符串提取**和**字符串查找**。</span><span class="sxs-lookup"><span data-stu-id="003f7-108">Two **String** functoids refer to the numeric position of a character in a string: **String Extract** and **String Find**.</span></span> <span data-ttu-id="003f7-109">这些 functoid 在 1 处而不是在 0 处开始计数字符位置。</span><span class="sxs-lookup"><span data-stu-id="003f7-109">These functoids begin counting character positions at 1, not 0.</span></span>  
  
 <span data-ttu-id="003f7-110">这两个字符串修整 functoid**字符串左侧 Trim**和**字符串右侧 Trim**，删除所有空格字符 （空格、 制表符和等等） 从左侧或右侧 （因为在这种情况可能是） 指定的字符串。</span><span class="sxs-lookup"><span data-stu-id="003f7-110">The two string trimming functoids, **String Left Trim** and **String Right Trim**, remove all white space characters (spaces, tabs, and so on) from the left  or right (as the case may be) of the specified string.</span></span>  

## <a name="available-functoids"></a><span data-ttu-id="003f7-111">可用的 functoid</span><span class="sxs-lookup"><span data-stu-id="003f7-111">Available functoids</span></span> 
 <span data-ttu-id="003f7-112">**字符串**functoid 均：</span><span class="sxs-lookup"><span data-stu-id="003f7-112">The **String** functoids are:</span></span> 

* <span data-ttu-id="003f7-113">Lowercase</span><span class="sxs-lookup"><span data-stu-id="003f7-113">Lowercase</span></span>
* <span data-ttu-id="003f7-114">Size</span><span class="sxs-lookup"><span data-stu-id="003f7-114">Size</span></span>
* <span data-ttu-id="003f7-115">字符串连接</span><span class="sxs-lookup"><span data-stu-id="003f7-115">String Concatenate</span></span>
* <span data-ttu-id="003f7-116">字符串提取</span><span class="sxs-lookup"><span data-stu-id="003f7-116">String Extract</span></span>
* <span data-ttu-id="003f7-117">字符串查找</span><span class="sxs-lookup"><span data-stu-id="003f7-117">String Find</span></span>
* <span data-ttu-id="003f7-118">左侧字符串提取</span><span class="sxs-lookup"><span data-stu-id="003f7-118">String Left</span></span>
* <span data-ttu-id="003f7-119">字符串左侧空格裁剪</span><span class="sxs-lookup"><span data-stu-id="003f7-119">String Left Trim</span></span>
* <span data-ttu-id="003f7-120">右侧字符串提取</span><span class="sxs-lookup"><span data-stu-id="003f7-120">String Right</span></span>
* <span data-ttu-id="003f7-121">字符串右侧空格裁剪</span><span class="sxs-lookup"><span data-stu-id="003f7-121">String Right Trim</span></span>
* <span data-ttu-id="003f7-122">大写</span><span class="sxs-lookup"><span data-stu-id="003f7-122">Uppercase</span></span>

<span data-ttu-id="003f7-123">更多详细信息这些 functoid [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]。</span><span class="sxs-lookup"><span data-stu-id="003f7-123">More details on these functoids [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)].</span></span>
  
## <a name="see-also"></a><span data-ttu-id="003f7-124">另请参阅</span><span class="sxs-lookup"><span data-stu-id="003f7-124">See Also</span></span>  
-  [<span data-ttu-id="003f7-125">如何在向地图添加基本 Functoid</span><span class="sxs-lookup"><span data-stu-id="003f7-125">How to Add Basic Functoids to a Map</span></span>](../core/how-to-add-basic-functoids-to-a-map.md)   
-  <span data-ttu-id="003f7-126">**字符串 Functoid 引用**[!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]</span><span class="sxs-lookup"><span data-stu-id="003f7-126">**String Functoids Reference** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]</span></span>