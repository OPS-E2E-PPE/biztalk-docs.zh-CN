---
title: 如何配置映射验证和测试参数 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 1768918c-e94f-476f-b288-9e030c691177
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 0c39b185284d3787e88abcd70bcb6827385361bd
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65341388"
---
# <a name="how-to-configure-map-validation-and-test-parameters"></a>如何配置映射验证和测试参数
需要设置映射验证和测试参数在验证和测试映射前,**属性**映射的窗口。  
  
## <a name="configure-the-map-validation-and-test-parameters"></a>配置映射验证和测试参数  
  
1.  在解决方案资源管理器，右键单击映射其属性页，你想要配置，然后单击**属性**。  
  
2.  在属性窗口中执行以下操作。  
  
    |使用此选项|执行的操作|  
    |--------------|----------------|  
    |**验证测试映射输入**|配置是否想要测试映射前根据源架构验证实例消息。|  
    |**验证测试映射输出**|配置是否想要测试映射后根据目标架构验证实例消息。|  
    |**测试映射输入实例**|配置测试映射时要使用的实例消息数据的位置。<br /><br /> 如果配置此属性，则还必须配置**测试映射输入**属性。|  
    |**测试映射输出实例**|配置想要存储的测试映射操作的输出的文件的位置。<br /><br /> 如果配置此属性，则还必须配置**测试映射输出**属性。|  
    |**TestMap Input**|配置输入的实例数据格式。|  
    |**测试映射输出**|配置测试映射时要使用的输出数据类型。|  
  
    > [!IMPORTANT]
    >  如果你想要测试映射，必须先配置映射属性。  

开发映射后，接下来的步骤之一是对其进行验证。 本主题提供用于验证映射的分步说明。  
  
## <a name="validate-a-biztalk-map"></a>验证 BizTalk 映射  
  
1.  在解决方案资源管理器，打开你想要验证的映射。  
  
2.  在解决方案资源管理器，右键单击该映射，然后选择**验证映射**。  
  
3.  在中**输出**窗口中，验证结果。  
  
> [!IMPORTANT]
>  如果在输出中使用自定义数据或常量，则必须验证您的源的数据类型的测试数据和目标的常量值有效。 验证映射时，BizTalk 映射器不会检查实例数据是否违反了架构中定义的任何数据类型。 这是测试映射或验证实例数据使用 BizTalk 编辑器时。 

## <a name="test-a-biztalk-map"></a>测试 BizTalk 映射

开发映射后，接下来的步骤之一是对其进行测试。 本主题提供有关测试映射包括步骤的分步说明，以查看映射编译器生成的 XSLT。  
  
1.  在解决方案资源管理器，右键单击你想要测试，然后选择的映射**测试映射**。  
  
2.  验证结果的**输出**窗口。  
  
    > [!IMPORTANT]
    >  建议您配置输入和输出实例属性属性窗口中的，然后再测试映射。  
  
## <a name="review-the-xslt"></a>查看 XSLT  
 通常它可用于检查映射编译器生成的 XSLT。 检查 XSLT 的优势包括：  
  
- 如果使用循环或自定义 functoid 时，将更好地了解如何执行循环和如何调用自定义 functoid。  
  
- 如果你具有复杂的代码图，查看 XSLT 将允许您看到如何映射翻译为转换，并可能会为您提供见解如何更好地构造、 替换或简化一个或多个部分。  
  
- 如果使用自定义脚本或其他项目，查看 XSLT 便可以看到脚本、 项目和映射的其他部分的交互方式。  
  
  换而言之，查看 XSLT 是调试映射的好办法。  
  
#### <a name="view-the-xslt-generated-by-the-map-compiler"></a>查看映射编译器所生成的 XSLT  
  
1.  从 Visual Studio BizTalk 项目中，选择**解决方案资源管理器**选项卡上，右键单击映射，并选择**验证映射**。  
  
2.  滚动输出窗口以查找 XSL 文件的 URL。 按**CTRL**，然后选择要查看该文件的 URL。  
  
> [!NOTE]
>  对 XSL 文件所做的更改不会反映在映射中，并在下一个生成上覆盖。  
  
## <a name="see-also"></a>另请参阅  

[如何调试映射](../core/how-to-debug-maps.md)  
[排除地图故障](../core/troubleshooting-maps.md)  