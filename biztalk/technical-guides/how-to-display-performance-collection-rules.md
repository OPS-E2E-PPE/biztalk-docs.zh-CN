---
title: "如何显示性能收集规则 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 546aa853-c372-4e26-a1ed-19294c658583
caps.latest.revision: "6"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: cd7b7d1d2e368572740a3c7a54799bc56b2330e3
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-display-performance-collection-rules"></a><span data-ttu-id="a843a-102">如何显示性能收集规则</span><span class="sxs-lookup"><span data-stu-id="a843a-102">How to Display Performance Collection Rules</span></span>
<span data-ttu-id="a843a-103">若要显示性能收集规则，使用此部分中的脚本。</span><span class="sxs-lookup"><span data-stu-id="a843a-103">To display performance collection rules, use the script in this section.</span></span> <span data-ttu-id="a843a-104">此脚本适用于大多数规则。</span><span class="sxs-lookup"><span data-stu-id="a843a-104">This script works for the majority of rules.</span></span> <span data-ttu-id="a843a-105">它创建一个.csv 文件，包括下表中列出的列，并可以使用 Office Excel 查看。</span><span class="sxs-lookup"><span data-stu-id="a843a-105">It creates a .csv file that includes the columns listed in the following table, and can be viewed using Office Excel.</span></span>  
  
|<span data-ttu-id="a843a-106">列</span><span class="sxs-lookup"><span data-stu-id="a843a-106">Column</span></span>|<span data-ttu-id="a843a-107">Description</span><span class="sxs-lookup"><span data-stu-id="a843a-107">Description</span></span>|  
|------------|-----------------|  
|<span data-ttu-id="a843a-108">WriteToDB 或 CollectionPerformanceData</span><span class="sxs-lookup"><span data-stu-id="a843a-108">WriteToDB or CollectionPerformanceData</span></span>|<span data-ttu-id="a843a-109">写入 Operations Manager 数据库。</span><span class="sxs-lookup"><span data-stu-id="a843a-109">Writes to the Operations Manager database.</span></span>|  
|<span data-ttu-id="a843a-110">WriteToDW 或 CollectPerfDataWarehouse</span><span class="sxs-lookup"><span data-stu-id="a843a-110">WriteToDW or CollectPerfDataWarehouse</span></span>|<span data-ttu-id="a843a-111">写入数据仓库。</span><span class="sxs-lookup"><span data-stu-id="a843a-111">Writes to the data warehouse.</span></span>|  
|<span data-ttu-id="a843a-112">WC</span><span class="sxs-lookup"><span data-stu-id="a843a-112">WC</span></span>|<span data-ttu-id="a843a-113">将性能计数器的基准数据存储到操作数据库。</span><span class="sxs-lookup"><span data-stu-id="a843a-113">Stores baseline data for a performance counter into the operational database.</span></span>|  
  
#### <a name="to-display-performance-collection-rules"></a><span data-ttu-id="a843a-114">若要显示性能收集规则</span><span class="sxs-lookup"><span data-stu-id="a843a-114">To display performance collection rules</span></span>  
 <span data-ttu-id="a843a-115">若要显示管理组中的性能收集规则，请运行以下脚本：</span><span class="sxs-lookup"><span data-stu-id="a843a-115">To display the performance collection rules in the management group, run the following script:</span></span>  
  
```  
function GetPerfCounterName ([String] $configuration)   
{   
$config = [xml] ("<config>" + $configuration + "</config>")   
return ($config.Config.ObjectName + "\" + $config.Config.CounterName)   
}   
function GetFrequency ([String] $configuration)   
{   
$config = [xml] ("<config>" + $configuration + "</config>")   
$frequency = $config.Config.Frequency;   
if($frequency -eq $null)   
{   
$frequency = $config.Config.IntervalSeconds;   
}   
return ($frequency)   
}   
function GetDisplayName($performanceRule)   
{   
if($performanceRule.DisplayName -eq $null)   
{   
return ($performanceRule.Name);   
}   
else   
{   
return ($performanceRule.DisplayName);   
}   
}   
function GetWriteActionNames($performanceRule)   
{   
$writeActions = "";   
foreach($writeAction in $performanceRule.WriteActionCollection)   
{   
$writeActions += " " + $writeAction.Name;   
}   
return ($writeActions);   
}   
$perf_collection_rules = Get-SCOMManagementPack -DisplayName "BizTalk Server Monitoring" | Get-SCOMRule | where-object{$_.Category -eq "PerformanceCollection"}  
  
$perf_collection_rules | select-object @{name="Type";expression={foreach-object {(Get-SCOMClass -id:$_.Target.Id).DisplayName}}},@{name="RuleDisplayName";expression={foreach-object {GetDisplayName $_}}} ,@{name="CounterName";expression={foreach-object {GetPerfCounterName $_.DataSourceCollection[0].Configuration}}},@{name="Frequency";expression={foreach-object {GetFrequency $_.DataSourceCollection[0].Configuration}}},@{name="WriteActions";expression={foreach-object {GetWriteActionNames $_}}} | sort Type,RuleDisplayName,CounterName | export-csv "c:\perf_collection_rules.csv"  
  
```