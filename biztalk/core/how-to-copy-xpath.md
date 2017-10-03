---
title: "如何复制 XPath |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 404599d4-0fb3-4c7c-91e6-1295d9d0965e
caps.latest.revision: "12"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: bb282c5c32d8da62a9da6d7a9c900c798e44eee7
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-copy-xpath"></a><span data-ttu-id="1308f-102">如何复制 XPath</span><span class="sxs-lookup"><span data-stu-id="1308f-102">How to Copy XPath</span></span>
<span data-ttu-id="1308f-103">XML 架构定义 (XSD) 语言提供了在 BizTalk Server 中定义的消息架构的基本语法。</span><span class="sxs-lookup"><span data-stu-id="1308f-103">The XML Schema definition (XSD) language provides the underlying syntax of the message schemas defined within BizTalk Server.</span></span> <span data-ttu-id="1308f-104">尽管 BizTalk 映射器中的树视图使用了特定于 BizTalk 的记录和字段节点（在其他节点类型中）的图形化层次结构，并且每个树视图都具有自己的属性集，但此类层次结构将作为 XSD 进行构造和保存。</span><span class="sxs-lookup"><span data-stu-id="1308f-104">Although the tree views in BizTalk Mapper use a BizTalk-specific graphical hierarchy of record and field nodes (among other types of nodes), each with its own set of properties, such hierarchies are constructed and persisted as XSD.</span></span>  
  
 <span data-ttu-id="1308f-105">在映射很复杂并且跨越多个网格页的情况下，可能很难找到架构节点的父节点。</span><span class="sxs-lookup"><span data-stu-id="1308f-105">In scenarios where maps are complex and span across grid pages, locating the parent of a schema node can be difficult.</span></span> <span data-ttu-id="1308f-106">此时可使用 XSD 路径。</span><span class="sxs-lookup"><span data-stu-id="1308f-106">The XSD path will be of use here.</span></span> <span data-ttu-id="1308f-107">您可以使用 XSD 路径获取有关架构节点的深度信息。</span><span class="sxs-lookup"><span data-stu-id="1308f-107">You can use the XSD path to get information about the depth of schema nodes.</span></span> <span data-ttu-id="1308f-108">此外，可以在其他网格页中重新使用此路径来标识关系。</span><span class="sxs-lookup"><span data-stu-id="1308f-108">Also, you can reuse this path in another grid page to identify the relationship.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="1308f-109">先决条件</span><span class="sxs-lookup"><span data-stu-id="1308f-109">Prerequisites</span></span>  
 <span data-ttu-id="1308f-110">这些说明需要 BizTalk 映射器处于运行状态。</span><span class="sxs-lookup"><span data-stu-id="1308f-110">These instructions require that BizTalk Mapper is running.</span></span>  
  
### <a name="to-copy-the-xsd-path-xpath"></a><span data-ttu-id="1308f-111">复制 XSD 路径 (XPath) 的步骤</span><span class="sxs-lookup"><span data-stu-id="1308f-111">To copy the XSD path (XPath)</span></span>  
  
1.  <span data-ttu-id="1308f-112">右键单击架构节点为其想 XSD 路径，并依次**复制 XPath**。</span><span class="sxs-lookup"><span data-stu-id="1308f-112">Right-click the schema node for which you want the XSD path, and then click **Copy XPath**.</span></span>  
  
2.  <span data-ttu-id="1308f-113">打开文本编辑器。</span><span class="sxs-lookup"><span data-stu-id="1308f-113">Open a text editor.</span></span> <span data-ttu-id="1308f-114">在“编辑” 菜单上，单击“粘贴”。</span><span class="sxs-lookup"><span data-stu-id="1308f-114">On the **Edit** menu, click **Paste**.</span></span> <span data-ttu-id="1308f-115">现在，您可以看到 XSD 路径。</span><span class="sxs-lookup"><span data-stu-id="1308f-115">You can now see the XSD path.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="1308f-116">或者，可以按 Ctrl + V 将路径粘贴到文本编辑器中。</span><span class="sxs-lookup"><span data-stu-id="1308f-116">Alternatively, you can press CTRL+V to paste the path in a text editor.</span></span>  
  
     <span data-ttu-id="1308f-117">以下代码显示了所选架构节点的 XSD 路径。</span><span class="sxs-lookup"><span data-stu-id="1308f-117">The code below displays the XSD path for the selected schema node.</span></span>  
  
    ```  
    /*[local-name()='<Schema>']/*[local-name()='Shipment']/*[local-name()='DataCollection']  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="1308f-118">另请参阅</span><span class="sxs-lookup"><span data-stu-id="1308f-118">See Also</span></span>  
 <span data-ttu-id="1308f-119">[在 BizTalk 映射程序中使用增强的功能](../core/using-enhanced-features-in-biztalk-mapper.md) </span><span class="sxs-lookup"><span data-stu-id="1308f-119">[Using Enhanced Features in BizTalk Mapper](../core/using-enhanced-features-in-biztalk-mapper.md) </span></span>  
 <span data-ttu-id="1308f-120">[如何替换架构](../core/how-to-replace-schemas.md) </span><span class="sxs-lookup"><span data-stu-id="1308f-120">[How to Replace Schemas](../core/how-to-replace-schemas.md) </span></span>  
 <span data-ttu-id="1308f-121">[如何展开和折叠架构树](https://msdn.microsoft.com/library/ee253802(v=bts.10).aspx)</span><span class="sxs-lookup"><span data-stu-id="1308f-121">[How to Expand and Collapse the Schema Trees](https://msdn.microsoft.com/library/ee253802(v=bts.10).aspx)</span></span>