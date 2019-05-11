---
title: 如何检测 Functoid 的配置问题 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 32afc333-934c-4ffb-b1b5-61af07157200
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: da91fbeb9afc3d6f93a319e82e7e83d396ad4e16
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65385235"
---
# <a name="how-to-detect-configuration-issues-for-a-functoid"></a>如何检测 Functoid 的配置问题
使用映射，时可能会遇到 functoid 和/或链接的配置问题。 BizTalk 映射器使用一个可视化机制，以帮助快速识别与 functoid 配置关联的问题。 此可视指示将呈现为警告注释的 functoid 图标上 (对于例如![Functoid IntelliSense](../core/media/mapper-functoidintellisense.gif "Mapper_FunctoidIntelliSense")) 在关系视图中。 本主题提供有关如何检测 functoid 配置问题的信息。  
  
 当映射器检测到未正确配置 functoid 时，会出现警告状态图标。 将鼠标放到 functoid 还显示的映射器识别的问题的信息摘要。 例如，如果 functoid 不具有最小数量的有效输入，该 functoid 的工具提示将提到所需的输入参数的数目。  
  
## <a name="prerequisites"></a>先决条件  
 此操作需要 BizTalk 映射器正在运行。  
  
### <a name="to-detect-configuration-issues-for-a-functoid"></a>若要检测为 functoid 配置问题  
  
1.  将所需的 functoid 从工具箱拖到网格页。 您会看到带有警告图标的 functoid。  
  
2.  您可以执行以下操作：  
  
    -   将鼠标指针移动到 functoid 上。 工具提示将显示有关错误和需要执行的信息。  
  
         下图显示了配置 functoid"加法。"时含错误信息的工具提示  
  
         ![Functoid 配置中的错误检测](../core/media/errordetectionfunctoid.gif "ErrorDetectionFunctoid")  
  
    -   双击该 functoid。 **配置\<Functoid\> Functoid**对话框显示警告图标根据输入参数。 这表示未配置所选 functoid 的输入的参数。  
  
         下图显示有关"加法"functoid 的输入参数的错误信息。  
  
         ![未配置 functoid 时显示的警告](../core/media/configure-input-parameters-warningicon.gif "Configure_input_parameters_WarningIcon")  
  
## <a name="see-also"></a>请参阅  
 [使用 BizTalk 映射器中的增强功能](../core/using-enhanced-features-in-biztalk-mapper.md)