---
title: "错误-为第二个输入表提取程序 Functoid 不有效 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: bts10.map.error.secondInputForTableExtractorNotValid
ms.assetid: 099f7374-8625-40af-a74b-24c4de941a7b
caps.latest.revision: "6"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 5e674ad6777ebff53fefe053e1b6af46ebc54ef3
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/28/2017
---
# <a name="error---second-input-for-table-extractor-functoid-not-valid"></a><span data-ttu-id="c57c0-102">错误-为第二个输入表提取程序 Functoid 不有效</span><span class="sxs-lookup"><span data-stu-id="c57c0-102">Error - Second Input for Table Extractor Functoid Not Valid</span></span>
<span data-ttu-id="c57c0-103">**错误代码**</span><span class="sxs-lookup"><span data-stu-id="c57c0-103">**Error Code**</span></span>  
  
 <span data-ttu-id="c57c0-104">btm1073</span><span class="sxs-lookup"><span data-stu-id="c57c0-104">btm1073</span></span>  
  
 <span data-ttu-id="c57c0-105">**说明**</span><span class="sxs-lookup"><span data-stu-id="c57c0-105">**Explanation**</span></span>  
  
 <span data-ttu-id="c57c0-106">第二个输入参数相关**表提取程序**functoid 无效。</span><span class="sxs-lookup"><span data-stu-id="c57c0-106">The second input parameter to the relevant **Table Extractor** functoid is not valid.</span></span> <span data-ttu-id="c57c0-107">此参数必须为正整数常量，该值指示表循环为配置的网格中的有效列**表循环**functoid 指示的第一个输入参数。</span><span class="sxs-lookup"><span data-stu-id="c57c0-107">This parameter must be a positive integer constant that indicates a valid column in the table looping grid configured for the **Table Looping** functoid that is indicated by the first input parameter.</span></span>  
  
 <span data-ttu-id="c57c0-108">**用户执行任何操作**</span><span class="sxs-lookup"><span data-stu-id="c57c0-108">**User Action**</span></span>  
  
 <span data-ttu-id="c57c0-109">确保相关的输入的参数**表提取程序**functoid，如通过访问其**输入参数**属性和**配置\<Functoid\>Functoid**对话框中，是下表中所示。</span><span class="sxs-lookup"><span data-stu-id="c57c0-109">Ensure that the input parameters to the relevant **Table Extractor** functoid, as accessed through its **Input Parameters** property and the **Configure \<Functoid\> Functoid** dialog box, are as shown in the following table.</span></span>  
  
|<span data-ttu-id="c57c0-110">表提取程序 functoid 输入的参数数</span><span class="sxs-lookup"><span data-stu-id="c57c0-110">Table Extractor functoid input parameter number</span></span>|<span data-ttu-id="c57c0-111">Description</span><span class="sxs-lookup"><span data-stu-id="c57c0-111">Description</span></span>|  
|-----------------------------------------------------|-----------------|  
|<span data-ttu-id="c57c0-112">1</span><span class="sxs-lookup"><span data-stu-id="c57c0-112">1</span></span>|<span data-ttu-id="c57c0-113">从链接**表循环**从此 functoid**表提取程序**functoid 将拉取列数据，由其第二个参数。</span><span class="sxs-lookup"><span data-stu-id="c57c0-113">Link from the **Table Looping** functoid from which this **Table Extractor** functoid will pull column data as indicated by its second parameter.</span></span>|  
|<span data-ttu-id="c57c0-114">2</span><span class="sxs-lookup"><span data-stu-id="c57c0-114">2</span></span>|<span data-ttu-id="c57c0-115">通过配置的数据表中的有效列数**表循环网格**属性**表循环**functoid 由第一个输入参数指定。</span><span class="sxs-lookup"><span data-stu-id="c57c0-115">The number of a valid column in the data table configured through the **Table Looping Grid** property of the **Table Looping** functoid specified by the first input parameter.</span></span>|