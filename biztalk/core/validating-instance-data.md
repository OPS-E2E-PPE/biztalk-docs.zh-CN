---
title: 验证实例数据 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 19c3ca83-0abf-42ba-8e29-653ff12d5e20
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 648e3e97a3a7173278256d109f362938c3176988
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65398579"
---
# <a name="validate-instance-data"></a>验证实例数据

## <a name="overview"></a>概述
在测试映射的过程中，你可能想要根据要验证实例数据符合架构结构的源和目标架构验证实例数据。 要验证针对源或目标架构的实例消息，请右键单击解决方案资源管理器中的架构，然后单击**验证实例**。  

> [!IMPORTANT]
>  如果在输出中使用自定义数据或常量，则必须验证您的源的数据类型的测试数据和目标的常量值有效。 验证映射时，BizTalk 映射器不会检查实例数据违反了定义架构的任何数据类型。 这是测试映射或验证实例数据时。  

 有关如何生成和验证实例数据的使用 BizTalk 编辑器的详细信息，请参阅[实例消息的生成和验证](../core/instance-message-generation-and-validation.md)并[实例验证](../core/instance-validation.md)。 . **值**架构的节点的属性也会影响 BizTalk 生成实例数据的方式。 有关详细信息，请参阅**Schema 节点属性** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]。

## <a name="see-also"></a>请参阅  
- [实例消息的生成和验证](../core/instance-message-generation-and-validation.md)   
- [如何在 Visual Studio 中的架构验证](../core/how-to-validate-schemas-in-visual-studio.md)   
- **映射属性参考** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]  
- [测试映射](../core/testing-maps.md)
