---
title: 无法识别的消息中 XML 拆装器管道组件 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- Allow Unrecognized Messages property
- XMLNorm.AllowUnrecognizedMessage property
- pipeline components, XML Disassembler
- XML Disassembler [pipeline component], unrecognized messages
ms.assetid: 5a6be3a8-0bac-426a-bf0b-5091191091de
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c09d381a74b8f5083b600de73b72ac3c4d4da00d
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65400831"
---
# <a name="unrecognized-messages-in-the-xml-disassembler-pipeline-component"></a>XML 拆装器管道组件中无法识别的消息
XML 拆装器组件可能会处理一条消息"无法识别"在以下情况下：  
  
- 带任何正文、 空白正文、 正文中的空数据接收一条 XML 消息。  
  
- 收到一条 XML 消息，但没有架构部署它。  
  
  根据处理无法识别的消息**允许无法识别的消息**属性 (或在**XMLNorm.AllowUnrecognizedMessage**消息上下文属性)。  
  
  如果**允许无法识别的消息**设置为**True**，将发生以下情况：  
  
- 带任何正文、 正文为空，或为空中的数据正文传递的消息通过 XML 拆装器保持不变。  
  
- 没有关联的已部署的架构传递的 XML 文档原封不动地通过 XML 拆装器。  
  
- 由 XML 拆装器而不考虑架构是否显式组件属性中引用或架构解析过程中找到，具有与之关联的已部署的架构的 XML 文档进行处理。  
  
  如果**允许无法识别的消息**设置为**False**，将发生以下情况：  
  
- 通过 XML 拆装器不传递任何正文、 正文为空或正文中的数据为空的消息。  
  
- 没有与它关联的已部署的架构的 XML 文档不通过拆装器。 报告错误并挂起该消息，如有可能。  
  
- 由 XML 拆装器而不考虑架构是否显式组件属性中引用或架构解析过程中找到，具有与之关联的已部署的架构的 XML 文档进行处理。  
  
  默认情况下，XML 拆装器不允许无法识别的消息。  
  
> [!NOTE]
>  非 XML 消息不会处理 XML 拆装器而不考虑**允许无法识别的消息**属性设置。  
  
## <a name="see-also"></a>请参阅  
 [XML 拆装器管道组件](../core/xml-disassembler-pipeline-component.md)   
 [如何配置 XML 拆装器管道组件](../core/how-to-configure-the-xml-disassembler-pipeline-component.md)