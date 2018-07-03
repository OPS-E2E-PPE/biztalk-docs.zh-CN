---
title: 如何对节点名称字符进行编码 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 6462856b-7a52-40c9-9aff-c0579130eec9
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 9f374f9ebdfabfff1cc123fe2ad2f9d05a2b3c63
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36994054"
---
# <a name="how-node-name-characters-get-encoded"></a><span data-ttu-id="f5507-102">如何对节点名称字符进行编码</span><span class="sxs-lookup"><span data-stu-id="f5507-102">How Node Name Characters Get Encoded</span></span>
<span data-ttu-id="f5507-103">如果使用节点名称中不允许的字符，BizTalk 编辑器会发出提示，询问您是否要继续不允许的字符或编码字符 (**确定**或**取消**)。</span><span class="sxs-lookup"><span data-stu-id="f5507-103">If you use a character that is not allowed in a node name, BizTalk Editor prompts you, asking if you want to proceed with the disallowed character or characters encoded (**OK** or **Cancel**).</span></span> <span data-ttu-id="f5507-104">如果继续，每个不允许的字符编码，如下所示：</span><span class="sxs-lookup"><span data-stu-id="f5507-104">If you proceed, each disallowed character is encoded as follows:</span></span>  
  
- <span data-ttu-id="f5507-105">不允许的字符编码为"*xDDDD\\*"其中"DDDD"是 4 位十六进制 Unicode 字符的表示形式。</span><span class="sxs-lookup"><span data-stu-id="f5507-105">Disallowed characters are encoded as "*xDDDD\\*" where "DDDD" is the 4-digit hexadecimal Unicode representation of the character.</span></span> <span data-ttu-id="f5507-106">例如，空格字符 (0x0020) 编码为"*x0020\\*"。</span><span class="sxs-lookup"><span data-stu-id="f5507-106">For example, the space character (0x0020) is encoded as "*x0020\\*".</span></span>  
  
- <span data-ttu-id="f5507-107">如果两个或多个相邻不允许的字符进行编码，则它们之间使用单个下划线字符。</span><span class="sxs-lookup"><span data-stu-id="f5507-107">If two or more adjacent disallowed characters are encoded, only a single underscore character is used between them.</span></span> <span data-ttu-id="f5507-108">例如，将三个空格编码为"*x0020_x0020_x0020\\*"而非"*x0020\__x0020\__x0020\\*"。</span><span class="sxs-lookup"><span data-stu-id="f5507-108">For example, three spaces are encoded as "*x0020_x0020_x0020\\*" rather than "*x0020\__x0020\__x0020\\*".</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="f5507-109">您可以禁用提示输入节点名称编码通过设置**显示编码警告对话框**属性设置为**False**中的 BizTalk 编辑器文件夹**选项**对话框中，可在上找到**工具**菜单中，或通过选择**不再显示此对话框，在将来**节点名称编码对话框中的复选框。</span><span class="sxs-lookup"><span data-stu-id="f5507-109">You can disable prompting for node name encoding by setting the **Show Encode Warning Dialog** property to **False** in the BizTalk Editor folder of the **Options** dialog box, available on the **Tools** menu, or by selecting the **Do not show this dialog in the future** check box in the node name encoding dialog box.</span></span> <span data-ttu-id="f5507-110">有关此对话框中选项的详细信息，请参阅[管理架构树视图](../core/how-to-manage-the-schema-tree-view.md)。</span><span class="sxs-lookup"><span data-stu-id="f5507-110">For more information about the options in this dialog box, see [Managing the Schema Tree View](../core/how-to-manage-the-schema-tree-view.md).</span></span>  
  
 <span data-ttu-id="f5507-111">在架构树视图在 BizTalk 编辑器中显示通过使用您键入的字符的节点名称。</span><span class="sxs-lookup"><span data-stu-id="f5507-111">The schema tree view in BizTalk Editor displays node names by using the characters you type.</span></span> <span data-ttu-id="f5507-112">BizTalk 映射器还显示你键入而不是编码版本的字符。</span><span class="sxs-lookup"><span data-stu-id="f5507-112">BizTalk Mapper also displays the characters you have typed rather than the encoded version.</span></span> <span data-ttu-id="f5507-113">在 XSD 视图的 BizTalk 编辑器中，和 XSD 文件本身中，则使用编码的节点名称。</span><span class="sxs-lookup"><span data-stu-id="f5507-113">In the XSD view of BizTalk Editor, and in the XSD file itself, the encoded node name is used.</span></span> <span data-ttu-id="f5507-114">例如，如果将名称节点采购订单，它将显示为采购订单在 BizTalk 编辑器和 BizTalk 映射器中的架构树中。</span><span class="sxs-lookup"><span data-stu-id="f5507-114">For example, if you name a node Purchase Order, it will be displayed as Purchase Order in the schema trees in both BizTalk Editor and BizTalk Mapper.</span></span> <span data-ttu-id="f5507-115">在 XSD 视图的 BizTalk 编辑器中，对应的元素节点，第一次插入时，将按如下所示。</span><span class="sxs-lookup"><span data-stu-id="f5507-115">In the XSD view of BizTalk Editor, the corresponding element node, when first inserted, will be as follows.</span></span>  
  
```  
<element name="Purchase_x0020_Order" type="xs:string />  
  
```  
  
## <a name="see-also"></a><span data-ttu-id="f5507-116">请参阅</span><span class="sxs-lookup"><span data-stu-id="f5507-116">See Also</span></span>  
 <span data-ttu-id="f5507-117">[节点名称属性](../core/node-name-property.md) </span><span class="sxs-lookup"><span data-stu-id="f5507-117">[Node Name Property](../core/node-name-property.md) </span></span>  
 [<span data-ttu-id="f5507-118">已编码的节点名称字符</span><span class="sxs-lookup"><span data-stu-id="f5507-118">Which Node Name Characters Get Encoded</span></span>](../core/which-node-name-characters-get-encoded.md)