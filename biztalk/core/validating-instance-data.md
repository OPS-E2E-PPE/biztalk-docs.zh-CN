---
title: 验证实例数据 |Microsoft 文档
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
ms.openlocfilehash: 86cde9d6133959e34ec09880be8a6beca5c37191
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22287973"
---
# <a name="validate-instance-data"></a>验证实例数据

## <a name="overview"></a>概述
测试映射过程，你可能想要验证针对要验证实例数据符合架构结构的源和目标架构的实例数据。 要验证实例消息针对源或目标架构，请右键单击解决方案资源管理器中的架构，然后单击**验证实例**。  
  
> [!IMPORTANT]
>  如果在输出中使用自定义数据或常量，则必须验证你的源的数据类型测试数据和目标常量值是有效的。 在验证映射时，BizTalk 映射程序不会检查实例数据违反了定义架构的任何数据类型。 在测试映射或验证实例数据时，会进行此检查。  
  
 有关如何生成和使用 BizTalk 编辑器验证实例数据的详细信息，请参阅[实例消息生成和验证](../core/instance-message-generation-and-validation.md)和[实例验证](../core/instance-validation.md)。 实例时都提供 SQL Server 登录名。 **值**架构的节点的属性还会影响如何 BizTalk 生成实例数据。 有关详细信息，请参阅**架构节点属性** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]。
  
## <a name="see-also"></a>另请参阅  
-  [实例消息生成和验证](../core/instance-message-generation-and-validation.md)   
-  [如何验证在 Visual Studio 中的架构](../core/how-to-validate-schemas-in-visual-studio.md)   
-  **映射属性引用**[!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]  
-  [测试映射](../core/testing-maps.md)