---
title: 开发探测管道组件 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- pipeline components [custom], probing
- IProbeMessage interface
- pipeline interfaces, IProbeMessage
ms.assetid: c3da467d-5270-4c7f-9c38-ce9989bf1b63
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 54da9d0433b0ca416e5c0da797a4d4c8678aab8a
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65389454"
---
# <a name="developing-a-probing-pipeline-component"></a>开发探测管道组件
任何管道组件 （一般、 组装或拆装） 都可以实现`IProbeMessage`接口是否必须支持消息探测功能。 探测组件用于具有的管道阶段**第一个匹配**执行模式。 在此类阶段中，BizTalk 消息引擎的消息的开始部分提供给组件，以便确定组件是否识别的消息的格式。 如果组件识别格式，则整个消息交给此组件进行处理。  
  
 **IProbeMessage**接口公开单个方法**探测**，这使组件可以检查消息的开始部分。 返回值确定是否运行此组件。 以下步骤概述了 BizTalk 消息引擎如何运行需要识别的阶段：  
  
1. 如果阶段不包含任何组件，则不会运行阶段和消息交给随后的阶段进行处理。  
  
2. 检查组件是否实现**IProbeMessage**接口。 如果没有，消息引擎调用该组件。 阶段处理完成，消息交给下一个阶段。  
  
3. **探测**调用方法。 如果返回值是 **，则返回 True**，该组件已运行。 然后阶段处理完成，并将消息提供给下一个阶段。  
  
4. 消息引擎获取阶段中的下一个组件。 如果没有更多组件，并且所有组件已运行，则将生成错误的管道处理失败。 如果没有更多组件并且至少一个组件都已运行，在处理完成。  
  
   如果阶段不需要识别 (例如，执行模式是**所有**)，消息引擎调用组件，而无需为第一个查询**IProbeMessage**接口并调用**探测**方法。  
  
## <a name="see-also"></a>请参阅  
 [开发常规管道组件](../core/developing-a-general-pipeline-component.md)   
 [开发汇编程序管道组件](../core/developing-an-assembling-pipeline-component.md)   
 [开发拆装管道组件](../core/developing-a-disassembling-pipeline-component.md)   
 [报告来自管道组件的错误](../core/reporting-errors-from-pipeline-components.md)   
 [配置本地管道组件](../core/configuring-native-pipeline-components.md)   
 [部署管道组件](../core/deploying-pipeline-components.md)