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
ms.openlocfilehash: 72e2651c38d3cc69e5c6d7c7d80c6e0d29136033
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36966598"
---
# <a name="string-functoids"></a><span data-ttu-id="4a32f-102">“字符串”Functoid</span><span class="sxs-lookup"><span data-stu-id="4a32f-102">String Functoids</span></span>

## <a name="overview"></a><span data-ttu-id="4a32f-103">概述</span><span class="sxs-lookup"><span data-stu-id="4a32f-103">Overview</span></span>
<span data-ttu-id="4a32f-104">**字符串**functoid 用于以标准方式转换为全部大写或全部小写、 字符串连接、 确定字符串长度、 空白裁剪等操作字符串和其他操作。</span><span class="sxs-lookup"><span data-stu-id="4a32f-104">**String** functoids are used to manipulate strings in standard ways such as conversions to all uppercase or all lowercase, string concatenation, determination of string length, white space trimming, and so on.</span></span>  

 <span data-ttu-id="4a32f-105">这些 functoid**所有字母都大写**，**小写**，**大小**，**字符串右侧空格裁剪**，并**字符串左侧空格裁剪**只接受一个输入的参数。</span><span class="sxs-lookup"><span data-stu-id="4a32f-105">The functoids **Uppercase**, **Lowercase**, **Size**, **String Right Trim**, and **String Left Trim** accept only one input parameter.</span></span> <span data-ttu-id="4a32f-106">这些 functoid**字符串查找**，**左侧字符串提取**，并**右侧字符串提取**接受两个输入参数。</span><span class="sxs-lookup"><span data-stu-id="4a32f-106">The functoids **String Find**, **String Left**, and **String Right** accept two input parameters.</span></span> <span data-ttu-id="4a32f-107">**字符串中提取**functoid 接受三个输入，而**字符串连接**functoid 接受 1 到 100 之间的输入的参数。</span><span class="sxs-lookup"><span data-stu-id="4a32f-107">The **String Extract** functoid accepts three inputs, whereas the **String Concatenate** functoid accepts input parameters between 1 and 100.</span></span>  

 <span data-ttu-id="4a32f-108">两个**字符串**functoid 引用字符串中字符的数字位置：**字符串提取**并**字符串查找**。</span><span class="sxs-lookup"><span data-stu-id="4a32f-108">Two **String** functoids refer to the numeric position of a character in a string: **String Extract** and **String Find**.</span></span> <span data-ttu-id="4a32f-109">这些 functoid 在 1 处而不是在 0 处开始计数字符位置。</span><span class="sxs-lookup"><span data-stu-id="4a32f-109">These functoids begin counting character positions at 1, not 0.</span></span>  

 <span data-ttu-id="4a32f-110">这两个字符串裁剪 functoid**字符串左侧空格裁剪**并**字符串右侧空格裁剪**，删除所有空白字符 （空格、 制表符等） 从左侧或右侧 （如可能是这种情况） 的指定字符串。</span><span class="sxs-lookup"><span data-stu-id="4a32f-110">The two string trimming functoids, **String Left Trim** and **String Right Trim**, remove all white space characters (spaces, tabs, and so on) from the left  or right (as the case may be) of the specified string.</span></span>  

## <a name="available-functoids"></a><span data-ttu-id="4a32f-111">可用的 functoid</span><span class="sxs-lookup"><span data-stu-id="4a32f-111">Available functoids</span></span> 
 <span data-ttu-id="4a32f-112">**字符串**functoid 包括：</span><span class="sxs-lookup"><span data-stu-id="4a32f-112">The **String** functoids are:</span></span> 

* <span data-ttu-id="4a32f-113">Lowercase</span><span class="sxs-lookup"><span data-stu-id="4a32f-113">Lowercase</span></span>
* <span data-ttu-id="4a32f-114">Size</span><span class="sxs-lookup"><span data-stu-id="4a32f-114">Size</span></span>
* <span data-ttu-id="4a32f-115">字符串连接</span><span class="sxs-lookup"><span data-stu-id="4a32f-115">String Concatenate</span></span>
* <span data-ttu-id="4a32f-116">字符串提取</span><span class="sxs-lookup"><span data-stu-id="4a32f-116">String Extract</span></span>
* <span data-ttu-id="4a32f-117">字符串查找</span><span class="sxs-lookup"><span data-stu-id="4a32f-117">String Find</span></span>
* <span data-ttu-id="4a32f-118">左侧字符串提取</span><span class="sxs-lookup"><span data-stu-id="4a32f-118">String Left</span></span>
* <span data-ttu-id="4a32f-119">字符串左侧空格裁剪</span><span class="sxs-lookup"><span data-stu-id="4a32f-119">String Left Trim</span></span>
* <span data-ttu-id="4a32f-120">右侧字符串提取</span><span class="sxs-lookup"><span data-stu-id="4a32f-120">String Right</span></span>
* <span data-ttu-id="4a32f-121">字符串右侧空格裁剪</span><span class="sxs-lookup"><span data-stu-id="4a32f-121">String Right Trim</span></span>
* <span data-ttu-id="4a32f-122">大写</span><span class="sxs-lookup"><span data-stu-id="4a32f-122">Uppercase</span></span>

<span data-ttu-id="4a32f-123">这些 functoid 的详细信息[!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]。</span><span class="sxs-lookup"><span data-stu-id="4a32f-123">More details on these functoids [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)].</span></span>

## <a name="see-also"></a><span data-ttu-id="4a32f-124">请参阅</span><span class="sxs-lookup"><span data-stu-id="4a32f-124">See Also</span></span>  
- [<span data-ttu-id="4a32f-125">如何向映射添加基本 Functoid</span><span class="sxs-lookup"><span data-stu-id="4a32f-125">How to Add Basic Functoids to a Map</span></span>](../core/how-to-add-basic-functoids-to-a-map.md)   
- <span data-ttu-id="4a32f-126">**字符串 Functoid 参考** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]</span><span class="sxs-lookup"><span data-stu-id="4a32f-126">**String Functoids Reference** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]</span></span>
