---
title: "自定义视图 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 9084cc07-be98-4c57-afea-4fa369a38bad
caps.latest.revision: "6"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 184f49330374126f4afc0bd4bb376ea31a5ca681
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="custom-views"></a><span data-ttu-id="4b4e9-102">自定义视图</span><span class="sxs-lookup"><span data-stu-id="4b4e9-102">Custom Views</span></span>
<span data-ttu-id="4b4e9-103">自定义视图通常是只读的窗口控件对象 (派生自**System.Windows.Forms.Control**)，以及由要表示的架构中的文件或文件支持的类型为自定义的显示格式的扩展通过 BizTalk 编辑器扩展中。</span><span class="sxs-lookup"><span data-stu-id="4b4e9-103">A custom view is typically a read-only window control object (derived from **System.Windows.Forms.Control**), and is provided by an extension to represent the schema in a display format customized for the type of file or files supported by the BizTalk Editor extension.</span></span> <span data-ttu-id="4b4e9-104">扩展可以实现多个自定义视图，虽然它不需要具有任何自定义视图。</span><span class="sxs-lookup"><span data-stu-id="4b4e9-104">An extension can implement multiple custom views, though it need not have any custom view.</span></span>  
  
 <span data-ttu-id="4b4e9-105">自定义视图在 XSD 视图所在的 BizTalk 编辑器窗格中作为附加视图显示，可以通过使用视图底部的选项卡进行访问。</span><span class="sxs-lookup"><span data-stu-id="4b4e9-105">A custom view is displayed as an additional view in the same BizTalk Editor pane as the XSD view, accessible by using tabs at the bottom of the views.</span></span> <span data-ttu-id="4b4e9-106">例如，平面文件扩展会添加一个选项卡标记为“平面文件”的新视图。</span><span class="sxs-lookup"><span data-stu-id="4b4e9-106">For example, the Flat File Extension adds a new view with a tab labeled Flat File.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4b4e9-107">另请参阅</span><span class="sxs-lookup"><span data-stu-id="4b4e9-107">See Also</span></span>  
 [<span data-ttu-id="4b4e9-108">扩展 BizTalk 编辑器</span><span class="sxs-lookup"><span data-stu-id="4b4e9-108">Extending BizTalk Editor</span></span>](../core/extending-biztalk-editor.md)