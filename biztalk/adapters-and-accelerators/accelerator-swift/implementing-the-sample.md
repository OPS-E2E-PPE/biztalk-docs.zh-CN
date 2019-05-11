---
title: 实现示例 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: cd788fd3-b070-40d5-a3d3-ac8e5208cc47
caps.latest.revision: 2
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ca5f7a6d3561e8217a3eebca16b48644a56238da
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65377353"
---
# <a name="implementing-the-sample"></a>实现示例
若要实现此示例，请继续阅读，如下所示：  
  
1.  为 SWIFT 架构创建一个新的文件夹 (\<DocumentSchemaLocation\>实用工具语法中)。 要为其创建/修改的 InfoPath 窗体的所有架构必须都位于此文件夹时执行的实用程序。  
  
2.  如果您正在生成 MT 消息的 InfoPath 窗体，则复制**SWIFT 基本 Types.xsd**并**SWIFT 常见数据 Types.xsd**从**\<驱动器：\> files\Microsoft BizTalk Accelerator for SWIFT\<消息包版本\>消息 Pack\SWIFT Messages\A4SWIFT SRG\<消息包版本\>\Base 架构**到文件夹，为 SWIFT 架构创建。  
  
3.  复制要为其创建到为 SWIFT 架构在步骤 1 中创建的文件夹的 InfoPath 窗体的所有架构。  
  
4.  创建或指定用于保存创建的 InfoPath 窗体模板解决方案文件的文件夹 (\<DestinationFolderPath\>实用工具语法中)。 如果不创建输出文件夹，该实用工具将使用路径和命令行传递的名称来创建相同。  
  
5.  [可选]-创建一个文本文件\<NameOfFileContainingSchemaList\> ，它列出为其在 InfoPath 窗体是要生成的消息的消息类型。 例如消息类型可以是 MT103，MT102 等。消息名称直接传递命令行而不是创建此文本文件。  
  
## <a name="syntax-of-command-usage-for-formgeneratorexe"></a>命令为 FormGenerator.exe 的用法的语法  
  
```csharp  
FormGenerator [-b]   [-#] <TemplateFolderPath> [<TemplateFolderPath2>   
   [...<TemplateFolderPath#>]]  
 <DestinationFolderPath>     <DocumentSchemaLocation>  
   { [<SpaceSeparatedDocumentSchemaList>] |   [-f <NameOfFileContainingSchemaList>] }  
  
```  
  
 其中：  
  
-   -b:如果指定，则会在创建后编译窗体。  
  
-   TemplateFolderPath： 包含用于创建 InfoPath 解决方案的模板文件的文件夹  
  
-   -#:如果指定，模板将查找在多个模板路径中 (任意多个数字 # 指定为整数) 和指定的顺序。  
  
-   在其中创建窗体文件夹的 DestinationFolderPath:  
  
-   DocumentSchemaLocation： 位置的架构 （包括基类和常用的 MT 消息的架构）  
  
-   SpaceSeparatedDocumentSchemaList： 空格分隔的列表等 MT103 MT300 的架构。  
  
-   -f:如果指定，则需要从文件读取架构列表。  
  
-   NameOfFileContainingSchemaList： 的包含列表的文件的名称。  
  
    > [!NOTE]
    >  上面的命令是 MT、 MX 和类别 0 的泛型命令消息。 特定命令来生成这些类型的窗体中给出了下面各节。