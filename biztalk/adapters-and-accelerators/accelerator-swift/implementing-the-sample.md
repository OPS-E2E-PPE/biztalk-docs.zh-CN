---
title: 实现示例 |Microsoft 文档
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
ms.openlocfilehash: d6622d201c6f7b7d94694a77198d0eb562482489
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/28/2017
ms.locfileid: "25966699"
---
# <a name="implementing-the-sample"></a><span data-ttu-id="5c4da-102">实现示例</span><span class="sxs-lookup"><span data-stu-id="5c4da-102">Implementing the Sample</span></span>
<span data-ttu-id="5c4da-103">若要实现此示例，请继续执行，如下所示：</span><span class="sxs-lookup"><span data-stu-id="5c4da-103">To implement the sample, proceed as follows:</span></span>  
  
1.  <span data-ttu-id="5c4da-104">为 SWIFT 架构创建一个新文件夹 (\<DocumentSchemaLocation\>实用工具语法中)。</span><span class="sxs-lookup"><span data-stu-id="5c4da-104">Create a new folder for SWIFT schemas (\<DocumentSchemaLocation\> in the utility syntax).</span></span> <span data-ttu-id="5c4da-105">要为其创建/修改 InfoPath 窗体的所有架构必须都位于此文件夹时执行的实用程序。</span><span class="sxs-lookup"><span data-stu-id="5c4da-105">All schemas for which you are going to create/modify the InfoPath forms must be located in this folder when you execute the utility.</span></span>  
  
2.  <span data-ttu-id="5c4da-106">如果你正在生成 MT 消息的 InfoPath 窗体，则复制**SWIFT 基 Types.xsd**和**SWIFT 常见数据 Types.xsd**从**\<驱动器：\> files\Microsoft BizTalk Accelerator for SWIFT\<消息包版本\>消息 Pack\SWIFT Messages\A4SWIFT SRG\<消息包版本\>\Base 架构**到文件夹你为 SWIFT 架构创建。</span><span class="sxs-lookup"><span data-stu-id="5c4da-106">If you are generating InfoPath forms for MT messages then copy **SWIFT Base Types.xsd** and **SWIFT Common Data Types.xsd** from **\<drive :\> \Program Files\Microsoft BizTalk Accelerator for SWIFT \<Message Pack Version\> Message Pack\SWIFT Messages\A4SWIFT-SRG\<Message Pack Version\>\Base Schemas** into the folder that you created for SWIFT schemas.</span></span>  
  
3.  <span data-ttu-id="5c4da-107">将复制所有要为其创建为对于 SWIFT 架构在步骤 1 中创建的文件夹的 InfoPath 窗体的架构。</span><span class="sxs-lookup"><span data-stu-id="5c4da-107">Copy all schemas for which you are going to create InfoPath forms into the folder that you created for SWIFT schemas in Step 1.</span></span>  
  
4.  <span data-ttu-id="5c4da-108">创建或指定一个文件夹来保存创建的 InfoPath 窗体模板解决方案文件 (\<DestinationFolderPath\>实用工具语法中)。</span><span class="sxs-lookup"><span data-stu-id="5c4da-108">Create or designate a folder to hold the created InfoPath form template solution files (\<DestinationFolderPath\> in the utility syntax).</span></span> <span data-ttu-id="5c4da-109">如果不创建输出文件夹，该实用工具将使用路径和命令行传递的名称来创建相同。</span><span class="sxs-lookup"><span data-stu-id="5c4da-109">If you do not create the output folder, the utility will create the same with path and name that you pass on the command line.</span></span>  
  
5.  <span data-ttu-id="5c4da-110">[可选]-创建一个文本文件\<NameOfFileContainingSchemaList\> ，它列出为生成 InfoPath 窗体的消息的消息类型。</span><span class="sxs-lookup"><span data-stu-id="5c4da-110">[Optional]-  Create a text file \<NameOfFileContainingSchemaList\> that lists the message types for messages for which the InfoPath form is to be generated.</span></span> <span data-ttu-id="5c4da-111">例如消息类型可以是 MT103，MT102 等。命令行而不是创建此文本文件可以直接传递消息名称。</span><span class="sxs-lookup"><span data-stu-id="5c4da-111">For e.g. Message Type can be MT103, MT102 etc. The Message names can directly be passed through the command line instead of creating this text file.</span></span>  
  
## <a name="syntax-of-command-usage-for-formgeneratorexe"></a><span data-ttu-id="5c4da-112">FormGenerator.exe 的命令用法的语法</span><span class="sxs-lookup"><span data-stu-id="5c4da-112">Syntax of Command usage for FormGenerator.exe</span></span>  
  
```csharp  
FormGenerator [-b]   [-#] <TemplateFolderPath> [<TemplateFolderPath2>   
   [...<TemplateFolderPath#>]]  
 <DestinationFolderPath>     <DocumentSchemaLocation>  
   { [<SpaceSeparatedDocumentSchemaList>] |   [-f <NameOfFileContainingSchemaList>] }  
  
```  
  
 <span data-ttu-id="5c4da-113">其中：</span><span class="sxs-lookup"><span data-stu-id="5c4da-113">Where:</span></span>  
  
-   <span data-ttu-id="5c4da-114">-b： 如果指定，将在创建后编译窗体。</span><span class="sxs-lookup"><span data-stu-id="5c4da-114">-b: If specified, forms will be compiled after creation.</span></span>  
  
-   <span data-ttu-id="5c4da-115">TemplateFolderPath： 包含用于创建 InfoPath 解决方案的模板文件的文件夹</span><span class="sxs-lookup"><span data-stu-id="5c4da-115">TemplateFolderPath: the folder containing the template files used to create the InfoPath solution</span></span>  
  
-   <span data-ttu-id="5c4da-116">-#: 如果指定，模板将在中查找多个模板路径 (任意多个数字 # 指定的整数) 和指定的顺序。</span><span class="sxs-lookup"><span data-stu-id="5c4da-116">-#: If specified, templates will be looked up in multiple template paths (as many as the integer number # specifies) and in the order specified.</span></span>  
  
-   <span data-ttu-id="5c4da-117">将在其中创建窗体文件夹的 DestinationFolderPath:</span><span class="sxs-lookup"><span data-stu-id="5c4da-117">DestinationFolderPath: the folder where the forms will be created</span></span>  
  
-   <span data-ttu-id="5c4da-118">DocumentSchemaLocation： 的架构 （包括基类和常见架构 MT 消息） 的位置</span><span class="sxs-lookup"><span data-stu-id="5c4da-118">DocumentSchemaLocation: location of schemas (including base and common schemas for MT messages)</span></span>  
  
-   <span data-ttu-id="5c4da-119">SpaceSeparatedDocumentSchemaList： 空格分隔的列表类似 MT103 MT300 的架构。</span><span class="sxs-lookup"><span data-stu-id="5c4da-119">SpaceSeparatedDocumentSchemaList: space-separated list of schemas like MT103 MT300.</span></span>  
  
-   <span data-ttu-id="5c4da-120">-f： 如果指定，需要从文件读取架构列表。</span><span class="sxs-lookup"><span data-stu-id="5c4da-120">-f: If specified, the schema list needs to be read from a file.</span></span>  
  
-   <span data-ttu-id="5c4da-121">NameOfFileContainingSchemaList： 的包含列表的文件的名称。</span><span class="sxs-lookup"><span data-stu-id="5c4da-121">NameOfFileContainingSchemaList: name of file containing the list.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="5c4da-122">上面的命令是 MT、 MX 和类别 0 泛型命令消息。</span><span class="sxs-lookup"><span data-stu-id="5c4da-122">The above command is a generic command for MT, MX and Category 0 messages.</span></span> <span data-ttu-id="5c4da-123">特定的命令以生成这些类型的窗体中给出了以下各节。</span><span class="sxs-lookup"><span data-stu-id="5c4da-123">Specific commands to generate these types of forms are given in the below sections.</span></span>