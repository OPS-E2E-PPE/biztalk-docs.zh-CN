---
title: "实例生成 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 14060dca-5e14-474a-bf2c-4e8bc56e3c61
caps.latest.revision: "10"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 46bd3d2bc6852ec0c73fbbe4ffc55924a8012ce5
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="instance-generation"></a><span data-ttu-id="f3650-102">生成实例</span><span class="sxs-lookup"><span data-stu-id="f3650-102">Instance Generation</span></span>
<span data-ttu-id="f3650-103">BizTalk 编辑器时，将调用**IInstanceGenerator.GenerateInstance**满足以下条件时的扩展方法：</span><span class="sxs-lookup"><span data-stu-id="f3650-103">BizTalk Editor invokes the **IInstanceGenerator.GenerateInstance** method of an extension when the following conditions are met:</span></span>  
  
-   <span data-ttu-id="f3650-104">扩展使用设置为标准**标准**属性**架构**节点。</span><span class="sxs-lookup"><span data-stu-id="f3650-104">The extension is set as standard by using the **Standard** property of the **Schema** node.</span></span>  
  
-   <span data-ttu-id="f3650-105">上**属性页**与架构中，关联的对话框**生成实例输出类型**属性设置为**本机。**</span><span class="sxs-lookup"><span data-stu-id="f3650-105">On the **Property Pages** dialog box associated with the schema, the **Generate Instance Output Type** property is set to **Native.**</span></span>  
  
-   <span data-ttu-id="f3650-106">上**属性页**与架构中，关联的对话框**输出实例文件名**属性设置为输出实例将保存到文件的名称。</span><span class="sxs-lookup"><span data-stu-id="f3650-106">On the **Property Pages** dialog box associated with the schema, the **Output Instance Filename** property is set to the name of the file that the output instance will be saved to.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="f3650-107">如果**输出实例文件名**未设置属性、 对于生成的实例消息中，使用临时文件夹中的默认文件名称和在输出窗口中提供的链接。</span><span class="sxs-lookup"><span data-stu-id="f3650-107">If the **Output Instance Filename** property is not set, a default file name in a temporary folder is used for the generated instance message, and a link to it is provided in the Output window.</span></span>  
  
 <span data-ttu-id="f3650-108">之前**IInstanceValidator.ValidateInstance**调用方法时，BizTalk 编辑器生成示例 XML 实例消息，然后将其传递并在指定的文件**输出实例文件名**属性或默认文件名，该方法。</span><span class="sxs-lookup"><span data-stu-id="f3650-108">Before the **IInstanceValidator.ValidateInstance** method is called, BizTalk Editor generates a sample XML instance message, and then passes it and the file specified in the **Output Instance Filename** property, or a default file name, to that method.</span></span>  
  
 <span data-ttu-id="f3650-109">如果出现错误，数组的形式返回错误消息**IValidationInfo**对象，并显示在[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]任务列表窗口。</span><span class="sxs-lookup"><span data-stu-id="f3650-109">If errors occur, error messages are returned as an array of **IValidationInfo** objects, and are displayed in the [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] Task List window.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f3650-110">另请参阅</span><span class="sxs-lookup"><span data-stu-id="f3650-110">See Also</span></span>  
 [<span data-ttu-id="f3650-111">扩展 BizTalk 编辑器</span><span class="sxs-lookup"><span data-stu-id="f3650-111">Extending BizTalk Editor</span></span>](../core/extending-biztalk-editor.md)