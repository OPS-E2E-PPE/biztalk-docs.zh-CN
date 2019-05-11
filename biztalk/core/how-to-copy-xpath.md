---
title: 如何复制 XPath |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 404599d4-0fb3-4c7c-91e6-1295d9d0965e
caps.latest.revision: 12
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 5bf9a8da90f264abb0953592abf16dc0e157fcb5
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65385603"
---
# <a name="how-to-copy-xpath"></a><span data-ttu-id="06d98-102">如何复制 XPath</span><span class="sxs-lookup"><span data-stu-id="06d98-102">How to Copy XPath</span></span>
<span data-ttu-id="06d98-103">XML 架构定义 (XSD) 语言提供了 BizTalk Server 中定义的消息架构的基本语法。</span><span class="sxs-lookup"><span data-stu-id="06d98-103">The XML Schema definition (XSD) language provides the underlying syntax of the message schemas defined within BizTalk Server.</span></span> <span data-ttu-id="06d98-104">尽管 BizTalk 映射器中的树视图使用特定于 BizTalk 的图形化层次结构的记录和字段节点 （在其他类型的节点），每个都具有其自己的属性集，此类层次结构构造和保存为 XSD。</span><span class="sxs-lookup"><span data-stu-id="06d98-104">Although the tree views in BizTalk Mapper use a BizTalk-specific graphical hierarchy of record and field nodes (among other types of nodes), each with its own set of properties, such hierarchies are constructed and persisted as XSD.</span></span>  
  
 <span data-ttu-id="06d98-105">在映射很复杂并且跨越多个网格页的情况下，很难找到架构节点的父节点。</span><span class="sxs-lookup"><span data-stu-id="06d98-105">In scenarios where maps are complex and span across grid pages, locating the parent of a schema node can be difficult.</span></span> <span data-ttu-id="06d98-106">此处使用的是将 XSD 路径。</span><span class="sxs-lookup"><span data-stu-id="06d98-106">The XSD path will be of use here.</span></span> <span data-ttu-id="06d98-107">可以使用 XSD 路径获取信息架构节点的深度。</span><span class="sxs-lookup"><span data-stu-id="06d98-107">You can use the XSD path to get information about the depth of schema nodes.</span></span> <span data-ttu-id="06d98-108">此外，您可以重复使用此路径在另一个网格页中以标识此关系。</span><span class="sxs-lookup"><span data-stu-id="06d98-108">Also, you can reuse this path in another grid page to identify the relationship.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="06d98-109">先决条件</span><span class="sxs-lookup"><span data-stu-id="06d98-109">Prerequisites</span></span>  
 <span data-ttu-id="06d98-110">这些说明需要 BizTalk 映射器处于运行状态。</span><span class="sxs-lookup"><span data-stu-id="06d98-110">These instructions require that BizTalk Mapper is running.</span></span>  
  
### <a name="to-copy-the-xsd-path-xpath"></a><span data-ttu-id="06d98-111">复制 XSD 路径 (XPath)</span><span class="sxs-lookup"><span data-stu-id="06d98-111">To copy the XSD path (XPath)</span></span>  
  
1.  <span data-ttu-id="06d98-112">右键单击架构节点为其希望的 XSD 路径，然后依次**复制 XPath**。</span><span class="sxs-lookup"><span data-stu-id="06d98-112">Right-click the schema node for which you want the XSD path, and then click **Copy XPath**.</span></span>  
  
2.  <span data-ttu-id="06d98-113">打开文本编辑器。</span><span class="sxs-lookup"><span data-stu-id="06d98-113">Open a text editor.</span></span> <span data-ttu-id="06d98-114">在“编辑” 菜单上，单击“粘贴”。</span><span class="sxs-lookup"><span data-stu-id="06d98-114">On the **Edit** menu, click **Paste**.</span></span> <span data-ttu-id="06d98-115">现在可以看到 XSD 路径。</span><span class="sxs-lookup"><span data-stu-id="06d98-115">You can now see the XSD path.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="06d98-116">此外，您可以按 CTRL + V 将路径粘贴到文本编辑器中。</span><span class="sxs-lookup"><span data-stu-id="06d98-116">Alternatively, you can press CTRL+V to paste the path in a text editor.</span></span>  
  
     <span data-ttu-id="06d98-117">下面的代码显示了所选的架构节点的 XSD 路径。</span><span class="sxs-lookup"><span data-stu-id="06d98-117">The code below displays the XSD path for the selected schema node.</span></span>  
  
    ```  
    /*[local-name()='<Schema>']/*[local-name()='Shipment']/*[local-name()='DataCollection']  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="06d98-118">请参阅</span><span class="sxs-lookup"><span data-stu-id="06d98-118">See Also</span></span>  
 <span data-ttu-id="06d98-119">[使用 BizTalk 映射器中的增强的功能](../core/using-enhanced-features-in-biztalk-mapper.md) </span><span class="sxs-lookup"><span data-stu-id="06d98-119">[Using Enhanced Features in BizTalk Mapper](../core/using-enhanced-features-in-biztalk-mapper.md) </span></span>  
 <span data-ttu-id="06d98-120">[如何替换架构](../core/how-to-replace-schemas.md) </span><span class="sxs-lookup"><span data-stu-id="06d98-120">[How to Replace Schemas](../core/how-to-replace-schemas.md) </span></span>  
 <span data-ttu-id="06d98-121">[如何展开和折叠架构树](https://msdn.microsoft.com/library/ee253802(v=bts.10).aspx)</span><span class="sxs-lookup"><span data-stu-id="06d98-121">[How to Expand and Collapse the Schema Trees](https://msdn.microsoft.com/library/ee253802(v=bts.10).aspx)</span></span>