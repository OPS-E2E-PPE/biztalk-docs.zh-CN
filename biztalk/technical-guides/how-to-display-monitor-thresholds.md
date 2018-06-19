---
title: 如何显示监视器阈值 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 88d88b15-0691-49d9-b116-1a2ae95bead9
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: be3818512f76e95655e0441f039176fe6f855344
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22297701"
---
# <a name="how-to-display-monitor-thresholds"></a><span data-ttu-id="009a9-102">如何显示监视器阈值</span><span class="sxs-lookup"><span data-stu-id="009a9-102">How to Display Monitor Thresholds</span></span>
<span data-ttu-id="009a9-103">若要显示监视器阈值，请使用本部分中介绍的脚本。</span><span class="sxs-lookup"><span data-stu-id="009a9-103">To display monitor thresholds, use the script described in this section.</span></span> <span data-ttu-id="009a9-104">此脚本适用于多数监视器。</span><span class="sxs-lookup"><span data-stu-id="009a9-104">This script works for the majority of monitors.</span></span> <span data-ttu-id="009a9-105">它创建一个.csv 文件，包括下表中所述列，并可以使用 Office Excel 查看。</span><span class="sxs-lookup"><span data-stu-id="009a9-105">It creates a .csv file that includes the columns described in the following table, and can be viewed using Office Excel.</span></span>  
  
|<span data-ttu-id="009a9-106">列</span><span class="sxs-lookup"><span data-stu-id="009a9-106">Column</span></span>|<span data-ttu-id="009a9-107">Description</span><span class="sxs-lookup"><span data-stu-id="009a9-107">Description</span></span>|  
|------------|-----------------|  
|<span data-ttu-id="009a9-108">类型</span><span class="sxs-lookup"><span data-stu-id="009a9-108">Type</span></span>|<span data-ttu-id="009a9-109">监视器的目标的对象的类型。</span><span class="sxs-lookup"><span data-stu-id="009a9-109">The type of objects the monitor is targeted.</span></span>|  
|<span data-ttu-id="009a9-110">DisplayName</span><span class="sxs-lookup"><span data-stu-id="009a9-110">DisplayName</span></span>|<span data-ttu-id="009a9-111">监视器显示名称。</span><span class="sxs-lookup"><span data-stu-id="009a9-111">The display name of the monitor.</span></span>|  
|<span data-ttu-id="009a9-112">阈值</span><span class="sxs-lookup"><span data-stu-id="009a9-112">Threshold</span></span>|<span data-ttu-id="009a9-113">使用监视器的阈值。</span><span class="sxs-lookup"><span data-stu-id="009a9-113">The threshold used by the monitor.</span></span>|  
|<span data-ttu-id="009a9-114">AlertOnState</span><span class="sxs-lookup"><span data-stu-id="009a9-114">AlertOnState</span></span>|<span data-ttu-id="009a9-115">确定是否监视器生成警报的状态更改时。</span><span class="sxs-lookup"><span data-stu-id="009a9-115">Determines whether the monitor generates an alert when the state changes.</span></span>|  
|<span data-ttu-id="009a9-116">AutoResolveAlert</span><span class="sxs-lookup"><span data-stu-id="009a9-116">AutoResolveAlert</span></span>|<span data-ttu-id="009a9-117">确定当监视器状态将变回绿色时将自动解决生成的警报。</span><span class="sxs-lookup"><span data-stu-id="009a9-117">Determines whether the generated alert will be automatically resolved when the monitor state goes back to green.</span></span>|  
|<span data-ttu-id="009a9-118">AlertSeverity</span><span class="sxs-lookup"><span data-stu-id="009a9-118">AlertSeverity</span></span>|<span data-ttu-id="009a9-119">生成警报的严重性。</span><span class="sxs-lookup"><span data-stu-id="009a9-119">The severity of the generated alert.</span></span>|  
  
#### <a name="to-display-monitor-thresholds"></a><span data-ttu-id="009a9-120">若要显示监视器阈值</span><span class="sxs-lookup"><span data-stu-id="009a9-120">To display monitor thresholds</span></span>  
 <span data-ttu-id="009a9-121">运行以下脚本以创建显示监视器阈值的.csv 文件：</span><span class="sxs-lookup"><span data-stu-id="009a9-121">Run the following script to create the .csv file that displays the monitor thresholds:</span></span>  
  
```  
function GetThreshold ([String] $configuration)   
{   
  $config = [xml] ("<config>" + $configuration + "</config>")   
  $threshold = $config.Config.Threshold   
  if($threshold -eq $null)   
  {   
    $threshold = $config.Config.MemoryThreshold   
  }   
  if($threshold -eq $null)   
  {   
    $threshold = $config.Config.CPUPercentageThreshold   
  }   
  if($threshold -eq $null)   
  {   
    if($config.Config.Threshold1 -ne $null -and $config.Config.Threshold2 -ne $null)   
    {   
      $threshold = "first threshold is: " + $config.Config.Threshold1 + " second threshold is: " + $config.Config.Threshold2   
    }   
  }   
  if($threshold -eq $null)   
  {   
    if($config.Config.ThresholdWarnSec -ne $null -and $config.Config.ThresholdErrorSec -ne $null)   
    {   
      $threshold = "warning threshold is: " + $config.Config.ThresholdWarnSec + " error threshold is: " + $config.Config.ThresholdErrorSec   
    }   
  }   
  if($threshold -eq $null)   
  {   
    if($config.Config.LearningAndBaseliningSettings -ne $null)   
    {   
      $threshold = "no threshold (baseline monitor)"   
    }   
  }   
  return $threshold   
}   
#$perfMonitors = get-monitor -Criteria:"IsUnitMonitor=1 and Category='PerformanceHealth'"   
$perfMonitors = Get-ScommanagementPack -DisplayName "BizTalk Server Monitoring" | get-scommonitor | where-object{$_.XmlTag -eq "UnitMonitor" -and $_.Category -eq "PerformanceHealth"}  
  
$perfMonitors | select-object @{name="Target";expression={foreach-object {(Get-SCOMClass -Id:$_.Target.Id).DisplayName}}},DisplayName, @{name="Threshold";expression={foreach-object {GetThreshold $_.Configuration}}}, @{name="AlertOnState";expression={foreach-object {$_.AlertSettings.AlertOnState}}}, @{name="AutoResolveAlert";expression={foreach-object {$_.AlertSettings.AutoResolve}}}, @{name="AlertSeverity";expression={foreach-object {$_.AlertSettings.AlertSeverity}}} | sort Target, DisplayName | export-csv "c:\monitor_thresholds.csv"  
  
```