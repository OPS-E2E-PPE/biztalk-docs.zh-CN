---
title: 错误-第二个表循环 Functoid 的输入无效 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- bts10.map.error.secondInputForTableLoopingNotValid
ms.assetid: 22771f36-5969-40b1-a957-3ca67e19c3fd
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 24ab38e947667e894445399e1916fe9e0a3b26fc
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65346919"
---
# <a name="error---second-input-for-table-looping-functoid-not-valid"></a><span data-ttu-id="5aea2-102">错误-第二个表循环 Functoid 的输入无效</span><span class="sxs-lookup"><span data-stu-id="5aea2-102">Error - Second Input for Table Looping Functoid Not Valid</span></span>
<span data-ttu-id="5aea2-103">**错误代码**</span><span class="sxs-lookup"><span data-stu-id="5aea2-103">**Error Code**</span></span>  
  
 <span data-ttu-id="5aea2-104">btm1072</span><span class="sxs-lookup"><span data-stu-id="5aea2-104">btm1072</span></span>  
  
 <span data-ttu-id="5aea2-105">**说明**</span><span class="sxs-lookup"><span data-stu-id="5aea2-105">**Explanation**</span></span>  
  
 <span data-ttu-id="5aea2-106">第二个输入参数的相关**表循环**functoid 不是有效。</span><span class="sxs-lookup"><span data-stu-id="5aea2-106">The second input parameter to the relevant **Table Looping** functoid is not valid.</span></span> <span data-ttu-id="5aea2-107">此参数必须是正整数，用于指示关联表循环网格中的列数。</span><span class="sxs-lookup"><span data-stu-id="5aea2-107">This parameter must be a positive integer that indicates the number of columns in the associated table looping grid.</span></span>  
  
 <span data-ttu-id="5aea2-108">**用户执行任何操作**</span><span class="sxs-lookup"><span data-stu-id="5aea2-108">**User Action**</span></span>  
  
 <span data-ttu-id="5aea2-109">确保输入的参数**表循环**functoid，在通过访问**输入参数**属性并**配置\<Functoid\>Functoid**对话框中下, 表所示。</span><span class="sxs-lookup"><span data-stu-id="5aea2-109">Ensure that the input parameters to the **Table Looping** functoid, as accessed through the **Input Parameters** property and the **Configure \<Functoid\> Functoid** dialog box, are as shown in the following table.</span></span>  
  
|<span data-ttu-id="5aea2-110">表循环 functoid 输入参数编号</span><span class="sxs-lookup"><span data-stu-id="5aea2-110">Table Looping functoid input parameter number</span></span>|<span data-ttu-id="5aea2-111">Description</span><span class="sxs-lookup"><span data-stu-id="5aea2-111">Description</span></span>|  
|---------------------------------------------------|-----------------|  
|<span data-ttu-id="5aea2-112">1</span><span class="sxs-lookup"><span data-stu-id="5aea2-112">1</span></span>|<span data-ttu-id="5aea2-113">输入的实例消息从一条记录的链接或源架构中的字段，其中出现次数控制的一组关联的次数**表提取程序**functoid 的运行。</span><span class="sxs-lookup"><span data-stu-id="5aea2-113">Link from a record or field in the source schema, the number of occurrences of which an input instance message controls the number of times the set of associated **Table Extractor** functoids are run.</span></span>|  
|<span data-ttu-id="5aea2-114">2</span><span class="sxs-lookup"><span data-stu-id="5aea2-114">2</span></span>|<span data-ttu-id="5aea2-115">通过配置的数据表中的列数**表循环网格**属性的相关**表循环**functoid。</span><span class="sxs-lookup"><span data-stu-id="5aea2-115">The number of columns in the data table configured through the **Table Looping Grid** property of the relevant **Table Looping** functoid.</span></span>|  
|<span data-ttu-id="5aea2-116">3 – 100</span><span class="sxs-lookup"><span data-stu-id="5aea2-116">3 – 100</span></span>|<span data-ttu-id="5aea2-117">常量和链接 （来自源架构或来自其他 functoid 的输出中） 将成为可能的与表循环网格的数据源。</span><span class="sxs-lookup"><span data-stu-id="5aea2-117">Constants and links (from the source schema or output from other functoids) that will become possible sources of data with the table looping grid.</span></span>|