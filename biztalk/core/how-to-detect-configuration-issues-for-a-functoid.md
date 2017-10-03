---
title: "如何为 Functoid 检测配置问题 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 32afc333-934c-4ffb-b1b5-61af07157200
caps.latest.revision: "9"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 322a97aba4ec5e02cf754106df30b0c9f0088e1b
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-detect-configuration-issues-for-a-functoid"></a>如何检测 Functoid 的配置问题
使用映射时，您可能会遇到 functoid 和/或链接的配置问题。 BizTalk 映射器使用可视化效果机制来帮助快速识别与 functoid 配置相关的问题。 此视觉指示将呈现为 functoid 图标的警告批注 (有关例如![Functoid IntelliSense](../core/media/mapper-functoidintellisense.gif "Mapper_FunctoidIntelliSense")) 的关系视图中。 本主题提供有关如何检测 functoid 配置问题的信息。  
  
 当映射器检测到未正确配置 functoid 时，将显示警告状态图标。 将鼠标放到 functoid 上还会显示有关映射器所发现问题的简短信息。 例如，如果 functoid 不含有最低数量的有效输入，则 functoid 的工具提示将提到要求的输入参数数。  
  
## <a name="prerequisites"></a>先决条件  
 此操作要求 BizTalk 映射器处于运行状态。  
  
### <a name="to-detect-configuration-issues-for-a-functoid"></a>检测 functoid 的配置问题  
  
1.  将所需的 functoid 从工具箱拖到网格页中。 您将看到带有警告图标的 functoid。  
  
2.  您可以执行以下操作之一：  
  
    -   将鼠标指针移到 functoid 上。 此时工具提示将显示有关错误和需要执行的操作信息。  
  
         下图显示了配置 functoid“加法”时含错误信息的工具提示。  
  
         ![Functoid 配置中的错误检测](../core/media/errordetectionfunctoid.gif "ErrorDetectionFunctoid")  
  
    -   双击该 functoid。 **配置\<Functoid > Functoid**对话框中显示针对输入参数的警告图标。 这表明所选 functoid 未配置输入参数。  
  
         下图显示了有关“加法”functoid 输入参数的错误信息。  
  
         ![未配置 functoid 时显示的警告](../core/media/configure-input-parameters-warningicon.gif "Configure_input_parameters_WarningIcon")  
  
## <a name="see-also"></a>另请参阅  
 [在 BizTalk 映射程序中使用增强的功能](../core/using-enhanced-features-in-biztalk-mapper.md)