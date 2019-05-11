---
title: 如何读取管道组件属性 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- pipeline components, properties
ms.assetid: 10b1c59c-7ba4-453f-9aaa-1ce9ecf31fac
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 1f9a91edb33167ca97ea73949c8419d1df1521ca
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65335687"
---
# <a name="how-to-read-pipeline-component-properties"></a>如何读取管道组件属性
属性窗口包含组件的两部分： 常规属性和组件属性。 常规属性是通用的所有组件，但是它们的值组件之间发生变化。  
  
### <a name="to-read-the-general-properties-for-a-pipeline-component"></a>读取管道组件的常规属性  
  
1.  将管道组件拖放到管道，该阶段，或选择某一组件，如果管道中已存在。  
  
2.  在属性窗口中**常规**部分中，执行以下操作。  
  
    |使用此选项|执行的操作|  
    |--------------|----------------|  
    |**名称**|指明组件名称。|  
    |**程序集**|指示程序集和组件的相关的.NET 信息。|  
    |**说明**|指示管道组件的友好名称。|  
    |**托管**|指示是否已托管管道组件。 **是**如果组件是.NET 托管的组件;**否**如果管道组件是一个 COM 组件。|  
    |**路径**|指示该.NET 组件的完全限定的路径。|  
    |**类型**|指示组件类型，该程序集，以及相关组件的.NET 信息。|  
  
## <a name="see-also"></a>请参阅  
 [配置本地管道组件](../core/configuring-native-pipeline-components.md)   
 [使用管道设计器创建管道](../core/creating-pipelines-with-pipeline-designer.md)