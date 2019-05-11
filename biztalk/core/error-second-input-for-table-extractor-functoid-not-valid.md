---
title: 错误-第二个表提取程序 Functoid 的输入不有效 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- bts10.map.error.secondInputForTableExtractorNotValid
ms.assetid: 099f7374-8625-40af-a74b-24c4de941a7b
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 3c53e84e62422a70214a4cfd90979de85538e158
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65388439"
---
# <a name="error---second-input-for-table-extractor-functoid-not-valid"></a><span data-ttu-id="c1e3e-102">错误-第二个表提取程序 Functoid 的输入不有效</span><span class="sxs-lookup"><span data-stu-id="c1e3e-102">Error - Second Input for Table Extractor Functoid Not Valid</span></span>
<span data-ttu-id="c1e3e-103">**错误代码**</span><span class="sxs-lookup"><span data-stu-id="c1e3e-103">**Error Code**</span></span>  
  
 <span data-ttu-id="c1e3e-104">btm1073</span><span class="sxs-lookup"><span data-stu-id="c1e3e-104">btm1073</span></span>  
  
 <span data-ttu-id="c1e3e-105">**说明**</span><span class="sxs-lookup"><span data-stu-id="c1e3e-105">**Explanation**</span></span>  
  
 <span data-ttu-id="c1e3e-106">第二个输入参数的相关**表提取程序**functoid 不是有效。</span><span class="sxs-lookup"><span data-stu-id="c1e3e-106">The second input parameter to the relevant **Table Extractor** functoid is not valid.</span></span> <span data-ttu-id="c1e3e-107">此参数必须是一个正整数常量，它指示表循环网格为配置中的有效列**表循环**由第一个输入参数指示的 functoid。</span><span class="sxs-lookup"><span data-stu-id="c1e3e-107">This parameter must be a positive integer constant that indicates a valid column in the table looping grid configured for the **Table Looping** functoid that is indicated by the first input parameter.</span></span>  
  
 <span data-ttu-id="c1e3e-108">**用户执行任何操作**</span><span class="sxs-lookup"><span data-stu-id="c1e3e-108">**User Action**</span></span>  
  
 <span data-ttu-id="c1e3e-109">确保相关的输入的参数**表提取程序**functoid，在通过访问其**输入参数**属性并**配置\<Functoid\>Functoid**对话框中下, 表所示。</span><span class="sxs-lookup"><span data-stu-id="c1e3e-109">Ensure that the input parameters to the relevant **Table Extractor** functoid, as accessed through its **Input Parameters** property and the **Configure \<Functoid\> Functoid** dialog box, are as shown in the following table.</span></span>  
  
|<span data-ttu-id="c1e3e-110">表提取程序 functoid 输入参数编号</span><span class="sxs-lookup"><span data-stu-id="c1e3e-110">Table Extractor functoid input parameter number</span></span>|<span data-ttu-id="c1e3e-111">Description</span><span class="sxs-lookup"><span data-stu-id="c1e3e-111">Description</span></span>|  
|-----------------------------------------------------|-----------------|  
|<span data-ttu-id="c1e3e-112">1</span><span class="sxs-lookup"><span data-stu-id="c1e3e-112">1</span></span>|<span data-ttu-id="c1e3e-113">从链接**表循环**functoid 从中**表提取程序**functoid 将提取列数据，由其第二个参数。</span><span class="sxs-lookup"><span data-stu-id="c1e3e-113">Link from the **Table Looping** functoid from which this **Table Extractor** functoid will pull column data as indicated by its second parameter.</span></span>|  
|<span data-ttu-id="c1e3e-114">2</span><span class="sxs-lookup"><span data-stu-id="c1e3e-114">2</span></span>|<span data-ttu-id="c1e3e-115">通过配置的数据表中的有效列数**表循环网格**的属性**表循环**functoid 指定的第一个输入参数。</span><span class="sxs-lookup"><span data-stu-id="c1e3e-115">The number of a valid column in the data table configured through the **Table Looping Grid** property of the **Table Looping** functoid specified by the first input parameter.</span></span>|