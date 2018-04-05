---
title: 如何读取管道组件属性 |Microsoft 文档
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
ms.openlocfilehash: 19a6ccbcbe7588a0a75b4dbe6bf821a19fab965c
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-read-pipeline-component-properties"></a>如何读取管道组件属性
“属性”窗口包含组件的两部分：常规属性和组件属性。 常规属性是所有组件共有的属性，尽管常规属性的值在各个组件中都有所不同。  
  
### <a name="to-read-the-general-properties-for-a-pipeline-component"></a>读取管道组件的常规属性  
  
1.  将管道组件拖至管道的某个阶段中，或者如果管道组件已存在于管道中，则选择该组件。  
  
2.  在属性窗口中，在**常规**部分中，执行以下操作。  
  
    |使用此选项|执行的操作|  
    |--------------|----------------|  
    |**名称**|指明组件名称。|  
    |**程序集**|指明该组件的程序集和相关 .NET 信息。|  
    |**Description**|指明该管道组件的友好名称。|  
    |**管理**|指明是否托管该管道组件。 **是**如果组件为.NET 托管的组件;**否**如果管道组件是一个 COM 组件。|  
    |**路径**|指明该 .NET 组件的完全限定路径。|  
    |**类型**|指明该组件的组件类型、程序集和相关的 .NET 信息。|  
  
## <a name="see-also"></a>另请参阅  
 [配置本机管道组件](../core/configuring-native-pipeline-components.md)   
 [使用管道设计器中创建管道](../core/creating-pipelines-with-pipeline-designer.md)