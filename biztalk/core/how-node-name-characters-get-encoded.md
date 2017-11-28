---
title: "节点名称字符获取编码方式 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 6462856b-7a52-40c9-9aff-c0579130eec9
caps.latest.revision: "6"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 2d2c9410e56b2b50a32ec73ce5f49ae59909f59a
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="how-node-name-characters-get-encoded"></a><span data-ttu-id="cef62-102">如何对节点名称字符进行编码</span><span class="sxs-lookup"><span data-stu-id="cef62-102">How Node Name Characters Get Encoded</span></span>
<span data-ttu-id="cef62-103">如果使用节点名称中不允许的字符时，BizTalk 编辑器会发出提示，询问你是否要继续不允许的字符或编码的字符 (**确定**或**取消**)。</span><span class="sxs-lookup"><span data-stu-id="cef62-103">If you use a character that is not allowed in a node name, BizTalk Editor prompts you, asking if you want to proceed with the disallowed character or characters encoded (**OK** or **Cancel**).</span></span> <span data-ttu-id="cef62-104">如果继续，每个不允许的字符编码，如下所示：</span><span class="sxs-lookup"><span data-stu-id="cef62-104">If you proceed, each disallowed character is encoded as follows:</span></span>  
  
-   <span data-ttu-id="cef62-105">不允许的字符编码为"_xDDDD\_""DDDD"所在 4 位十六进制 Unicode 字符的表示形式。</span><span class="sxs-lookup"><span data-stu-id="cef62-105">Disallowed characters are encoded as "_xDDDD\_" where "DDDD" is the 4-digit hexadecimal Unicode representation of the character.</span></span> <span data-ttu-id="cef62-106">例如，空格字符 (0x0020) 编码为"_x0020\_"。</span><span class="sxs-lookup"><span data-stu-id="cef62-106">For example, the space character (0x0020) is encoded as "_x0020\_".</span></span>  
  
-   <span data-ttu-id="cef62-107">如果两个或多个相邻不允许的字符进行编码，它们之间使用单个下划线字符。</span><span class="sxs-lookup"><span data-stu-id="cef62-107">If two or more adjacent disallowed characters are encoded, only a single underscore character is used between them.</span></span> <span data-ttu-id="cef62-108">例如，三个空格被编码为"_x0020_x0020_x0020\_"而非"_x0020\__x0020\__x0020\_"。</span><span class="sxs-lookup"><span data-stu-id="cef62-108">For example, three spaces are encoded as "_x0020_x0020_x0020\_" rather than "_x0020\__x0020\__x0020\_".</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="cef62-109">你可以禁用提示输入通过设置的节点名称编码**显示编码警告对话框**属性**False** BizTalk 编辑器文件夹中的**选项**对话框中，可在上找到**工具**菜单上，或通过选择**将来不显示此对话框**编码对话框中的节点名称中的复选框。</span><span class="sxs-lookup"><span data-stu-id="cef62-109">You can disable prompting for node name encoding by setting the **Show Encode Warning Dialog** property to **False** in the BizTalk Editor folder of the **Options** dialog box, available on the **Tools** menu, or by selecting the **Do not show this dialog in the future** check box in the node name encoding dialog box.</span></span> <span data-ttu-id="cef62-110">有关此对话框中选项的详细信息，请参阅[管理架构树视图](../core/how-to-manage-the-schema-tree-view.md)。</span><span class="sxs-lookup"><span data-stu-id="cef62-110">For more information about the options in this dialog box, see [Managing the Schema Tree View](../core/how-to-manage-the-schema-tree-view.md).</span></span>  
  
 <span data-ttu-id="cef62-111">BizTalk 编辑器中的架构树视图显示通过使用您键入的字符的节点名称。</span><span class="sxs-lookup"><span data-stu-id="cef62-111">The schema tree view in BizTalk Editor displays node names by using the characters you type.</span></span> <span data-ttu-id="cef62-112">BizTalk 映射程序还会显示您键入而不是编码版本的字符。</span><span class="sxs-lookup"><span data-stu-id="cef62-112">BizTalk Mapper also displays the characters you have typed rather than the encoded version.</span></span> <span data-ttu-id="cef62-113">在 XSD 视图的 BizTalk 编辑器中，以及 XSD 文件本身中，则使用编码的节点名称。</span><span class="sxs-lookup"><span data-stu-id="cef62-113">In the XSD view of BizTalk Editor, and in the XSD file itself, the encoded node name is used.</span></span> <span data-ttu-id="cef62-114">例如，如果名称节点采购订单时，它将显示为采购订单 BizTalk 编辑器和 BizTalk 映射程序中的架构树中。</span><span class="sxs-lookup"><span data-stu-id="cef62-114">For example, if you name a node Purchase Order, it will be displayed as Purchase Order in the schema trees in both BizTalk Editor and BizTalk Mapper.</span></span> <span data-ttu-id="cef62-115">在 XSD 视图的 BizTalk 编辑器中，相应的元素节点，首先插入时，将，如下所示。</span><span class="sxs-lookup"><span data-stu-id="cef62-115">In the XSD view of BizTalk Editor, the corresponding element node, when first inserted, will be as follows.</span></span>  
  
```  
<element name="Purchase_x0020_Order" type="xs:string />  
  
```  
  
## <a name="see-also"></a><span data-ttu-id="cef62-116">另请参阅</span><span class="sxs-lookup"><span data-stu-id="cef62-116">See Also</span></span>  
 <span data-ttu-id="cef62-117">[节点名称属性](../core/node-name-property.md) </span><span class="sxs-lookup"><span data-stu-id="cef62-117">[Node Name Property](../core/node-name-property.md) </span></span>  
 [<span data-ttu-id="cef62-118">节点名称字符获取编码</span><span class="sxs-lookup"><span data-stu-id="cef62-118">Which Node Name Characters Get Encoded</span></span>](../core/which-node-name-characters-get-encoded.md)