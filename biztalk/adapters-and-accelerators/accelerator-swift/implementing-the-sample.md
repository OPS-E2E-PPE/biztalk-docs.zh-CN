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
# <a name="implementing-the-sample"></a><span data-ttu-id="d090b-102">实现示例</span><span class="sxs-lookup"><span data-stu-id="d090b-102">Implementing the Sample</span></span>
<span data-ttu-id="d090b-103">若要实现此示例，请继续阅读，如下所示：</span><span class="sxs-lookup"><span data-stu-id="d090b-103">To implement the sample, proceed as follows:</span></span>  
  
1.  <span data-ttu-id="d090b-104">为 SWIFT 架构创建一个新的文件夹 (\<DocumentSchemaLocation\>实用工具语法中)。</span><span class="sxs-lookup"><span data-stu-id="d090b-104">Create a new folder for SWIFT schemas (\<DocumentSchemaLocation\> in the utility syntax).</span></span> <span data-ttu-id="d090b-105">要为其创建/修改的 InfoPath 窗体的所有架构必须都位于此文件夹时执行的实用程序。</span><span class="sxs-lookup"><span data-stu-id="d090b-105">All schemas for which you are going to create/modify the InfoPath forms must be located in this folder when you execute the utility.</span></span>  
  
2.  <span data-ttu-id="d090b-106">如果您正在生成 MT 消息的 InfoPath 窗体，则复制**SWIFT 基本 Types.xsd**并**SWIFT 常见数据 Types.xsd**从**\<驱动器：\> files\Microsoft BizTalk Accelerator for SWIFT\<消息包版本\>消息 Pack\SWIFT Messages\A4SWIFT SRG\<消息包版本\>\Base 架构**到文件夹，为 SWIFT 架构创建。</span><span class="sxs-lookup"><span data-stu-id="d090b-106">If you are generating InfoPath forms for MT messages then copy **SWIFT Base Types.xsd** and **SWIFT Common Data Types.xsd** from **\<drive :\> \Program Files\Microsoft BizTalk Accelerator for SWIFT \<Message Pack Version\> Message Pack\SWIFT Messages\A4SWIFT-SRG\<Message Pack Version\>\Base Schemas** into the folder that you created for SWIFT schemas.</span></span>  
  
3.  <span data-ttu-id="d090b-107">复制要为其创建到为 SWIFT 架构在步骤 1 中创建的文件夹的 InfoPath 窗体的所有架构。</span><span class="sxs-lookup"><span data-stu-id="d090b-107">Copy all schemas for which you are going to create InfoPath forms into the folder that you created for SWIFT schemas in Step 1.</span></span>  
  
4.  <span data-ttu-id="d090b-108">创建或指定用于保存创建的 InfoPath 窗体模板解决方案文件的文件夹 (\<DestinationFolderPath\>实用工具语法中)。</span><span class="sxs-lookup"><span data-stu-id="d090b-108">Create or designate a folder to hold the created InfoPath form template solution files (\<DestinationFolderPath\> in the utility syntax).</span></span> <span data-ttu-id="d090b-109">如果不创建输出文件夹，该实用工具将使用路径和命令行传递的名称来创建相同。</span><span class="sxs-lookup"><span data-stu-id="d090b-109">If you do not create the output folder, the utility will create the same with path and name that you pass on the command line.</span></span>  
  
5.  <span data-ttu-id="d090b-110">[可选]-创建一个文本文件\<NameOfFileContainingSchemaList\> ，它列出为其在 InfoPath 窗体是要生成的消息的消息类型。</span><span class="sxs-lookup"><span data-stu-id="d090b-110">[Optional]-  Create a text file \<NameOfFileContainingSchemaList\> that lists the message types for messages for which the InfoPath form is to be generated.</span></span> <span data-ttu-id="d090b-111">例如消息类型可以是 MT103，MT102 等。消息名称直接传递命令行而不是创建此文本文件。</span><span class="sxs-lookup"><span data-stu-id="d090b-111">For e.g. Message Type can be MT103, MT102 etc. The Message names can directly be passed through the command line instead of creating this text file.</span></span>  
  
## <a name="syntax-of-command-usage-for-formgeneratorexe"></a><span data-ttu-id="d090b-112">命令为 FormGenerator.exe 的用法的语法</span><span class="sxs-lookup"><span data-stu-id="d090b-112">Syntax of Command usage for FormGenerator.exe</span></span>  
  
```csharp  
FormGenerator [-b]   [-#] <TemplateFolderPath> [<TemplateFolderPath2>   
   [...<TemplateFolderPath#>]]  
 <DestinationFolderPath>     <DocumentSchemaLocation>  
   { [<SpaceSeparatedDocumentSchemaList>] |   [-f <NameOfFileContainingSchemaList>] }  
  
```  
  
 <span data-ttu-id="d090b-113">其中：</span><span class="sxs-lookup"><span data-stu-id="d090b-113">Where:</span></span>  
  
-   <span data-ttu-id="d090b-114">-b:如果指定，则会在创建后编译窗体。</span><span class="sxs-lookup"><span data-stu-id="d090b-114">-b: If specified, forms will be compiled after creation.</span></span>  
  
-   <span data-ttu-id="d090b-115">TemplateFolderPath： 包含用于创建 InfoPath 解决方案的模板文件的文件夹</span><span class="sxs-lookup"><span data-stu-id="d090b-115">TemplateFolderPath: the folder containing the template files used to create the InfoPath solution</span></span>  
  
-   <span data-ttu-id="d090b-116">-#:如果指定，模板将查找在多个模板路径中 (任意多个数字 # 指定为整数) 和指定的顺序。</span><span class="sxs-lookup"><span data-stu-id="d090b-116">-#: If specified, templates will be looked up in multiple template paths (as many as the integer number # specifies) and in the order specified.</span></span>  
  
-   <span data-ttu-id="d090b-117">在其中创建窗体文件夹的 DestinationFolderPath:</span><span class="sxs-lookup"><span data-stu-id="d090b-117">DestinationFolderPath: the folder where the forms will be created</span></span>  
  
-   <span data-ttu-id="d090b-118">DocumentSchemaLocation： 位置的架构 （包括基类和常用的 MT 消息的架构）</span><span class="sxs-lookup"><span data-stu-id="d090b-118">DocumentSchemaLocation: location of schemas (including base and common schemas for MT messages)</span></span>  
  
-   <span data-ttu-id="d090b-119">SpaceSeparatedDocumentSchemaList： 空格分隔的列表等 MT103 MT300 的架构。</span><span class="sxs-lookup"><span data-stu-id="d090b-119">SpaceSeparatedDocumentSchemaList: space-separated list of schemas like MT103 MT300.</span></span>  
  
-   <span data-ttu-id="d090b-120">-f:如果指定，则需要从文件读取架构列表。</span><span class="sxs-lookup"><span data-stu-id="d090b-120">-f: If specified, the schema list needs to be read from a file.</span></span>  
  
-   <span data-ttu-id="d090b-121">NameOfFileContainingSchemaList： 的包含列表的文件的名称。</span><span class="sxs-lookup"><span data-stu-id="d090b-121">NameOfFileContainingSchemaList: name of file containing the list.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="d090b-122">上面的命令是 MT、 MX 和类别 0 的泛型命令消息。</span><span class="sxs-lookup"><span data-stu-id="d090b-122">The above command is a generic command for MT, MX and Category 0 messages.</span></span> <span data-ttu-id="d090b-123">特定命令来生成这些类型的窗体中给出了下面各节。</span><span class="sxs-lookup"><span data-stu-id="d090b-123">Specific commands to generate these types of forms are given in the below sections.</span></span>