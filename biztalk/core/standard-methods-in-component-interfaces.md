---
title: 组件接口中的标准方法 |Microsoft Docs
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
ms.openlocfilehash: eecb56f262a56e6567b44b146c631542cb1ceda6
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36994822"
---
# <a name="standard-methods-in-component-interfaces"></a><span data-ttu-id="0e38c-102">组件接口中的标准方法</span><span class="sxs-lookup"><span data-stu-id="0e38c-102">Standard Methods in Component Interfaces</span></span>
<span data-ttu-id="0e38c-103">组件接口的标准方法如下：</span><span class="sxs-lookup"><span data-stu-id="0e38c-103">The standard methods for the component interface are as follows:</span></span>  
  
- `Create`  
  
- `Find`  
  
- `Get`  
  
- `Save`  
  
  <span data-ttu-id="0e38c-104">只有基础组件中的这些方法可用。</span><span class="sxs-lookup"><span data-stu-id="0e38c-104">Only those methods in the underlying component are available.</span></span> <span data-ttu-id="0e38c-105">例如，如果基础组件不包含 `Add` 功能，则 `Create` 不可用。</span><span class="sxs-lookup"><span data-stu-id="0e38c-105">For example, if the underlying component does not contain `Add` capabilities, `Create` is unavailable.</span></span>  
  
## <a name="viewing-or-changing-available-methods"></a><span data-ttu-id="0e38c-106">查看或更改可用方法</span><span class="sxs-lookup"><span data-stu-id="0e38c-106">Viewing or Changing Available Methods</span></span>  
  
#### <a name="to-view-or-change-available-methods"></a><span data-ttu-id="0e38c-107">若要查看或更改可用方法</span><span class="sxs-lookup"><span data-stu-id="0e38c-107">To view or change available methods</span></span>  
  
1.  <span data-ttu-id="0e38c-108">打开组件接口**属性**对话框。</span><span class="sxs-lookup"><span data-stu-id="0e38c-108">Open the component interface **Properties** dialog box.</span></span>  
  
     <span data-ttu-id="0e38c-109">![](../core/media/psadapter-46-ps-properties.gif "PSAdapter_46_PS_Properties")</span><span class="sxs-lookup"><span data-stu-id="0e38c-109">![](../core/media/psadapter-46-ps-properties.gif "PSAdapter_46_PS_Properties")</span></span>  
  
2.  <span data-ttu-id="0e38c-110">单击**标准方法**选项卡。</span><span class="sxs-lookup"><span data-stu-id="0e38c-110">Click the **Standard Methods** tab.</span></span>  
  
3.  <span data-ttu-id="0e38c-111">选择所需的方法，然后依次**确定**。</span><span class="sxs-lookup"><span data-stu-id="0e38c-111">Select the desired methods, and then click **OK**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0e38c-112">请参阅</span><span class="sxs-lookup"><span data-stu-id="0e38c-112">See Also</span></span>  
 <span data-ttu-id="0e38c-113">[如何创建组件接口](../core/how-to-create-component-interfaces.md) </span><span class="sxs-lookup"><span data-stu-id="0e38c-113">[How to Create Component Interfaces](../core/how-to-create-component-interfaces.md) </span></span>  
 [<span data-ttu-id="0e38c-114">附件 C：使用组件接口</span><span class="sxs-lookup"><span data-stu-id="0e38c-114">Appendix C: Using Component Interfaces</span></span>](../core/appendix-c-using-component-interfaces.md)