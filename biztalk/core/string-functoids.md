---
title: 字符串 Functoid |Microsoft Docs
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
ms.openlocfilehash: f2da7881495d2c685faaba6f9c9cf00eb565a7af
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65244153"
---
# <a name="string-functoids"></a><span data-ttu-id="0ddca-102">字符串 Functoid</span><span class="sxs-lookup"><span data-stu-id="0ddca-102">String Functoids</span></span>

## <a name="overview"></a><span data-ttu-id="0ddca-103">概述</span><span class="sxs-lookup"><span data-stu-id="0ddca-103">Overview</span></span>
<span data-ttu-id="0ddca-104">**字符串**functoid 用于以标准方式转换为全部大写或全部小写、 字符串连接、 确定字符串长度、 空白裁剪等操作字符串和其他操作。</span><span class="sxs-lookup"><span data-stu-id="0ddca-104">**String** functoids are used to manipulate strings in standard ways such as conversions to all uppercase or all lowercase, string concatenation, determination of string length, white space trimming, and so on.</span></span>  

 <span data-ttu-id="0ddca-105">这些 functoid**所有字母都大写**，**小写**，**大小**，**字符串右侧空格裁剪**，并**字符串左侧空格裁剪**只接受一个输入的参数。</span><span class="sxs-lookup"><span data-stu-id="0ddca-105">The functoids **Uppercase**, **Lowercase**, **Size**, **String Right Trim**, and **String Left Trim** accept only one input parameter.</span></span> <span data-ttu-id="0ddca-106">这些 functoid**字符串查找**，**左侧字符串提取**，并**右侧字符串提取**接受两个输入参数。</span><span class="sxs-lookup"><span data-stu-id="0ddca-106">The functoids **String Find**, **String Left**, and **String Right** accept two input parameters.</span></span> <span data-ttu-id="0ddca-107">**字符串中提取**functoid 接受三个输入，而**字符串连接**functoid 接受 1 到 100 之间的输入的参数。</span><span class="sxs-lookup"><span data-stu-id="0ddca-107">The **String Extract** functoid accepts three inputs, whereas the **String Concatenate** functoid accepts input parameters between 1 and 100.</span></span>  

 <span data-ttu-id="0ddca-108">两个**字符串**functoid 引用字符串中字符的数字位置：**字符串提取**并**字符串查找**。</span><span class="sxs-lookup"><span data-stu-id="0ddca-108">Two **String** functoids refer to the numeric position of a character in a string: **String Extract** and **String Find**.</span></span> <span data-ttu-id="0ddca-109">这些 functoid 开始计数字符位置 1，而不是 0。</span><span class="sxs-lookup"><span data-stu-id="0ddca-109">These functoids begin counting character positions at 1, not 0.</span></span>  

 <span data-ttu-id="0ddca-110">这两个字符串裁剪 functoid**字符串左侧空格裁剪**并**字符串右侧空格裁剪**，删除所有空白字符 （空格、 制表符等） 从左侧或右侧 （如可能是这种情况） 的指定字符串。</span><span class="sxs-lookup"><span data-stu-id="0ddca-110">The two string trimming functoids, **String Left Trim** and **String Right Trim**, remove all white space characters (spaces, tabs, and so on) from the left  or right (as the case may be) of the specified string.</span></span>  

## <a name="available-functoids"></a><span data-ttu-id="0ddca-111">可用的 functoid</span><span class="sxs-lookup"><span data-stu-id="0ddca-111">Available functoids</span></span> 
 <span data-ttu-id="0ddca-112">**字符串**functoid 包括：</span><span class="sxs-lookup"><span data-stu-id="0ddca-112">The **String** functoids are:</span></span> 

* <span data-ttu-id="0ddca-113">Lowercase</span><span class="sxs-lookup"><span data-stu-id="0ddca-113">Lowercase</span></span>
* <span data-ttu-id="0ddca-114">大小</span><span class="sxs-lookup"><span data-stu-id="0ddca-114">Size</span></span>
* <span data-ttu-id="0ddca-115">字符串连接</span><span class="sxs-lookup"><span data-stu-id="0ddca-115">String Concatenate</span></span>
* <span data-ttu-id="0ddca-116">字符串提取</span><span class="sxs-lookup"><span data-stu-id="0ddca-116">String Extract</span></span>
* <span data-ttu-id="0ddca-117">字符串查找</span><span class="sxs-lookup"><span data-stu-id="0ddca-117">String Find</span></span>
* <span data-ttu-id="0ddca-118">左侧字符串提取</span><span class="sxs-lookup"><span data-stu-id="0ddca-118">String Left</span></span>
* <span data-ttu-id="0ddca-119">字符串左侧空格裁剪</span><span class="sxs-lookup"><span data-stu-id="0ddca-119">String Left Trim</span></span>
* <span data-ttu-id="0ddca-120">右侧字符串提取</span><span class="sxs-lookup"><span data-stu-id="0ddca-120">String Right</span></span>
* <span data-ttu-id="0ddca-121">字符串右侧空格裁剪</span><span class="sxs-lookup"><span data-stu-id="0ddca-121">String Right Trim</span></span>
* <span data-ttu-id="0ddca-122">大写</span><span class="sxs-lookup"><span data-stu-id="0ddca-122">Uppercase</span></span>

<span data-ttu-id="0ddca-123">这些 functoid 的详细信息[!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]。</span><span class="sxs-lookup"><span data-stu-id="0ddca-123">More details on these functoids [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)].</span></span>

## <a name="see-also"></a><span data-ttu-id="0ddca-124">请参阅</span><span class="sxs-lookup"><span data-stu-id="0ddca-124">See Also</span></span>  
- [<span data-ttu-id="0ddca-125">如何向映射添加基本 Functoid</span><span class="sxs-lookup"><span data-stu-id="0ddca-125">How to Add Basic Functoids to a Map</span></span>](../core/how-to-add-basic-functoids-to-a-map.md)   
- <span data-ttu-id="0ddca-126">**字符串 Functoid 参考** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]</span><span class="sxs-lookup"><span data-stu-id="0ddca-126">**String Functoids Reference** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]</span></span>
