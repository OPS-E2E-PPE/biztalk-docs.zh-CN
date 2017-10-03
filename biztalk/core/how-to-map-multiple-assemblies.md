---
title: "如何将多个程序集映射 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- assemblies, tracking profiles
- tracking profiles, mapping assemblies
- assemblies, maps
ms.assetid: 136f1943-9643-4551-8b5b-150c4b4bfebe
caps.latest.revision: "12"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 20a55b6e88889ccfa36adcac11fe548ab1b25bc6
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-map-multiple-assemblies"></a>如何映射多个程序集
BizTalk 应用程序可包含多个含有 BAM 活动所引用的数据项的程序集。 以下过程说明如何将多个程序集映射到一个跟踪配置文件。  
  
### <a name="to-map-multiple-assemblies"></a>映射多个程序集  
  
1.  打开现有的跟踪配置文件，或创建一个新跟踪配置文件。 有关创建跟踪配置文件的详细信息，请参阅[如何创建跟踪配置文件](../core/how-to-create-a-tracking-profile.md)。  
  
2.  单击**选择事件源**按钮 （位于右窗格中的跟踪配置文件中相应的编辑器上方）。  
  
3.  选择**选择业务流程计划**从级联菜单的菜单项。  
  
4.  选择要从中业务流程，通过单击包含业务流程中的程序集的父程序集**程序集名称**列表框中，并依次**下一步**。  
  
5.  选择是中的数据项的源的业务流程**Orchestration 名称**列表框中，并依次**确定**。  
  
6.  在右窗格中选择数据项，然后将其拖动到左窗格的活动中的相应节点。  
  
7.  重复步骤 2 至 6 映射其他程序集。  
  
### <a name="to-map-the-second-assembly"></a>映射第二个程序集  
  
1.  单击**选择事件源**。  
  
2.  选择**选择业务流程计划**从级联菜单的菜单项。  
  
3.  选择要从中通过单击包含业务流程中的程序集的业务流程的下一步父程序集**程序集名称**列表框中，并依次**下一步**按钮。  
  
4.  选择是中的数据项的源的业务流程**Orchestration 名称**列表框中，并依次**确定**。  
  
5.  在右窗格中选择数据项，然后将其拖动到左窗格的活动中的相应节点。  
  
## <a name="see-also"></a>另请参阅  
 [如何将映射事件源](../core/how-to-map-event-sources.md)   
 [创建跟踪配置文件](../core/creating-tracking-profiles.md)