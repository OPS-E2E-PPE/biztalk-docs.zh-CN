---
title: 错误-表循环数据无效 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- bts10.map.error.tableLoopingDataNotValid
ms.assetid: 19c38e79-bab0-4899-ae24-e1485327e891
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e62678e7dc4e0aceee128cb24bc0ff34129168cd
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65388410"
---
# <a name="error---table-looping-data-not-valid"></a><span data-ttu-id="7e379-102">错误-表循环数据无效</span><span class="sxs-lookup"><span data-stu-id="7e379-102">Error - Table Looping Data Not Valid</span></span>
<span data-ttu-id="7e379-103">**错误代码**</span><span class="sxs-lookup"><span data-stu-id="7e379-103">**Error Code**</span></span>  
  
 <span data-ttu-id="7e379-104">btm1065</span><span class="sxs-lookup"><span data-stu-id="7e379-104">btm1065</span></span>  
  
 <span data-ttu-id="7e379-105">**说明**</span><span class="sxs-lookup"><span data-stu-id="7e379-105">**Explanation**</span></span>  
  
 <span data-ttu-id="7e379-106">关联与相关的数据的表**表循环**functoid 不是有效的很可能是由于该 functoid 或未正确配置的表循环网格的配置不正确第二个输入参数。</span><span class="sxs-lookup"><span data-stu-id="7e379-106">The table of data associated with the relevant **Table Looping** functoid is not valid, probably due to an incorrectly configured second input parameter to the functoid, or an incorrectly configured table looping grid.</span></span>  
  
 <span data-ttu-id="7e379-107">**用户执行任何操作**</span><span class="sxs-lookup"><span data-stu-id="7e379-107">**User Action**</span></span>  
  
 <span data-ttu-id="7e379-108">确保输入的参数**表循环**functoid，在通过访问**输入参数**属性并**配置\<Functoid\>Functoid**对话框中下, 表所示。</span><span class="sxs-lookup"><span data-stu-id="7e379-108">Ensure that the input parameters to the **Table Looping** functoid, as accessed through the **Input Parameters** property and the **Configure \<Functoid\> Functoid** dialog box, are as shown in the following table.</span></span>  
  
|<span data-ttu-id="7e379-109">表循环 functoid 输入参数编号</span><span class="sxs-lookup"><span data-stu-id="7e379-109">Table Looping functoid input parameter number</span></span>|<span data-ttu-id="7e379-110">Description</span><span class="sxs-lookup"><span data-stu-id="7e379-110">Description</span></span>|  
|---------------------------------------------------|-----------------|  
|<span data-ttu-id="7e379-111">1</span><span class="sxs-lookup"><span data-stu-id="7e379-111">1</span></span>|<span data-ttu-id="7e379-112">输入的实例消息从一条记录的链接或源架构中的字段，其中出现次数控制的一组关联的次数**表提取程序**functoid 的运行。</span><span class="sxs-lookup"><span data-stu-id="7e379-112">Link from a record or field in the source schema, the number of occurrences of which an input instance message controls the number of times the set of associated **Table Extractor** functoids are run.</span></span>|  
|<span data-ttu-id="7e379-113">2</span><span class="sxs-lookup"><span data-stu-id="7e379-113">2</span></span>|<span data-ttu-id="7e379-114">通过配置的数据表中的列数**表循环网格**属性的相关**表循环**functoid。</span><span class="sxs-lookup"><span data-stu-id="7e379-114">The number of columns in the data table configured through the **Table Looping Grid** property of the relevant **Table Looping** functoid.</span></span>|  
|<span data-ttu-id="7e379-115">3 – 100</span><span class="sxs-lookup"><span data-stu-id="7e379-115">3 – 100</span></span>|<span data-ttu-id="7e379-116">常量和链接 （来自源架构或来自其他 functoid 的输出中） 将成为可能的与表循环网格的数据源。</span><span class="sxs-lookup"><span data-stu-id="7e379-116">Constants and links (from the source schema or output from other functoids) that will become possible sources of data with the table looping grid.</span></span>|  
  
 <span data-ttu-id="7e379-117">另外，请确保正确配置表循环网格中，通过**表循环网格**属性和**表循环配置**对话框。</span><span class="sxs-lookup"><span data-stu-id="7e379-117">Also, ensure that you properly configure the table looping grid, as accessed through the **Table Looping Grid** property and the **Table Looping Configuration** dialog box.</span></span> <span data-ttu-id="7e379-118">必须将访问每个单元格选择一个常数或链接的值由关联**表提取程序**functoid。</span><span class="sxs-lookup"><span data-stu-id="7e379-118">A constant or link value must be chosen for every cell that will be accessed by an associated **Table Extractor** functoid.</span></span>