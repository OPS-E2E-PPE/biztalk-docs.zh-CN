---
title: 如何将多个程序集映射 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- assemblies, tracking profiles
- tracking profiles, mapping assemblies
- assemblies, maps
ms.assetid: 136f1943-9643-4551-8b5b-150c4b4bfebe
caps.latest.revision: 12
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 0bdd70b7790599255ccd802d7f0e290df763982c
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65336344"
---
# <a name="how-to-map-multiple-assemblies"></a>如何映射多个程序集
BizTalk 应用程序可以包含多个 BAM 活动所引用的数据项目驻留在其中的程序集。 以下过程演示如何将多个程序集映射到跟踪配置文件。  
  
### <a name="to-map-multiple-assemblies"></a>若要将多个程序集映射  
  
1.  打开现有的跟踪配置文件或创建新的跟踪配置文件。 有关创建跟踪配置文件的详细信息，请参阅[如何创建跟踪配置文件](../core/how-to-create-a-tracking-profile.md)。  
  
2.  单击**选择事件源**按钮 （位于跟踪配置文件编辑器中的右窗格上方）。  
  
3.  选择**选择业务流程计划**级联菜单中的菜单项。  
  
4.  选择要从中提取业务流程通过单击包含业务流程中的程序集的父程序集**程序集名称**列表框中，，然后单击**下一步**。  
  
5.  选择业务流程中的数据项的源**业务流程名称**列表框中，，然后单击**确定**。  
  
6.  在右窗格中选择的数据项目，并将其拖到左窗格中的活动中的相应节点。  
  
7.  重复步骤 2 到 6 映射其他程序集。  
  
### <a name="to-map-the-second-assembly"></a>若要映射的第二个程序集  
  
1.  单击**选择事件源**。  
  
2.  选择**选择业务流程计划**级联菜单中的菜单项。  
  
3.  选择要从中提取业务流程通过单击包含业务流程中的程序集的下一步父程序集**程序集名称**列表框中，，然后单击**下一步**按钮。  
  
4.  选择业务流程中的数据项的源**业务流程名称**列表框中，，然后单击**确定**。  
  
5.  在右窗格中选择的数据项目，并将其拖到左窗格中的活动中的相应节点。  
  
## <a name="see-also"></a>请参阅  
 [如何将映射事件源](../core/how-to-map-event-sources.md)   
 [创建跟踪配置文件](../core/creating-tracking-profiles.md)