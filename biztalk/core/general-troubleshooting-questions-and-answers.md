---
title: 常规疑难解答问题和答案 |Microsoft 文档
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
ms.openlocfilehash: 37e63f8838dea7adee91b5b43b2bc881cb53eae1
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22247101"
---
# <a name="general-troubleshooting-questions-and-answers"></a>常见疑难问题与解答
本主题包含有助于解决 BizTalk 映射器问题的问题和解答。  
  
## <a name="how-do-i-specify-xslt-output-settings"></a>如何指定 XSLT 输出设置？  
 您可以使用 BizTalk 映射器包括或省略 XML 声明，并且控制用于输出实例数据的编码。  
  
#### <a name="include-or-exclude-an-xml-declaration"></a>包括或排除 XML 声明  
  
1.  在网格视图中，单击映射器网格。 **属性**窗口将显示网格属性。  
  
2.  中的下拉列表**省略 XML 声明**属性中，选择**是**省略 XML 声明，或选择**否**无法省略 XML 声明。  
  
#### <a name="set-encoding-for-output-instance-data"></a>设置编码输出实例数据  
  
1.  在网格视图中，单击映射器网格。 **属性**窗口将显示网格属性。  
  
2.  中的下拉列表**XSLT 编码**属性，你的字符集的选择想要用于输出实例数据。  
  
## <a name="how-do-i-create-multipart-mappings"></a>如何创建多部分映射？  
 如果你有多个映射在一起使用，你将需要使用一个业务流程中合并它们**转换**形状以在一起对其进行测试。 BizTalk 映射器一次只能测试一个映射。  
  
## <a name="why-isnt-my-database-functoid-working"></a>为什么我数据库 functoid 不工作？  
 数据库 functoid**数据库查找**和**值提取程序**不直接返回错误的信息; 相反，它们可捕获该信息并将其到其提供**错误返回** functoid 以供你的代码图。 你可以使用**错误返回**functoid 用于错误检测，如以下方案中所示：  
  
-   当你的代码图具有**数据库查找**或**值提取程序**functoid 不按预期方式运行。 若要查看错误消息，请暂时将该 functoid 映射到输出架构中的某个字段。  
  
-   如果在数据库操作失败时您的应用程序应该有不同的消息内容。 你可以使用**错误返回**functoid 检测到错误并将错误消息映射到备用结构，因此，下游应用程序可以控制的方式作出反应。  
  
 若要避免仅在运行时检测到的错误，请确保的第一个参数**错误返回**functoid 是输出**数据库查找**functoid，以及不在任何其他 functoid 的输出数据库类别。  
  
 有关使用**错误返回**functoid （包括示例），请参阅**Functoid 引用** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]。
  
## <a name="why-is-my-map-failing-when-calling-my-custom-functoid"></a>地图失败的原因时调用我自定义 functoid？  
 自定义 functoid 必须在安装到全局程序集缓存 (GAC)[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]计算机它们可以由映射调用之前。 验证包含自定义 functoid 的程序集具有签名并放入 gac。 同时，还将程序集复制到“%BTSINSTALLPATH%\Developer Tools\Mapper Extensions”文件夹中。  
  
 有关安装到 GAC 的程序集的详细信息，请参阅[位于 GAC 中的程序集安装](../core/assembly-installation-in-the-gac.md)。 若要查看程序集安装到 GAC 中，导航到的程序集目录你[!INCLUDE[btsWinNoVersion](../includes/btswinnoversion-md.md)]安装目录。  
  
## <a name="see-also"></a>另请参阅  
 [排除地图故障](../core/troubleshooting-maps.md)