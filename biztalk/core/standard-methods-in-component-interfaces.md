---
title: 组件接口中的标准方法 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- component interfaces, standard methods
- methods, viewing
- methods, component interfaces
- methods, changing
ms.assetid: 2273d946-3fc8-4b2d-a6a1-9e4f0da74d5b
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f44b3977a3921d92b1f3f83dd3e744f14b5709fc
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22278045"
---
# <a name="standard-methods-in-component-interfaces"></a><span data-ttu-id="e4512-102">组件接口中的标准方法</span><span class="sxs-lookup"><span data-stu-id="e4512-102">Standard Methods in Component Interfaces</span></span>
<span data-ttu-id="e4512-103">组件接口的标准方法如下：</span><span class="sxs-lookup"><span data-stu-id="e4512-103">The standard methods for the component interface are as follows:</span></span>  
  
-   `Create`  
  
-   `Find`  
  
-   `Get`  
  
-   `Save`  
  
 <span data-ttu-id="e4512-104">只有基础组件中的这些方法可用。</span><span class="sxs-lookup"><span data-stu-id="e4512-104">Only those methods in the underlying component are available.</span></span> <span data-ttu-id="e4512-105">例如，如果基础组件不包含 `Add` 功能，则 `Create` 不可用。</span><span class="sxs-lookup"><span data-stu-id="e4512-105">For example, if the underlying component does not contain `Add` capabilities, `Create` is unavailable.</span></span>  
  
## <a name="viewing-or-changing-available-methods"></a><span data-ttu-id="e4512-106">查看或更改可用方法</span><span class="sxs-lookup"><span data-stu-id="e4512-106">Viewing or Changing Available Methods</span></span>  
  
#### <a name="to-view-or-change-available-methods"></a><span data-ttu-id="e4512-107">若要查看或更改可用的方法</span><span class="sxs-lookup"><span data-stu-id="e4512-107">To view or change available methods</span></span>  
  
1.  <span data-ttu-id="e4512-108">打开组件接口**属性**对话框。</span><span class="sxs-lookup"><span data-stu-id="e4512-108">Open the component interface **Properties** dialog box.</span></span>  
  
     ![](../core/media/psadapter-46-ps-properties.gif "PSAdapter_46_PS_Properties")  
  
2.  <span data-ttu-id="e4512-109">单击**标准方法**选项卡。</span><span class="sxs-lookup"><span data-stu-id="e4512-109">Click the **Standard Methods** tab.</span></span>  
  
3.  <span data-ttu-id="e4512-110">选择所需的方法，然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="e4512-110">Select the desired methods, and then click **OK**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e4512-111">另请参阅</span><span class="sxs-lookup"><span data-stu-id="e4512-111">See Also</span></span>  
 <span data-ttu-id="e4512-112">[如何创建组件接口](../core/how-to-create-component-interfaces.md) </span><span class="sxs-lookup"><span data-stu-id="e4512-112">[How to Create Component Interfaces](../core/how-to-create-component-interfaces.md) </span></span>  
 [<span data-ttu-id="e4512-113">附录 c： 使用组件接口</span><span class="sxs-lookup"><span data-stu-id="e4512-113">Appendix C: Using Component Interfaces</span></span>](../core/appendix-c-using-component-interfaces.md)