---
title: 错误-表循环 Functoid 不是有效的输入参数个数 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- bts10.map.error.badParamCountForTableLooping
ms.assetid: 616e54aa-f6e3-4a49-afe2-278a0724e226
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 68cc75282c7dd18925f39b339521d8ecb41911b9
ms.sourcegitcommit: d27732e569b0897361dfaebca8352aa97bb7efe1
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/10/2019
ms.locfileid: "65530727"
---
# <a name="error---input-parameter-count-for-table-looping-functoid-not-valid"></a><span data-ttu-id="b8952-102">错误-表循环 Functoid 不是有效的输入参数个数</span><span class="sxs-lookup"><span data-stu-id="b8952-102">Error - Input Parameter Count for Table Looping Functoid Not Valid</span></span>
<span data-ttu-id="b8952-103">**错误代码**</span><span class="sxs-lookup"><span data-stu-id="b8952-103">**Error Code**</span></span>  
  
 <span data-ttu-id="b8952-104">btm1070</span><span class="sxs-lookup"><span data-stu-id="b8952-104">btm1070</span></span>  
  
 <span data-ttu-id="b8952-105">**说明**</span><span class="sxs-lookup"><span data-stu-id="b8952-105">**Explanation**</span></span>  
  
 <span data-ttu-id="b8952-106">指定相关的输入参数的数目**表循环**functoid 不是有效。</span><span class="sxs-lookup"><span data-stu-id="b8952-106">The number of input parameters specified for the relevant **Table Looping** functoid is not valid.</span></span>  
  
 <span data-ttu-id="b8952-107">**用户执行任何操作**</span><span class="sxs-lookup"><span data-stu-id="b8952-107">**User Action**</span></span>  
  
 <span data-ttu-id="b8952-108">确保输入的参数**表循环**functoid，在通过访问**输入参数**属性并**配置\<Functoid\>Functoid**对话框中下, 表所示。</span><span class="sxs-lookup"><span data-stu-id="b8952-108">Ensure that the input parameters to the **Table Looping** functoid, as accessed through the **Input Parameters** property and the **Configure \<Functoid\> Functoid** dialog box, are as shown in the following table.</span></span>  
  
|<span data-ttu-id="b8952-109">表循环 functoid 输入参数编号</span><span class="sxs-lookup"><span data-stu-id="b8952-109">Table Looping functoid input parameter number</span></span>|<span data-ttu-id="b8952-110">Description</span><span class="sxs-lookup"><span data-stu-id="b8952-110">Description</span></span>|  
|---------------------------------------------------|-----------------|  
|<span data-ttu-id="b8952-111">1</span><span class="sxs-lookup"><span data-stu-id="b8952-111">1</span></span>|<span data-ttu-id="b8952-112">输入的实例消息从一条记录的链接或源架构中的字段，其中出现次数控制的一组关联的次数**表提取程序**functoid 的运行。</span><span class="sxs-lookup"><span data-stu-id="b8952-112">Link from a record or field in the source schema, the number of occurrences of which an input instance message controls the number of times the set of associated **Table Extractor** functoids are run.</span></span>|  
|<span data-ttu-id="b8952-113">2</span><span class="sxs-lookup"><span data-stu-id="b8952-113">2</span></span>|<span data-ttu-id="b8952-114">通过配置的数据表中的列数**表循环网格**属性的相关**表循环**functoid。</span><span class="sxs-lookup"><span data-stu-id="b8952-114">The number of columns in the data table configured through the **Table Looping Grid** property of the relevant **Table Looping** functoid.</span></span>|  
|<span data-ttu-id="b8952-115">3 – 100</span><span class="sxs-lookup"><span data-stu-id="b8952-115">3 – 100</span></span>|<span data-ttu-id="b8952-116">常量和链接 （来自源架构或来自其他 functoid 的输出中） 将成为可能的与表循环网格的数据源。</span><span class="sxs-lookup"><span data-stu-id="b8952-116">Constants and links (from the source schema or output from other functoids) that will become possible sources of data with the table looping grid.</span></span>|