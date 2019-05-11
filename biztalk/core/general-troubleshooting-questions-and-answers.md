---
title: 常规故障排除问题和解答 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: d2f89d92-0a97-4017-8b8e-6afd8b20eaf4
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 373d8cd1c140426427490202d0c8590488a2fcda
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65345248"
---
# <a name="general-troubleshooting-questions-and-answers"></a>常见疑难问题与解答
本主题有问题和答案，帮助您解决 BizTalk 映射器的问题。  
  
## <a name="how-do-i-specify-xslt-output-settings"></a>如何指定 XSLT 输出设置？  
 你可以使用 BizTalk 映射器包括或省略 XML 声明，并控制用于输出实例数据的编码。  
  
#### <a name="include-or-exclude-an-xml-declaration"></a>包含或排除的 XML 声明  
  
1.  在网格视图中，单击映射器网格。 **属性**窗口中显示网格属性。  
  
2.  中的下拉列表**忽略 XML 声明**属性中，选择**是**省略 XML 声明，或选择**否**不以省略 XML 声明。  
  
#### <a name="set-encoding-for-output-instance-data"></a>设置编码为输出实例数据  
  
1.  在网格视图中，单击映射器网格。 **属性**窗口中显示网格属性。  
  
2.  中的下拉列表**XSLT 编码**属性中，选择的字符集要用于输出实例数据。  
  
## <a name="how-do-i-create-multipart-mappings"></a>如何创建多部分映射？  
 如果必须一起使用的多个映射，需要将它们合并在业务流程中使用**转换**形状一起进行测试。 BizTalk 映射器可以测试一次只有一个映射。  
  
## <a name="why-isnt-my-database-functoid-working"></a>为什么我的数据库 functoid 不能正常工作？  
 数据库 functoid**数据库查找**并**值提取程序**不直接返回错误信息; 而是捕获信息并提供到**错误返回** functoid 以供您的映射。 可以使用**错误返回**functoid 来检测错误如以下方案中所示：  
  
- 当您的映射具有**数据库查找**或**值提取程序**不按预期方式运行的 functoid。 若要查看的错误消息，暂时将提取 functoid 映射到输出架构中的字段。  
  
- 如果数据库操作失败时，你的应用程序需要不同的消息内容。 可以使用**错误返回**functoid 来检测到错误，并将错误消息映射到一个替代结构，以便下游应用程序可以控制的方式作出反应。  
  
  若要避免仅在运行时检测到的错误，请确保的第一个参数**错误返回**functoid 是输出**数据库查找**functoid 和不在其他任何 functoid 的输出数据库类别。  
  
  有关使用详细信息**错误返回**functoid （包括示例），请参阅**Functoid 参考** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]。
  
## <a name="why-is-my-map-failing-when-calling-my-custom-functoid"></a>我的地图失败的原因时调用我的自定义 functoid？  
 自定义 functoid 必须在安装到全局程序集缓存 (GAC)[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]计算机之前可以通过映射调用它们。 验证已签名并放入 gac 中包含自定义 functoid 的程序集。 此外，将该程序集复制到文件夹"%BTSINSTALLPATH%\Developer Tools\Mapper Extensions"。  
  
 有关程序集安装到 GAC 的详细信息，请参阅[程序集安装在 GAC 中](../core/assembly-installation-in-the-gac.md)。 若要查看程序集安装到 GAC 中，导航到的程序集目录你[!INCLUDE[btsWinNoVersion](../includes/btswinnoversion-md.md)]安装目录。  
  
## <a name="see-also"></a>请参阅  
 [排除地图故障](../core/troubleshooting-maps.md)