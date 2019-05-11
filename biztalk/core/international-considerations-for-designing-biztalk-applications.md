---
title: 设计 BizTalk 应用程序的国际化注意事项 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 9daaaaf7-6149-4e62-9e9b-b6356fc820d2
caps.latest.revision: 15
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 5fad9a0933409457e4f27f2f30412902f058a900
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65381718"
---
# <a name="international-considerations-for-designing-biztalk-applications"></a>设计 BizTalk 应用程序的国际化注意事项
强烈建议您查看以下已知问题，当开发国际[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]应用程序。  
  
 **计算机名称的字符限制**  
  
 安装[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]不支持在名称中包含以下字符集以外的字母的计算机上： 字母 （A-Z、 a 到 z），数字 (0-9)、 连字符 （-） 和下划线 (_)。 支持仅包含在此集中字母的计算机名称。  
  
 **字符无法正确显示，或执行操作完全未显示由于不正确的字体和字体回退设置**  
  
 在中您可能会遇到字符 （如 Czech 字符） 显示问题[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]宿主是 Microsoft 的工具[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]。 若要解决这些问题，可能需要修改 Visual Studio 选项选项卡中可用的字体设置，然后选择您知道支持的字符的另一种字体。 可以选择 Tahoma 或 Microsoft Sans Serif，作为默认字体为其提供的字体回退功能。  
  
 **代理项对字符显示为方块在 BizTalk Server 管理控制台和其他 BizTalk Server 工具**  
  
 您可能没有可以显示在 BizTalk Server 管理控制台中的代理项对字符和其他[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]工具。 代理项对是包含两个代码单元的一系列的单一抽象字符的编码的字符集表示形式。 请确保具有合适的字体 （它包含在中文版的 Office XP 和 2003年） 在系统上安装。 它还可能有必要更改字体选项中具有相应功能的工具 (如[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)])。  
  
 在没有字体设置选项的其他工具，代理项对字符将显示为方块，例如，在管理控制台。 如果您看到的方块，未损坏的字符;它们只是不能正确显示由于缺乏字体支持。  
  
 **Web 服务字符限制**  
  
 如果计划使用业务流程发布为 Web 服务，你可能会遇到的问题在 Web 服务文件的名称 （.asmx 文件） 和 Web 服务中的虚拟目录中使用这些名称在业务流程名称和端口名称中使用的字符发布向导。 仅 Microsoft Internet 信息服务 (IIS) 7.0 （包含在 Microsoft Windows Server 2008 和 Windows Vista） 完全支持 Unicode 字符。 因此，如果使用早期版本的 IIS 或 Windows，业务流程，名称端口、 Web 服务和虚拟目录名称必须包含仅受 Windows 的语言版本的 ANSI 字符 （例如，日语字符不是允许的英文版的 Windows 上）。  
  
 另外还要注意中的 Web 服务的项目名称[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]被限制为 ASCII 字符。  
  
 **使用不同的文档的编码**  
  
 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 支持许多不同编码的 XML 和平面文件文档，例如 utf-16、 UTF-8、 简体中文 GBK、 简体中文 GB18030 等。  
  
 对于入站文档[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]可以识别 XML 文档中的编码声明，如"\<？ xml 版本"1.0"encoding ="GB2312"？\>"。 平面文件架构有**代码页**属性以指示入站平面文件文档的编码。  
  
 对于出站文档、 XML 和平面文件组装器使用**目标字符集**属性。 如果指定此属性，则[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]将出站文档转换为指定的字符而不考虑原始设置。 如果没有**目标字符集**设置属性、 XML 使用 utf-8 协议，平面文件使用在平面文件架构中指定的代码页。  
  
 **从了不受支持的代码页为 Windows 代码页的代码转换**  
  
 若要实现来自不受支持的代码页的代码转换到 Windows 代码页，必须创建自定义管道组件。  
  
 **对文档编码的字节顺序标记影响**  
  
 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 确定字符编码，并生成具有特定的字符编码以不同的方式为平面文件消息和 XML 消息的文档。  
  
 **架构编辑器可能包含多个语言中的属性**  
  
 XML 架构定义语言 (XSD) 属性名称显示在架构编辑器属性窗口和 XML 源代码中未进行本地化，并在所有本地化版本均以英语显示。 以本地语言显示其他属性。 例如，在的简体中文版[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]，架构属性是在英语中，但其他属性以中文显示。  
  
 **平面文件中的区域设置相关数据**  
  
 多个区域设置表示数据，例如日期、 时间、 数字和货币使用不同的格式比 XML 标准中定义这些格式。 例如，多个区域设置使用句点 （.）、 非十进制分隔符，因此数字五个和第三季度可能表示为 5,75。  
  
 在[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]、 所有字段从都平面文件除日期和时间被视为字符串，以便解析才能成功。 但是，使用 XML 验证，生成的 XML 消息失败期间根据架构进行验证。  
  
 对于日期和时间字段，分析器会尝试分析到使用自定义日期或时间格式，如果它定义，并将其写入 XML 格式或使用作为字符串的原始值，如果未定义日期或时间格式的 DateTime 实例的字段值。 同样，如果使用 XML 验证，则得到的日期或时间可能未能通过验证如果不使用自定义日期或时间格式，并且使用平面文件消息中的字段值不是正确的 XML 日期或时间格式。  
  
 请注意，您还可以创建自定义管道组件或更新字段值以生成有效的 XML 的映射。  
  
 **BAM 定义语言支持**  
  
 部署 BAM 定义 XML 文件之前，必须确保用于创建此文件的语言与正在部署所在的计算机的区域设置相匹配。 如果该文件和计算机设置不匹配，必须先重新启动用于运行 BM.exe 的计算机。  
  
> [!NOTE]
>  BAM 定义 XML 文件不能包含多个语言的文本，除非所有语言都使用同一代码页或只有两种语言都包括在内并且其中一种是英语。  
  
## <a name="see-also"></a>请参阅  
 [管道组件中实现字符编码](../core/implementing-character-encoding-in-a-pipeline-component.md)   
 [处理拆装器管道组件中的编码](../core/handling-encoding-in-a-disassembler-pipeline-component.md)   
 [平面文件拆装器管道组件中的字符编码](../core/character-encoding-in-the-flat-file-disassembler-pipeline-component.md)   
 [平面文件组装器管道组件中的字符编码](../core/character-encoding-in-the-flat-file-assembler-pipeline-component.md)   
 [XML 组装器管道组件中的字符编码](../core/character-encoding-in-the-xml-assembler-pipeline-component.md)   
 [XML 反汇编程序管道组件中的字符编码](../core/character-encoding-in-xml-disassembler-pipeline-component.md)