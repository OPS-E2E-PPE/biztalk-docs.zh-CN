---
title: 消息验证 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- validating, messages
- messages, validating
ms.assetid: 720ab16a-7ab4-4741-9951-9ab10a2c4c24
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 67d3da2162fedcb266e5b754e8bb55893238d7e3
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65303681"
---
# <a name="message-validation"></a>消息验证
消息验证发生的传入和传出 HL7 消息 HL7 2.X 接收和发送管道。 你可以配置验证只有 MSH （标头） 段，或整个消息正文。 此外，就可以根据唯一本地化版本的架构进行验证。 通过定义一个唯一的命名空间值，并使用此命名空间值 （在参与方级别） 的 HL7 消息传送配置和定义消息的实际架构的目标命名空间属性中完成此操作。 在运行时，Microsoft BizTalk Accelerator for HL7 ([!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]) 使用命名空间和架构的根引用属性的组合来选择消息分析和验证相应的架构。  
  
 分析器和序列化程序来执行基于与消息关联的参与方设置的验证。 其他参与方设置，包括批处理、 确认和消息标头重写会影响分析器或序列化程序如何执行验证。  
  
> [!NOTE]
>  序列化程序执行一系列的步骤，包括 （如果适用） 执行从 MSH 映射，标头重写和执行 XML 验证。 如果标头重写和验证过程是同时启用了，并且标头重写过程将不正确的值输入到标头字段，该消息将通过验证，即使该消息是通过正文验证。  
  
## <a name="see-also"></a>请参阅  
 [ MSH 替代](../../adapters-and-accelerators/accelerator-hl7/msh-override.md)