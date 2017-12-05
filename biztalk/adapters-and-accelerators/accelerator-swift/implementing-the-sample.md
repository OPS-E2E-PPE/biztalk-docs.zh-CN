---
title: "实现示例 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: cd788fd3-b070-40d5-a3d3-ac8e5208cc47
caps.latest.revision: "2"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: d6622d201c6f7b7d94694a77198d0eb562482489
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/28/2017
---
# <a name="implementing-the-sample"></a>实现示例
若要实现此示例，请继续执行，如下所示：  
  
1.  为 SWIFT 架构创建一个新文件夹 (\<DocumentSchemaLocation\>实用工具语法中)。 要为其创建/修改 InfoPath 窗体的所有架构必须都位于此文件夹时执行的实用程序。  
  
2.  如果你正在生成 MT 消息的 InfoPath 窗体，则复制**SWIFT 基 Types.xsd**和**SWIFT 常见数据 Types.xsd**从**\<驱动器：\> files\Microsoft BizTalk Accelerator for SWIFT\<消息包版本\>消息 Pack\SWIFT Messages\A4SWIFT SRG\<消息包版本\>\Base 架构**到文件夹你为 SWIFT 架构创建。  
  
3.  将复制所有要为其创建为对于 SWIFT 架构在步骤 1 中创建的文件夹的 InfoPath 窗体的架构。  
  
4.  创建或指定一个文件夹来保存创建的 InfoPath 窗体模板解决方案文件 (\<DestinationFolderPath\>实用工具语法中)。 如果不创建输出文件夹，该实用工具将使用路径和命令行传递的名称来创建相同。  
  
5.  [可选]-创建一个文本文件\<NameOfFileContainingSchemaList\> ，它列出为生成 InfoPath 窗体的消息的消息类型。 例如消息类型可以是 MT103，MT102 等。命令行而不是创建此文本文件可以直接传递消息名称。  
  
## <a name="syntax-of-command-usage-for-formgeneratorexe"></a>FormGenerator.exe 的命令用法的语法  
  
```csharp  
FormGenerator [-b]   [-#] <TemplateFolderPath> [<TemplateFolderPath2>   
   [...<TemplateFolderPath#>]]  
 <DestinationFolderPath>     <DocumentSchemaLocation>  
   { [<SpaceSeparatedDocumentSchemaList>] |   [-f <NameOfFileContainingSchemaList>] }  
  
```  
  
 其中：  
  
-   -b： 如果指定，将在创建后编译窗体。  
  
-   TemplateFolderPath： 包含用于创建 InfoPath 解决方案的模板文件的文件夹  
  
-   -#: 如果指定，模板将在中查找多个模板路径 (任意多个数字 # 指定的整数) 和指定的顺序。  
  
-   将在其中创建窗体文件夹的 DestinationFolderPath:  
  
-   DocumentSchemaLocation： 的架构 （包括基类和常见架构 MT 消息） 的位置  
  
-   SpaceSeparatedDocumentSchemaList： 空格分隔的列表类似 MT103 MT300 的架构。  
  
-   -f： 如果指定，需要从文件读取架构列表。  
  
-   NameOfFileContainingSchemaList： 的包含列表的文件的名称。  
  
    > [!NOTE]
    >  上面的命令是 MT、 MX 和类别 0 泛型命令消息。 特定的命令以生成这些类型的窗体中给出了以下各节。