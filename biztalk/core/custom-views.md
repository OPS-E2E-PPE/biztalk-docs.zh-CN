---
title: 自定义视图 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 9084cc07-be98-4c57-afea-4fa369a38bad
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 60433668a62c1a7b7483aca3af82ecd8c5d7f8c7
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65353324"
---
# <a name="custom-views"></a><span data-ttu-id="ef5cc-102">自定义视图</span><span class="sxs-lookup"><span data-stu-id="ef5cc-102">Custom Views</span></span>
<span data-ttu-id="ef5cc-103">自定义视图通常是只读的窗口控件对象 (派生自**System.Windows.Forms.Control**)，并提供的扩展来表示文件或文件支持的类型自定义的显示格式的架构BizTalk 编辑器扩展插件。</span><span class="sxs-lookup"><span data-stu-id="ef5cc-103">A custom view is typically a read-only window control object (derived from **System.Windows.Forms.Control**), and is provided by an extension to represent the schema in a display format customized for the type of file or files supported by the BizTalk Editor extension.</span></span> <span data-ttu-id="ef5cc-104">扩展可以实现多个自定义视图，但它不需要任何自定义视图。</span><span class="sxs-lookup"><span data-stu-id="ef5cc-104">An extension can implement multiple custom views, though it need not have any custom view.</span></span>  
  
 <span data-ttu-id="ef5cc-105">自定义视图将显示为在 XSD 视图，通过在视图底部使用选项卡可访问的同一 BizTalk 编辑器窗格中的其他视图。</span><span class="sxs-lookup"><span data-stu-id="ef5cc-105">A custom view is displayed as an additional view in the same BizTalk Editor pane as the XSD view, accessible by using tabs at the bottom of the views.</span></span> <span data-ttu-id="ef5cc-106">例如，平面文件扩展与标记为平面文件的选项卡添加一个新的视图。</span><span class="sxs-lookup"><span data-stu-id="ef5cc-106">For example, the Flat File Extension adds a new view with a tab labeled Flat File.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ef5cc-107">请参阅</span><span class="sxs-lookup"><span data-stu-id="ef5cc-107">See Also</span></span>  
 [<span data-ttu-id="ef5cc-108">扩展 BizTalk 编辑器</span><span class="sxs-lookup"><span data-stu-id="ef5cc-108">Extending BizTalk Editor</span></span>](../core/extending-biztalk-editor.md)