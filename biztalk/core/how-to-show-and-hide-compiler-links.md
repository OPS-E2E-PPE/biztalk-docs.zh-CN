---
title: 如何显示和隐藏编译器链接 |Microsoft Docs
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
ms.openlocfilehash: 931d829d37e6fdb594746598164a4b189c75a763
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65383878"
---
# <a name="how-to-show-and-hide-compiler-links"></a>如何显示和隐藏编译器链接
在编译映射时，BizTalk 映射器将创建名为编译器链接以说明在映射中所需的所有链接的其他链接。 下面的链接的一些仅隐含你创建的链接。 当编译，或测试映射，在 Visual Studio 输出窗口中的最后一行，可显示或隐藏在主窗口中的这些其他编译器链接。 默认情况下，编译器链接显示为红色虚线。  
  
### <a name="to-show-or-hide-compiler-links"></a>若要显示或隐藏编译器链接  
  
1. 在解决方案资源管理器，右键单击你想要查看，并单击其编译器链接的映射**测试映射**。  
  
2. 在 Visual Studio 错误列表窗口中，滚动至末尾并双击显示的行**双击此处进行显示/隐藏编译器链接**。  
  
    为更改从编译器链接的显示状态向显示隐藏的或从隐藏到所示，只需双击试的行。  
  
   > [!NOTE]
   >  当你生成/重新生成 BizTalk 项目或解决方案，其中包含一个或多个映射，该消息**双击此处进行显示/隐藏编译器链接**中显示**错误列表**适用于 Visual Studio 窗口项目或解决方案中的所有映射。  
  
   若要测试映射，必须配置为输入和输出实例属性。 有关如何配置这些属性的详细信息，请参阅[如何配置映射验证和测试参数](../core/how-to-configure-map-validation-and-test-parameters.md)。  
  
## <a name="see-also"></a>请参阅  
 [使用链接指定记录和字段映射](../core/using-links-to-specify-record-and-field-mappings.md)