---
title: "如何配置映射验证和测试参数 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 1768918c-e94f-476f-b288-9e030c691177
caps.latest.revision: "9"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f691a58ece178ee00ce983e400e5420ef54fafdf
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-configure-map-validation-and-test-parameters"></a>如何配置映射验证和测试参数
在验证和测试映射时之前，您需要在设置映射验证和测试参数**属性**映射的窗口。  
  
## <a name="configure-the-map-validation-and-test-parameters"></a>配置映射验证和测试参数  
  
1.  在解决方案资源管理器，右键单击你想要配置，，然后单击其属性页的映射**属性**。  
  
2.  在“属性”窗口中，执行以下操作。  
  
    |使用此选项|执行的操作|  
    |--------------|----------------|  
    |**验证测试映射输入**|配置在测试映射前是否根据源架构验证实例消息。|  
    |**验证测试映射输出**|配置在测试映射后是否根据目标架构验证实例消息。|  
    |**测试映射输入实例**|配置测试映射时要使用的实例消息数据的位置。<br /><br /> 如果你配置此属性，则还必须配置**测试映射输入**属性。|  
    |**测试映射输出实例**|配置您希望将测试映射操作输出要存储到的文件位置。<br /><br /> 如果你配置此属性，则还必须配置**测试映射输出**属性。|  
    |**测试映射输入**|配置输入实例数据格式。|  
    |**测试映射输出**|配置测试映射时要使用的输出数据类型。|  
  
    > [!IMPORTANT]
    >  如果要测试映射，必须先配置映射属性。  

您已开发你的代码图后下, 一步的步骤之一是对其进行验证。 本主题提供用于验证地图的分步说明。  
  
## <a name="validate-a-biztalk-map"></a>验证 BizTalk 映射  
  
1.  在解决方案资源管理器，打开你想要验证的映射。  
  
2.  在解决方案资源管理器，请右键单击映射，，然后选择**验证映射**。  
  
3.  在**输出**窗口中，验证结果。  
  
> [!IMPORTANT]
>  如果在输出中使用自定义数据或常量，则必须验证你的源的数据类型测试数据和目标常量值是有效的。 在验证映射时，BizTalk 映射程序不会检查实例数据是否与架构中定义的任何数据类型冲突。 测试映射或验证实例数据使用 BizTalk 编辑器时，是完成此操作。 

## <a name="test-a-biztalk-map"></a>测试 BizTalk 映射

开发映射后要执行的步骤之一即是对其进行测试。 本主题提供有关测试映射的分步说明，其中包括有关查看映射编译器所生成的 XSLT 的步骤的说明。  
  
1.  在解决方案资源管理器，右键单击你想要测试，，然后选择的地图**测试映射**。  
  
2.  验证的结果**输出**窗口。  
  
    > [!IMPORTANT]
    >  建议您先在“属性”窗口中配置输入和输出实例属性，然后再测试映射。  
  
## <a name="review-the-xslt"></a>查看 XSLT  
 通常它可用于检查由映射编译器生成的 XSLT。 一些检查 XSLT 的优势包括：  
  
-   如果使用循环或自定义 functoid，你将更好地了解如何执行循环如何调用自定义 functoid。  
  
-   如果你具有复杂的代码图，查看 XSLT 将使您能够请参阅如何映射转换成一个转换，并可能会给出了解有关如何更好的结构、 替换或简化其中一个或多个部件。  
  
-   如果你使用自定义脚本或其他项目，则查看 XSLT 将可以查看脚本、 项目和映射的其他部分的交互方式。  
  
 换而言之，查看 XSLT 是调试地图的好办法。  
  
#### <a name="view-the-xslt-generated-by-the-map-compiler"></a>查看由映射编译器生成的 XSLT  
  
1.  从 Visual Studio BizTalk 项目，选择**解决方案资源管理器**选项卡上，右键单击一个代码图，，然后选择**验证映射**。  
  
2.  滚动输出窗口以确定该 XSL 文件的 URL。 按**CTRL**，然后选择要查看该文件的 URL。  
  
> [!NOTE]
>  对 XSL 文件所做的更改不会反映在代码图，并在下一个生成时会被覆盖。  
  
## <a name="see-also"></a>另请参阅  

[如何调试地图](../core/how-to-debug-maps.md)  
[排除地图故障](../core/troubleshooting-maps.md)  