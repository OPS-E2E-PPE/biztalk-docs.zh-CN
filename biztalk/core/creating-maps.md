---
title: 创建映射 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: cc9f8ad1-4aad-4866-8aa4-4877fdc5e5f9
caps.latest.revision: 14
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 0e27f4fae142f4c781f95be148ec80e2dff51383
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "37003094"
---
# <a name="creating-maps"></a>创建映射
上一个选项卡中显示为 BizTalk 映射器的主用户界面[!INCLUDE[btsCoName](../includes/btsconame-md.md)][!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]编辑窗口。 此显示分成三个窗格。 左窗格以树视图的形式显示源架构。 右窗格以树视图的形式显示目标架构。 中间窗格以多个页面的形式显示网格。 为了指示要如何将数据从源架构映射到目标架构，需在要映射的记录和字段之间绘制线条。 这些线条称为*链接*，它们是最基本的方法指定的数据的映射。 有关链接记录和字段的详细信息，请参阅[映射中的链接](../core/links-in-maps.md)。  
  
 如果要实现更高级的映射方法，可以使用 functoid。 Functoid 是 BizTalk 映射器中的选项卡上提供的工具[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]工具箱。 您可以使用它们来创建映射，以执行更复杂的操作，如：  
  
- 将源架构中的两个字段的值相加，然后将结果放到目标架构的字段中。  
  
- 计算循环记录中某个字段的平均值，然后将结果放到目标架构的字段中。  
  
- 根据业务需求，编写自定义脚本以处理实例数据。  
  
  有关 functoid 的详细信息，请参阅[映射中的 Functoid](../core/functoids-in-maps.md)。  
  
  BizTalk 映射器可以支持从简单父子关系到繁琐复杂的记录和层次循环的多种不同的映射方案。 创建映射时，请注意以下事项：  
  
- BizTalk 映射器不支持合并和排序。  
  
- 如果源架构结构和目标架构结构非常不同，有可能无法在单个映射中完成转换。 您可能需要双传递。  
  
- **循环**functoid 非常灵活而且功能强大，但您将无法再检测到源架构上的值的更改以开始目标循环的下一个迭代时中断迭代。  
  
- 你可以在方法外部变量声明**脚本**functoid，这会导致变量处于映射生存期的作用域。 因此，可以使用**脚本**functoid 之间的转换作用域区域保留值。  
  
  处理的所有数据[!INCLUDE[btsCoName](../includes/btsconame-md.md)][!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]在运行时必须采用 XML 格式。 在映射之前，所有非 XML 数据必须转换成等效的 XML 格式。 同样，映射过程何时完成，[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]使用映射操作的输出创建贸易合作伙伴或向其发送数据的应用程序识别的文件格式。  
  
  BizTalk 映射器包含编译器。 这一工具级组件可生成将输入实例消息转换或翻译成输出实例消息所需的可扩展样式表语言转换 (XSLT)。  
  
  本部分提供有关使用 BizTalk 映射器在两个架构之间创建映射的特定于任务的信息。 假定您已打开 BizTalk 映射器，并已选择源架构和目标架构。  
  
## <a name="in-this-section"></a>本节内容  
  
-   [管理项目中的映射](../core/managing-maps-within-projects.md)  
  
-   [使用链接指定记录和字段映射](../core/using-links-to-specify-record-and-field-mappings.md)  
  
-   [使用 Functoid 创建更复杂的映射](../core/using-functoids-to-create-more-complex-mappings.md)  
  
-   [如何创建在无映射](../core/how-to-create-a-map-without-maps.md)  
  
-   [管理默认映射器行为使用\<mapsource\>](../core/managing-default-mapper-behavior-using-mapsource.md)