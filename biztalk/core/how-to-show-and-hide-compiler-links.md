---
title: 如何显示和隐藏编译器链接 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 66bfd9de-c4d2-46ee-854f-cf7c7cd07368
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 66d9b9ee8901ea2d93a73fd227a0ac1623e25669
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22255541"
---
# <a name="how-to-show-and-hide-compiler-links"></a>如何显示和隐藏编译器链接
编译地图时，BizTalk 映射程序将创建名为编译器链接来应对需要在映射中的所有链接的其他链接。 你创建的链接仅隐含的一些这些链接。 当你编译，或测试，地图中，在 Visual Studio 输出窗口中的最后一行，可显示或隐藏这些主窗口中的其他编译器链接。 默认情况下，编译器链接显示为红色虚线。  
  
### <a name="to-show-or-hide-compiler-links"></a>若要显示或隐藏编译器链接  
  
1.  在解决方案资源管理器，右键单击你想要查看，，然后单击其编译器链接的映射**测试映射**。  
  
2.  在 Visual Studio 错误列表窗口中，滚动到结束，并双击该连线表明**双击此处以显示/隐藏编译器链接**。  
  
     到更改从编译器链接的显示状态显示为隐藏，或从隐藏到所示，只需双击再次的行。  
  
    > [!NOTE]
    >  当你构建/重新构建 BizTalk 项目或解决方案，其中包含一个或多个地图，该消息**双击此处以显示/隐藏编译器链接**中显示**错误列表**为 Visual Studio 窗口项目或解决方案中的所有映射。  
  
 若要测试映射，必须配置输入和输出实例的属性。 有关如何配置这些属性的详细信息，请参阅[如何配置映射验证和测试参数](../core/how-to-configure-map-validation-and-test-parameters.md)。  
  
## <a name="see-also"></a>另请参阅  
 [使用链接以指定记录和字段映射](../core/using-links-to-specify-record-and-field-mappings.md)