---
title: "有关设计 BizTalk 应用程序的国际注意事项 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 9daaaaf7-6149-4e62-9e9b-b6356fc820d2
caps.latest.revision: "15"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 7ef22467c18580219e8587d63017d8bf146090d4
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/28/2017
---
# <a name="international-considerations-for-designing-biztalk-applications"></a>有关设计 BizTalk 应用程序的国际注意事项
强烈建议你查看以下已知问题，当你开发国际时[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]应用程序。  
  
 **计算机名称的字符限制**  
  
 安装[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]不支持在名称中包含以下一组外部的字母的计算机上： 字母 （A 到 Z、 a 到 z），数字 (0-9)、 连字符 （-） 和下划线 (_)。 支持仅机包含此集中的字母的名称。  
  
 **字符无法正确显示，或者不显示在所有由于不正确的字体和字体回退设置**  
  
 在驻留于 Microsoft [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 中的 [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] 工具中，您可能会遇到字符（如 Czech 字符）显示问题。 要解决这些问题，可能需要修改 Visual Studio“选项”选项卡中提供的字体设置，选择另一种您知道支持要显示的字符的字体。 你可以选择 Tahoma 或 Microsoft Sans Serif 作为为其提供字体回退功能的默认字体。  
  
 **代理项对字符中显示为平方 BizTalk Server 管理控制台和其他 BizTalk Server 工具**  
  
 你可能无法将能够在 BizTalk Server 管理控制台中显示代理项对字符和其他[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]工具。 代理项对是序列的两个代码单元组成单个抽象字符的编码的字符表示形式。 请确保你具有合适 （它包括在 Office XP 和 2003年中文版本） 在系统上安装的字体。 可能还需要在具有相应功能的工具（如 [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]）中更改字体选项。  
  
 如果不使用字体设置选项的其他工具，代理项对字符将显示为平方，如管理控制台。 如果你看到平方，未损坏字符;它们只是无法正常显示由于缺乏字体支持。  
  
 **Web 服务字符限制**  
  
 如果你打算发布作为 Web 服务业务流程，你可能会遇到问题中使用业务流程名称和端口名称的 Web 服务文件的名称 （.asmx 文件） 和 Web 服务中的虚拟目录中会使用这些名称字符发布向导。 只有 Microsoft Internet 信息服务 (IIS) 7.0（包括在 Microsoft Windows Server 2008 和 Windows Vista 中）完全支持 Unicode 字符。 因此，如果你使用早期版本的 IIS 或 Windows，业务流程，名称端口、 Web 服务和虚拟目录名称必须包括仅支持的语言版本的 Windows 的 ANSI 字符 （例如，日语字符不是允许在英语版本的 Windows 上）。  
  
 另外还要注意，[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] 中 Web Services 的项目名称只限于使用 ASCII 字符。  
  
 **使用不同的文档编码**  
  
 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 支持用于 XML 和平面文件文档的许多不同编码，如 UTF-16、UTF-8、简体中文 GBK、简体中文 GB18030 等。  
  
 对于入站文档，[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]可以识别 XML 文档中的编码声明如"\<？ xml 版本 ="1.0"encoding ="GB2312"？\>"。 平面文件架构具有**代码页**属性以指示传入的平面文件文档的编码。  
  
 对于出站文档、 XML 和平面文件汇编程序使用**目标 charset**属性。 如果指定了此属性，[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 会将出站文档转换为指定的字符集，而不管原始文档如何。 如果没有**目标 charset**设置属性、 XML 使用 utf-8 协议和平面文件使用在平面文件架构中指定的代码页。  
  
 **代码从不支持的代码页转换到的 Windows 代码页**  
  
 若要实现来自不受支持的代码页的代码转换到 Windows 代码页，必须创建自定义管道组件。  
  
 **对文档编码字节顺序标记影响**  
  
 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 确定字符编码，然后利用平面文件和 XML 消息的各自不同的特定字符编码来生成文档。  
  
 **架构编辑器可能包含多个语言中的属性**  
  
 在“架构编辑器属性”窗口和 XML 源代码中显示的 XML 架构定义语言 (XSD) 属性名未进行本地化，在所有本地化版本中均以英语显示。 本地语言显示其他属性。 例如，在 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 的简体中文版中，架构属性以英文显示，但其他属性以中文显示。  
  
 **平面文件中的依赖于区域设置的数据**  
  
 多个区域设置表示如日期、 时间、 编号和货币使用比标准的 XML 中定义这些格式的不同格式的数据。 例如，多个区域设置使用小数分隔符的句点 （.）、 以外，因此数五个和第三个季度可能表示为 5,75。  
  
 在 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 中，平面文件中除日期和时间之外的所有字段均作为字符串处理，这样解析才能成功。 但是，当使用 XML 验证，在根据架构验证过程中失败生成的 XML 消息。  
  
 对于日期和时间字段，分析器试图分析到 DateTime 实例使用的自定义日期或时间格式，如果它定义，并且写入 XML 格式，或将作为字符串的原始值，如果日期或时间格式未定义的字段值。 同样，如果使用 XML 验证，生成日期或时间可能未通过验证如果不使用自定义日期或时间格式，且在平面文件消息中使用的字段值未采用正确的 XML 日期或时间格式。  
  
 请注意，你还可以创建自定义管道组件或更新字段值来生成有效的 XML 的映射。  
  
 **BAM 定义语言支持**  
  
 你可以部署的 BAM 定义 XML 文件之前，必须确保用于创建此文件的语言匹配正在部署在其的计算机的区域设置。 如果该文件和计算机设置不匹配，你必须先重新启动运行 BM.exe 所用于的计算机。  
  
> [!NOTE]
>  除非所有语言都使用的相同的代码页或只有两种语言都包括在内并且其中一个是英语，BAM 定义 XML 文件不能包含多个语言的文本。  
  
## <a name="see-also"></a>另请参阅  
 [实现管道组件中的字符编码](../core/implementing-character-encoding-in-a-pipeline-component.md)   
 [处理反汇编程序管道组件中编码](../core/handling-encoding-in-a-disassembler-pipeline-component.md)   
 [平面文件反汇编程序管道组件中的字符编码](../core/character-encoding-in-the-flat-file-disassembler-pipeline-component.md)   
 [平面文件汇编管道组件中的字符编码](../core/character-encoding-in-the-flat-file-assembler-pipeline-component.md)   
 [XML 汇编程序管道组件中的字符编码](../core/character-encoding-in-the-xml-assembler-pipeline-component.md)   
 [XML 反汇编程序管道组件中的字符编码](../core/character-encoding-in-xml-disassembler-pipeline-component.md)