---
title: 如何显示监视器阈值 |Microsoft Docs
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
ms.openlocfilehash: 92db77c3e13bd479d71f845bd0854d721d2d6938
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65253314"
---
# <a name="how-to-display-monitor-thresholds"></a>如何显示监视器阈值
若要显示监视器阈值，请使用在本部分中所述的脚本。 此脚本适用于多数监视器。 它创建包含下表中所述的列的.csv 文件，可以使用 Office Excel 查看。  
  
|“列”|Description|  
|------------|-----------------|  
|类型|监视器的目标的对象的类型。|  
|DisplayName|监视器的显示名称。|  
|阈值|使用监视器的阈值。|  
|AlertOnState|确定在状态更改时，监视器是否生成警报。|  
|AutoResolveAlert|确定当监视器状态将恢复为绿色时将自动解决生成的警报。|  
|AlertSeverity|生成警报的严重性。|  
  
#### <a name="to-display-monitor-thresholds"></a>若要显示监视器阈值  
 运行以下脚本来创建显示监视器阈值的.csv 文件：  
  
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