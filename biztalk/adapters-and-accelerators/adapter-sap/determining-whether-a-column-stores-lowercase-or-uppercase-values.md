---
title: 确定列是否存储小写或大写值 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 1edc8332-d8c7-4040-895b-f121fb03df44
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 9a457ddbde4a6a1dcfa3b4d2c4f818d01dcae009
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65373528"
---
# <a name="determining-whether-a-column-stores-lowercase-or-uppercase-values"></a><span data-ttu-id="09268-102">确定列存储小写或大写值</span><span class="sxs-lookup"><span data-stu-id="09268-102">Determining Whether a Column Stores Lowercase or Uppercase Values</span></span>
<span data-ttu-id="09268-103">本部分列出了要在 SAP 系统，以确定是否 SAP 表中的列存储小写或大写字符上执行的高级任务。</span><span class="sxs-lookup"><span data-stu-id="09268-103">This section lists high-level tasks to be performed on the SAP system to determine whether a column in an SAP table stores lowercase or uppercase characters.</span></span> <span data-ttu-id="09268-104">有关详细说明如何执行此任务必须与 SAP 管理员联系或，请参阅 SAP 文档。</span><span class="sxs-lookup"><span data-stu-id="09268-104">For detailed instructions on how to perform this task you must contact your SAP administrator or refer to SAP documentation.</span></span>  
  
### <a name="to-determine-the-case-of-values-stored-in-a-column"></a><span data-ttu-id="09268-105">若要确定在列中存储的值的用例</span><span class="sxs-lookup"><span data-stu-id="09268-105">To determine the case of values stored in a column</span></span>  
  
1.  <span data-ttu-id="09268-106">启动将 SAP GUI。</span><span class="sxs-lookup"><span data-stu-id="09268-106">Start the SAP GUI.</span></span>  
  
2.  <span data-ttu-id="09268-107">转到事务 SE37 并执行 DDIF_TABL_GET。</span><span class="sxs-lookup"><span data-stu-id="09268-107">Go to Transaction SE37 and execute DDIF_TABL_GET.</span></span>  
  
3.  <span data-ttu-id="09268-108">为 NAME 参数指定包含你想要确定字符大小写信息的列的表的名称。</span><span class="sxs-lookup"><span data-stu-id="09268-108">For the NAME parameter, specify the table name containing the column for which you want to determine the character case information.</span></span> <span data-ttu-id="09268-109">例如，KNA1。</span><span class="sxs-lookup"><span data-stu-id="09268-109">For example, KNA1.</span></span>  
  
4.  <span data-ttu-id="09268-110">第一个表参数是 DD03P_TAB。</span><span class="sxs-lookup"><span data-stu-id="09268-110">The first table parameter is DD03P_TAB.</span></span> <span data-ttu-id="09268-111">单击以查看表中的行的参数。</span><span class="sxs-lookup"><span data-stu-id="09268-111">Click the parameter to see the rows in the table.</span></span> <span data-ttu-id="09268-112">此表中的每一行对应一列 （如 KNA1) 表中您指定在步骤 3 中。</span><span class="sxs-lookup"><span data-stu-id="09268-112">Every row in this table corresponds to a column in the table (such as KNA1) you specified in step 3.</span></span>  
  
5.  <span data-ttu-id="09268-113">在 DD03P_TAB，查找每个行的小写形式的列中的值。</span><span class="sxs-lookup"><span data-stu-id="09268-113">In DD03P_TAB, look for the value in the LOWERCASE column for each row.</span></span> <span data-ttu-id="09268-114">如果小写列中的值为 X，（例如 KNA1)，表中的相应列可以存储小写和大写字符。</span><span class="sxs-lookup"><span data-stu-id="09268-114">If the value in the LOWERCASE column is 'X', the corresponding column in the table (such as KNA1), can store both lowercase and uppercase characters.</span></span> <span data-ttu-id="09268-115">如果小写列中的值为空，相应的列只能存储大写字符。</span><span class="sxs-lookup"><span data-stu-id="09268-115">If the value in the LOWERCASE column is empty, the corresponding column can only store uppercase characters.</span></span>  
  
     <span data-ttu-id="09268-116">例如，对于名称行小写字母列是 X。因此，KNA1 中的名称列可以存储大写和小写字符。</span><span class="sxs-lookup"><span data-stu-id="09268-116">For example, for the NAME row the LOWERCASE column is X. So, the NAME column in KNA1 can store both uppercase and lowercase characters.</span></span> <span data-ttu-id="09268-117">但是，对于 LAND1 行小写字母列为空。</span><span class="sxs-lookup"><span data-stu-id="09268-117">However, for the LAND1 row the LOWERCASE column is empty.</span></span> <span data-ttu-id="09268-118">因此，KNA1 表中的 LAND1 列只能存储大写字符。</span><span class="sxs-lookup"><span data-stu-id="09268-118">So, the LAND1 column in KNA1 table can only store uppercase characters.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="09268-119">请参阅</span><span class="sxs-lookup"><span data-stu-id="09268-119">See Also</span></span>  
 [<span data-ttu-id="09268-120">特定的 SAP 适配器方案中使用 SAP GUI 执行任务</span><span class="sxs-lookup"><span data-stu-id="09268-120">Performing Tasks Using the SAP GUI for Specific SAP Adapter Scenarios</span></span>](../../adapters-and-accelerators/adapter-sap/performing-tasks-using-the-sap-gui-for-specific-sap-adapter-scenarios.md)